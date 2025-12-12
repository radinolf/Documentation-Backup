---
description: >-
  Trough the Rest API Client you can configure a call by a third party endpoint
  to take advantage of the services within the DAC. It means that you can push
  data and features in any legacy technology.
---

# Rest API Client

Trough the Rest API Client you can configure a call by a third party endpoint to take advantage of the services within the DAC. It means that you can push data and features in any legacy technology.

The REST API, defined by the REST client, uses the HTTP protocol to send, retrieve data and responses in JSON format. You can use standard HTTP methods to view, update, or delete resources via the API.

During the API configuration phase, you can define:

* **The Endpoint**: the URL of the resource made available to the endpoint.
* **The HTTP Method**: tells the server what action the client wants to perform. The available methods are GET, DELETE, POST, PUT.
* **The Headers**: this section defines the additional information that will then be transmitted to the server and the client, for example the authorization. NOTE: All DAC APIs require the authorization token in the form Bearer .
* **Body**: the body of the request is defined, for the End Points that require it.
* **Test Parameters**: if the API contains parameters, you can define values to be used in the API test.
* **Response**: the result of the call is obtained. At the top right is the status code and the response time. In Body and Header the result and detailed information of the call

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/RestAPI/RestApi.png)

During the creation of an API, in addition to the name and a description, an Alias is assigned. This can be used within the DAC components that use the API to return or send data. For example, the alias can be used in the execution button widget where the execution type is an API. Another useful information is the object ID. The alias cannot be changed.

The DAC objects that exploit API calls to return or send data are:

* [Execute Button](https://widgets.decisyon.com/button-1/)&#x20;
* Program
* Custom Widget and [Data Connector](../widget-designer.md)
* [Alert](../alert.md)

You can access the documentation of the Api exposed by Decisyon by selecting the Online Help >> REST API Documentation item from the vertical Toolbar.

{% hint style="info" %}
You can use **Environment Eariables** in the API. To know which environment variables to use see  [App Composer Environment Variable](../settings/general-information.md)


{% endhint %}
