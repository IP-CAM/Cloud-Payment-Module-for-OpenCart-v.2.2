Übersetzungstypen
Textübersetzung
Ausgangstext
# CloudPayments modul' dlya OpenCart Modul' pozvolit s legkost'yu dobavit' na vash sayt oplatu bankovskimi kartami cherez platezhnyy servis CloudPayments. Dlya korrektnoy raboty modulya neobkhodima registratsiya v servise. Poryadok registratsii opisan v [dokumentatsii CloudPayments](https://cloudpayments.ru/Docs/Connect) ### Vozmozhnosti * Odnostadiynaya skhema oplaty; * Dvukhstadiynaya skhema oplaty; * Vybor dizayna vidzheta oplaty; * Otmena, podtverzhdeniye i vozvrat platezhey iz LK CMS; * Lokalizatsiya vidzheta oplaty; * Podderzhka onlayn-kass (FZ-54); * Nastroyka NDS dlya sluzhby dostavki; * Tegi sposoba i predmeta rascheta; * Otpravka chekov po email; * Otpravka chekov po SMS; ### Sovmestimost' OpenCart v.2.2 i vyshe; ### Ustanovka cherez panel' upravleniya V paneli admniistratora zayti v razdel "Moduli/Rasshireniya" -> "Ustanovka rasshireniy" i zagruzit' arkhiv. ### Ruchnaya ustanovka Raspakovat' iz arkhiva katalog upload i zagruzit' v koren' OpenCart. Yesli u vy ispol'zuyete opencart v.2.3, to ispol'zuyte upload iz kataloga for 2.3 only. Yesli u vy ispol'zuyete opencart v.2.2, to ispol'zuyte upload iz kataloga for 2.2 only. ### Nastroyka modulya 1. Pereyti v nastroyki modulya "Moduli/Rasshireniya" -> "Moduli/Rasshireniya" -> "Oplata". Vybrat' CloudPayments i aktivirovat' modul'. 2. Zayti v nastroyki modulya i ukazat': * Identifikator sayta — Public id sayta iz lichnogo kabineta CloudPayments * Sekretnyy klyuch — API Secret iz lichnogo kabineta CloudPayments * Status - vklyucheno Zatem sokhranit' vvedennyye parametry. Dopolnitel'no mozhno takzhe ukazat': regiony, dlya kotorykh budet deystvovat' metod oplaty, minimal'nuyu summu zakaza, poryadok sortirovki pri vyvode metodov oplaty. A takzhe vklyuchit' dvukhstadiynuyu oplatu, formirvaniye onlayn-cheka i nastroit' trebuyemyye statusy zakaza na opredelennyye sobytiya. 3. V lichnom kabinete CloudPayments ukazat' URL uvedomleniy so vkladki "Uvedomleniya" ### Dvukhstadiynaya oplata V etom rezhime oplata proiskhodit v dva etapa: avtorizatsiya platezha (blokirovka summy na karte pokupatelya) i podtverzhdeniye spisaniya. Dlya raboty modulya v etom rezhime mogut potrebovat'sya dopolnitel'nyye statusy zakaza: * Avtorizovan — Na dannyy status zakaz perevoditsya pri poluchenii uvedomleniya ob avtorizatsii oplaty. Po umolchaniyu zakaz perevoditsya v status "Ozhidaniye"; * Podtverzhden — Pri perevoda zakaza na dannyy status otpravlyayetsya zapros na podtverzhdeniye oplaty. Neobkhodim yesli trebuyetsya podtverzhdat' zakaz do otpravki. Po umolchaniyu oplata podtverzhdayetsya pri smene statusa na "Sdelka zavershena". Dannyye statusy mozhno sozdat' v "Sistema" -> "Lokalizatsiya" -> "Statusy zakazov". A nastroit' ikh na trebuyemyye sobytiya v nastroykakh modulya (vkladka "Statusy"). Takzhe v nastroykakh modulya trebuyetsya vklyuchit' dvukhstadiynuyu oplatu ustanoviv znacheniye sootvetstvushchego parametra v "vklyucheno". ### Integratsiya s onlayn-kassoy Modul' pozvolyayet integrirovat' onlayn-kassu pri oplate i otmenakh platezhey. Dlya etogo podklyuchit' kassu v lichnom kabinete CloudPayments https://cloudpayments.ru/Docs/Kassa i ukazat' dopolnitel'nyye nastroyki modulya: * Formirovat' onlayn-chek — Vklyucheno * Stavka NDS — Ukazaniye stavki NDS. Vse vozmozhnyye znacheniya ukazany v dokumentatsii https://cloudpayments.ru/Docs/Kassa#data-format * Stavka NDS dlya dostavki — Ukazaniye otdel'noy stavki NDS dlya dostavki. Yesli dostavka platnaya, to ona v cheke oformlyayetsya otdel'noy strokoy so svoyey stavkoy NDS. Znacheniya analogichno stavke NDS dlya tovarov. * Sistema nalogooblozheniya — Tip sistemy nalogooblozheniya. Vozmozhnyye znacheniya perechisleny v dokumentatsii CloudPayments https://cloudpayments.ru/Docs/Directory#taxation-system * Sposob rascheta — priznak sposoba rascheta dlya tovarov; * Predmet rascheta — priznak predmeta rascheta dlya tovarov; * Status dostavki - **Dostavlen** (Ili **Shipped** na eng versii admin paneli). _Otdel'nyy status dostavki neobkhodim pri formirovanii dvukh chekov: odin chek - pri postuplenii deneg ot pokupatelya, vtoroy pri otgruzke tovara. Otpravka vtorogo cheka vozmozhna pri sleduyushchikh sposobakh rascheta: Predoplata, Predoplata 100%, Avans._ ### Uvedomleniya o sobytiyakh V sisteme predusmotreno neskol'ko vidov uvedomleniy: dlya proverki vozmozhnosti vypolnit' oplatu, dlya informirovaniya ob uspeshnykh i neuspeshnykh platezhakh, a takzhe dlya informirovaniya o vydannykh kassovykh chekakh. V lichnom kabinete CloudPayments zaydite v nastroyki sayta, propishite v nastroykakh uvedomleniya, kak opisano na vkladke "uvedomleniya" nastroyki modulya. == Changelog == = 2.0 = * Dobavleny tegi sposobov i predmetov rascheta; * Ustraneny nekotoryye oshibki s mul'tivalyutnost'yu; * Ustraneny nekotoryye oshibki s kassovymi chekami; = 1.2 = * Ustraneny nekotoryye oshibki; * Publikatsiya plagina na marketpleys. = 1.0 = * Publikatsiya plagina na [GitHub](https://github.com/cloudpayments/CMS-OpenCart-CP).
Mehr anzeigen
4800 / 5000
Übersetzungsergebnisse
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

