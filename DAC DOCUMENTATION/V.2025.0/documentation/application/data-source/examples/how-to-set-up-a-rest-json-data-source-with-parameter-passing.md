# How to set up a Rest/JSON Data source with parameter passing

## **Introduction**

In this example, we will configure a Rest/JSON data source with the objective of invoking a REST API that returns a details of a specific plant. The plant code is passed by a parameter in the REST request .

## **Prerequisites**

In this example, you are simulating to use an external API the responds on the URL

`https://example.com/energyData?plant={{Plant_code}}`&#x20;

and that provides, as a response, the list of plants in JSON format filtered based on the Plant\_code passed via query string.

{% code lineNumbers="true" %}
```json
// This is an example of the response body in JSON format
[
    {
        "plant_code": "Rome",
        "series": "Total_ consumption",
        "series_id": "Tc",
        "datetime": "2023-12-31T23:00:00.000Z",
        "value": "497"
    },
    {
        "plant_code": "Rome",
        "series": "Total_ consumption",
        "series_id": "Tc",
        "datetime": "2024-01-01T00:00:00.000Z",
        "value": "472"
    },
    {
        "plant_code": "Rome",
        "series": "Total_ consumption",
        "series_id": "Tc",
        "datetime": "2024-01-01T01:00:00.000Z",
        "value": "375"
    },
    {
        "plant_code": "Rome",
        "series": "Total_ consumption",
        "series_id": "Tc",
        "datetime": "2024-01-01T02:00:00.000Z",
        "value": "299"
    }
    .....
```
{% endcode %}

The JSON represents an array of objects, each containing information about a plant. Each object in the array represents a different plant, along with a datapoint of a time series. Here is a detailed explanation:

* `plant_code:` The identifying code of the plant
* `series`: The name of the time series
* `series_id`: A unique identifier for the time series
* `datetime`: The date and time associated with the data point
* `value`: The value associated with this data point

### **Create Table**

To replicate the example, you could create a table that contains the Plant data.

```
CREATE TABLE <YOUR_DB_SCHEMA>.test_read_data_from nodered (
	plant_code varchar NULL,
	series varchar NULL,
	datetime timestamp NULL,
	value numeric NULL,
	series_id varchar NULL
);
```

To insert rows into the table, please follow the script provided below:

{% file src="../../../../.gitbook/assets/Sql data.sql" %}

### Simulate an endpoint

