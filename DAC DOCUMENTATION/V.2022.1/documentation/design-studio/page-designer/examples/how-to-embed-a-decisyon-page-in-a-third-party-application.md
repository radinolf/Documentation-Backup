# How to embed a Decisyon page in a third party application

In this example we can learn how to embed a Decisyon page in a third party application and how to pass the authorization token within the link.

Using the authorization token in the page link allows you to view pages via external link without inserting the user credentials.

### **1. How to configure DAC to allow embedding**  <a href="#id-1.-how-to-configure-dac-to-allow-embedding" id="id-1.-how-to-configure-dac-to-allow-embedding"></a>

To include a page of a DAC in an iframe it is necessary to configure the [Content Security Policy](https://content-security-policy.com/) of both DAC and the web application you want to use to include the pages of DAC.

For what concerns your web application, the configuration to the CSP depends on its nature and you must refer to the appropriate documentation to get information on how to set it.

Anyway, what you need to set up is the “_defaul-src_” directive including in its definition the url of the DAC instance you want to get the pages from, for example:

_default-src: 'self' https://\<dac-url>:\* ;_

To include a pages from DAC, you need to configure the CSP’s “_frame-ancestors”_ directive, adding the url of the including web application in the DAC’s CSP specification. This can be done setting a environment variable while installing the DAC itself:

* appcomposer.security.csp.frame-ancestors: "'self' https://\<your-web-app>:\* ;"\
  <br>

**This configuration works under https only: using http it will never work due to security constraints applied by browsers.**

### **2.How to get the link to embed the page** <a href="#id-2.-how-to-get-the-link-to-embed-the-page" id="id-2.-how-to-get-the-link-to-embed-the-page"></a>

Access the page that we want to embed and enable any command of the Action Bar of the Page.

From the Page, open the settings menu from the button and select **Share** (only visible to administrators)

From _Share,_ a pop-up opens with two links, as shown in the figure, and select the Link for embedding page into other content.

The default action bar is not active. to activate it select the Action Bar group, relating to the pag&#x65;**.**

![](<../../../../.gitbook/assets/image (318).png>)

The following is the syntax of the two URLs:

&#x200C;_**http://\<HOST>:\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE ID**>/_**\[view** or **embedView]**

**Example**:

http://44.192.83.92:8080/content/page/3FDT7TT\_968528107142161/embedView

For more details please see the _Page Designer >> Accessing page from External System_

### **2.How to generate a user token** <a href="#id-2.how-to-generate-a-user-token" id="id-2.how-to-generate-a-user-token"></a>

To access a page without requiring a user access, an authorization token must be generated.

Access on the User Profile and generate the token from the appropriate button.

![](<../../../../.gitbook/assets/image (36).png>)

e.g. This is the Token _**KFIOLAKUIEZDOX5THVUY**_

For more details See the documentation _**Administratin**>>_[_**User Profile & Change Password**_](../../../run-time/administration/)

### **3. How to add the authentication token to the link** <a href="#id-3.-how-to-add-the-authentication-token-to-the-link" id="id-3.-how-to-add-the-authentication-token-to-the-link"></a>

Now we can add the authentication token into the URL link

This is the syntax:

> _**http://\<HOST>:\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE ID**>/_**\[view** or **embedView]?token=\<token>**

&#x20;

_**Example:**_

[http://Decisyon/content/page/3FDT7TT\_968528107142161/embedView](http://44.192.83.92:8080/content/page/3FDT7TT_968528107142161/embedView)**?token=**_**KFIOLAKUIEZDOX5THVUY**_

### **4.How to use the link in a iFrame**  <a href="#id-4.how-to-use-the-link-in-a-iframe" id="id-4.how-to-use-the-link-in-a-iframe"></a>

Now you can use the link into the html pag

```
<!doctype html>
<html lang="it">
<head><title>How to use the link in iFrame</title></head>
<body>
<iframe src="https://xx.xx.xx.xxx:8080/content/page/3FDT7TT_968528107142161/embedView?token=KFIOLAKUIEZDOX5THVUY" width="1024" height="768">
</iframe>
</body>
</html>
```

&#x20;This is the result.

![](<../../../../.gitbook/assets/image (243).png>)

### How to pass parameters in the link that will be used in the page <a href="#id-5.-how-to-pass-parameters-in-the-link-that-will-be-used-in-the-page" id="id-5.-how-to-pass-parameters-in-the-link-that-will-be-used-in-the-page"></a>

In the case you want to enter the pre-selected parameters you have to add the following syntax to the link:

This is the syntax:

> _http://\<HOST>:\<PORT>/\<CONTEXT>/ content/Page/\<OWNER>\_\<PAGE ID>/_\[view or embedView]_?_ _**pNames=\<PARAMETER>\&pValues=\<VALUES>**&#x74;oken=\<token>_

_**Example:**_

In this example in the URL passed the authorization token and

_**http://decisyon/content/page/3FDT7TT\_968528107142161/embedView?pNames=\<Plant>\&pValues=<001>token=\<KFIOLAKUIEZDOX5THVUY>**_

In this example the URL are passed multiple value for one parameter

http://decisyon/content/page/HTTED1G\_305623317026461/embedView?pNames=Plant\&pValues=202101%23%23%23%23%23002%23%23%23%23%23003token=KFIOLAKUIEZDOX5THVUY



{% hint style="info" %}
**Parameters** and **groups of values** are separated with %23\_%23\_%23&#x20;

The **values** are separated with %23%23%23%23%23
{% endhint %}

For more detail to use the paramiters in the consult the manual [Page Designer](/broken/pages/-MhIPCzeRKVk_czjJXrf)

### Some examples -How to pass parameters by external link or embed link<br>

**1 Parameter 1 Value**&#x20;

_Example:_

https://decisyon/content/page/HTTED1G\_149651824588xxx/view?**pNames=PAR1**&**pValues**=111

![](<../../../../.gitbook/assets/image (224).png>)

**1 Parameter 2 Values**

The **values** are separated with %23%23%23%23%23

_Example:_

https://decisyon/content/page/HTTED1G\_149651824588XXX/view?**pNames=PAR1**&**pValues**=11&#x31;**%23%23%23%23%23**222

![](<../../../../.gitbook/assets/image (228).png>)

**2 Parameters 1 value**

**Parameters** and **groups of values** are separated with %23\_%23\_%23&#x20;

_Example:_

https://decisyon/content/page/HTTED1G\_149651824588456/view?**pNames=PAR1%23\_%23\_%23PAR2\&pValues**=11&#x31;_%23\_%23\_%2&#x33;_&#x32;22

![](<../../../../.gitbook/assets/image (3).png>)

**2 Parameters 2 Values**&#x20;

The **Parameters** and **groups of values** are separated with %23\_%23\_%23 and the **values** are separated with %23%23%23%23%23

Example:

https://decisyon/content/page/HTTED1G\_149651824588XXX/view?**pNames**=**PAR1%23\_%23\_%23PAR2**&**pValues**=11&#x31;**%23%23%23%23%23**22&#x32;**%23\_%23\_%23**22&#x32;**%23%23%23%23%23**333

![](<../../../../.gitbook/assets/image (9).png>)

**2 Parameters 2 Value + Tenant**&#x20;

https://decisyon/content/page/HTTED1G\_149651824588XXX/view?**pNames**=_**PAR1**_**%23\_%23\_%23**_**PAR2**_&**pValues**=11&#x31;**%23%23%23%23%23**22&#x32;**%23\_%23\_%23**22&#x32;**%23%23%23%23%23**33&#x33;**\&tenant**=571615067201018

**EMBED**&#x20;

**1 Parameters 1 Value**&#x20;

https://decisyon/content/page/HTTED1G\_149651824588456/embedView?**pNames**=**PAR1**&**pValues**=111

![](<../../../../.gitbook/assets/image (22).png>)

**1 Parameters 2 Values**

&#x20;https://decisyon/content/page/HTTED1G\_149651824588456/embedView?**pNames**=**PAR1**&**pValues**=11&#x31;**%23%23%23%23%23**222

![](<../../../../.gitbook/assets/image (25).png>)

**2 Parameters 1 Values**&#x20;

https://decisyon/content/page/HTTED1G\_149651824588456/embedView?**pNames**=**PAR1**%23\_%23\_%23**PAR2**&**pValues**=11&#x31;**%23\_%23\_%23**222

![](<../../../../.gitbook/assets/image (17).png>)

**2 Parameters 2 Values**

&#x20;https://decisyon/content/page/HTTED1G\_149651824588xxx/embedView?**pNames**=**PAR1**%23\_%23\_%23**PAR2**&**pValues**=11&#x31;**%23%23%23%23%23**22&#x32;**%23\_%23\_%23**22&#x32;**%23%23%23%23%23**333

![](<../../../../.gitbook/assets/image (1).png>)

