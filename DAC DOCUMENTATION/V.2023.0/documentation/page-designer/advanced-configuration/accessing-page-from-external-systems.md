# Accessing Page from External Systems

Pages defined in DAC can be recalled: the system provides for the **automatic generation of a link**, including the desired parameters.

This makes it possible to dynamically link DAC Pages to external (web-type) applications, for example, by requesting the Page filtered by the parameters of the source application.

<figure><img src="../../../.gitbook/assets/image (958).png" alt=""><figcaption></figcaption></figure>

You can display the links:

* To open DAC directly on a specific Page page,
* To open the Page only, to then be entered in an application; this method is embedded.

The operations are the following:

* Enables any command of the Action Bar of the mashboard
* From the Page, open the settings menu from the button and select **Share** (only visible to administrators)

![](<../../../.gitbook/assets/91 (3).png>)

* From _Share_ a pop-up opens with two links, shown in the figure.

![](<../../../.gitbook/assets/92 (4).png>)

the following is the syntax of the two URLs:

**https://**_**\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE ID**>_**embedView?token=\<token>\&tenant\_id**

\
**https://**_**\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE ID**>_**view?token=\<token>\&tenant\_id**

where:

_**\<HOST> -**_ Host name or IP of the Application Server

_**\<PORT>**_ _**-**_ port of the Application Server

_**\<CONTEXT**_> _**-**_ name of the Web Application DAC

_**\<OWNER>**_ _**-**_ ID of the application

<_**Page**_ ID

* **view** _**-**_&#x66;or direct opening
* **embed view** _**-**_&#x66;or embed opening

**\<Token>** it's pobbible to insert the user token (Optional). In this case the page is accessed with the user to whom the token belongs.

**\<tenant\_id> :** This is the id of tenant selected in the page. When the tenant id is passed in query string, the page opens and the specified tenant is automatically selected,assuming the user is associated to the tenant. If the tenant id is not referring to any existing tenant of DAC, an error message is displayed to the user stating that the specified tenant doesn’t exists and user’s last tenant is automatically selected. If the user is not associated to the passed tenant, an error message is displayed to the user stating that the he/she is not authorized to the tenant and user’s last tenant is automatically selected.

For access to the Page already authenticated, enter the part shown below in the previous link:

_http://\<HOST>:\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE\_ID>/_\[view or embedView]_?**csUsrn=\<USER ID>\&csPass=\<PASSWORD>\[\&crypted=1]**_

where:

* **csUsrn:** user id
* **csPass:**&#x70;assword of the user clear or encrypted
* **crypted:** if the value 1 is set the password is encrypted. If you do not want to enter an encrypted password, the variable is not entered in the link.

The encrypted password for a specific user can be retrieved by the system administrator inside the SUBJECT table of the db. In this case the _CsPass_ variable will have the encrypted password associated

In the case where you want to enter the preselected parameters add the following syntax to the link:

_http://\<HOST>:\<PORT>/\<CONTEXT>/ content/Page/\<OWNER>\_\<PAGE ID>/_\[view or embedView]_?_ _**pNames=\<PARAMETER>\&pValues=\<VALUES>**_

where:

* _**\<PARAMETER>**_ is the list of the parameters

The parameters are listed separately from %23\_%23\_%23, so _n_ parameters have the following syntax:

_Param&#x31;**%23\_%23\_%23**Param&#x32;**%23\_%23\_%23**…Paramn_

* _**\<VALUE>**_ the corresponding values to be assigned to the parameters. The values of each parameter are always separated by the same separator _**%23\_%23\_%23**_.

So if _Param1_ has the value _Val1, Param2_ has the value _Val2, Paramn_ has the value _Valn_ the correct syntax is the following:

_Val&#x31;**%23\_%23\_%23**Val&#x32;**%23\_%23\_%23**…Valn_

In case one or more parameters must be assigned more values, the separator between the multivalue is _**%23%23%23%23%23**_

So if _Param1_ assumes three values _Val11, Val12 and Val13_ the syntax becomes:

_Val1&#x31;**%23%23%23%23%23**Val1&#x32;**%23%23%23%23%23**Val1&#x33;**%23\_%23\_%23**Val&#x32;**%23\_%23\_%23**…Valn_

&#x20;**Note:** _for operation on browsers IE8/IE10, often cleaning the cache is not sufficient to correctly use the direct access links, rather you must perform the following operations:_

1. _enable the “Always update from server” option, which is in “Development tools (F12)” -> Cache;_
2. _system “logout”;_
3. _access the system with one of the direct access links;_
4. _system “logout”;_
5. _disable the “Always update the server” option;_
6. _access with one of the direct access links._

Example of a Link to a Page

Step 1: Page link

![](<../../../.gitbook/assets/93 (4).png>)

_Access a dashboard page in debug mode. Select the parameters, for example the following were selected:_

* _Area -> CENTER_
* _Region -> Lazio_
* _Business Unit -> Business Unit 01._

_Reload the page (click on the Sales Analysis tab). The parameters set are displayed in the debug window, page parameter value section._

**Step 2: Page link**

_From the Action Bar select the button shown in the figure and choose the Share menu item._

_A window opens with two links_

* _Direct Link to the Page. Provides direct access to the Page page. Authentication is automatic and any page parameters are set automatically._
* _Direct link to DAC. To access DAC, placing it directly on the Page. The authentication mode is automatic._
* _The link with the passage of the parameters is as follows:_

_http://192.168.2.102:8080/Decisyon450MANUAL/content/Page/RTQDANB\_216381316292328/view?pNames=AREA\&pValues=2\&pNames=Region\&pValues=714\&pNames=Business\_Unit\&pValues=0_

_Note that in pName and pValue, the parameters exported from Page found in the debug window have been entered_





