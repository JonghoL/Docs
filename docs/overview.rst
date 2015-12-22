Integration Overview
=============

There are multiple ways to incorporate the payment gateway within a website or mobile device. These options vary based upon ease of integration, required resources, features, and additional security.

Transaction Request APIs
-------------------

Three-Step Redirect API
~~~~~~~

The Three Step Redirect is the preferred API for customized web-based payment processing. Using this integration method significantly reduces a merchant's PCI footprint without sacrificing end-user look and feel. This method is required when using Verified by Visa/Mastercard SecureCode (Payer Authentication).

Direct Post API
~~~~~~

The Direct Post method is the simplest integration method for both web-based and non web-based payment applications, however, merchants using this integration method should have passed a PCI vulnerability scan before use.

Mobile API
~~~~~~~~~~~~~~~~

The Mobile API supports iOS and Android based devices. These SDKs include a mobile card reader library which simplifies integrations for applications requiring encrypted mobile card readers. Additionally, an end-to-end encryption library is included, allowing merchants to send both swiped and keyed-in payment information without ever touching any sensitive data.
