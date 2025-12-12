# REST/ JSON

## Introduction

In today's interconnected world, accessing and manipulating data through web services has become a  basic necessity of modern software development. One of the most common ways to interact with these web services is via RESTful endpoints, utilizing the simple but powerful JSON format for data exchange.&#x20;

App Composer allow app developers to define a data source for a REST service and is able to read response body in JSON format.&#x20;

Understanding how to properly configure and use a data source for a REST endpoint is crucial for developers and analysts alike, enabling them to efficiently work with web-based data in real-time.

In the following sections, we will explore how to retrieve data from a REST API using JSON. Specifically, we'll look at how to set up a data source configured for accessing a REST/JSON API, highlighting the necessary steps and considerations for effectively fetching and utilizing data from such services.

Below, we can see the summary interface image of a Data Source.

<figure><img src="../../../../.gitbook/assets/image (1848).png" alt=""><figcaption></figcaption></figure>

1. In **Data Source Connection Details**, it shows the **URL** of the endpoint where the API is available.
2. In the **table definition**, it displays a preview of the table defined in the data source configuration.
3. The **Test Configuration** button is used to test the data source connection after the configuration.
4.  The **Configure the  Data Source** button is used to access the interface where we can configure the data source parameters."

    <br>

## **Data Source Configuration**

Select “**Configure the Data Source**“ button to open the Data Source REST configuration panel.

<figure><img src="../../../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

### Define **Endpoint**

To define the **Endpoint s**elect the method GET or POST and insert the API's URL.&#x20;

{% hint style="info" %}
Please note that only endpoint with method GET or POST are supported in the data source.
{% endhint %}

It also be possible to use a **parameters** or environment variable as placeholder in the query endpoint. In case of parameters, you can later define the test value to be assigned to the parameter before the request is executed.

<figure><img src="../../../../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

### Define Request b**ody and request headers**

When using the POST method in an API request, it is possible to specify the request body. Please note that also in the request body it is possible to user parameter.

<figure><img src="../../../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

When defining HTTP headers, both the key and value must be specified. Use of parameters or environment variables within headers is highly recommended, especially for sensitive information like Bearer tokens, to avoid hard-coding them into your configuration. This approach ensures better security and flexibility in managing credentials.

<figure><img src="../../../../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>



To insert a new row select the button (+)

