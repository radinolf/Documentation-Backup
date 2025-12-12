# How to create a DS on a REST JSON data source

## Introduction

In this example, you will configure a Rest/JSON data source with the objective of invoking a REST API that returns a list of plants in JSON format. You will display the list of plants in a report.

## **Prerequisites**

In this example, you are simulating to use an external API the responds on the URL `https://example.com/api/listOfPlant` and that provide as a response the list of plants in JSON format.

```json
{
  "rows": [
    {
      "Plant_code": "Rome",
      "description": "Rome",
      "Latitude": "41.902800",
      "Longitude": "12.496400",
      "Timezone": "Europe/Rome",
      "active": 1
    },
    {
      "Plant_code": "Hannover",
      "description": "Hannover",
      "Latitude": "52.373920",
      "Longitude": "9.735603",
      "Timezone": "Europe/Berlin",
      "active": 1
    },
    {
      "Plant_code": "Madrid",
      "description": "Madrid",
      "Latitude": "40.416705",
      "Longitude": "-3.703800",
      "Timezone": "Europe/Madrid",
      "active": 1
    },
    {
      "Plant_code": "Brussels",
      "description": "Brussels",
      "Latitude": "50.847600",
      "Longitude": "4.357200",
      "Timezone": "Europe/Brussels",
      "active": 0
    }
  ]
}
```

The JSON represents an array of objects, each containing information about a plant. Each object in the array represents a different plant, along with its respective details. Here is a detailed explanation:

* `Plant_code`: The unique code for the plant.
* `description:` The description of the plant.
* `Latitude`: The geographical latitude of the plant.
* `Longitude`: The geographical longitude of the plant.
* `Timezone`: The timezone in which the plant is located.
* `active`: An indicator that can be 1 (active) or 0 (inactive), indicating the status of the plant.

To simulate an endpoint in [Node-RED](https://nodered.org/), you can download and import our flow into your Node-RED setup. For additional details, we recommend exploring the Node-RED documentation. This setup can help you create your data source more efficiently.

{% file src="../../../../.gitbook/assets/Flow listOfPlants.json" %}
You can download and import this flow in Node-RED editor to simulate the external endpoint. Please note that it has been created with Node-RED 3.1.3
{% endfile %}

<figure><img src="../../../../.gitbook/assets/image (2009).png" alt=""><figcaption></figcaption></figure>

## **Step 1: Create the Data Source**

<figure><img src="../../../../.gitbook/assets/image (2002).png" alt=""><figcaption></figcaption></figure>

* Open Design Studio
* Create a new Data Source , from the toolbar select **Tools>>Data Source.**
* Select database type **REST/JSON**

Click on the '**Configure Data Source**' button located at the bottom right of the panel.

<figure><img src="../../../../.gitbook/assets/image (2003).png" alt=""><figcaption></figcaption></figure>

1. Insert the Endpoint of the API that to invoke, in this case `https://example.com/api/listOfPlant`
2. Click the button "**Test Endpoint Invocation**"
3. Click the Next button

Now you need to map the JSON and flatten it in a table-suitable format.

<figure><img src="../../../../.gitbook/assets/image (2005).png" alt=""><figcaption></figcaption></figure>

1. On the left, you can view the JSON schema calculated by App Composer.
2. Click on  **Show Sample Data** to display the JSON data.

In order to structure a database table based on a JSON schema, it's crucial to identify the "Row Element" and determine which fields from the JSON schema will serve as columns within the table. The "Row Element" refers to a distinctive entity or object that will represent each row in your table. Fields from the JSON schema, on the other hand, are selected to become the columns of the table, representing attributes or properties of the "Row Element."

<figure><img src="../../../../.gitbook/assets/image (2004).png" alt=""><figcaption></figcaption></figure>

* **Row Element**: Determines the specific JSON Object that represents the data shown in the table. Selecting a JSON property, such as "rows", translates each object contained (e.g., plant information) into a separate table row.
* **Fields**: Specifies the mapping of JSON attributes to table columns. Each attribute can be assigned an alias, which the system uses as its logical name.

Click on "Finish" and save the data source.

**Define the alias of the data source**

<figure><img src="../../../../.gitbook/assets/image (386).png" alt=""><figcaption></figcaption></figure>

From the property 'alias-name,' you can define an alias that allows you to identify this alias in the application. In this example, we chose 'LISTOFPLANT' as the alias.

## **Step 2: Create a SQL report**

You can now create a SQL report to display the data from the data source

<figure><img src="../../../../.gitbook/assets/image (2006).png" alt=""><figcaption></figcaption></figure>

1. Select the SQL tab.
2. Choose the REST/JSON data source created earlier (LIST OF PLANT). Select "remote," and from the menu, choose the alias name of your data source.
3. Use the SQL editor to write your query. For example:

```sql
select 
rest.JSONData.Plant_code as Plant_code ,
rest.JSONData.description as description,
rest.JSONData.Latitude as Latitude,
rest.JSONData.Longitude as Longitude,
rest.JSONData.Timezone as Timezone,
rest.JSONData.active as active
from rest.JSONData
```

For steps on setting up an SQL report, see the dedicated documentation:

{% content-ref url="../../../report/sql-report.md" %}
[sql-report.md](../../../report/sql-report.md)
{% endcontent-ref %}

## **Step 3: View the data**

Go back to editing the report by selecting the SQL Tab at the bottom.

The Cube metrics created through the query, will have a different color.

<figure><img src="../../../../.gitbook/assets/image (2007).png" alt=""><figcaption></figcaption></figure>

Now, insert the levels into the report to view the data and exec the report.

This is the result:

<figure><img src="../../../../.gitbook/assets/image (2008).png" alt=""><figcaption></figcaption></figure>
