# Using API to create a new user group

## Introduction

In this example we explore how to use DAC API to create a new User group using the DAC [Rest API Client](../../rest-api-client.md) to execute the API. In this example, the DAC API is executed internally within the DAC, rather than by an external application.

This is the API used in this example, is available in the group "Group" , Version 2 of Swagger documentation.

`/api/v2/rest/application/{application}/group`

<figure><img src="../../../../.gitbook/assets/image (209).png" alt=""><figcaption></figcaption></figure>

## Prerequisites

To execute the API, it's necessary to know the Application ID (OWNER) for the application where you are creating the user group.

{% hint style="success" %}
You can retrieve **application ID** (**owner**) information from the metadataInfo property of any object in DAC .

![](<../../../../.gitbook/assets/image (210).png>)
{% endhint %}



## **Step 1. Configure the Rest APi Client**

{% tabs %}
{% tab title="Header" %}
<figure><img src="../../../../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

Create a new API, use the POST method and insert the URL of the API.

In the Header of the API specify the:

* **Authorization**: In the value insert the[ built-in variables](https://documentation.decisyon.com/documentation/sdk-and-api/rest-api-client#how-to-use-authorization-tokens) `%DAC_ACCESS_TOKEN%`. This variable enables dynamic token assignment, removing the need to hard-code a static Bearer token within the REST API Client configuration. It ensures that API requests utilize the access token granted to the current user.
* **content-type:** is `application/json`.
* **accept :** is `application/json`.
{% endtab %}

{% tab title="Body" %}
<figure><img src="../../../../.gitbook/assets/image (213).png" alt=""><figcaption></figcaption></figure>

As specified in Swagger, it's important to note that this API requires a body in the request.

```json
{
  "id": 123456789,    
  "application": "<owner>",
  "name": "API_GROUP",
  "folder": -1,
  "attr_1": "1",
  "attr_2": "2",
  "attr_3": "3",
  "attr_4": "4",
  "attr_5": "5"
}

```

* **ID**: Set a unique ID to identify the group.
* **Application**: Enter the identifying code of the application (owner) where the group will be created.
* **Name**: Provide a name for the group being created.
* **Folder**: Input the code identifying the location where the group will be created. In this case, the folder with code -1 corresponds to the root.
* **Attr\_1 to Attr\_5**: Specify any values to associate with the group's attributes. In this example, default values proposed by Swagger have been retained.
{% endtab %}

{% tab title="Send API" %}
<figure><img src="../../../../.gitbook/assets/image (2012).png" alt=""><figcaption></figcaption></figure>

After sending the API request, the response of the call appears in the headers. If the status is 200, it indicates that the request was successful.
{% endtab %}
{% endtabs %}

## **Step 2. Verify the new group**

Now we can access the Group Administration section to see the new group created by the API.

<figure><img src="../../../../.gitbook/assets/image (2014).png" alt=""><figcaption></figcaption></figure>

In the figure above, we can observe the new group named "API\_GROUP." We can see the group's name, the unique identifier code of the application where the group was created, and the  attributes have also been populated.&#x20;
