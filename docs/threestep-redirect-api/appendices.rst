Appendices
=============

  - `Appendix 1`_
  - `Appendix 2`_
  - `Appendix 3`_

Appendix 1
---------------

.. list-table:: AVS Response Codes
   :widths: 10 90

   * - X
     - Exact match, 9-character numeric ZIP
   * - Y
     - Exact match, 5-character numeric ZIP
   * - D
     - Exact match, 5-character numeric ZIP
   * - M
     - Exact match, 5-character numeric ZIP
   * - A
     - Address match only
   * - B
     - Address match only
   * - W
     - 9-character numeric ZIP match only
   * - Z
     - 5-character ZIP match only
   * - P
     - 5-character ZIP match only
   * - L
     - 5-character ZIP match only
   * - N
     - No address or ZIP match only
   * - C
     - No address or ZIP match only
   * - U
     - Address unavailable
   * - G
     - Non-U.S. issuer does not participate
   * - I
     - Non-U.S. issuer does not participate
   * - R
     - Issuer system unavailable
   * - E
     - Not a mail/phone order
   * - S
     - Service not supported
   * - O
     - AVS not available
   * - B
     - AVS not available



Appendix 2
---------------

.. list-table:: CVV Response Codes
  :widths: 10 90

  * - M
    - CVV2/CVC2 match
  * - N
    - CVV2/CVC2 no match
  * - P
    - Not processed
  * - S
    - Merchant has indicated that CVV2/CVC2 is not present on card
  * - U
    - Issuer is not certified and/or has not provided Visa encryption keys


Appendix 3
---------------

.. list-table:: Result Code Table
   :widths: 10 90

   * - 100
     - Transaction was approved.
   * - 200
     - Transaction was declined by processor.
   * - 201
     - Do not honor.
   * - 202
     - Insufficient funds.
   * - 203
     - Over limit.
   * - 204
     - Transaction not allowed.
   * - 220
     - Incorrect payment information
   * - 221
     - No such card issuer.
   * - 222
     - No card number on file with issuer.
   * - 223
     - Expired card.
   * - 224
     - Invalid expiration date.
   * - 225
     - Invalid card security code.
   * - 240
     - Call issuer for further information.
   * - 250
     - Pick up card.
   * - 251
     - Lost card.
   * - 252
     - Stolen card.
   * - 253
     - Fraudulent card.
   * - 260
     - Declined with further instructions available. (See response text)
   * - 261
     - Declined-Stop all recurring payments.
   * - 262
     - Declined-Stop this recurring program.
   * - 263
     - Declined-Update cardholder data available.
