# Rest API Client



The REST API Client is a versatile and robust feature within DAC that enables application developers to configure and execute RESTful requests to external services with ease. It serves as a bridge, allowing the applications to interact with external web services, access data, and perform actions beyond the boundaries of DAC instance. This opens up a world of possibilities for data retrieval, data synchronization, automation, integration with a digital ecosystem and more.

Any endpoint configured in a REST API Client must be whitelisted to prevent a `403 - Forbidden` error message. Endpoints that were propely working with DAC 2023.1.x, could now return this error unless they are whitelisted.

{% hint style="warning" %}
&#x20;When migrating to version 2023.2.0, it is necessary to define a white list with all external URLs that can be invoked by the REST API Client. Please see the[ Migration Notes](../../release-notes-documentation/untitled/version-2023.2.0/migration-notes.md#rest-api-client-url-whitelist)
{% endhint %}

In this chapter you'll learn how to configure REST requests, handle responses, and leverage this feature for several use cases.

The REST API Client uses the HTTP protocol to send and retrieve data in JSON format.

{% hint style="info" %}
Please note that only response body in JSON format are supported.
{% endhint %}

The common HTTP methods configurable in the REST API Client are

* GET
* POST
* PUT
* DELETE
* PATCH

An existing REST API Client can be used by other DAC objects, such as:

