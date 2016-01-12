Third Party Shopping Carts
=============

Gateway Emulator
-------------------


We have designed our gateway to be able to handle transaction submissions and responses in the Authorize.Net format. We call this our Gateway Emulator.

To use the Gateway Emulator, your shopping cart or application must support the Authorize.Net AIM or SIM method of integration. If the application supports the AIM or SIM method, you simply need to change the transaction POST URL to our Gateway Emulator URL.

The Gateway does not support the emulation of XML AIM, CIM, ARB, DPM, Card Present or Transaction Details APIs.


Our Gateway Emulator URL is:


.. list-table::
   :header-rows: 1

   * - Method
     - URL

   * - AIM
     - https://secure.nzgateway.com/gateway/transact.dll

   * - SIM
     - https://secure.nzgateway.com/cart/ausi.php


You will need to change any production and test Authorize.Net URLs to one of the above URLs. The following URLs should be replaced:


 .. list-table::

    * - https://secure.authorize.net/gateway/transact.dll

    * - https://test.authorize.net/gateway/transact.dll


Some applications will not contain the test URL. In that case, you will only be changing one URL. Once you have updated the URLs to point to us, the application will submit transactions without needing changes to the code base.

You will then need to configure the Authorize.Net AIM or SIM payment module with the following credentials:

API ID or Login ID is your gateway username.
Transaction Key is your gateway password.
The MD5 Hash is the word "gateway" without the marks.

For testing, you can use the username and password of "demo" and "password".
