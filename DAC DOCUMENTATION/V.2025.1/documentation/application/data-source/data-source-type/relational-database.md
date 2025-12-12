# Relational Database

## Oracle RDBMS

In the following section, we will examine the process of configuring a data source, focusing on Oracle 10g, Oracle 11g, and Oracle 12c databases.&#x20;

<figure><img src="../../../../.gitbook/assets/image (433).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properità of the Database and the Data source see the [Common properties](relational-database.md#common-properties) paragraph.

### Properties&#x20;

Below the table containing all the advanced properties for the Oracle 10g, Oracle 11g, Oracle 12c  data source configuration.

<table data-full-width="true"><thead><tr><th width="237.49999999999994">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td><a data-footnote-ref href="#user-content-fn-1"><strong>Report temp tables</strong></a></td><td></td></tr><tr><td>nologging-on-create-table</td><td>Allows you to set the NOLOGGING property for Oracle database operations.</td></tr><tr><td>global-temp-table</td><td>Enable/disable the use of Global Temporary Table to create final datamart.</td></tr><tr><td>purge-on-drop</td><td>Include the option “purge” when dropping a temporary table</td></tr><tr><td>custom-tablespace</td><td>Enable the use of a custom Oracle tablespace to store temporary table.</td></tr><tr><td>tablespace-name</td><td>Input the name of the Oracle tablespace where to store temporary tables</td></tr></tbody></table>

## ⛔ Teradata (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (432).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properità of the Database and the Data source see the [Common properties](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/yAjw1iF7BRk9VYaJYNdQ/~/changes/94/documentation/application/data-source/datasource-type/relational-database#common-properties) paragraph.

### &#x20;Properties&#x20;

Below the table containing all the advanced properties for the Teradata 15.x  data source configuration.

<table data-full-width="true"><thead><tr><th width="240.49999999999994">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td>integrate-metric-functions </td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td></tr><tr><td><strong>Storage tables schema</strong></td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td></tr></tbody></table>

## Microsoft SQL Server 2008, Microsoft SQL Server 2012

<figure><img src="../../../../.gitbook/assets/image (435).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properties of the Database and the Data source see the [Common properties](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/yAjw1iF7BRk9VYaJYNdQ/~/changes/94/documentation/application/data-source/datasource-type/relational-database#common-properties) paragraph.

### &#x20;Properties&#x20;

Below the table containing all the advanced properties for the Microsoft SQL Server 2008, Microsoft SQL Server 2012  data source configuration

<table data-full-width="true"><thead><tr><th width="246.49999999999994">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td>integrate-metric-functions </td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td></tr><tr><td><a data-footnote-ref href="#user-content-fn-1"><strong>Report temp tables</strong></a></td><td></td></tr><tr><td>global-temp-table</td><td>Enable/disable the use of Global Temporary Table to create final datamart.</td></tr><tr><td><strong>Storage tables schema</strong></td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td></tr></tbody></table>

## &#x20;Oracle MySQL&#x20;

<figure><img src="../../../../.gitbook/assets/image (436).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properità of the Database and the Data source see the [Common properties](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/yAjw1iF7BRk9VYaJYNdQ/~/changes/94/documentation/application/data-source/datasource-type/relational-database#common-properties) paragraph.

### Properties

Below the table containing all the advanced properties for the Oracle MySQL 5.5 data source configuration

<table data-full-width="true"><thead><tr><th width="220.49999999999994">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td>integrate-metric-functions </td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td></tr><tr><td><a data-footnote-ref href="#user-content-fn-1"><strong>Report temp tables</strong></a></td><td></td></tr><tr><td>mysql-storage-engine</td><td>In specifies the Storage Engine of MySQL to create the temporary tables of the reports. If 'undefined' is select, the system will not add the Storage Engine clause and the default one will be used.</td></tr><tr><td><strong>Storage tables schema</strong></td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td></tr></tbody></table>

## ⛔ IBM DB2 (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (437).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properità of the Database and the Data source see the [Common properties](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/yAjw1iF7BRk9VYaJYNdQ/~/changes/94/documentation/application/data-source/datasource-type/relational-database#common-properties) paragraph.

### Properties

Below the table containing all the advanced properties for the IBM DB2 9.x  data source configuration

<table data-full-width="true"><thead><tr><th width="255.49999999999994">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td>integrate-metric-functions </td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td></tr><tr><td><a data-footnote-ref href="#user-content-fn-1"><strong>Report temp tables</strong></a></td><td></td></tr><tr><td>createTableAs-withData </td><td>If enabled, "CREATE ABLE AS SELECT" sql statement will be execute with "WITH DATA" option. Please before enable, check that your Database support this option.</td></tr><tr><td><strong>Storage tables schema</strong></td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td></tr></tbody></table>

