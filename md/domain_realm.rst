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

`Index (d) <../../_index.html>`__ » `krb5 <../../krb5.html>`__ »
`setting <../setting.html>`__ » domain\_realm

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

.. rubric:: Puppet Defined Type: domain\_realm
   :name: puppet-defined-type-domain_realm

.. raw:: html

   </div>

.. raw:: html

   <div class="box_info">

Defined in:
    manifests/setting/domain\_realm.pp

.. raw:: html

   </div>

.. rubric:: Overview
   :name: overview

.. raw:: html

   <div class="docstring">

.. raw:: html

   <div class="discussion">

This define allows you to configure individual domain => realm mappings.

It was specifically created so that you could pass in your domains as a
name array and then your realm as a value.

man 5 krb5.conf

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

-  realm (``String``) -

   .. raw:: html

      <div class="inline">

   The realm to which to map your domain.

   .. raw:: html

      </div>

-  ensure (``String``)\ `` => 'present'`` -

   .. raw:: html

      <div class="inline">

   Whether to set or clear the key. Valid values are 'present' and
   'absent'. Setting anything besides 'absent' will default to
   'present'.

   .. raw:: html

      </div>

-  target
   (``AbsolutePath``)\ `` => pick(getvar('::krb5::config::config_dir'), '/etc/krb5.conf.d')``
   -

   .. raw:: html

      <div class="inline">

   The target \*directory\* to which to add setting files.

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
