# Authentication

## Introduction

APIs play a crucial role in the integration and communication between different systems. To ensure security and controlled access to resources, DAC offers the possibility to generate and use both API Keys and Tokens.

## Authentication with Tokens and API Keys <a href="#generate-token" id="generate-token"></a>

The [**Token**](authentication.md#personal-access-tokens) generated in DAC is a security token created and used during an authentication process. It can contain information about the user, permissions (scopes), and the validity period. It provides a more secure and dynamic form of authentication, can be short-term, and can be revoked or regenerated. API Tokens are primarily used for access to private and secure APIs.

&#x20;They are essential in situations where security and data protection are critical. They are employed in applications that require detailed control of permissions and sessions, ensuring that only authorized users or devices can access the services.&#x20;

Additionally, API Tokens are essential for services that require user or device-based authentication, using protocols like OAuth and JWT.

An[ **API Key**](authentication.md#api-keys) is a unique identifier, to identify the client making the request. It is a static string of alphanumeric characters.

These keys allow access to services without the need to provide user credentials like username and password.

It provides a simple and static form of authenticati on since it generally does not change unless manually regenerated.

It is primarily used to track and control the API usage by clients. It can also limit access based on the client's service level.

### **Personal Access Token**

The App Composer API uses personal access tokens to authenticate requests.

API requests are authenticated using the [Bearer Auth](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#authentication_schemes) scheme. To authenticate a request, provide the token in the Authorization header of the request:

```http
GET /api/rest/instance/version HTTP/1.1
Host: <your_hostname>
accept: application/json
Authorization: Bearer <your_token>
```

Access tokens are tied to the App Composer user account for which they were created. A token provides the same level of access & privileges that its associated user account would have.

{% hint style="warning" %}
Please be sure to keep your API access tokens secure! Do not share them in emails, chat messages, client-side code or publicly accessible sites.
{% endhint %}

The token can be used in the following use cases:

* to invoke the [App Composer REST API](https://documentation.decisyon.com/documentation/sdk-and-api/app-composer-api)
* to deploy or delete an application in a target environment during an [application synchronization](https://documentation.decisyon.com/documentation/application-synchronization-wip)
* t[o view or embed App Composer pages](https://documentation.decisyon.com/documentation/page-designer/advanced-configuration/accessing-page-from-external-systems), passing the token in query string to prevent the login screen to show up.

See how to generate a [**personal Access Token**](authentication.md#generate-token-1)

### **API Keys**

In addition to personal access tokens, App Composer also supports the use of API Keys to authenticate requests. API requests are authenticated using the Bearer Auth scheme. To authenticate a request, provide the token in the Authorization header of the request:

```http
GET /api/rest/instance/version HTTP/1.1
Host: <your_hostname>
accept: application/json
Authorization: Bearer <your_api_key>
```

API Keys are not tied to the App Composer user account but are system tokens. API keys are linked to the specific client for which they were created and can be used to monitor and control API usage. They provide a simple and static authentication method, ideal for applications with limited or controlled access.

{% hint style="danger" %}
Please be sure to keep your API Keys secure! Do not share them in emails, chat messages, client-side code, or publicly accessible sites.
{% endhint %}

The API Token can be used in the following use cases:

* **Production Data Monitoring:** An API Key can be used to authenticate and authorize automatic requests between the production management system and the machine monitoring system. This allows for monitoring production data, such as production without the need for manual login by operators.
* **Report Generation:** An API Key can be used to automate the generation and sending of weekly sales reports, without user intervention.

See how to generate an[ **API KEY**](authentication.md#generate-the-api-key)

## Generate Token <a href="#generate-token" id="generate-token"></a>

The generated token provides the necessary authentication token to perform actions on the DAC APIs, with allowed actions defined by the request scopes.&#x20;

To generate a new token, users can open their user profile settings.&#x20;

By default, the token does not have an expiration date, but it can be configured to have a limited duration. All users, including administrators and business users, have the ability to generate a personal access token. Users can manage token lifespans and permissions based on their specific needs and security requirements.

<figure><img src="https://documentation.decisyon.com/~gitbook/image?url=https:%2F%2Fcontent.gitbook.com%2Fcontent%2FyAjw1iF7BRk9VYaJYNdQ%2Fblobs%2FmnyhA326KlInJGo4lGfZ%2Fimage.png&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6c3aa474ebc7e8dc557b650f176a74f46f369a74e5cb47de7a66c5cdeaff0030" alt=""><figcaption></figcaption></figure>

By default, tokens are created with no expiration. However, if an expiration date is specified upon creation, any API requests made after this date will result in an `HTTP 401 “Unauthorized”` error.

In the Scopes, you can select the the scope of the token:

* If you select **Login into the DAC,** you can generate a token that authorizes the access to App Composer user interface. This scope must be selected, for example, to access pages via external links, to embed a DAC page in another application or to deploy or delete an application.
* If you select "**Manage token**" you can generate a token that can be used to verify the validity of other tokens. For example, provided a Token you can invoke the Rest API `.../api/v2/rest/check_token` which allows you to determine if the token is active and to whom it belongs to.

<figure><img src="https://documentation.decisyon.com/~gitbook/image?url=https:%2F%2Fcontent.gitbook.com%2Fcontent%2FyAjw1iF7BRk9VYaJYNdQ%2Fblobs%2FUlrbRpqxc6ZqQVrwT58G%2Fimage.png&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6ecc7ab8cc8a30c5109a3f75d50f915d0a06134e97b6e223b40d91972e615e37" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
**Use cases**

In DAC applications, it happens that both basic user tokens and administrator tokens are used.

Business user tokens are used for example, when a specific laptop/thin client/device starts up automatically and needs to open DAC in a browser without asking the authentication via the login page.

Administrator tokens are used for internal application communications. For example, an administrator token is used because it has the ability to make APIs request to DAC, such as refreshing a page when an event happens outside the App Composer.
{% endhint %}

### Using token in a Rest API <a href="#how-to-use-token-in-the-rest-api" id="how-to-use-token-in-the-rest-api"></a>

To invoke a **DAC REST API**, a bearer token is required to authorize the request. The token to be use is generated from the user profile page.

`Authorization: Bearer <DAC Token>`

In the following example, the App Composer [REST API Client](https://documentation.decisyon.com/documentation/sdk-and-api/rest-api-client) is used to execute a request to an API exposed by DAC. The token to authenticate a request to App Composer API must be generated from the user profile page.

{% hint style="info" %}
When you need to consume App Composer API from within the DAC Instance, it's possible to use the variable `%DAC_ACCESS_TOKEN%` that contains the value of the token issued to the user at login.

For further details see [How to use authorization tokens](https://documentation.decisyon.com/documentation/sdk-and-api/rest-api-client#how-to-use-authorization-tokens)
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (216).png" alt=""><figcaption></figcaption></figure>

### Using token to deploy or delete an application <a href="#how-to-use-the-token-to-deploy-or-delete-an-application-in-a-target-environment" id="how-to-use-the-token-to-deploy-or-delete-an-application-in-a-target-environment"></a>

<figure><img src="https://documentation.decisyon.com/~gitbook/image?url=https:%2F%2Fcontent.gitbook.com%2Fcontent%2FyAjw1iF7BRk9VYaJYNdQ%2Fblobs%2FmRAUAV1maf03SYwq9hYX%2Fimage.png&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6a8252e26dc6a515e0d1606f869dd58f73a9f46059aa71a26699ae367e07fb50" alt=""><figcaption></figcaption></figure>

The token is also used when deploying the application in a target environment: in the source environment you need to set a token from an administrator user of the target environment. In this case, the token doesn’t require any specific scope.

{% hint style="info" %}
You can also see the document: [Synchronization](https://documentation.decisyon.com/documentation/application-synchronization-wip)
{% endhint %}

#### **Using token to view or embed pages** <a href="#view-or-embed-pages" id="view-or-embed-pages"></a>

It's possible to open an App Composer page or embed it in another application without insert the user credential adding in the query string of the URL the token: “`?token=<DAC Token>`” .

{% hint style="warning" %}
Token used for this purpose must have been generated with the "_Login into DAC_" scope.
{% endhint %}

After the token is generated, you can include it in the URL:

`https://<application URL>/content/Page/<OWNER>_<PAGE ID>/[view or embedView]?token=<token`

{% hint style="info" %}
You can also see the example:[ How to get the link to embed the page ](https://documentation.decisyon.com/documentation/page-designer/advanced-configuration/embed-a-dac-page-in-a-third-party-application#2.-how-to-get-the-link-to-embed-the-page)>>[ 2.How to generate a user token](https://documentation.decisyon.com/documentation/page-designer/advanced-configuration/embed-a-dac-page-in-a-third-party-application#2.how-to-generate-a-user-token).
{% endhint %}

## Generate the API Key

To generate an API Key, you need to access [Cockpit](../../introduction/application/cockpit/), the microservice responsible for managing and monitoring applications. To gain access to Cockpit, it is essential to be included in the whitelist of authorized users.

Once you have access to Cockpit, you can proceed with generating the API Key by selecting the "**API Key**" button from the toolbar.

<figure><img src="../../../.gitbook/assets/image (2179).png" alt=""><figcaption></figcaption></figure>

Select **Generate API Key** and configure this propreties

* **Description:** Enter a description for the token (mandatory).
* **Expiration Date**: It is possible to define an expiration date for the API Key (optional).

The **Generate** button generates the API key.

<figure><img src="../../../.gitbook/assets/image (2181).png" alt=""><figcaption></figcaption></figure>

After selecting the Cancel button, the window closes and the new API Key is saved in the system.

<figure><img src="../../../.gitbook/assets/image (2183).png" alt=""><figcaption></figcaption></figure>

### Using API Key in a Rest API

Let’s assume we want to create an API key, which will be used as an authorization token within an API that generates a DAC report. This example outlines the steps required to generate and use the API key to access a specific feature.

The API used in this example is as follows:

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

**Step 1 - Generate API Key**\
Access on Cockpit webapp and generate an API key.

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

Select **Generate API Key** and configure this propreties

* **Description:** Enter a description for the token (mandatory).
* **Expiration Date**: It is possible to define an expiration date for the API Key (optional).

**Step 2- Access on Swagger**

Access Swagger to test the API using the API Key as an authorization token. This way, you can obtain the information needed to execute the API from any client.

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

1. Enter the API Key as an authorization token to test the API.
2. Define the parameters required by the API
3. Execute the API

**Step 3 - APi Response**

<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

1. The GET request is sent to the specified URL. The header provides information for setting up the request headers:
   1. `accept: application/json` tells the server that the client wants the response in JSON format.
   2. `Authorization: Bearer YOUR_API_KEY` includes the access API key required to authorize the request.
2. `Request URL`: use this URL to execute this API from any other client.
3. The response of the call is in JSON format.

Now Run the API from Postman or other client

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

Configure the API with the headers as shown in the Swagger documentation. Enter the API Key as the Authorization Token and remember to include "Bearer" before the API Key (e.g., `Bearer YOUR_API_KEY`). Execute the API and view the result of the call.

<figure><img src="../../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>
