# Data Source

### Introduction

Design Studio allows you to configure the connection to asource of data, i.e. relational database, Rest API or flat files.The connections are used to access the data in those systems. Data sources are used in DAC for various purposes:

* as a remote database of an application
* to map dimensions or cubes on remote systems
* to present them on Pages

It’s possible to configure as a data source

* [predefined databases](data-source.md#data-source-for-predefined-rdbms), indicated in the installation guide (Data sources compatible with DAC)
* [flat file](data-source.md#connections-to-flat-files) (Excel, CSV )
* [Data Source Rest JSon](data-source.md#data-source-rest-json)

Connections are managed in the **Data source editor**, which is accessed from the **Tools** menu item in Design Studio.

<figure><img src="../../.gitbook/assets/image (232).png" alt=""><figcaption></figcaption></figure>

**Database Type:** it is possible to select the type of database among those supported:

| **Category**    | **Data source type**      |
| --------------- | ------------------------- |
| Relational DBMS | Oracle 10g                |
| Relational DBMS | Oracle 11g                |
| Relational DBMS | Oracle 12 c               |
| Relational DBMS | Teradata 15.x             |
| Relational DBMS | Microsoft SQL Server 2008 |
| Relational DBMS | Microsoft SQL Server 2012 |
| Relational DBMS | Oracle MySQL 5.5          |
| Relational DBMS | IBM DB2 9.x,              |
| Relational DBMS | PostgreSQL 9.6            |
| Relational DBMS | Sap Hana                  |
| Flat files      | XLS                       |
| Flat files      | CSV                       |
| API             | REST /JSON                |

The **Test Connection** button performs a connection test, using the parameters entered for the data source.

### Datasource Properties

Properties for the data source are explained in the table below. Some of these properties are in common between the various data sources.

<table data-header-hidden><thead><tr><th></th><th></th><th width="150"></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td></td><td></td><td>Oracle 10 g 11g 12c</td><td>Teradata 15x</td><td>Microsoft SQL  server 2008  2012</td><td>IBM DB2.9.x</td><td>Postgre SQL 9.6</td><td>Sap Hana</td><td>Oracle my sql 5.5</td><td>Excel file (.xlsx) CSV Rest/JSON</td></tr><tr><td><strong>PROPERTIES</strong></td><td><strong>DESCRIPTION</strong></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td><strong>Main</strong></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>metadataInfo</td><td></td><td>X</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td></tr><tr><td>max-rows-selected</td><td>To define the maximum limit allowed for responses to queries on the data source</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td></tr><tr><td>dsrest-call-body</td><td>To define the call body</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x</td></tr><tr><td>dsrest-call-method</td><td>To define the call method</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x</td></tr><tr><td>is-read-only</td><td>For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td><td>x</td></tr><tr><td>integrate-metric-functions</td><td>Can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the <em>metric- functions</em>, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.</td><td></td><td></td><td></td><td>x</td><td>x</td><td>x</td><td>x</td><td></td></tr><tr><td><strong>Report temp tables</strong></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>nologging-on-create-table</td><td>Allows you to set the NOLOGGING property for Oracle database operations.</td><td>x</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>global-temp-table</td><td>Enable/disable the use of Global Temporary Table to create final datamart.</td><td>x</td><td></td><td>x</td><td></td><td></td><td>x</td><td></td><td></td></tr><tr><td>purge-on-drop</td><td>Include the option “purge” when dropping a temporary table</td><td>x</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>custom-tablespace</td><td>Enable the use of a custom Oracle tablespace to store temporary table.</td><td>x</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>tablespace-name</td><td>Input the name of the tablespace</td><td>x</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>mysql-storage-engine</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x</td><td></td></tr><tr><td>Storage tables schema</td><td></td><td></td><td></td><td></td><td>x</td><td>x</td><td>x</td><td>x</td><td></td></tr><tr><td>report-final-tables</td><td>Schema where all the final report datamart are stored (“FX”prefix as table table)</td><td></td><td></td><td></td><td>x</td><td>x</td><td>x</td><td>x</td><td></td></tr><tr><td>report-interm-tables</td><td>Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)</td><td></td><td></td><td></td><td>x</td><td>x</td><td>x</td><td>x</td><td></td></tr><tr><td>excel-integration-tables</td><td>Schema where all the Excel integration tables (used by the Execute Button widget) are stored.</td><td></td><td></td><td></td><td>x</td><td>x</td><td>x</td><td>x</td><td></td></tr><tr><td>alias-name</td><td>It’s a mandatory properties that is used to uniquely identify this data source in the application. The alias will be displayed when you need to select an external data source during the data mapping.</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x</td></tr></tbody></table>

There are properties that are applicable for any type of data source (Main Group) and properties that are specific to the selected data source (Database Group)

The properties of the Main group are

_**alias-name**_ it’s a mandatory properties that is used to uniquely identify this data source in the application. The alias will be displayed when you need to select an external data source during the data mapping.

This name will appear in the list of the external datasources (**Remote**) (valido solo per Excel file (.xlsx) CSV XML Rest/JSON)

* _**max-rows-selected**_ to define the maximum limit allowed for responses to queries on the data source
* _**is-read-only**_ for data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.

The native data sources for read only have the property enabled and not modifiable; some example are the flat files.

If the property is disabled, i.e. for NOT READ-ONLY data source, the property is available:

* _**integrate-metric-functions**_ can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the _metric- functions_, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.

### Data Source for Predefined RDBMS

All types of data sources are listed in Select Data source Type, including those relating to the database. The predefined JDBC connection string is proposed for each type of database.

![](<../../.gitbook/assets/1 (9)>)

* **Database Connection:** in this set of properties you enter the database connection parameters.

After sets the Database connecion properties, the JDBC string is configured automatically

When the data source is a relational databse it’s possible to configure specific schema where to store the temporary table using the “Storage tables schema” properties.

By the default, for a new data source each of this property is set to \<default> and it means that the schema to use is inherted from the tool “Preferences >> Main>> Storage Table Schema”. When a schema is defined for the datasource, the default is ignored and the data source selected schema is used.

When the data source is a relational databse it’s possible to configure specific schema where to store the temporary table using the “Storage tables schema” properties.

By the default, for a new data source each of this property is set to \<default> and it means that the schema to use is inherted from the tool “Preferences → Main → Storage Table Schema”. When a schema is defined for the datasource, the default is ignored and the data source selected schema is used.

* **report-final-tables**: Schema where all the final report datamart are stored (“FX”prefix as table table)
* **report-interm-tables:** Schema where all the intermediate step tables of a report execution are stored (“DX”,”TX”,”UX” prefix as table table)
* **excel-integration-tables**: Schema where all the Excel integration tables (used by the Execute Button widget) are stored.

Specific properties are available for certain types of data source environments for the temporary tables generated by the system (Report temp tables group). Good configuration allows performance to be improved. These properties are only used for data sources enabled for writing (not read-only): in this case, temporary tables are generated on the data source.

* Specific properties for “Oracle” database are:
  * _**nologging-on-create-table:**_ Allows you to set the NOLOGGING property for Oracle database operations.
  * **global temp-table** Enable/disable the use of Global Temporary Table to create final datamart.
  * _**purge-on-drop:**_ Include the option “purge” when dropping a temporary table
  * _**custom-tablespace**_ Enable the use of a custom Oracle tablespace to store temporary table.
    * _**tablespace-name:**_ input the name of the tablespace

### **Connections to flat files**

Flat files can be used as a data source. The file must be rechable from Design Studio in order to properly configure the data source and from the web application in order to read it at run time.

![](<../../.gitbook/assets/3 (12)>)

The file on the client is used to define the selection queries:the file is displayed like a table: the file name is used as “table name” and each file’s column is displayed as “table column”. The file on the server will be used when the connection to the data source requests the data from pages and widgets in the web application.

**Note:** Closing DAC-DS will close all connections opened by the data source.

#### Data Source for Excel Files

For the connection to Microsoft Excel, proceed as follows:

1. Select Excel file (.xlsx) as data source type.
2. In **File Path on Client** enter the path, including the Excel file on the _client_. The _Browse_ button opens the window to select the file.This file must be in the same client where Design Studio is executed
3. In **File Path on Server,** enter the path, including the Excel file on the DAC server. The path must start from the name of the unit present on the AS server, which must have visibility privileges on the folder where the file resides.

It is not possible to enter the HTTP path. In this case it is necessary to map the link as the folder on the server but reachable from the webapp.

![](<../../.gitbook/assets/4 (10)>)

Some validation criteria exist, which are applied to the Excel type data source:

* The name of the Excel file and the names of the first row of the same file must start with a letter
* The names of the columns can’t start with a character or with “\_”
* The first row cannot be empty because it is used as column name

The first line of data cannot be a numerical value and the successive ones text, the contrary is allowed. Textually defining the values in the first line of data is sufficient (putting the first character in the cell for the first value).

#### Data Source for CSV Files

Proceed as follows to connect to a CSV file:

1. Select CSV file as data source type.
2. Enter the path, WITHOUT the name of the local file, in **File Path on Client**. The Browse button opens the window to select the file.
3. Enter in **File Path on Server**, the path, WITHOUT the name of the file on the DAC AS server. The path must start from the name of the unit present on the AS server, which must have visibility privileges on the folder where the file resides.
4. Type the separator of the values (**Values** **Separator**), the **File Extension** and if the first row must be used for the names of the columns (**Use** **first row as column names**)

![](<../../.gitbook/assets/5 (3)>)

If several CSV files exist in the folders indicated, the system will interpret them as differen tables.

###

### Data Source REST JSon

The **REST JSon** retrieves data from a REST API when the response body is in JSON format.

![](<../../.gitbook/assets/10 (2)>)

To configure the data source, select the REST JSon item from the Select Data Source Type menu.

Select “**Configure the Data Source**“ button to open the Data Source REST configuration panel.

![](<../../.gitbook/assets/11 (3)>)

The parameters you can configure the data source are:

**Endpoint**: insert the **Endopoint** where the REST service is available.

The endpoint supports the use of variables in the path and the query string.Es: [http://localhost:8081/weather/\{{city\}}?day=\{{day\}}](http://localhost:8081/weather/%7B%7Bcity%7D%7D?day=%7b%7bday%7d%7d)

These variables can also be used in the Headers' values. The parameter must be enclosed between double to identify them as variables.

It also be possible to use some keywords between percent symbols as placeholder form as environment information of the binded services i.e **%ACCESS\_TOKEN%** for the Access Token.

* **Headers**: define the http’s Headers
  * Select the button

![](../../.gitbook/assets/12)

to insert a new row.

*
  * **Key** defines the name of the header (e.g. <**Content-Type**: text/html>
  * **Value** defines the value of header (e.g. \<Content-Type: **text/html**>)
  * Select the button

![](<../../.gitbook/assets/13 (2)>)

to remove a selected row.

![C:\\](<../../.gitbook/assets/14 (3)>)

Set variables’ default value&#x73;**:** Enables a panel in which you can define the default values of the variables, if provided in the endpoint and / or the headers value.

![](../../.gitbook/assets/15)

Example of endpoint with variable: [http://localhost:8081/turbines?type=\{{type\}}](http://localhost:8081/turbines?type=%7b%7btype%7d%7d)

When the "type" variable is valued, the values returned by the JSon will be filtered for that value.

The parameter can be used to filter the pages where, for objects that use this data source, you can map the parameters of the page, with the variables used for its definition.

**Authentication:** In case the third party endpoint requires a basic authentication for the request, enable the basic Authentication properties and insert username and password.

After configuring the request, select the test button to test it.

**Mapping JSon in tabular format**

In the next step of the wizard, it si possible to map the response JSON to a tabular format, transforming the response in a table that can be later used to map dimensions, cubes or build a SQL report on top of it.

![](<../../.gitbook/assets/17 (1)>)

* **JSon Schema** Displays the structure of the JSon that is downloaded from the endpoint. The JSon schema can have a complex structure, JSon Object, to which the JSon Attribute is associated.
* **Show Sample Data** opens a dialog where you can see the response body of the request in a raw format.
* ![C:\c490439d88e47ebeed818ff9fb75957f](<../../.gitbook/assets/18 (4)>)
* **Row Element:** defines which JSon Object identifies the information displayed in the table. For example, if you select the "Citizens" object, then for each citizen in a city in the JSon payload, a row in the table will be created with the respective information.
* **Fields**: defines which JSon attributes will be mapped as table fields. You can define an alias for each attribute. The alias will be identified by the system as the logical name of the attribute.
* **Active Paging**. enable or disable the pagination. If enabled, it allows you to select which json attribute will be used for paging
* **Table Definition:** defines the type and key for each field in the table.
  * **Key**: through a flag determines which fields identify the primary key of the table.
  * **Type**: the type of data format. The box selection will activate a menu that will allow you to select one of the following STRING, INT, DOUBLE, LONG, DATETIME (see the pattern that can be used) and BOOLEAN formats.
  * **Pattern**: define the pattern applicable only for “DATETIME” type

**Show Content Sample**

Show Content Sample button shows a preview of the report data and it’s possible to move the columns in a different position.

![](<../../.gitbook/assets/19 (6)>)

### Pattern

List of patterns that can be used.

| DESCRIPTION                                                                                     | PATTERN                   | EXAMPLE                       |
| ----------------------------------------------------------------------------------------------- | ------------------------- | ----------------------------- |
| Year                                                                                            | yyyy                      | 1997                          |
| Year and month                                                                                  | yyyy-MM                   | 1997-07                       |
| Complete date                                                                                   | yyyy-MM-dd                | 1997-07-16                    |
| Complete date plus hours and minutes (timezone name)                                            | yyyy-MM-dd'T'HH:mm z      | 1997-07-16T19:20 CET          |
| Complete date plus hours, minutes and seconds (timezone name)                                   | yyyy-MM-dd'T'HH:mm:ss z   | 1997-07-16T19:20:30 CET       |
| Complete date plus hours, minutes, seconds and a decimal fraction of a second (timezone name)   | yyyy-MM-dd'T'HH:mm:ss.s z | 1997-07-16T19:20:30.45 CET    |
| Complete date plus hours and minutes (timezone offset)                                          | yyyy-MM-dd'T'HH:mm Z      | 1997-07-16T19:20 +01:00       |
| Complete date plus hours, minutes and seconds (timezone offset)                                 | yyyy-MM-dd'T'HH:mm:ss Z   | 1997-07-16T19:20:30 +01:00    |
| Complete date plus hours, minutes, seconds and a decimal fraction of a second (timezone offset) | yyyy-MM-dd'T'HH:mm:ss.s Z | 1997-07-16T19:20:30.45 +01:00 |

| LEGEND                                                             |
| ------------------------------------------------------------------ |
| yyyy = four-digit year                                             |
| MM = two-digit month (01=January, etc.)                            |
| dd = two-digit day of month (01 through 31)                        |
| hh = two digits of hour (00 through 12)                            |
| HH = two digits of hour (00 through 23) (am/pm NOT allowed)        |
| mm = two digits of minute (00 through 59)                          |
| ss = two digits of second (00 through 59)                          |
| s = one or more digits representing a decimal fraction of a second |
| Z = time zone designator (+hh:mm or -hh:mm)                        |
| z = time zone name designator (eg. CET)                            |

### **Example: Using and configuring a JSon Data Source REST**

The following example shows how to create a report that displays the JSon data.

**Step 1:Creating the Datasource Rest JSon**

![](<../../.gitbook/assets/20 (6)>)

1. To create a new Data Source, select Tools >> Data Sources and choose as the Data Source type Rest/JSon. Select the Configure the Data Source button.
2. By convention, you should enter an alias-name (Main section property). This will then serve to recognize the datasource during the cube and dimension creation phase

**Step 2 Data Source REST Configuration**

![](<../../.gitbook/assets/image (295).png>)

1. In the "Datasource REST Configuration" panel, enter the data source Endopoint.
2. Define the headings (if required)
3. Perform a test to invoke the Endpoint “Test Endpoint Invocation”.

**Step 3 Data Source REST Configuration**



![](<../../.gitbook/assets/image (341).png>)

In the next panel, JSon payload formatting is defined in tabular formatting.

1. On the left is the structure of the JSon file.
2. The Show Sample Data button shows the sample data of the JSon being interrogated.

![](<../../.gitbook/assets/image (730).png>)

On the left select the attributes with a double click. In the Field section there are all the attribute selected. In the Alias column it’s possible to modify the Alias name.

**Step 4 : Mapping Data Source REST JSon**

![](<../../.gitbook/assets/image (711).png>)

* In the table containing the information mapped in the attributes will be created for each array.
* The table will therefore have the same structure as that displayed in the Table Definition section.
  * Select the table key
  * Select the type for each attribute. By default, the system associates the type that corresponds to that of the type of JSon.
* After the mapping is completed, press the Finish button and test the datasource "Test the Datasource" from the main screen.
