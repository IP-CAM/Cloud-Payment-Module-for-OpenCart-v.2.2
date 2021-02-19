# CloudPayments module for OpenCart
The module will allow you to easily add payment by bank cards to your website through the CloudPayments payment service.
Registration in the service is required for the module to work correctly.

The registration procedure is described in [CloudPayments documentation] (https://cloudpayments.ru/Docs/Connect)

### Opportunities
* One-step payment scheme;
* Two-stage payment scheme;
* Choice of payment widget design;
* Cancellation, confirmation and refund of payments from LC CMS;
* Localization of the payment widget;
* Support for online cash registers (FZ-54);
* Setting up VAT for the delivery service;
* Tags of the method and subject of calculation;
* Sending checks by email;
* Sending checks by SMS;

### Compatibility
OpenCart v.2.2 and higher;

### Installation via control panel

In the admin panel go to the section "Modules / Extensions" -> "Install extensions" and download the archive.

### Manual installation

Unpack the upload directory from the archive and upload it to the OpenCart root.
If you are using opencart v.2.3, then use upload from the for 2.3 only directory.
If you are using opencart v.2.2, then use upload from the for 2.2 only directory.

### Module configuration

1. Go to the module settings "Modules / Extensions" -> "Modules / Extensions" -> "Payment".
Select CloudPayments and activate the module.
2. Go to the module settings and specify:
    * Site identifier - Public id of the site from the personal account of CloudPayments
    * Secret key - API Secret from your CloudPayments personal account
    * Status - included
    
    Then save the entered parameters.
    
    Additionally, you can also specify: regions for which the payment method will be valid,
    minimum order amount, sorting order when displaying payment methods.
    And also enable two-step payment, generate an online receipt and set up the required order statuses
    for certain events.
3. In your CloudPayments personal account, specify the URL of notifications from the "Notifications" tab

### Two-step payment

In this mode, payment takes place in two stages: payment authorization (blocking the amount on the buyer's card)
and confirmation of the write-off.
Additional order statuses may be required for the module to work in this mode:

* Authorized - The order is transferred to this status upon receipt of a payment authorization notification.
    By default, the order is transferred to the "Pending" status;
* Confirmed - When the order is transferred to this status, a request is sent to confirm the payment.
    Required if order confirmation is required before shipment.
    By default, the payment is confirmed when the status is changed to "Deal completed".
        
These statuses can be created in "System" -> "Localization" -> "Order statuses".
And configure them for the required events in the module settings (the "Statuses" tab).
Also in the module settings you need to enable two-stage payment by setting the value
the corresponding parameter to "on".

### Integration with online checkout

The module allows you to integrate an online cashier when making payments and canceling payments.
To do this, connect the cashier in your CloudPayments personal account https://cloudpayments.ru/Docs/Kassa and specify additional module settings:

* Generate Online Check - Included
* VAT rate - Indication of the VAT rate.
All possible values ​​are indicated in the documentation https://cloudpayments.ru/Docs/Kassa#data-format
* VAT rate for shipping - Specifies a separate VAT rate for shipping.
If delivery is paid, then it is drawn up in a separate line in the check with its own VAT rate.
The values ​​are the same as the VAT rate for goods.
* Taxation system - Type of taxation system.
Possible values ​​are listed in the CloudPayments documentation https://cloudpayments.ru/Docs/Directory#taxation-system
* Calculation method - a sign of the calculation method for goods
* Subject of calculation - a sign of the subject of calculation for goods;
* Delivery status - ** Delivered ** (Or ** Shipped ** on the eng version of the admin panel).
_Separate delivery status is required when generating two checks: one check - when money is received from the buyer, the second when the goods are shipped. Sending a second check is possible with the following payment methods: Prepayment, Prepayment 100%, Advance._

### Event notifications

The system provides several types of notifications: to check the possibility of making a payment, to inform about successful and unsuccessful payments, as well as to inform about issued cashier's checks.
In your CloudPayments personal account, go to the site settings, write in the notification settings, as described on the "notifications" tab of the module settings.

== Changelog ==
= 2.0 =
* Added tags for methods and items of calculation;
* Fixed some bugs with multicurrency;
* Fixed some bugs with cashier's checks;

= 1.2 =
* Fixed some bugs;
* Publishing the plugin to the marketplace.

= 1.0 =
* Publishing the plugin to [GitHub] (https://github.com/cloudpayments/CMS-OpenCart-CP). 