## PostgreSQL&#x20;

<figure><img src="../../../../.gitbook/assets/image (438).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properità of the Database and the Data source see the [Common properties](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/yAjw1iF7BRk9VYaJYNdQ/~/changes/94/documentation/application/data-source/datasource-type/relational-database#common-properties) paragraph.

### Properties

Below the table containing all the advanced properties for the PostgreSQL 9.6 data source configuration

<table data-full-width="true"><thead><tr><th width="284.5">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td>integrate-metric-functions </td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td></tr><tr><td><strong>Storage tables schema</strong></td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td></tr></tbody></table>

## Sap Hana

<figure><img src="../../../../.gitbook/assets/image (439).png" alt=""><figcaption></figcaption></figure>

For the configuration of the connection properità of the Database and the Data source see the [Common properties](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/yAjw1iF7BRk9VYaJYNdQ/~/changes/94/documentation/application/data-source/datasource-type/relational-database#common-properties) paragraph.

### Properties

Below the table containing all the advanced properties for the PostgreSQL 9.6 data source configuration

<table data-full-width="true"><thead><tr><th width="277.5">Property</th><th>Description</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td></td></tr><tr><td>metadataInfo</td><td>Information about the metadata of the application.</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td></tr><tr><td>integrate-metric-functions </td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td></tr><tr><td><a data-footnote-ref href="#user-content-fn-1"><strong>Report temp tables</strong></a></td><td></td></tr><tr><td>global-temp-table</td><td>If enabled, "CREATE ABLE AS SELECT" sql statement will be execute with "WITH DATA" option. Please before enable, check that your Database support this option.</td></tr><tr><td><strong>Storage tables schema</strong></td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td></tr></tbody></table>

## Common properties&#x20;

For all relational database types, the configuration method for both Database (Database Configuration) and Data source (Data source Configuration) is the same. Below, we show the properties and their functions:

![](<../../../../.gitbook/assets/1 (7)>)

**Database Type**

Choose the desired database from the dropdown menu.

**Database Connection**

Set of properties you enter the database connection parameters.

After sets the Database connecion properties, the **JDBC string** is configured automatically.

If you select the fleg **Edit JDBC String**, you can change the sgtringa JDBC

When the data source is a relational databse it’s possible to configure specific schema where to store the temporary table using the “Storage tables schema” properties.

By the default, for a new data source each of this property is set to \<default> and it means that the schema to use is inherted from the tool “Tools>> Main>> Storage Table Schema”.

**Data Source Configuration**

* **Alias:** The alias is a symbolic name or label used to uniquely identify the data source. The data source alias is mandatory and is useful to recognize the data source when it is [associated with DAC objects](../introduction.md#app-composer-objects-associated-to-a-datasource)
* **MinIdle:** it is the minimum number of connections that should be maintained in the connection pool, even when they are not currently in use. It helps to ensure that there are connections ready for use without having to create them each time.
* **IdleTimeout:** it is the period  (in milliseconds)  after which an inactive connection is considered unused and can be removed from the connection pool.&#x20;
* **MaxPoolSize: i**t is the maximum number of connections that can be created in the connection pool. Beyond this limit, no further connections will be created until some of the existing connections are released.
* **MaxLifetime:** it is the maximum period (in milliseconds) for which a connection can be maintained in the connection pool before being discarded.
* **ConnectionTimeout:** is the duration (in milliseconds) during which the data source attempts to establish a connection. If a connection cannot be established within this set time, an error is triggered, providing a mechanism to handle connection establishment failures promptly
* **ValidationTimeout:** indicates the maximum time (in milliseconds) the data source will wait for confirmation that a connection is still valid.
* **LeakDetectionThreshold:** This parameter represents the threshold (in milliseconds) below which the data source considers a connection as a "leak[^2]". If a connection has been acquired but never released, it may indicate a potential memory leak issue. For example , if you set `LeakDetectionThreshold` to 1800000, it means that a connection can remain inactive for 30 minutes before being considered a potential leak.

{% hint style="info" %}
**Note**

When creating a new data source, it's important to note that the properties listed below already have default values. These default values represent the minimum required for ensuring the proper functioning of the data source. However, you can customize these values based on the project's specific needs, thereby optimizing the data source's performance in accordance with application requirements.
{% endhint %}



[^1]: This property group enables only when the is-read-only property is selected

[^2]: A "leak" connection refers to a situation in where a connection to a database is not properly closed or released, leading to resource inefficiency, potential performance issues, and may result in connection pool exhaustion.