* [​Execute Button](https://widgethubdocumentation.gitbook.io/button)
* [Snippet](code-snipped-editor/)
* [Custom Widget and Data Connector](../widgets/widget-editor/)​
* [​Alert](/broken/pages/-MfHi5Aiv9yiVk-UbNA1)
* [Action List](../app-functionality/action-list/)

It’s possible to use App Composer [Environment Variables](../introduction/application/appcomposer/general-info.md#app-composer-environment-variable) in the REST client.

{% hint style="success" %}
Requests have a timeout that can be configured by changing the property `appcomposer.http.client.connection-timeout` in the POD. Can also set the maximum time allowed to receive a response after the connection has been successfully established by the `property appcomposer.http.client.read-timeout`

For more details see the[ installation guide](https://dac-documentation-1.gitbook.io/installation-guides/v/v.2023.2.2/)
{% endhint %}

Rest API Clients are available at **Main Menu -->Administration --> Rest API Client**

<figure><img src="../../.gitbook/assets/image (454).png" alt=""><figcaption></figcaption></figure>

### Creating a new REST Client

To create a New API click the button **New**.

<figure><img src="../../.gitbook/assets/image (455).png" alt=""><figcaption></figcaption></figure>

During the creation of a New endpoint define:

* **Name** : Name of the API
* **Alias** : The alias assigned to the REST Client uniquely identify it in the App Compose instance. For example, the alias can be used in the [Execution Button](https://widgets.decisyon.com/button-1/v/execute-button-1/execute-button/execution-type/rest-api) widget where the execution type is "REST Client".&#x20;
* **Description**: It allows to include a clear and detailed explanation of what the client does, how it works and what its purpose is. This can help developers understand the functionality and utility of the client, allowing them to use it effectively.
* **Folder**: Select a destination catalog folder where to save the client. When the folder is not selected, the REST Client is saved in the root.

### Configuring Rest API Client

<figure><img src="../../.gitbook/assets/image (456).png" alt=""><figcaption></figcaption></figure>

During the client configuration phase, you need to set:

* **The Endpoint**: the URL of the resource made available to the endpoint.
* **The HTTP Method**: the HTTP method used in the request. The supported methods are `GET`, `DELETE`, `POST`, `PUT`.
* **The Headers**: this section defines the headers that will be included in the request, such as `Authorization` header
* **Body**: the body of the request, usually in JSON format.
* **Test Parameters**: It's possible to define parameters in each component of the request (endpoint, headers and body). If the client contains parameters, you can define here the values to be used when testing the client.
* **Send**: click this button to execute the request.

{% hint style="success" %}
If you want to know how to configure test params see the [Example 2 ](code-snipped-editor/examples/example-2.md)
{% endhint %}

* **Response**: shows the response of the request (only after you clicked on the "**Send**" button). At the top right is the status code and the response time. In Body and Header the result and detailed information of the request.

<figure><img src="../../.gitbook/assets/image (457).png" alt=""><figcaption></figcaption></figure>

### How to use Authorization Tokens

When configuring the header of the request, App Composer allow us to use built-in variables in the request:



| Variable Name            | Content                                                                                                                                      | Example                                                                                                                                                            |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **%ACCESS\_TOKEN%**      | It contains the value of the access token issued by the OIDC server configured in the App Composer instance and assigned to the logged user. | It can be used when the Access Token issues by the identity provider must be used to execute request to external API that could be authorized with the same token. |
| **%ID\_TOKEN%**          | It contains the value of the ID token issued by the OIDC server configured in the App Composer instance and assigned to the logged user.     | It can be used when the Access Token issues by the identity provider must be used to execute request to external API that could be authorized with the same token. |
| **%DAC\_ACCESS\_TOKEN%** | It contains the value of the internal access token issued by App Composer.                                                                   | It can be used to execute request to App Composer API.                                                                                                             |

When creating the API, the **Authorization** header will suggest to use either the **%DAC\_ACCESS\_TOKEN%** or **%ACCESS\_TOKEN%** variable.

<figure><img src="../../.gitbook/assets/image (458).png" alt=""><figcaption></figcaption></figure>

The keyword "Bearer" is used to specify the type of token that is sent by the DAC to the HTTP request. The term "Bearer" indicates that the token is an access token, that is a token that grants access to protected resources.

### How to consume the value defined in an Environment Variable

[Environment variables](https://documentation.decisyon.com/documentation/introduction/application/overview-of-ui/general-info#app-composer-environment-variable) can also be used the configuring the client. These variables, when used within the URL, are defined within double curly brackets.

`https://{{DAC_ENV_URL}}/application/<application_owner>/page/<page_id>/event/<event_name>`

<figure><img src="../../.gitbook/assets/image (459).png" alt=""><figcaption></figcaption></figure>

In this example we have three environments: Development, Test, and Production and want to migrate the application between these various environments. In this scenario, you can use environment variables to make URLs of API calls dynamic accordingly to the environment.

<figure><img src="../../.gitbook/assets/image (460).png" alt=""><figcaption></figcaption></figure>

Let’s see the example above:

* Environment variables are defined for each environment (DEV, TEST and PROD).
* The environment variables will all have the same name, in the example `DAC_ENV_URL`.
* Each environment variable will be set with the URL value of each environment in which it was created.
* The REST API Client will not change depending on the environment, but by using the environment variable `{{DAC_ENV_URL}}` the request will be executed with the value assigned in each environment to the variable `DAC_ENV_URL`.





### **Example - Execute request passing parameters from a page**

When you want to execute a REST Client passing parameters from a page within DAC, the client must be configured as follow:

`https://postman-echo.com/get?Plant={{Plant_Name}}`

The “`Plant_Name`” (defined with curly brackets) is the parameter of the request and the value can be dynamically assigned to a page parameter, in example when the user input the value in a “text field” widget.

**Step 1. Create the API**

In this example we will create an API where the value of the Plant is passed through a parameter from a Page of the DAC.

<figure><img src="../../.gitbook/assets/image (461).png" alt=""><figcaption></figcaption></figure>

We create the REST API Client that will have the following endpoint

`https://postman-echo.com/get?Plant={{Plant_Name}}`

{% hint style="danger" %}
The `param_name` will be identical to the `param base name` of the widget where the value is entered.
{% endhint %}

To execute an API test, in the Test Parameters tab add the Platn\_Name parameter in the Key column and associate a value (for example Latina) .

<figure><img src="../../.gitbook/assets/image (1892).png" alt=""><figcaption></figcaption></figure>

The response to the call API will be as follows:



<figure><img src="../../.gitbook/assets/image (462).png" alt=""><figcaption></figcaption></figure>

**Step 2 . Page Designer**

The image below shows the page structure with the widgets needed to execute the REST Client.

<figure><img src="../../.gitbook/assets/image (463).png" alt=""><figcaption></figcaption></figure>

For the Textfield widget that has the **base param name** is qual to the **Param\_Name** passed in the API.

The main properties to configure for the Execute Button widget are:

* `Execution-type`: REST\_API
  * `api-alias`: select the Client created in step 1
* `api-params-mapping:` defines the mapping between the parameter used by the REST API Client with the parameters available in the page. In this case, the parameter defined in the Textfield widget.

**Step 3: View the Page in DAC**

<figure><img src="../../.gitbook/assets/image (464).png" alt=""><figcaption></figcaption></figure>

Once the user open the page, input the value in the "Plant" text field and then click the "Execute" button: the request is executed using the value input by the user.

{% hint style="info" %}
For a more detailed example see also [**How consume the response of a POST request in a DAC page**](https://documentation.decisyon.com/documentation/page-designer/advanced-configuration/how-consume-the-response-of-a-post-request-in-a-dac-page)
{% endhint %}
