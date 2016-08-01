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

`Index (s) <../_index.html>`__ » `krb5 <../krb5.html>`__ » setting

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

.. rubric:: Puppet Defined Type: setting
   :name: puppet-defined-type-setting

.. raw:: html

   </div>

.. raw:: html

   <div class="box_info">

Defined in:
    manifests/setting.pp

.. raw:: html

   </div>

.. rubric:: Overview
   :name: overview

.. raw:: html

   <div class="docstring">

.. raw:: html

   <div class="discussion">

.. rubric:: Define: krb5::setting
   :name: label-Define%3A+krb5%3A%3Asetting

This define allows you to set individual configuration elements in
/etc/krb5.conf without explicitly needing to specify all of the augeas
parameters.

Sections with nested sub-sections or allowed repeated keys have their
own specialized defines.

For particular configuration parameters, please see:

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

-  value (``String``) -

   .. raw:: html

      <div class="inline">

   The string that should be used to set the desinated value. This
   string will \*not\* be processed so make sure that it's what you want
   to output to the system.

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

-  ensure (``String``)\ `` => 'present'`` -

   .. raw:: html

      <div class="inline">

   Whether to set or clear the key. Valid values are 'present' and
   'absent'. Setting anything besides 'absent' will default to
   'present'.

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
