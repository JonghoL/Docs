Methodology
=============


Overview
^^^^^^^^^^^^^^^^^

While our online reporting interface allows merchants to quickly and easily retrieve detailed information about past transactions, a need for additional flexibility may be required. For example, a merchant may have custom accounting software that requires up-to-date information about the settlement status of all credit card transactions every day.

This document describes how developers can query our reporting engine directly to retrieve transaction reports in a machine readable format. Once the data has been retrieved, it can then be parsed and imported into a variety of software applications.


Communication
^^^^^^^^^^^^^^^^^
The communication protocol used to send messages to the Payment Gateway is through the HTTP protocol over an SSL connection (HTTPS). The format you must use is name/value pairs delimited by ampersand.

URL:	https://secure.nzgateway.com/api/query.php
Example Query String:	username=username&password=password&transaction_id=123456789
You may use either GET or POST to pass your request to the Query API. The name/value pairs that are accepted by the Payment Gateway can be found in the 'Variables' section of this API.

The Query API can be tested with live credentials or a dedicated test account only. Please contact your Merchant Service Provider for more information.

The Query API will respond in Universal Time Coordinated (UTC).
