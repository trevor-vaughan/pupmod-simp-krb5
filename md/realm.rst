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

`Index (r) <../../_index.html>`__ » `krb5 <../../krb5.html>`__ »
`setting <../setting.html>`__ » realm

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

.. rubric:: Puppet Defined Type: realm
   :name: puppet-defined-type-realm

.. raw:: html

   </div>

.. raw:: html

   <div class="box_info">

Defined in:
    manifests/setting/realm.pp

.. raw:: html

   </div>

.. rubric:: Overview
   :name: overview

.. raw:: html

   <div class="docstring">

.. raw:: html

   <div class="discussion">

This define allows you to add a realm to the [realms] section of
/etc/krb5.conf

man 5 krb5.conf -> REALMS SECTION

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

-  admin\_server (``HostString``) -

   .. raw:: html

      <div class="inline">

   The host where the admin server is running.

   .. raw:: html

      </div>

-  kdc (``HostString``)\ `` => ''`` -

   .. raw:: html

      <div class="inline">

   The host where the KDC is running.

   .. raw:: html

      </div>

-  default\_domain (``String``)\ `` => ''`` -

   .. raw:: html

      <div class="inline">

   The default domain in which hosts are assumed to be present.

   .. raw:: html

      </div>

-  v4\_instance\_convert (``Hash``)\ `` => ''`` -

   .. raw:: html

      <div class="inline">

   A hash of 'tag name' to 'tag value' mappings for default domain
   mapping translations.

   .. raw:: html

      </div>

-  v4\_realm (``String``)\ `` => ''`` -

   .. raw:: html

      <div class="inline">

   The v4 realm to be used when talking to legacy systems.

   .. raw:: html

      </div>

-  auth\_to\_local\_names (``Hash``)\ `` => ''`` -

   .. raw:: html

      <div class="inline">

   A hash of 'principal names' to 'local user names' per the man page.

   .. raw:: html

      </div>

-  auth\_to\_local (``String``)\ `` => ''`` -

   .. raw:: html

      <div class="inline">

   A general rule for mapping to local user names. The following values
   are allowed: DB: RULE: DEFAULT

   .. raw:: html

      </div>

-  target
   (``AbsolutePath``)\ `` => pick(getvar('::krb5::config::config_dir'), '/etc/krb5.conf.d')``
   -

   .. raw:: html

      <div class="inline">

   The krb5 configuration directory

   .. raw:: html

      </div>

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