* **Key** defines the name of the header (e.g. **`Content-Type`**`: text/html)`
* **Value** defines the value of header (e.g. `Content-Type:`` `**`text/html`**)

To remove a row, select the row and click the button (X).

![](<../../../../.gitbook/assets/14 (2)>)

### Using parameters in the Data source

When configuring a REST data source, parameters can be defined within the request. These parameters allow for dynamic values to be passed to the data source when the request is executed. For instance, values for parameters can originate from widgets on a page, offering a highly flexible approach to crafting dynamic requests to the endpoint.

To ensure smooth execution, parameters must have default values defined before the request is executed. These default values are utilized during testing of the data source and in scenarios where a specific parameter value is not provided.

To set default values for parameters, click the "**Set variables' default values**" button and define default values for each parameter specified in the request configuration.

<figure><img src="../../../../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
For correct configuration, the parameter name should be enclosed in double braces

https://api.Plant.com/PlantName?Name=**\{{Plant\_Name\}}**&#x20;
{% endhint %}

### **Authentication**

App Composer offers support for three authentication methods in REST data sources:&#x20;

* no authentication
* basic authentication
* bearer token

With "no authentication," requests are made without any authentication credentials.&#x20;

"Basic authentication" requires the inclusion of a username and password:

<figure><img src="../../../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

&#x20;"Bearer token" involves the use of a token provided by an external identity provider and that can be used in the request header.&#x20;

When utilizing the REST Data Source to fetch data from an API provided by App Composer, leverage the `%DAC_ACCESS_TOKEN%` system parameter. This parameter encapsulates the current user's token, ensuring authentic requests without the need to hard-code the token value directly within the data source properties.

{% hint style="warning" %}
When utilizing this parameter, it's crucial to ensure the logged-in user has the adequate permissions to execute the request. If the user's scope is insufficient, an HTTP status code `403 - Unauthorized` may be returned, indicating authorization failure.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (134).png" alt=""><figcaption><p>In this screenshot, we see a code snippet from App Composer being used as an endpoint. Additionally, the Bearer token corresponds to the currently logged-in user.</p></figcaption></figure>

### Test Endpoint Invocation

To test that the endpoint has been configured correctly, click on the "Test Endpoint Invocation" button.

<figure><img src="../../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

## **Mapping JSON in tabular format** &#x20;

The REST Data source in App Composer offers a powerful capability to not only read the schema of JSON data but also to flatten complex JSON structures into a more manageable table format. This functionality enables app developers to transform intricate JSON data into a format easily readable in traditional table layouts, facilitating the mapping of dimensions or the creation of SQL reports directly from the JSON data.&#x20;

With this feature, app developers can efficiently leverage JSON data sources for various analytical and reporting purposes within the application.

<figure><img src="../../../../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

1. **JSON Schema** Displays the structure of the JSON calculated from the response body. The JSON schema can have a complex structure, JSON Object, to which a JSON Attribute is associated.
2. **Show Sample Data** opens a dialog where you can see the response body of the request in a raw format.                                                                                            ![C:\c490439d88e47ebeed818ff9fb75957f](<../../../../.gitbook/assets/18 (3)>)
3. **Row Element:** The "row" element serves as the key component used to flatten JSON data into a tabular format. When processing JSON data, each "row" represents a single entry or record in the resulting table structure. By organizing JSON data into rows, the REST Data source can efficiently transform complex nested structures into a format conducive to tabular representation. For example, if you select the "Citizens" object, then for each citizen in a city in the JSON payload, a row in the table will be created with the respective information.
4. **Fields**: defines which JSON attributes will be mapped as table fields. You can define an alias for each attribute. The alias will be identified by the system as the logical name of the attribute.
5. **Active Paging:** enable or disable the pagination. If enabled, it allows you to select which JSON attribute will be used for paging
6.  **Show Content Sample:** display a preview of the flattened table based on the predefined schema. When clicked, this button generates a sample representation of the data structure in a flattened format, reflecting how the JSON data will appear when processed by the REST Data source. This preview helps users visualize and verify the accuracy of the table structure before proceeding with further configurations or data operations.

    ![](<../../../../.gitbook/assets/19 (5)>)
7. **Table Definition:** defines the type and key for each field in the table.
   * **Alias**: show the Alias name of the level. It will be later visible in he application
   * **Key**: determines which fields identify the primary key of the table.
   * **Type**: the type of data format. The box selection will activate a menu that will allow you to select one of the following STRING, INT, DOUBLE, LONG, DATETIME (see the pattern that can be used) and BOOLEAN formats.
   * **Pattern**: define the pattern applicable only for “DATETIME” type

#### How to map Dates

If you have a level that contains date-related data, you can select the DATETIME type from the Type menu and define the pattern used in the pattern column.

In the next paragraph there is the list of patterns

<figure><img src="../../../../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

### Date Pattern

List of patterns and tokens that can be used.

<table data-full-width="true"><thead><tr><th width="267.3333333333333">Pattern</th><th>Description</th><th>Example</th></tr></thead><tbody><tr><td>yyyy</td><td>Year</td><td>1997</td></tr><tr><td>yyyy-MM</td><td>Year and month</td><td>1997-07</td></tr><tr><td>yyyy-MM-dd</td><td>Complete date</td><td>1997-07-16</td></tr><tr><td>yyyy-MM-dd'T'HH:mm z</td><td>Complete date plus hours and minutes (timezone name)</td><td>1997-07-16T19:20 CET</td></tr><tr><td>yyyy-MM-dd'T'HH:mm:ss z</td><td>Complete date plus hours, minutes and seconds (timezone name)</td><td>1997-07-16T19:20:30 CET</td></tr><tr><td>yyyy-MM-dd'T'HH:mm:ss.s z</td><td>Complete date plus hours, minutes, seconds and a decimal fraction of a second (timezone name)</td><td>1997-07-16T19:20:30.45 CET</td></tr><tr><td>yyyy-MM-dd'T'HH:mm Z</td><td>Complete date plus hours and minutes (timezone offset)</td><td>1997-07-16T19:20 +01:00</td></tr><tr><td>yyyy-MM-dd'T'HH:mm:ss Z</td><td>Complete date plus hours, minutes and seconds (timezone offset)</td><td>1997-07-16T19:20:30 +01:00</td></tr><tr><td>yyyy-MM-dd'T'HH:mm:ss.s Z</td><td>Complete date plus hours, minutes, seconds and a decimal fraction of a second (timezone offset)</td><td>1997-07-16T19:20:30.45 +01:00</td></tr></tbody></table>

<table><thead><tr><th width="215">Token</th><th>Legend</th></tr></thead><tbody><tr><td>yyyy</td><td>four-digit year</td></tr><tr><td>MM</td><td>two-digit month (01=January, etc.)</td></tr><tr><td>dd</td><td>two-digit day of month (01 through 31)</td></tr><tr><td>hh</td><td>two digits of hour (00 through 12)</td></tr><tr><td>HH</td><td>two digits of hour (00 through 23) (am/pm NOT allowed)</td></tr><tr><td>mm</td><td>two digits of minute (00 through 59)</td></tr><tr><td>ss</td><td>two digits of second (00 through 59)</td></tr><tr><td>s</td><td>one or more digits representing a decimal fraction of a second</td></tr><tr><td>Z</td><td>time zone designator (+hh:mm or -hh:mm)</td></tr><tr><td>z</td><td>time zone name designator (eg. CET)</td></tr></tbody></table>

### Using DAC Environment Variable in the REST Data Source

To use a DAC environment variable in a REST Data Source, you can include it in different parts of the REST request such as the endpoint, headers, or request body. A typical use case is to store a Bearer token in a DAC environment variable and then use it in the authorization header of the request.

<figure><img src="../../../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

In the provided image, there's an API that can fetch data from a [Snippet](../../../sdk-and-api/code-snipped-editor/) based on specific settings. Since the snippet is available within the same DAC instance, you need an access token for authentication to run it. You can use the `%DAC_ACCESS_TOKEN%` system parameter to re-use the token for the user that's currently logged in. Just ensure the user's token has the right permissions to carry out the request.

For further details on using DAC environment variables, please refer to:

{% content-ref url="../advanced-configurations-and-properties.md" %}
[advanced-configurations-and-properties.md](../advanced-configurations-and-properties.md)
{% endcontent-ref %}

## Data Source Properties

Properties for the data source REST/ JSON  are explained in the table below.&#x20;

| PROPERTIES         | DESCRIPTION                                                                                                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Main**           |                                                                                                                                                                                                         |
| metadataInfo       | Information about the metadata of the application.                                                                                                                                                      |
| alias-name         | It’s a mandatory properties that is used to uniquely identify this data source in the application. The alias will be displayed when you need to select an external data source during the data mapping. |
| max-rows-selected  | To define the maximum limit allowed for responses to queries on the data source                                                                                                                         |
| dsrest-call-body   | To define the call body                                                                                                                                                                                 |
| dsrest-call-method | To define the call method                                                                                                                                                                               |
| is-read-only       | For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.                                                     |
