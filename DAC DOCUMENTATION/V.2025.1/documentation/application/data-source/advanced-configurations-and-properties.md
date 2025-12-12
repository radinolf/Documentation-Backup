# Advanced configurations and properties

## Using DAC ENV in a Data Source

When creating a data source, the connection parameters, including the credentials of the database, are stored in the App Composer metadata. Some of this information, such as the password, is encrypted when persisted. While configuring the data source in this way is easy and straightforward, it can cause issues in certain scenarios, such as:

1. Password rotation
2. Change of database host or DNS
3. Fine-tuning data source settings
4. Modifying an API token
5. Changing an endpoint

In all of the above scenarios, it is necessary to open Design Studio and modify the data source properties. However, in a production environment, this may not be so easy.

This is where DAC Environment variables come in handy. By using defined DAC ENV variables in all the properties of a data source, you can avoid the need to open Design Studio and modify the properties directly. Instead, you can simply change the value of a DAC ENV variable.

<figure><img src="../../../.gitbook/assets/image (1937).png" alt=""><figcaption></figcaption></figure>

Furthermore, since the value of a DAC ENV variable is defined in the deployment HELM chart of App Composer, any DevOps team member can easily view and potentially change the value without needing knowledge about how to use Design Studio.

To use a DAC ENV variable in a data source, you must define the same variable as an operating system environment variable. When Design Studio executes queries, it retrieves the value of the DAC ENV variable from the operating system. If you haven't defined the variable, an error message will be displayed.&#x20;

{% hint style="info" %}
The name of environment variables must always start with **DAC\_ENV\_:** in example **DAC\_ENV\_dac\_db\_username**
{% endhint %}

{% tabs %}
{% tab title="Windows Batch" %}
{% code title="Example for windows CMD" lineNumbers="true" fullWidth="true" %}
```batch
rem Set environment variables with specified values
setx DAC_ENV_dac_db_username "appcomposer_user"
setx DAC_ENV_dac_db_password "P@ssw0rd!"
setx DAC_ENV_dac_db_host "localhost"
setx DAC_ENV_dac_db_name "appcomposer_db"
```
{% endcode %}
{% endtab %}

{% tab title="Power Shell" %}
{% code title="Powershell" lineNumbers="true" fullWidth="true" %}
```powershell
 # Set environment variables with specified values for the current Windows user
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_username", "appcomposer_user", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_password", "P@ssw0rd!", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_host", "localhost", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_name", "appcomposer_db", [System.EnvironmentVariableTarget]::User)
```
{% endcode %}
{% endtab %}
{% endtabs %}

To ensure the variables are correctly set, open the Windows Environment Variable dialog:

{% code title="Batch / Power Shell" lineNumbers="true" %}
```batch
rundll32.exe sysdm.cpl,EditEnvironmentVariables
```
{% endcode %}

<figure><img src="../../../.gitbook/assets/image (1935).png" alt=""><figcaption></figcaption></figure>

Additionally, if you define a data source using a DAC ENV variable, when the data source is synchronized from development to production, it will be synchronized using the DAC ENV variable. This makes the data source agnostic to the environment and reduces the risk of using development credentials in production or vice versa.

It is strongly recommended to always use DAC ENV variables in the definition of a data source. This simplifies the maintenance of the application when it is in production.

{% hint style="danger" %}
To ensure that Design Studio connects to the correct environment when switching between different environments, such as from DEV to TEST, it is crucial to modify the values of the DAC ENV defined in your operating system.&#x20;

Failing to do so will result in Design Studio connecting to the TEST environment, while the data source continues to connect to the DEV environment!
{% endhint %}

Here are some use cases where it's convenient to use a DAC environment in a data source:

<table data-full-width="false"><thead><tr><th>Use Case</th><th>Description</th></tr></thead><tbody><tr><td>Password rotation</td><td>Instead of manually updating the password in the data source properties, you can simply change the value of the DAC ENV variable associated with the password. This ensures that the data source continues to function without the need for manual intervention.</td></tr><tr><td>Change of Database Host</td><td>If the database host or DNS changes, you can update the value of the DAC ENV variable associated with the host. This allows the data source to connect to the new host without requiring changes to the data source properties in Design Studio.</td></tr><tr><td>Modifying an API Token</td><td>If an API token used by a data source needs to be modified, you can simply update the value of the DAC ENV variable associated with the token. This ensures that the data source continues to authenticate successfully without requiring changes to the data source properties.</td></tr><tr><td>Changing an API Endpoint</td><td>If the endpoint used by a data source changes, you can update the value of the DAC ENV variable associated with the endpoint. This allows the data source to connect to the new endpoint without needing modifications to the data source properties in Design Studio.</td></tr></tbody></table>

