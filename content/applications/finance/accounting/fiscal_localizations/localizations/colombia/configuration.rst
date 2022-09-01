=============
Configuration
=============

Install the Colombian localization modules
==========================================

To :ref:`install <general/install>` the modules, go to :menuselection:`Apps`, remove the *Apps*
filter and search for "Colombia". Then click on :guilabel:`Install` for the first two modules.

.. image:: colombia/colombia02.png
   :align: center
   :alt: Install the Colombia localization modules.

Configure credentials for Carvajal web service
==============================================

Once that the modules are installed, in order to be able to connect with Carvajal Web Service, it's
necessary to configure the user and credentials, this information will be provided by Carvajal.

Go to :menuselection:`Accounting --> Configuration --> Settings` and look for the *Colombian
Electronic Invoice* section.

.. image:: colombia/colombia03.png
   :align: center
   :alt: Configure credentials for Carvajal web service in Odoo.

Using the Testing mode it is possible to connect with a Carvajal testing environment. This allows
users to test the complete workflow and integration with the CEN Financiero portal, which is
accessible here:

`CTS (Carvajal T&S) <https://cenflab.cen.biz/site/>`_.

`CSC (Carvajal Servicios de Comunicación) <https://web-stage.facturacarvajal.com/>`_.

CSC is the default for new databases.

Once that Odoo and Carvajal are fully configured and ready for production the testing environment
can be disabled.

Configure your report data
==========================

As part of the configurable information that is sent in the XML, you can define the data for the
fiscal section and the bank information in the PDF.

Go to :menuselection:`Accounting --> Configuration --> Settings` and look for the *Colombian
Electronic Invoice* section.

.. image:: colombia/colombia04.png
   :align: center
   :alt: Configure your report data in Odoo.

Configure data required in the XML
==================================

Partner
-------

Identification
~~~~~~~~~~~~~~

As part of the Colombian Localization, the document types defined by the DIAN are now available on
the Partner form. Colombian partners have to have their identification number and document type
set:

.. image:: colombia/colombia05.png
   :align: center
   :alt: The document type of RUT set in Odoo.

.. tip::
   When the document type is RUT the identification number needs to be configured in Odoo
   including the verification digit, Odoo will split this number when the data to the third party
   vendor is sent.

Fiscal structure (RUT)
~~~~~~~~~~~~~~~~~~~~~~

The partner's responsibility codes (section 53 in the RUT document) are included as part of the
electronic invoice module given that is part of the information required by the DIAN.

These fields can be found in :menuselection:`Partner --> Sales & Purchase Tab --> Fiscal
Information`.

.. image:: colombia/colombia06.png
   :align: center
   :alt: The fiscal information included in the electronic invoice module in Odoo.

Additionally two booleans fields were added in order to specify the fiscal regimen of the partner.

Taxes
-----

If your sales transactions include products with taxes, it's important to consider that an extra
field *Value Type* needs to be configured per tax. This option is located in the
:guilabel:`Advanced Options tab`.

.. image:: colombia/colombia07.png
   :align: center
   :alt: The Value Type field in the Advanced Options tab in Odoo.

Retention tax types (ICA, IVA, Fuente) are also included in the options to configure your taxes.
This configuration is used in order to correctly display taxes in the invoice PDF.

.. image:: colombia/colombia08.png
   :align: center
   :alt: The ICA, IVA and Fuente fields in the Advanced Options tab in Odoo.

Journals
--------

Once the DIAN has assigned the official sequence and prefix for the electronic invoice resolution,
the Sales journals related to your invoice documents need to be updated in Odoo. The sequence can
be accessed using the :ref:`developer mode <developer-mode>`: :menuselection:`Accounting -->
Settings --> Configuration Setting --> Journals`.

.. image:: colombia/colombia09.png
   :align: center
   :alt: The sequence for the electronic invoice resolution in Odoo.

Once that the sequence is opened, the Prefix and Next Number fields should be configured and
synchronized with the CEN Financiero.

.. image:: colombia/colombia10.png
   :align: center
   :alt: The sequence and prefix for the electronic invoice resolution in Odoo.

Users
-----

The default template that is used by Odoo on the invoice PDF includes the job position of the
salesperson, so these fields should be configured:

.. image:: colombia/colombia11.png
   :align: center
   :alt: The job position field in the user form in Odoo.
