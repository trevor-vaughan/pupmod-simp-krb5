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

`Index (k) <_index.html>`__ » krb5kdc\_auto\_keytabs

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

.. rubric:: Puppet Type: krb5kdc\_auto\_keytabs
   :name: puppet-type-krb5kdc_auto_keytabs

.. raw:: html

   </div>

.. raw:: html

   <div class="box_info">

Defined in:
    lib/puppet/type/krb5kdc\_auto\_keytabs.rb

.. raw:: html

   </div>

.. raw:: html

   <div class="docstring">

.. raw:: html

   <div class="discussion">

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

-  name (Parameter) (Namevar) -

   .. raw:: html

      <div class="inline">

   The output directory to which to write the keytabs

   If '\_\_default\_\_' will be set to either
   \`$environmentpath/$environment/site\_files/krb5\_files/files/keytabs\`
   or \`/var/kerberos/krb5kdc/generated\_keytabs\` depending on which
   target path exists.

   .. raw:: html

      </div>

-  ensure (Property) -

   .. raw:: html

      <div class="inline">

   .. raw:: html

      </div>

-  all\_known (Parameter) Default value: ``(:false)`` -

   .. raw:: html

      <div class="inline">

   Generate keytabs for any 'host/.\*' entires known to the KDC.

   .. raw:: html

      </div>

-  global\_services (Parameter) -

   .. raw:: html

      <div class="inline">

   The global services that should be applied to **every**
   auto-generated principal

   .. raw:: html

      </div>

-  group (Parameter) Default value: ``('group')`` -

   .. raw:: html

      <div class="inline">

   The group that should own the generated keytabs, defaults to
   '#:group' when installing into a Puppet Environment and 'root'
   otherwise.

   .. raw:: html

      </div>

-  hosts (Parameter) -

   .. raw:: html

      <div class="inline">

   A Hash of hosts that should be managed in the KDC.

   The Hash format should be as follows:

   {

   .. code:: code

       'fqdn' => {
         'ensure'   => ('absent' | 'present') # Required
         'realms'   => ['REALM1', 'REALM2']   # Optional. Will be auto-upcased
         'services' => ['svc1','svc2']        # Optional
       }

   }

   If '$global\_services' is set, it will be added to the list of
   services for each host here.

   .. raw:: html

      </div>

-  introspect (Parameter) Default value: ``(:true)`` -

   .. raw:: html

      <div class="inline">

   Attempt to discover, and create, all relevant keytabs from data on
   the Puppet server.

   This **will** create host principals for discovered entities if they
   do not exist already!

   This takes a best guess from the SIMP default PKI key locations:

   .. code:: code

       * `${environmentpath}/${environment}/keydist`
       * `${environmentpath}/${environment}/site_files/pki_files/files/keydist`

   If \`$environmentpath\` is not set, then \`$confdir\` will be
   substituted for \`$environmentpath/${environment\`

   .. raw:: html

      </div>

-  purge (Parameter) Default value: ``(:true)`` -

   .. raw:: html

      <div class="inline">

   Remove all unmanaged keytabs from the '$name' directory

   .. raw:: html

      </div>

-  realms (Parameter) Default value: ``(Facter['domain'].value)`` -

   .. raw:: html

      <div class="inline">

   The realms under which the hosts should be generated

   .. raw:: html

      </div>

-  user (Parameter) Default value: ``('root')`` -

   .. raw:: html

      <div class="inline">

   The user that should own the generated keytabs, defaults to '#:user'
   when installing into a Puppet Environment and 'root' otherwise.

   .. raw:: html

      </div>

.. raw:: html

   </div>

.. rubric:: Features
   :name: features

.. raw:: html

   <div class="tags">

.. raw:: html

   </div>

.. rubric:: Available Providers
   :name: available-providers

.. raw:: html

   <div class="tags">

-  ```generate_provider`` <generate_provider.html>`__

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   <div id="footer">

Generated on Mon Aug 1 18:05:37 2016 by `yard <http://yardoc.org>`__
0.9.5 (ruby-2.1.10).

.. raw:: html

   </div>

.. raw:: html

   </div>
