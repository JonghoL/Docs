Transaction Operations
=============

Step1
-------

Sale/Auth/Credit/Validate/Offline
^^^^^^^^^^^^^^^^^

+----------------------------------------+--------------------------------------------------------------------------------+
| XML Element                            | Description                                                                    |
+========================================+================================================================================+
| **<sale|auth|credit|validate|offline>**| Type of transaction to perform.                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| api-key*                               | api-key is obtained in the security keys section of the control                |
|                                        | panel settings.                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| redirect-url*                          | A URL on your web server that the gateway will redirect your                   |
|                                        | customer to after sensitive data collection.                                   |
+----------------------------------------+--------------------------------------------------------------------------------+
| amount*                                | Total amount to be charged                                                     |
|                                        | (For "validate" actions, amount must be 0.00 or omitted).                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| authorization-code**                   | Specify authorization code. For use with "offline" action only.                |
+----------------------------------------+--------------------------------------------------------------------------------+
| ip-address                             | Cardholder's IP address. Format: xxx.xxx.xxx.xxx                               |
+----------------------------------------+--------------------------------------------------------------------------------+
| industry                               | Specify industry classification of transaction.                                |
|                                        | Values: 'ecommerce', 'moto', or 'retail'                                       |
+----------------------------------------+--------------------------------------------------------------------------------+
| billing-method                         | Set additional billing indicators. Values: 'recurring' or 'installment'        |
+----------------------------------------+--------------------------------------------------------------------------------+
| billing-number                         | Specify installment billing number, on supported processors.                   |
|                                        | For use when "billing-method" is set to installment. Values: 0-99              |
+----------------------------------------+--------------------------------------------------------------------------------+
| billing-total                          | Specify installment billing total on supported processors.                     |
|                                        | For use when "billing-method" is set to installment.                           |
+----------------------------------------+--------------------------------------------------------------------------------+
| processor-id                           | If using multiple processors, route to specified processor.                    |
|                                        | Obtained under Settings->Load Balancing                                        |
|                                        | in the merchant control panel.                                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| sec-code                               | ACH standard entry class codes.                                                |
|                                        | Values: 'PPD', 'WEB', 'TEL', 'CCD', 'POP', or 'ARC'                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor                             | Set payment descriptor on supported processors.                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-phone                       | Set payment descriptor phone on supported processors.                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-address                     | Set payment descriptor address on supported processors.                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-city                        | Set payment descriptor city on supported processors.                           |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-state                       | Set payment descriptor state on supported processors.                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-postal                      | Set payment descriptor postal code on supported processors.                    |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-country                     | Set payment descriptor country on supported processors.                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-mcc                         | Set payment descriptor mcc on supported processors.                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-merchant-id                 | Set payment descriptor merchant id on supported processors.                    |
+----------------------------------------+--------------------------------------------------------------------------------+
| descriptor-url                         | Set payment descriptor url on supported processors.                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| currency                               | Set transaction currency. Format: ISO 4217                                     |
+----------------------------------------+--------------------------------------------------------------------------------+
| order-description                      | Order description.                                                             |
+----------------------------------------+--------------------------------------------------------------------------------+
| customer-id                            | Customer identification.                                                       |
+----------------------------------------+--------------------------------------------------------------------------------+
| customer-vault-id                      | Load customer details from an existing customer vault record.                  |
|                                        | If set, no payment information is required during step two.                    |
+----------------------------------------+--------------------------------------------------------------------------------+
| merchant-receipt-email                 | Send merchant receipt to email                                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| customer-receipt                       | Send receipt if billing email included. Values: 'true' or 'false'              |
+----------------------------------------+--------------------------------------------------------------------------------+
| merchant-defined-field-#               | Merchant specified custom fields.                                              |
|                                        | Format: <merchant-defined-field-1>Value</merchant-defined-field-1>             |
+----------------------------------------+--------------------------------------------------------------------------------+
| tracking-number                        | Shipping tracking number.                                                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| shipping-carrier                       | Shipping carrier. Values: 'ups', 'fedex', 'dhl', or 'usps'                     |
+----------------------------------------+--------------------------------------------------------------------------------+
| order-id***                            | Order id.                                                                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| po-number***                           | Cardholder's purchase order number.                                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| tax-amount***                          | The sales tax included in the transaction amount associated with               |
|                                        | the purchase. Setting tax equal to '-1' indicates an order that                |
|                                        | is exempt from sales tax. Default: '0.00' Format: x.xx                         |
+----------------------------------------+--------------------------------------------------------------------------------+
| shipping-amount***                     | Total shipping amount.                                                         |
+----------------------------------------+--------------------------------------------------------------------------------+
| ship-from-postal****                   | Postal/ZIP code of the address from where purchased goods                      |
|                                        | are being shipped. Defaults to merchant profile postal code.                   |
+----------------------------------------+--------------------------------------------------------------------------------+
| summary-commodity-code****             | A code representing the type of commodity being purchased.                     |
|                                        | The acquirer or processor will provide a list of current codes.                |
+----------------------------------------+--------------------------------------------------------------------------------+
| duty-amount                            | Amount included in the transaction amount associated with                      |
|                                        | the import of the purchased goods. Default: '0.00'                             |
+----------------------------------------+--------------------------------------------------------------------------------+
| discount-amount                        | Amount included in the transaction amount of any discount                      |
|                                        | applied to the complete order by the merchant. Default: '0.00'                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| national-tax-amount                    | The national tax amount included in the transaction amount. Default: '0.00'    |
+----------------------------------------+--------------------------------------------------------------------------------+
| alternate-tax-amount                   | Second tax amount included in the transaction amount in                        |
|                                        | countries where more than one type of tax can be applied                       |
|                                        | to the purchases. Default: '0.00'                                              |
+----------------------------------------+--------------------------------------------------------------------------------+
| alternate-tax-id                       | Tax identification number of the merchant that reported                        |
|                                        | the alternate tax amount.                                                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| vat-tax-amount                         | Contains the amount of any value added taxes which can                         |
|                                        | be associated with the purchased item. Default: '0.00'                         |
+----------------------------------------+--------------------------------------------------------------------------------+
| vat-tax-rate                           | Contains the tax rate used to calculate the sales tax amount                   |
|                                        | appearing. Can contain up to 2 decimal places, ie 1% = 1.00. Default: '0.00'   |
+----------------------------------------+--------------------------------------------------------------------------------+
| vat-invoice-reference-number           | Invoice number that is associated with the VAT invoice.                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| customer-vat-registration              | Value added tax registration number supplied by the cardholder.                |
+----------------------------------------+--------------------------------------------------------------------------------+
| merchant-vat-registration              | Government assigned tax identification number of the merchant                  |
|                                        | from whom the goods or services were purchased.                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| order-date                             | Purchase order date. Defaults to the date of the transaction. Format: YYMMDD   |
+----------------------------------------+--------------------------------------------------------------------------------+
| cardholder-auth†                       | Set 3D Secure condition. Values: 'verified' or 'attempted'                     |
+----------------------------------------+--------------------------------------------------------------------------------+
| eci†                                   | E-commerce indicator. Values: '2', '5', or '7'                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| cavv†                                  | Cardholder authentication verification value. Format: base64 encoded           |
+----------------------------------------+--------------------------------------------------------------------------------+
| xid†                                   | Cardholder authentication transaction id. Format: base64 encoded               |
+----------------------------------------+--------------------------------------------------------------------------------+
| dup-seconds‡                           | Override duplicate transaction detection time in seconds.                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| avs-reject‡                            | The transaction is rejected if the address verification result is              |
|                                        | a code in this list. Values are letters obtained under                         |
|                                        | Settings->Address Verification in the control panel. Format: x|x|x|x...        |
+----------------------------------------+--------------------------------------------------------------------------------+
| cvv-reject‡                            | The transaction is rejected if the card ID verification result                 |
|                                        | is a code in this list.  Values are letters obtained                           |
|                                        | under Settings->Card ID Verification in the control panel. Format: x|x|x|x...  |
+----------------------------------------+--------------------------------------------------------------------------------+
| **<billing>**                          | The customer's billing information                                             |
+----------------------------------------+--------------------------------------------------------------------------------+
| billing-id                             | Specify billing id. Recommended when using customer vault                      |
|                                        | hybrid action. Will be ignored if no hybrid add/update-customer                |
|                                        | is done.                                                                       |
+----------------------------------------+--------------------------------------------------------------------------------+
| first-name                             | Cardholder's first name.                                                       |
+----------------------------------------+--------------------------------------------------------------------------------+
| last-name                              | Cardholder's last name.                                                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| address1                               | Cardholder's billing address.                                                  |
+----------------------------------------+--------------------------------------------------------------------------------+
| city                                   | Card billing city.                                                             |
+----------------------------------------+--------------------------------------------------------------------------------+
| state                                  | Card billing state/province. Format: CC                                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| postal                                 | Card billing postal code.                                                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| country                                | Card billing country code. Format: CC/ISO 3166                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| phone                                  | Billing phone number.                                                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| email                                  | Billing email address.                                                         |
+----------------------------------------+--------------------------------------------------------------------------------+
| company                                | Cardholder's company.                                                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| address2                               | Card billing address, line 2.                                                  |
+----------------------------------------+--------------------------------------------------------------------------------+
| fax                                    | Billing fax number.                                                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| account-type§                          | The customer's ACH account type. Values: 'checking' or 'savings'               |
+----------------------------------------+--------------------------------------------------------------------------------+
| entity-type§                           | The customer's ACH account entity. Values: 'personal' or 'business'            |
+----------------------------------------+--------------------------------------------------------------------------------+
| **</billing>**                         |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| **<shipping>**                         | The customer's shipping information.                                           |
+----------------------------------------+--------------------------------------------------------------------------------+
| shipping-id                            | Specify shipping id. Recommended when using customer vault                     |
|                                        | hybrid action. Will be ignored if no hybrid add/update-customer is done.       |
+----------------------------------------+--------------------------------------------------------------------------------+
| first-name                             | Shipping first name.                                                           |
+----------------------------------------+--------------------------------------------------------------------------------+
| last-name                              | Shipping last name.                                                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| address1                               | Shipping billing address.                                                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| city                                   | Shipping city.                                                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| state                                  | Shipping state/province. Format: CC                                            |
+----------------------------------------+--------------------------------------------------------------------------------+
| postal****                             | Shipping postal code.                                                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| country****                            | Shipping country code. Format: CC/ISO 3166                                     |
+----------------------------------------+--------------------------------------------------------------------------------+
| phone                                  | Shipping phone number.                                                         |
+----------------------------------------+--------------------------------------------------------------------------------+
| email                                  | Shipping email address.                                                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| company                                | Shipping company.                                                              |
+----------------------------------------+--------------------------------------------------------------------------------+
| address2                               | Shipping address, line 2.                                                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| fax                                    | Shipping fax number.                                                           |
+----------------------------------------+--------------------------------------------------------------------------------+
| **</shipping>**                        |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| **<product>**                          | Product line item detail. Multiple product elements are allowed.               |
+----------------------------------------+--------------------------------------------------------------------------------+
| product-code****¶                      | Merchant defined description code of the item being purchased.                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| description****                        | Description of the item(s) being supplied.                                     |
+----------------------------------------+--------------------------------------------------------------------------------+
| commodity-code****                     | International description code of the individual good or service               |
|                                        | being supplied.                                                                |
|                                        | The acquirer or processor will provide a list of current codes.                |
+----------------------------------------+--------------------------------------------------------------------------------+
| unit-of-measure****                    | Code for units of measurement as used in international trade. Default: 'EACH'  |
+----------------------------------------+--------------------------------------------------------------------------------+
| unit-cost****                          | Unit cost of item purchased. May contain up to 4 decimal places.               |
+----------------------------------------+--------------------------------------------------------------------------------+
| quantity****                           | Quantity of the item(s) being purchased. Default: '1'                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| total-amount****                       | Purchase amount associated with the item. Default to 'unit-cost' x 'quantity'  |
|                                        | rounded to the nearest penny.                                                  |
+----------------------------------------+--------------------------------------------------------------------------------+
| tax-amount****                         | Amount of tax on specific item. Amount should not be included                  |
|                                        | in item-total-amount. Default: '0.00'                                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| tax-rate****                           | Percentage representing the value-added tax applied. 1% = 1.00. Default: '0.00'|
+----------------------------------------+--------------------------------------------------------------------------------+
| discount-amount                        | Discount amount which can have been applied by the merchant                    |
|                                        | on the sale of the specific item. Amount should not be included                |
|                                        | in 'item-total-amount'.                                                        |
+----------------------------------------+--------------------------------------------------------------------------------+
| discount-rate                          | Discount rate for the line item. 1% = 1.00. Default: '0.00'                    |
+----------------------------------------+--------------------------------------------------------------------------------+
| tax-type                               | Type of value-added taxes that are being used.                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| alternate-tax-id                       | Tax identification number of the merchant that reported the                    |
|                                        | alternate tax amount.                                                          |
+----------------------------------------+--------------------------------------------------------------------------------+
| **</product>**                         |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| **<add-subscription>**                 | Perform a simultaneous 'hybrid' recurring action while processing              |
|                                        | a transaction.                                                                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| start-date                             | The first day that the customer will be charged. Format: YYYYMMDD              |
+----------------------------------------+--------------------------------------------------------------------------------+
| **<plan>**                             |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| plan-id                                | The unique plan ID that references only this recurring plan.                   |
+----------------------------------------+--------------------------------------------------------------------------------+
| payments                               | The number of payments before the recurring plan is complete.                  |
|                                        | Note: Use '0' for 'until canceled'                                             |
+----------------------------------------+--------------------------------------------------------------------------------+
| amount                                 | The plan amount to be charged each billing cycle. Format: x.xx                 |
+----------------------------------------+--------------------------------------------------------------------------------+
| day-frequency                          | How often, in days, to charge the customer. Cannot be set with                 |
|                                        | 'month-frequency' or 'day-of-month'.                                           |
+----------------------------------------+--------------------------------------------------------------------------------+
| month-frequency                        | How often, in months, to charge the customer. Cannot be set with               |
|                                        | 'day-frequency'. Must be set with 'day-of-month'.  Values: 1 through 24        |
+----------------------------------------+--------------------------------------------------------------------------------+
| day-of-month                           | The day that the customer will be charged. Cannot be set with                  |
|                                        | 'day-frequency'. Must be set with 'month-frequency'.                           |
|                                        | Values: 1 through 31 - for months without 29, 30, or 31 days,                  |
|                                        | the charge will be on the last day                                             |
+----------------------------------------+--------------------------------------------------------------------------------+
| **</plan>**                            |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| **</add-subscription>**                |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| **<add-customer|update-customer>**     | Perform a simultaneous 'hybrid' customer vault action while                    |
|                                        | processing a transaction. This tag can be blank if submitting                  |
|                                        | an 'add-customer' without specifying a 'customer-vault-id'.                    |
+----------------------------------------+--------------------------------------------------------------------------------+
| customer-vault-id                      | Specify customer vault id. If omitted, will be auto-generated                  |
|                                        | and returned in response. Required for 'update-customer'.                      |
+----------------------------------------+--------------------------------------------------------------------------------+
| **</add-customer|update-customer>**    |                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+
| partial-payments††                     | Specify whether a partial amount or full amount of the transaction             |
|                                        | should be settled.                                                             |
|                                        | Format: 'settle_partial' or 'payment_in_full'                                  |
+----------------------------------------+--------------------------------------------------------------------------------+
| partial-payment-id††                   | Specify a partial payment ID. Required to collect an additional                |
|                                        | amount associated with an existing Partial Payment Transaction.                |
|                                        | Do not use on initial transaction.                                             |
+----------------------------------------+--------------------------------------------------------------------------------+
|**</sale|auth|credit|validate|offline>**|                                                                                |
+----------------------------------------+--------------------------------------------------------------------------------+


+------------+-----------------------------------------+
| \*         | Always required                         |
+------------+-----------------------------------------+
| \*\*       | Required for credit card transactions   |
+------------+-----------------------------------------+
| \*\*\*     | Required for ACH transactions           |
+------------+-----------------------------------------+
| \*\*\*\*   | Required for Level 2 transactions       |
+------------+-----------------------------------------+
| †          | Required for Level 3 transactions       |
+------------+-----------------------------------------+
| ‡          | Required for offline transactions       |
+------------+-----------------------------------------+
