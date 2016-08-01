[![License](http://img.shields.io/:license-apache-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Build
Status](https://travis-ci.org/simp/pupmod-simp-krb5.svg)](https://travis-ci.org/simp/pupmod-simp-krb5)
[![SIMP
compatibility](https://img.shields.io/badge/SIMP%20compatibility-4.2.*%2F5.1.*-orange.svg)](https://img.shields.io/badge/SIMP%20compatibility-4.2.*%2F5.1.*-orange.svg)

Krb5 Puppet Module
==================

Table of Contents
-----------------

1.  [Overview](#overview)
2.  [Module Description - What the module does and why it is
    useful](#module-description)
3.  [Setup - The basics of getting started with krb5](#setup)
    -   [What krb5 affects](#what-krb5-affects)
    -   [Setup requirements](#setup-requirements)
    -   [Beginning with krb5](#beginning-with-krb5)

4.  [Usage - Configuration options and additional functionality](#usage)
    -   

        Creating Admin Principals\_

        :   -   ACL Configuration\_
            -   Create Your Admin Principal\_

    -   

        Creating Host Principals\_

        :   -   Create Your Keytabs\_

    -   Propagate the Keytabs\_

5.  [Reference - An under-the-hood peek at what the module is doing and
    how](#reference)
6.  [Limitations - OS compatibility, etc.](#limitations)
7.  [Development - Guide for contributing to the module](#development)
    -   [Acceptance Tests - Beaker env variables](#acceptance-tests)

Overview
--------

Puppet management of the MIT kerberos stack

This is a SIMP module
---------------------

This module is a component of the [System Integrity Management
Platform](https://github.com/NationalSecurityAgency/SIMP), a
compliance-management framework built on Puppet.

If you find any issues, they can be submitted to our
[JIRA](https://simp-project.atlassian.net/).

Please read our [Contribution
Guide](https://simp-project.atlassian.net/wiki/display/SD/Contributing+to+SIMP)
and visit our [developer
wiki](https://simp-project.atlassian.net/wiki/display/SD/SIMP+Development+Home).

This module is optimally designed for use within a larger SIMP
ecosystem, but many of its functions can be used independently.

Setup
-----

### What krb5 affects

This module helps administrators get a working KDC in place and clients
configured to use the KDC.

The module, by default, sets up a fully functional KDC in your
environment and generates keytabs for one admin user, and all of your
hosts that it can discover via keydist.

> **note**

> The keydist discovery only works if the KDC is on the same system as
> your Puppet Server!

### Setup Requirements

The only thing necessary to begin using krb5 is to install it into your
modulepath.

### Beginning with krb5

The following sections give a brief guide on how to get started, for
more information, please see the official Red Hat documentation at
<https://access.redhat.com/knowledge/docs/en-US/Red_Hat_Enterprise_Linux/6/html/Managing_Smart_Cards/Configuring_a_Kerberos_5_Server.html>

> **note**

> You can skip this section if you're using the default settings. These
> will complete the following for you with randomly generated passwords
> for all keytabs and the master password.

Usage
-----

### Creating Admin Principals

#### ACL Configuration

The following Puppet code snippet will create an ACL for your admin user
that is *probably* appropriate for your organization.

``` {.sourceCode .ruby}
krb5_acl{ "${::domain}_admin":
 principal       => "*/admin@${::domain}",
 operation_mask  => '*'
}
```

#### Create Your Admin Principal

Your first principal will be an admin principal and will be allowed to
manage the environment since it is in the admin group. This **must** be
created on the KDC system.

Run the following command, as root, to create your principal:

``` {.sourceCode .bash}
# /usr/sbin/kadmin.local -r YOUR.DOMAIN -q "addprinc <username>/admin"
```

You can now do everything remotely using this principal. Load it using

``` {.sourceCode .bash}
$ /usr/bin/kinit <username>/admin
```

### Creating Host Principals

Before you can really do anything with your hosts, you need to ensure
that the host itself has a keytab.

SIMP uses the /etc/puppet/keydist directory for each host to securely
distribute keytabs to the clients.

On the KDC, generate a principal for each host in your environment using
the following command:

``` {.sourceCode .bash}
# /usr/sbin/kadmin.local -r YOUR.DOMAIN -q 'addprinc -randkey host/<fqdn>'
```

#### Create Your Keytabs

Then, create a separate keytab file for each of your created hosts using
the following command:

``` {.sourceCode .bash}
# /usr/sbin/kadmin.local -r YOUR.DOMAIN -q 'ktadd -k <fqdn>.keytab host/<fqdn>'
```

### Propagate the Keytabs

Move all of the resulting keytab files SECURELY to
&lt;environment\_dir&gt;/keydist/&lt;fqdn&gt;/keytabs on the Puppet
server as appropriate for each file.

> **note**
>
> Make sure that all of your keytab directories are readable by the
> group **puppet** and not the entire world!

Then, update your node declarations to include '::krb5::keytab'.

Once the Puppet Agent runs on the clients, your keytabs will copied to
/etc/krb5\_keytabs. The keytab matching your fqdn will be set in place
as the default system keytab.

Limitations
-----------

SIMP Puppet modules are generally intended to be used on a Redhat
Enterprise Linux-compatible distribution such as EL6 and EL7.

Development
-----------

Please see the [SIMP Contribution
Guidelines](https://simp-project.atlassian.net/wiki/display/SD/Contributing+to+SIMP).

### Acceptance tests

To run the system tests, you need [Vagrant](https://www.vagrantup.com/)
installed. Then, run:

``` {.sourceCode .shell}
bundle exec rake acceptance
```

Some environment variables may be useful:

``` {.sourceCode .shell}
BEAKER_debug=true
BEAKER_provision=no
BEAKER_destroy=no
BEAKER_use_fixtures_dir_for_modules=yes
```

-   `BEAKER_debug`: show the commands being run on the STU and
    their output.
-   `BEAKER_destroy=no`: prevent the machine destruction after the tests
    finish so you can inspect the state.
-   `BEAKER_provision=no`: prevent the machine from being recreated.
    This can save a lot of time while you're writing the tests.
-   `BEAKER_use_fixtures_dir_for_modules=yes`: cause all module
    dependencies to be loaded from the `spec/fixtures/modules`
    directory, based on the contents of `.fixtures.yml`. The contents of
    this directory are usually populated by
    `bundle exec rake spec_prep`. This can be used to run acceptance
    tests to run on isolated networks.

