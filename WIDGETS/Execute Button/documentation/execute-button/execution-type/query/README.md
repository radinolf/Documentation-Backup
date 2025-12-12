# QUERY

## Overview

This operation performs one or more queries in the default data source or in the configured data source. When selection **QUERY** in the **execution-type** property, the **sql-formula\*** property is available to define the query. It is possible to either add or update the query. In the sql-formula\* dialog you can input the SQL Query

{% hint style="warning" %}
The widget doesn't support the SQL command `SELECT`: an exception will be displayed if configured with this command.
{% endhint %}

The query statement supports the use of parameters and you can specify whether they are required by using the **mandatory-params** property. When clicking the button with a parameter that doesn't have a value, the page will display a warning dialog.

<figure><img src="../../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

The query can be executed on any data source created in App Composer using the [**Data sources designer**](https://documentation.decisyon.com/documentation/application/data-source) (**Tools--> Data Source**). When selecting the **custom-datasource** property in the Execute button, the **data-source** property is enabled where you can associate the previously created data source.

<figure><img src="../../../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

### Execution-type Properties

The properties that are specific for the configuration of the **Execution-type QUERY** are listed below:

<table><thead><tr><th width="275">Specific Properties</th><th width="252">Description</th><th width="133" align="center">Type</th><th width="148" align="center">Default Value</th><th width="358" data-type="checkbox">Allow Page Parameters</th><th data-hidden>Group</th></tr></thead><tbody><tr><td><strong>custom-datasource</strong></td><td><p>When not configured, the query is executed on the default data source associated to the application. Enable this property to use a custom data source where to execute the defined query.</p><p>The activation of this property enables: </p><ul><li><strong>data source</strong>:  select the data source previously defined in the Data sources designer.</li></ul></td><td align="center">SWITCH</td><td align="center">False</td><td>false</td><td><strong>Execution</strong></td></tr><tr><td><strong>sql-formula*</strong></td><td>Input the SQL statement to execute.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td><strong>Execution</strong></td></tr></tbody></table>