You simulate the endpoint with [Node-RED](https://nodered.org/). You can download and import our training flow into your Node-RED instance. For additional details, we recommend exploring the Node-RED documentation. This flow can help you create your simulated endpoint more efficiently.

{% file src="../../../../.gitbook/assets/Node-red flow.json" %}
You can download and import this flow in Node-RED editor to simulate the external endpoint. Please note that it has been created with Node-RED 3.1.3
{% endfile %}

<figure><img src="../../../../.gitbook/assets/image (1894).png" alt=""><figcaption></figcaption></figure>

## Step 1: Create the Data Source

<figure><img src="../../../../.gitbook/assets/image (1895).png" alt=""><figcaption></figcaption></figure>

* Open Design Studio
* Create a new Data Source , from the toolbar select **Tools>>Data Source.**
* Select database type **REST/JSON**
* Click on the **Configure Data Source** button located at the bottom right of the panel.

### **Configure Data Source**

<figure><img src="../../../../.gitbook/assets/image (1896).png" alt=""><figcaption></figcaption></figure>

1. Insert the Endpoint of the API to invoke, in this case `https://example.com/energyData?plant={{Plant_code}}`
2.  Input a new headers to be used in the request: `Accept: application/json`

    <figure><img src="../../../../.gitbook/assets/image (1897).png" alt=""><figcaption></figcaption></figure>
3. Click the "Test" button. If the test is successful, click on "Next"
4. This API request the Authentication. Select enable Basic Authentication option and insert username and password. &#x20;
   * Please use this credentials.
     * &#x20;**Username**:  User\_test&#x20;
     * **Password**:  m1\_passw0rd&#x20;
5.  Now test Endpoint Invocation.

    <figure><img src="../../../../.gitbook/assets/image (2030).png" alt=""><figcaption></figcaption></figure>

    if the test is OK then press the Next button.

### **Map JSON**

Now you need to map the JSON and flatten it in a table-suitable format.

<figure><img src="../../../../.gitbook/assets/image (1898).png" alt=""><figcaption></figcaption></figure>

1. On the left, you can view the JSON schema calculated by App Composer based on the response body.
2. Click on **Show Sample Data** to display the JSON data.

In order to structure a database table based on a JSON schema, it's crucial to identify the "Row Element" and determine which fields from the JSON schema will serve as columns within the table. The "Row Element" refers to a distinctive entity or object that will represent each row in your table. Fields from the JSON schema, on the other hand, are selected to become the columns of the table, representing attributes or properties of the "Row Element."

<figure><img src="../../../../.gitbook/assets/image (1899).png" alt=""><figcaption></figcaption></figure>

1. **Row Element**: Determines the specific JSON Object that represents the data shown in the table. Selecting a JSON property, such as "array", translates each object contained (e.g., plant information) into a separate table row.
2. **Fields**: Specifies the mapping of JSON attributes to table columns. Each attribute can be assigned an alias, which the system uses as its logical name.
3. In the **Table Definition** you can select the type of attribute. In this example we change the type of datetime.

<figure><img src="../../../../.gitbook/assets/image (1900).png" alt=""><figcaption></figcaption></figure>

Click on "Finish" and save the data source.

### **Set the data source alias**

<figure><img src="../../../../.gitbook/assets/image (1901).png" alt=""><figcaption></figcaption></figure>

Using the `alias-name` property, you can set an alias for identification purposes within the application. In this case, we've designated the alias as JSON-PARAM.

## Step 2: Create a SQL report <a href="#step-2-create-a-sql-report" id="step-2-create-a-sql-report"></a>

<figure><img src="../../../../.gitbook/assets/image (1902).png" alt=""><figcaption></figcaption></figure>



1. Select the SQL tab.
2. Select the REST/JSON data source created earlier (LIST OF PLANT). Select "remote," and from the menu, choose the alias name of your data source.
3. Use the SQL editor to write your query. For example:

{% code title="You can copy and paste this SQL" %}
```sql
SELECT 
rest.JSONData.plant_code as Plant_Code,
rest.JSONData.series as series,
rest.JSONData.series_id as series_id,
rest.JSONData.datetime as datetime,
rest.JSONData.value as value
from rest.JSONData 
```
{% endcode %}

#### **Step 3: View the data** <a href="#step-3-view-the-data" id="step-3-view-the-data"></a>

Go back to editing the report by selecting the SQL Tab at the bottom. You can see a "Yellow" cube that has now been created thanks to your query.

### **Insert levels**

Now, drag\&drop the levels into the "rows" of the report.

<figure><img src="../../../../.gitbook/assets/image (1903).png" alt=""><figcaption></figcaption></figure>

### **Define a View Filter for testing the parameter.**

To filter the report based on the entered value through a parameter, we create a View Filter. Below are only the main steps. For more details, please refer to the dedicated documentation. [View Fil](https://documentation.decisyon.com/documentation/data-mapping/filters#filter-condition-on-dimensional-levels)ter

a. Define new **View filter** form the tab Custom

b. "Double-click to select the ‘Plant description' level, and in the formula panel, insert the parameter name. The parameter name must be enclosed between the characters `'?Plant?'.`

<figure><img src="../../../../.gitbook/assets/image (1907).png" alt=""><figcaption></figcaption></figure>

To set up an SQL report, please see the relevant documentation:

{% content-ref url="../../../report/sql-report.md" %}
[sql-report.md](../../../report/sql-report.md)
{% endcontent-ref %}

### **Execute the report**

Now execute the report. After the execution, it’s necessary to insert a test value that DAC will use to filter the report data. In this example we insert the value "ROME".

<figure><img src="../../../../.gitbook/assets/image (1908).png" alt=""><figcaption></figcaption></figure>

Now click OK to execute the report.

In this case the report has been filter by the Plant Rome.

<figure><img src="../../../../.gitbook/assets/image (1909).png" alt=""><figcaption></figcaption></figure>