## Storage table schema

The **Storage Table Schema** is a set of properties in relational database data sources that allows you to select the database schema where temporary or non-temporary tables created by application objects, such as reports or widgets, will be stored.

<figure><img src="../../../.gitbook/assets/image (1945).png" alt=""><figcaption><p>In this Data Source, the tables created for the Excel integration are stored in a database schema named "appcomposer_temp".</p></figcaption></figure>

For example, let's say you don't want additional tables to be created in the data schema. In this case, you can create a database schema called "`appcomposer_temp`" and select it as the target for storing temporary tables. By doing this, you ensure that the temporary tables are stored in a separate schema, keeping the data schema clean and organized. Additionally, when exporting the database, you could exclude the "`appcomposer_temp`" schema, resulting in a smaller exported file size.

To specify the storage schema for these tables, you can choose from a dropdown menu that lists available schemas within the same database where the data source operates.&#x20;

The three properties that you can configure are:

<table data-full-width="false"><thead><tr><th width="246.49999999999994">Property</th><th>Description</th></tr></thead><tbody><tr><td>report-final-tables</td><td>Schema to store the final <a href="../../report/report/execution.md">report datamart</a> (table with prefix <code>FX&#x3C;number></code>)</td></tr><tr><td>report-interm-tables</td><td>Schema to store the tables create during intermediate steps of <a href="../../report/report/execution.md">report execution</a> (table with prefix <code>DX&#x3C;number>,TX&#x3C;number>,UX&#x3C;number></code>)</td></tr><tr><td>excel-integration-tables</td><td>Schema to store the Excel Integration tables (used by the "<a href="https://widgets.decisyon.com/button-1/">Execute Button</a>" widget)</td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (1934).png" alt=""><figcaption></figcaption></figure>

By default, the three properties are configured with the value `<Default>` . This value implies that the schema used as a target to store the tables is not selected in the data source itself, but it is inherited by the same properties that are configured in the instance's properties.

## The "Default" Data Source

In App Composer, you can have multiple data sources per instance, and these data sources can be used in any applications within the same instance. This allows for flexible configuration, as it is possible to retrieve data from more than one data source within the same application or to re-use the same data source in multiple applications.\
\
To minimize manual tasks, each application can have a "default" data source selected. Any queries executed by App Composer objects within the application will use this selected data source by default, unless the App Developer explicitly modifies the settings. Additionally, for each individual object, a different data source can be selected for executing queries.

The application's default data source is configured through the properties.<br>

This configuration allows for scenarios where an application can retrieve data from a PostgreSQL database (which is set as the "default" data source), while specific widgets or reports can retrieve data from a REST/JSON API (which is another data source, but not the "default" for the application).

## Data Source Alias

When creating a new data source in App Composer, one of the mandatory properties to configure is the "Alias". The Alias is a string that uniquely identifies the data source within App Composer.&#x20;

When setting the data source alias, you must choose a name that meets the following criteria:

1. It must be unique, as you cannot have two data sources with the same alias.
2. It cannot contain any special characters.
3. It cannot have spaces.
4. It cannot start with a number.

The Alias is important because it is used to associate App Composer objects and features with a specific data source. For example, when creating a cube or dimensions, you can select a data source from a dropdown menu that displays the aliases.&#x20;

\
Additionally, when debugging the SQL query of an App Composer object, such as a report, you will see the data source alias next to the "`FROM`" clause as "`@<data_source_alias>`". This indicates that the query is being executed on the data source with that assigned alias.\
\
Here is an example of an SQL query that shows the use of a data source alias:

```sql
SELECT 
ASSET_ID as ASSET_ID, 
ASSET_DS as ASSET_DS,
(AVG((TURBINE_AVAIL_SUM_) * 100 )) AS AVAILABILITY_PERC_
FROM FX170745579421413525115@<DEMO-ASSET/>
WHERE ASSET_PB_ID IN('T01')
GROUP BY
ASSET_ID,
ASSET_DS;
```

In this query, the data source alias "`@<DEMO-ASSET/>`" is used to specify the data source on which the query should be executed.\
\
It is also possible to manually specify the alias in an SQL query. For example, if you define the following SQL query in the pre-selection values of a page, App Composer will execute the query using the data source corresponding to the alias used in the query:

```sql
SELECT plant_id, plant_name
FROM data.plants@<DEMO-ASSET/>
WHERE plant_country='Italy'
```
