# ⛔ Accessing Reports from External Systems

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

You can call reports defined in DAC with an URL with the following syntax:

_http://<**HOST>:<**:**PORT>/<**/**CONTEXT>/**&#x63;assiopeaWeb/report/report.jsp.cas?revent=_ _LW\_RSTATE\_LAUNCH\_REPORT\&csUsrn=**\<UTENTE**>\&csPass=**\<PWD**>\&csMLO=**\<OWNER**>\&idReportRequest=**\<idReport>**_

where:

_**\<HOST>**_ = name host or application server IP

_**\<PORT>**_ = port of application server

_**\<CONTEXT>**_ = name of DAC application

_**\<USERNAME**_> = username

_**\<PASSWORD>**_ = user password, encrypted (parameter "crypted" set to 1)

_**\<OWNER>**_ = model ID

<_**\<idReport> ID**_ code of the report

The password can be encrypted manually with encrypting mode "encrypt”, found in the "DecisyonCrypter” Java class. You’ll find this class in the library "cassiopea.jar" available in the "lib" folder of DAC.

This allows you to dynamically link DAC reports to external (web-type) applications, for example, by requesting the report filtered by the parameters of the source application.

This type of access opens the DAC interface with a minimized navigation bar, as shown in the diagram.
