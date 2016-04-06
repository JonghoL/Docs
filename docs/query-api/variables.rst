Variables
=============

+----------------------+----------------------------------------------------------------+
| Variable Name        | Description(Allowed Values)[Format]                            |
+======================+================================================================+
| username*            | Merchant username.                                             |
+----------------------+----------------------------------------------------------------+
| password*            | Merchant password.                                             |
+----------------------+----------------------------------------------------------------+
| condition            | A combination of values listed below can be passed and         |
|                      | should be separated by commas. For example, to retrieve all    |
|                      | transactions pending settlement or complete, the following     |
|                      | could be used:                                                 |
|                      |                                                                |
|                      | Example: condition=pendingsettlement,complete                  |
|                      +----------------------------------------------------------------+
|                      | pending: 'Auth Only' transactions that are awaiting capture.   |
|                      +----------------------------------------------------------------+
|                      | pendingsettlement: This transaction is awaiting settlement.    |
|                      +----------------------------------------------------------------+
|                      | failed: This transaction has failed.                           |
|                      +----------------------------------------------------------------+
|                      | canceled: This transaction has been voided.                    |
|                      +----------------------------------------------------------------+
|                      | complete: This transaction has settled.                        |
|                      +----------------------------------------------------------------+
|                      | unknown: An unknown error was encountered while processing     |
|                      | this transaction.                                              |
+----------------------+----------------------------------------------------------------+
| transaction_type     | Retrieves only transactions with the specified transaction     |
|                      | type. Use one of the following to specify payment type:        |
|                      |                                                                |
|                      +----------------------------------------------------------------+
|                      | cc: A credit card transaction.                                 |
|                      +----------------------------------------------------------------+
|                      | ck: A check transaction.                                       |
+----------------------+----------------------------------------------------------------+
| action_type          | Retrieves only transactions specified action types.            |
|                      | A combination of the values can be used and should be separated|
|                      | by commas. For example, to retrieve all transactions with      |
|                      | credit or refund actions, use the following:                   |
|                      |                                                                |
|                      | Example: action_type=refund,credit                             |
|                      +----------------------------------------------------------------+
|                      | sale: Sale transactions.                                       |
|                      +----------------------------------------------------------------+
|                      | refund: Refund transactions.                                   |
|                      +----------------------------------------------------------------+
|                      | credit: Credit transactions.                                   |
|                      +----------------------------------------------------------------+
|                      | auth: 'Auth Only' transactions.                                |
|                      +----------------------------------------------------------------+
|                      | capture: Captured transactions.                                |
|                      +----------------------------------------------------------------+
|                      | void: Voided transactions.                                     |
|                      +----------------------------------------------------------------+
|                      | return: Electronic Check (ACH) transactions that have returned |
|                      | before (return) or after settlement (late_return)              |
+----------------------+----------------------------------------------------------------+
| transaction_id       | Specify a transaction ID or a comma separated list of          |
|                      | transaction IDs to retrieve information on.                    |
+----------------------+----------------------------------------------------------------+
| order_id             | Retrieves only transactions with the specified Order ID.       |
+----------------------+----------------------------------------------------------------+
| last_name            | Retrieves only transactions with the specified last name.      |
+----------------------+----------------------------------------------------------------+
| email                | Retrieves only transactions with the specified billing email   |
|                      | address.                                                       |
+----------------------+----------------------------------------------------------------+
| cc_number            | Retrieves only transactions with the specified credit card     |
|                      | number. You can use either the full number or the last 4 digits|
|                      | of the credit card number.                                     |
+----------------------+----------------------------------------------------------------+
| merchant_defined_fiel| Retrieves only transactions with the specified merchant defined|
|d_#                   | field value.                                                   |
|                      | Replace the '#' with a field number (1-20)                     |
|                      | (Example: merchant_defined_field_12=value)                     |
+----------------------+----------------------------------------------------------------+
| start_date           | Only transactions that have been modified on or after this date|
|                      | will be retrieved. Note that any actions performed on a        |
|                      | transaction will cause the modified date to be updated.        |
|                      |                                                                |
|                      | Format: YYYYMMDDhhmmss                                         |
+----------------------+----------------------------------------------------------------+
| end_date             | Only transactions that have been modified on or before this    |
|                      | date will be retrieved. Note that any actions performed on a   |
|                      | transaction will cause the modified date to be updated.        |
|                      |                                                                |
|                      | Format: YYYYMMDDhhmmss                                         |
+----------------------+----------------------------------------------------------------+
| report_type          | Allows customer vault information or a html receipt to be      |
|                      | returned. If you would like to query the Customer Vault to view|
|                      | what customer information is stored in the Customer Vault, you |
|                      | must set the customer_vault variable.                          |
|                      | If you omit the customer_vault_id, the system will return all  |
|                      | customers that are stored in the vault. If you include a       |
|                      | customer_vault_id, it will return the customer record          |
|                      | associated with that ID.                                       |
|                      |                                                                |
|                      | Example: report_type=customer_vault&customer_vault_id=123456789|
|                      +----------------------------------------------------------------+
|                      | receipt: Will return an html receipt for a specified           |
|                      | transaction id.                                                |
|                      +----------------------------------------------------------------+
|                      | customer_vault: Set the Query API to return Customer Vault     |
|                      | data.                                                          |
+----------------------+----------------------------------------------------------------+
| mobile_device_license| Retrieves only transactions processed using the specified      |
|                      | mobile device.                                                 |
|                      | The device IDs for this parameter are available in the License |
|                      | Manager.                                                       |
|                      | Use 'any_mobile' to retrieve all mobile transactions.          |
|                      | A combination of the values can be used and should be separated|
|                      | by commas.                                                     |
|                      | Can not be used with 'mobile_device_nickname'.                 |
|                      |                                                                |
|                      | Example 1: mobile_device_license=D91AC56A-4242-3131-2323-2AE4AA|
|                      | 6DB6EB                                                         |
|                      |                                                                |
|                      | Example 2: mobile_device_license=any_mobile                    |
+----------------------+----------------------------------------------------------------+
| mobile_device_nicknam| Retrieves only transactions processed using mobile devices with|
|e                     | the specified nickname.                                        |
|                      | The nicknames for this parameter are available in the License  |
|                      | Manager.                                                       |
|                      | Can not be used with 'mobile_device_license'.                  |
|                      |                                                                |
|                      | Example (URL encoded): mobile_device_nickname=Jim's%20iPhone   |
+----------------------+----------------------------------------------------------------+
| customer_vault_id    | Set a specific Customer Vault record. Should only be used when |
|                      | report_type=customer_vault.                                    |
+----------------------+----------------------------------------------------------------+
