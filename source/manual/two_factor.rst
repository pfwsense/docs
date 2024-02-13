=========================
Two-factor authentication
=========================

.. image:: images/two_factor_authentication.png
   :width: 100%

Two-factor authentication also known as 2FA or 2-Step Verification is an authentication
method that requires two components, such as a pin/password + a token.

PFWsense (version >=16.1.14) offers support for Two-factor authentication throughout
the entire system, with one exception being console/ssh access.

Supported services are:

* PFWsense Graphical User Interface
* Captive Portal
* Virtual Private Networking - OpenVPN & IPsec
* Caching Proxy

New authentication servers can be added via  :menuselection:`System -> Access -> Servers`, which supports
both local users and users synchronised via ldap.  

----------------------------
Time-based One-time Password
----------------------------
TOTP is an algorithm that computes a one-time password from a shared secret key
and the current time. PFWsense supports RFC 6238.


--------------------
Google Authenticator
--------------------
PFWsense fully supports the use of Google's Authenticator application.
This application can generate tokens on Android, iOS and BlackBerry OS.
The usage of this application is free and very simple to setup using PFWsense.

-----------------
Other TOTP tokens
-----------------
The 2FA feature can be used with any time based one-time password token, although
it may be necessary to convert the tokens seed to the used format (base32).

---------------------
Configuration & Setup
---------------------
To setup see: :doc:`how-tos/two_factor`.
