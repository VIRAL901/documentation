================
QR Code payments
================

This feature allows users to generate a :abbr:`QR code (quick response code)` that customers can
scan with their mobile banking app to initiate a bank transfer or pay instantly.

Configuration
=============

Activate and set up QR code payments
------------------------------------

Go to :menuselection:`Accounting --> Configuration --> Settings`, and

#. Activate your country's fiscal localization package under the :guilabel:`Fiscal Localization`
   section to have access to all the country-specific accounting features.
#. Activate :guilabel:`QR codes` under the :guilabel:`Customer Payments` section.

The QR code type differs depending on the country you live in. Set it up following the related
accounting documentation page.

.. list-table::
   :header-rows: 1

   * - QR code types
     - Module name
     - Technical name
     - Description
   * - Pix
     - :doc:`Brazilian - Accounting<../../../finance/fiscal_localizations/brazil>`
     - `l10n_br`
     - The base module to manage chart of accounting and localization for Brazil.
   * - FPS
     - :doc:`Hong Kong - Accounting<../../../finance/fiscal_localizations/hong_kong>`
     - `l10n_hk`
     - The base module to manage chart of accounting and localization for Hong Kong.
   * - QRIS
     - :doc:`Indonesian - Accounting<../../../finance/fiscal_localizations/indonesia>`
     - `l10n_id`
     - The base module to manage chart of accounting and localization for Indonesia.
   * - PayNow
     - :doc:`Singapore - Accounting<../../../finance/fiscal_localizations/singapore>`
     - `l10n_sg`
     - The base module to manage chart of accounting and localization for Singapore.
   * - QR-bill
     - :doc:`Switzerland - Accounting<../../../finance/fiscal_localizations/switzerland>`
     - `l10n_ch`
     - The base module to manage chart of accounting and localization for Switzerland.
   * - PromptPay
     - :doc:`Thailand - Accounting<../../../finance/fiscal_localizations/thailand>`
     - `l10n_th`
     - The base module to manage chart of accounting and localization for Thailand.
   * - VietQR
     - :doc:`Vietnam - Accounting<../../../finance/fiscal_localizations/vietnam>`
     - `l10n_vn`
     - The base module to manage chart of accounting and localization for Vietnam.
   * - EPC
     - :doc:`Account SEPA QR Code<../../../finance/accounting/customer_invoices/epc_qr_code>`
     - `account_qr_code_sepa`
     - This module adds support for SEPA Credit Transfer QR-code generation.

Create the payment method
-------------------------

#. Open the Point of Sale application.
#. Go to :menuselection:`Configuration --> Payment Methods` and create a payment method.
#. Set a bank typed journal.
#. Select :guilabel:`Bank App (QR Code)` under the :guilabel:`Integration` section.
#. Select the :guilabel:`QR Code Format` from the dropdown menu.

   - Select :guilabel:`SEPA Credit Transfer QR` if you are part of the Single Euro Payments Area
     (SEPA).
   - Select :guilabel:`EMV Merchant-Presented QR-code` for other QR code types.

.. image:: qr_code_payment/qr-payment-methods-setting.png
   :alt: QR code payment method configuration

.. important::
   At least one bank account must be defined on the journal to allow registering QR code payments
   with Bank apps.

Once the payment method is created, you can select it in your POS settings. To do so, go to the
:ref:`POS' settings <configuration/settings>` and add the payment method under the
:guilabel:`Payment` section.

.. image:: qr_code_payment/qr-configuration-setting.png
   :alt: Enable QR code payment method

Register payments using QR codes
================================

When processing a payment, select the QR codes related payment method. A QR code is generated and
displayed on the screen for the customer to scan and pay with their mobile banking app.

.. image:: qr_code_payment/qr-payment-example.png
   :alt: QR code payment example

Hit :guilabel:`Confirm Payment` to validate the transaction.

.. important::
   Odoo does **not*** check the bank payment. It is recommended that users verify payments for
   validity before confirming them on the POS register.
