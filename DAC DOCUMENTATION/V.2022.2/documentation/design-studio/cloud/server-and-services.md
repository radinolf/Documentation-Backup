# Server & Services (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

To create or modify a configuration of service or server , select the Servers & Services item from the Cloud menu.

In the Servers & Services window you can create:

* [New Open Connect](server-and-services.md#Open-Connect-Server-definition)
* [New Configuration server](server-and-services.md#New-Configuration-Server)

### Open Connect Server definition <a href="#open-connect-server-definition" id="open-connect-server-definition"></a>

The OpenID authentication protocol allows users to authenticate to the DAC by reusing existing accounts. In this way, it will be possible to avoid that each user needs to register an account within the DAC.

When the container starts and no authentication service is configure in Design Studio, App Composer will automatically create a new authentication service leveraging the ENV variables of the container. Keycloak, Azure Active Directory or Schneider IDMS. If the instance have one or more auth service but none of them is flagged as “defaul”, the authentication service is automatically created and flagged as default. The user administrator must insert manually, the admin user ID claim value. Finally, when the service is created, all the configuration parameters are the same as those configured in the web application.

If the property Tool>>Preference>>Web>>automatic-user-creation is enabled, the first user that logs in the web application after the login will be marked as ‘administrator’.

![](<../../../.gitbook/assets/image (586).png>)

If the property Tool>>Preference>>Web>>automatic-user-creation is enabled, the first user that logs in the web application after the login will be marked as ‘administrator’.

To configure a New Open Connect Server select the same item from the menu, that opens, selecting the root of the Server Services list.![](blob:https://decisyon.atlassian.net/04b76d7f-cc74-44e8-9706-1ca3546f6cdf#media-blob-url=true\&id=0874131c-994f-4032-97c5-12b208f0e691\&collection=contentId-2295562241\&contextId=2295562241\&mimeType=image%2Fpng\&name=image-20210908-070242.png\&size=34698\&width=629\&height=337\&alt=)

![](<../../../.gitbook/assets/image (136).png>)

#### **Authentication** <a href="#authentication" id="authentication"></a>

![](<../../../.gitbook/assets/image (488).png>)

* **Type**
  * **OpenId Connect:** select the system of authentication type between those in the list.
* **Authentication on Design Studio:** Define the type of authentication in Design Studio
  * **Use as default:** if you want to log into Design Studio via Open Connect and make this authentication type the default then select this option.
  * **Port:** insert the TCP port number.
* **Authentication on DAC:** Define the type of authentication in DAC
  * **Admin User id Claim value:** Enter the ID of the user who will be appointed administrator at the first login.\
    The user IDs are registered within the Openconnect server that has been selected in the Open Id Connect property)
  * **Detailes:** Insert any detailed comments.

**Configuration**&#x20;

In the Configuration tab you can configure the URLs provided by the open contct ID that the chosen authentication system must expose are configured. This information can be found within the Open ID Connect chosen in the Authentication tab.![](blob:https://decisyon.atlassian.net/3ceb026e-ef0c-470d-ae68-33ae595bd9b5#media-blob-url=true\&id=ce664eb1-9c2d-452b-9f75-c65562457f23\&collection=contentId-2295562241\&contextId=2295562241\&mimeType=image%2Fpng\&name=image-20210908-091559.png\&size=44075\&width=626\&height=494\&alt=)

![](<../../../.gitbook/assets/image (744).png>)

**Deployment**

In the Deployment tab you can select if the service is deployed or no&#x74;**.**

![](<../../../.gitbook/assets/image (40).png>)

### New Configuration Server <a href="#new-configuration-server" id="new-configuration-server"></a>

If you want configure a Server select New Configuration serve form the menu that opens selecting the root of the Server Services list.![](blob:https://decisyon.atlassian.net/88e798f6-6616-4b0f-af29-dc23e870b658#media-blob-url=true\&id=8df9e311-e2b0-4595-9fe9-72219be4eb1a\&collection=contentId-2295562241\&contextId=2295562241\&mimeType=image%2Fpng\&name=image-20210910-065350.png\&size=15984\&width=503\&height=190\&alt=)

![](<../../../.gitbook/assets/image (112).png>)

**Configuration**:

**Security**:

In **Username** and **Password fields,** you can Insert the credential to access on the server.

**Endpoint**: Specify the Endpoint.

**Deployed**:

In the Deployment tab you can select if the service is deployed or not.
