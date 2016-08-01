.. raw:: html

   <div class="nav_wrap">

.. raw:: html

   <div id="resizer">

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   <div id="main" tabindex="-1">

.. raw:: html

   <div id="header">

.. raw:: html

   <div id="menu">

`Index (c) <../_index.html>`__ » `krb5 <../krb5.html>`__ » config

.. raw:: html

   </div>

.. raw:: html

   <div id="search">

.. raw:: html

   </div>

.. raw:: html

   <div class="clear">

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   <div id="content">

.. raw:: html

   <div class="module_header">

.. rubric:: Puppet Class: config
   :name: puppet-class-config

.. raw:: html

   </div>

Inherits:
    `krb5 <../krb5.html>`__

    -  `krb5 <../krb5.html>`__
    -  krb5::config

    `show all <#>`__
Defined in:
    manifests/config.pp

.. raw:: html

   <div class="clear">

.. raw:: html

   </div>

.. rubric:: Overview
   :name: overview

.. raw:: html

   <div class="docstring">

.. raw:: html

   <div class="discussion">

Basic configuration of the MIT Kerberos client

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   <div class="tags">

.. raw:: html

   </div>

.. rubric:: Parameter Summary
   :name: parameter-summary

.. raw:: html

   <div class="tags">

-  config\_dir (``AbsolutePath``)\ `` => '/etc/krb5.conf.simp.d'`` -

   .. raw:: html

      <div class="inline">

   The path to the Puppet managed config files.

   .. raw:: html

      </div>

-  default\_realm
   (``String``)\ `` => inline_template('<%= @domain.upcase %>')`` -

   .. raw:: html

      <div class="inline">

   Default realm to which to bind.

   .. raw:: html

      </div>

-  realm\_domains
   (``Array``)\ `` => [ inline_template('.<%= @domain %>'), $::domain ]``
   -

   .. raw:: html

      <div class="inline">

   Array of domains bound to the default realm set in $default\_realm.

   .. raw:: html

      </div>

-  dns\_lookup\_realm (``Boolean``)\ `` => false`` -

   .. raw:: html

      <div class="inline">

   Use DNS TXT records to lookup the realm.

   .. raw:: html

      </div>

-  dns\_lookup\_kdc (``Boolean``)\ `` => true`` -

   .. raw:: html

      <div class="inline">

   Use DNS SRV records to lookup the KDC.

   .. raw:: html

      </div>

-  renew\_lifetime (``String``)\ `` => '7d'`` -

   .. raw:: html

      <div class="inline">

   The default renewable lifetime for initial tickets. Should be a valid
   krb5 Time Duration string. @see
   http://web.mit.edu/kerberos/krb5-1.13/doc/basic/date\_format.html#duration

   .. raw:: html

      </div>

-  forwardable (``Boolean``)\ `` => true`` -

   .. raw:: html

      <div class="inline">

   Whether or not to make initial tickets forwardable by default. This
   is needed for SSH GSSAPI.

   .. raw:: html

      </div>

-  clockskew (``String``)\ `` => '500'`` -

   .. raw:: html

      <div class="inline">

   Max allowable amount of clockskew allowed before assuming that a
   message is invalid. Should be a valid krb5 Time Duration string. @see
   http://web.mit.edu/kerberos/krb5-1.13/doc/basic/date\_format.html#duration

   .. raw:: html

      </div>

-  permitted\_tgs\_enctypes (``Any``)\ `` => $::krb5::enctypes``
-  permitted\_tkt\_enctypes (``Any``)\ `` => $::krb5::enctypes``
-  permitted\_enctypes (``Any``)\ `` => $::krb5::enctypes``
-  puppet\_exclusive\_managed (``Any``)\ `` => true``

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   <div id="footer">

Generated on Mon Aug 1 18:05:38 2016 by `yard <http://yardoc.org>`__
0.9.5 (ruby-2.1.10).

.. raw:: html

   </div>

.. raw:: html

   </div>
