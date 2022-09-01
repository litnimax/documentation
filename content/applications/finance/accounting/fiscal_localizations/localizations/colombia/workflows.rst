=========
Workflows
=========

Main Workflows
==============

.. image:: colombia/colombia01.png
   :align: center
   :alt: Electronic invoice workflow in Odoo.

Invoice
-------

When all your master data and credentials has been configured, it's possible to start testing the
electronic invoice workflow.

Invoice creation
----------------

The functional workflow that takes place before an invoice validation doesn't change. The main
changes that are introduced with the electronic invoice are the next fields:

.. image:: colombia/colombia12.png
   :align: center
   :alt: Electronic invoice type in Odoo.

There are three types of documents:

- **Factura Electronica**: This is the regular type of document and its applicable for Invoices,
  Credit Notes and Debit Notes.
- **Factura de Importación**: This should be selected for importation transactions.
- **Factura de contingencia**: This is an exceptional type that is used as a manual backup in case
  that the company is not able to use the ERP and it's necessary to generate the invoice manually,
  when this invoice is added to the ERP, this invoice type should be selected.

Invoice validation
------------------

After the invoice is validated, an XML file is created and sent automatically to Carvajal. This
file is displayed in the chatter.

.. image:: colombia/colombia13.png
   :align: center
   :alt: Carvajal XML invoice file in Odoo chatter.

An extra field is now displayed in "Other Info" tab with the name of the XML file. Additionally
there is a second extra field that is displayed with the Electronic Invoice status, with the
initial value "In progress":

.. image:: colombia/colombia14.png
   :align: center
   :alt: Electronic invoice name and status in Odoo.

Reception of legal XML and PDF
------------------------------

The electronic invoice vendor receives the XML file and proceeds to validate the structure and the
information in it, if everything is correct the invoice status changes to "Validated" after using
the "Check Carvajal Status" button in the Action dropdown. They then proceed to generate a Legal
XML which includes a digital signature and a unique code (CUFE), a PDF invoice that includes a QR
code and the CUFE is also generated.

After this:

- A ZIP containing the legal XML and the PDF is downloaded and displayed in the invoice chatter:

  .. image:: colombia/colombia15.png
     :align: center
     :alt: ZIP file displayed in the invoice chatter in Odoo.

  .. image:: colombia/colombia16.png
     :align: center
     :alt:  XML and PDF contained in invoice ZIP file.

- The Electronic Invoice status changes to "Accepted."

Common errors
-------------

During the XML validation the most common errors are usually related to missing master data. In
such cases, error messages are shown in the chatter after updating the electronic invoice status.

.. image:: colombia/colombia17.png
   :align: center
   :alt: XML validation errors shown in the invoice chatter in Odoo.

After the master data is corrected, it's possible to reprocess the XML with the new data and send
the updated version, using the following button:

.. image:: colombia/colombia18.png
   :align: center
   :alt: Reprocess XML with new data and send updated version to Carvajal.

.. image:: colombia/colombia19.png
   :align: center
   :alt: The updated invoice status in Odoo.

Additional use cases
--------------------

The process for credit and debit notes is exactly the same as the invoice, the functional workflow
remains the same as well.

Advanced workflows
==================

Advanced workflow 1
-------------------