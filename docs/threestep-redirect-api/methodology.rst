Methodology
=============


Method Overview
^^^^^^^^^^^^^^^^^
  - **Step One**: Submit all transaction details to the Payment Gateway except the customer's sensitive payment information. The Payment Gateway will return a variable form-url.
	- **Step Two**: Create an HTML form that collects the customer's sensitive payment information and use the form-url that the Payment Gateway returns as the submit action in that form.
	- **Step Three**: Once the customer has been redirected, obtain the token-id and complete the transaction through an HTTPS POST including the token-id which abstracts the sensitive payment information that was collected directly by the Payment Gateway.

.. image:: _static/threestepredirect.png
