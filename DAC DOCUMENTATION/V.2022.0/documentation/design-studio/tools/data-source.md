---
description: >-
  DAC-DS allows you to configure connections to other systems, reachable in JDBC
  mode.
---

# Data Source

## Introduction

DAC-DS allows you to configure connections to other systems, reachable in JDBC mode. The connections are used to access the data in those systems. Data sources are used in DAC for various purposes:

* as a remote data warehouse of an application
* to map dimensions or cubes on remote systems
* to present them on Pages

Connections are available for:

* predefined databases, indicated in the installation guide (data sources compatible with DAC)
* non-predefined databases
* flat file (Excel, CSV and XML)
* Web Services
* Data Source Rest JSon.

Big Data or In Memory type data sources are defined in this module as well.

Connections are managed in the **Data source** module, that is accessed from the **Tools** menu item.

![](<../../../.gitbook/assets/image (235).png>)

The **Test** button performs a connection test, using the parameters entered for the data source.

The data source properties are divided into general ones, which are valid for all data source types.

(**Main** group), and specific ones, for the data source type (**Database** group). Only certain types of databases have specific properties.

The properties of the Main group set:

* **alias-name** necessary to use the data source as the data warehouse of an application or for the mapping of dimensions and cubes.

This name will appear in the list of the external data sources (**Remote**)

* **max-rows-selected** to define the maximum limit allowed for responses to queries on the data source
* **is-read-only** for data sources where writing is not permitted; the flag is already selected for the native data source for reading only, like the flat files.

The native data sources for read only have the property enabled and are not modifiable; some example are the flat files, Historian, etc.

If the property is disabled, i.e. for NOT READ-ONLY data source, the property is available:

* **integrate-metric-functions** can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the metric- functions, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.

Some data sources do not perform well when executing metric-functions (which mainly consist of operations to UPDATE the data in the temporary tables). Instead in the Database group some specific properties of the database are reported. They coincide with the system ones, Database section.

For the **connections to flat files** the file must be present on the Client of DAC and on the DAC Server.

![](<../../../.gitbook/assets/image (241).png>)

## Predefined RDBMS

The file on the client is used to define the selection queries: the file is actually structured by the system in the form of a table (with the respective fields). The file on the server will be used when the connection to the data source has requested access to the data.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds3.png)

Database type selectionPredefined JDBC connection string

The parameters indicated between the # sign in the predefined string are replaced.

After compiling the JDBC string, the following fields need to be entered:

* database access credentials (**Login/Password**)
* the **JDBC driver**; for the systems supported by DAC Data Model the JDBC driver used by DAC-DS is automatically proposed (flag **Use default JDBC driver**).

When settings differ from the default settings, deselect the flag and enter the name of the driver in **JDBC Driver.**

Some types of databases (selected in the menu above) do not have the JDBC driver in the DAC libraries (e.g. MySQL or Teradata). In this case, you are informed with an error message and invited to load the file in the appropriate location.

The driver must be provided by the database vendor (usually available on the Internet, on the vendor's support web site).

* the **connection pool is** required and must be indicated in the **JDBC** **pool field (JNDI name)**

For data sources on databases, properties (Storage tables schema) are available for selecting the target schema of the temporary tables. The properties are as follows:

* **report-final-tables**: tables containing the DataMart of the reports (“FX” prefix)
* **report-interm-tables:** tables created in the intermediate stages of running reports (“DX”,”TX”,”UX” prefix)
* **excel-integration-tables**: the screen where the integration table will be saved when the associated data source is Executive Object, as Excel Integration.

The default for each property is the same as the default for the detail parameters that define the data source itself. For example, the default for Oracle coincides with the login user, however the default for SQL Server coincides with the default associated with the user login, etc.

Specific properties are available for certain types of data source environments for the temporary tables generated by the system (Report temp tables group). Good configuration allows performance to be improved. These properties are only used for data sources enabled for writing (not read-only): in this case, temporary tables are generated on the data source.

The properties for data sources on **Oracle** are:

* **nologging-on-create-table**
* **custom-tablespace** and **tablespace-name**
* **purge-on-drop**

The properties for data sources on **MySql:**

* **mysql-storage-engine**

The properties for data sources and **AS400:**

* **createTableAs-withData**

The properties for data sources on **Oracle, SQLServer, Sybase** and **Sybase IQ:**

* **global temp-table**

### Excel Files

For the connection to Microsoft Excel, proceed as follows:

1. Select Excel file (.xlsx) as data source type.
2. In **File Path on Client** enter the path, including the Excel file on the client. The Browse button opens the window to select the file.
3. In **File Path on Server,** enter the path, including the Excel file on the DAC server. The path must start from the name of the unit present on the AS server, which must have visibility privileges on the folder where the file resides.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds5.png)

Some validation criteria exist, which are applied to the Excel type data source:

* The name of the Excel file and the names of the first row of the same file must start with a letter
* The names of the columns can start with a character or with “\_”
* The first row cannot be empty

The first line of data cannot be a numerical value and the successive ones text, the contrary is allowed. Textually defining the values in the first line of data is sufficient (putting the first character in the cell for the first value).

### CSV Files

Proceed as follows to connect to a CSV file:

1. Select **CSV file** as data source type.
2. Enter the path, WITHOUT the name of the local file, in **File Path on Client**. The Browse button opens the window to select the file.
3. Enter in **File Path on Server**, the path, WITHOUT the name of the file on the DAC AS server. The path must start from the name of the unit present on the AS server, which must have visibility privileges on the folder where the file resides.
4. Type the separator of the values (**Values** **Separator**), the **File Extension** and if the first row must be used for the names of the columns (**Use** **first row as column names**).

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds6.png)

If several CSV files exist in the folders indicated, the system will interpret them as different schemes/catalogs.

### XML files

Proceed as follows to connect to an XML file:

* Select XML file as datasource type
* In the **Xml File connection** section, enter:

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds7.png)

1. In **File Path on Client** the path, including the local XML file. The Browse button opens the window to select the file.
2. In **File Path on** **Server** the path, including the XML file on the DAC server. The path must start from the name of the unit on the server, which must have visibility privileges on the folder where the file resides.

In the **Xml mapping** section set the mapping to build a table, which is then used for the queries:

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds8.png)

* \<table> node, the mapping for the table is defined:
  * in **name**, the name you want to give the table
  * in **path**, identifies the element in the source file containing the information of interest
  * in **dateFormat**, the format of the dates in the table
  * in **namespaces**, the grouping of names under a single ID which is required to define the pertinence of the various TAGS used in the XML file
* node \<column>, the individual columns in the table are defined, indicating:
  * in **name**, the name of the column
  * in **path**, the path where the datum is contained in the XML file relating to the column
  * in **type**, the data type

### **Connection Example to XML Files**

The example proposes the configuration for the connection to an XML file containing information of the employees.

**Connection Example to XML Files**

The example proposes the configuration for the connection to an XML file containing information of the employees.

**Step 1: XML Files Connection**

![](https://gblobscdn.gitbook.com/assets%2F-LwNIm22v7i4UWM_U60u%2F-MLl__tN1E_UqA0Kgdri%2F-MLlbX-BR9NM_zcb8LAv%2Fimage.png?alt=media\&token=7dfe3153-bdff-41df-b6d3-cbfdb88a383c)

The source file consists of a series of elements empl:employee, which identifies an employee.

Every element empl:employee consists of a set of elements that contain the information relating to the employees.

At the top the example of a source file is shown.

The file contains the information relating to employees. In detail the variables contain the following information:

* \<empl:first\_name>Bill\</empl:first\_name> Name of the employee
* \<empl:last\_name>Adams\</empl:last\_name> Last name of the employee
* \<empl:age>25\</empl:age>  Age
* \<empl:hire\_date>12-06-1995\</empl:hire\_date> Date of birth
* \<empl:title>Java programmer\</empl:title> Title.

The file must be then selected in the data source.

[**Step 2: XML Mapping**](https://docs.decisyon.com/data-source/)\*\*\*\*

\*\*\*\*

**Step 2:** **XML Mapping**

![](https://gblobscdn.gitbook.com/assets%2F-LwNIm22v7i4UWM_U60u%2F-MLl__tN1E_UqA0Kgdri%2F-MLlblMP91M_2UZWHBCq%2Fimage.png?alt=media\&token=7e2b5296-8363-4e43-8023-e8a0d0b36e4f)

\*\*\*\*

The information mapped in the source file will be entered virtually into a temporary system table. The figure shows the code for the configuration of this table.

* **name="employees"** Name of the temporary table
* **path="/empl:employees/empl:employee"** identifies the element of the source file from which to acquire the data (employees see example above)
* **dateFormat="dd-MM-yyyy"** the format of the dates in the table
* **namespaces="empl:**[http://www.example.com/employees"\&gt](http://www.example.com/employees%22\&gt)**;** the grouping of names under a single identifier which is required to define the pertinence of the various TAGs used in the XML file

Declaration of the columns of the table

* **\<column name="firstname"** : Name of the column
* **type="string"** : type of column, if string or numeric
* **path="empl:first\_name"** : identifies the information to be entered in the column

### REST /JSON

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec ullamcorper mattis, pulvinar dapibus leo.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds12.png)

To configure the data source, select the REST JSon item from the Select Data Source Type menu.

Select the **Configure** button to open the Data Source REST configuration panel.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds13.png)

The parameters you can configure for the data source are:

* **Endpoint**: insert the **Endpoint** where the REST service is available using GET HTTP method.

The endpoint allows the use of variables in the path and the query string.Es: [http://localhost:8081/weather/\{{city\}}?day=\{{day\}}](http://localhost:8081/weather/%7B%7Bcity%7D%7D?day=\{{day\}})

These variables can also be used in the Headers' values. The parameter must be enclosed between double braces.

It also be possible to use some keywords between percent symbols as placeholder form as environment information of the bound services:

* **%ACCESS\_TOKEN%** for the Access Token.
* **%TIMESERIES.ZONE\_ID%** for the timeseries Zone-ID.
* **%TIMESERIES.URI%** for the timeseries url.

Keywords that will contain the info of the bound ASSET service are :

* **%ASSET.ZONE\_ID%:** for the asset Zone-ID.
* **%ASSET.URI%:** for the asset url.

Keywords that will contain the info of the bound ANALYTICS FRAMEWORK service are:

* **%ANALYTICSFRAMEWORK.ZONE\_ID%** for the analytics framework Zone-ID **.**
* **%ANALYTICSFRAMEWORK.CATALOGUE\_URI%:** for the analytics framework uri.

**Example:**

_\*\*_%TIMESERIES.URI%/v1/datapoints?query={"start":1472428800,"tags"\[{"name":"SENSOR\_033","limit":100}]}

**Headers**: define the http’s Headers

* Select the button (+) to insert a new row.&#x20;
* **Key** defines the name of the header (e.g. <**Content-Type**: text/html>
* **Value** defines the value of header (e.g. \<Content-Type: **text/html**>)
* Select the button (X) to remove a selected row.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds14.png)

**Set variables’ default values:** Enables a panel in which you can define the default values of the variables, if provided in the endpoint and / or the headers value.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds15.png)

Example of endpoint with variable: [http://localhost:8081/turbines?type=\{{type\}}](http://localhost:8081/turbines?type=\{{type\}})

When the "type" variable is valued, the values returned by the JSon will be filtered for that value.

The parameter can be used to filter the pages where, for objects that use this data source, you can map the parameters of the page, with the variables used for its definition.

**Authentication:** If necessary to configure the basic authentication credentials to access the API, enable the basic Authentication properties and insert username and password.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds16.png)

After configuring the invocation, select the test button to test it.

**Mapping JSon in a tabular format**

At the next step of the wizard, JSon mapping is executed in tabular format. Conversion to tabular format will then allow you to create cubes and dimensions for reporting and page analysis.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds17.png)

\*\*\*\*

* **JSon Schema:** Displays the structure of the JSon that is being interrogated.The JSon schema can have a complex structure, JSon Object, to which the JSon Attribute is associated.
* **Show Sample Data:** Opens a window where you can consult the JSon you are querying with data.
* **Row Element:** Defines which JSon Object identifies the information displayed in the table. For example, if you select the "Citizens" object, then for each citizen in a city in the JSon payload, a row in the table will be created with the respective information.
* **Fields**: Defines which JSon attributes will be mapped as table fields. You can define an alias for each attribute. The alias will be identified by the system as the logical name of the attribute.
* **Active Paging**: Enable or disable the pagination. If enabled, it allows you to select which json attribute will be used for paging.
* **Table Definition:** Defines the type and key for each field in the table.
  * **Key**: Through a flag determines which fields identify the primary key of the table.
  * **Type:** The type of data format. The box selection will activate a menu that will allow you to select one of the following STRING, INT, DOUBLE, LONG, DATETIME (see the pattern that can be used) and BOOLEAN formats.

For the Array Type JSon Attribute, you can specify the element of the array to be considered.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds18.png)

In brackets there is a number that can be edited (see figure above). This represents the array index location location. In this example, the item of position 0 is taken.

To retrieve all rows of an array attribute, you need to set in the attribute configuration instead of row index, an asterisk.

* e.g jsonAttribute\[\*]\[1] to retrieve all the value of the second column of the matrix;
* e.g. jsonAttribute\[\*] to retrieve all the value of the array attribute

N.B. the RowElement is no longer mandatory

**Note:** it’s possible to map in the REST Datasource a JSON that contains two nested arrays.\
In this way it’s possible to transform it in a tabular format and use it in a report or chart

**CONSTRAINTS**

* You can configure only one of special array (e.g. jsonAttribute\[\*]) or special matrix (e.g. jsonAttribute\[\*]\[1])
* When a special array is configured, the rowElement selected have to be the parent attribute
* When a special matrix is configured, the alias name can not be the same as the matrix attribute name
* **Show Content Simple:** the button displays the data extracted from the JSon file in tabular format

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds19.png)

\*\*\*\*

### **Patterns**

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

| LEGEND                                                                   |
| ------------------------------------------------------------------------ |
| yyyy = four-digit year                                                   |
| MM   = two-digit month (01=January, etc.)                                |
| dd    = two-digit day of month (01 through 31)                           |
| hh     = two digits of hour (00 through 12)                              |
| HH    = two digits of hour (00 through 23) (am/pm NOT allowed)           |
| mm   =  two digits of minute (00 through 59)                             |
| ss     = two digits of second (00 through 59)                            |
| s       = one or more digits representing a decimal fraction of a second |
| Z       = time zone designator (+hh:mm or -hh:mm)                        |
| z       = time zone name designator (eg. CET)                            |

###

### Example: Using and Configuring a JSon Data Source REST

**T**he following example shows how to create a report that displays the JSon data.

The main steps are:

* Creating the Data Source REST JSon.
* Dimension mapping.
* Cube mapping.
* Creating the report.
*

{% tabs %}
{% tab title="Step 1" %}
Creating the Data Source Rest JSon

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds20.png)

\*\*\*\*

1. To create a new Data Source, select Tools >> Data Sources and choose as the Data Source type Rest JSon. Select the Configure button.
{% endtab %}

{% tab title="Step 2" %}
**Data Source REST Configuration**

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds21.png)

1. In the “Datasource REST Configuration” panel, enter the data source Endpoint.

For this example, authentication credentials are not provided.

1. Perform a test to invoke the Endpoint Invocation Endpoint.
{% endtab %}

{% tab title="Step 3" %}
**Data Source REST Configuration**

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds22.png)

In the next panel, JSon payload formatting is defined in tabular formatting.

1. On the left is the structure of the JSon file.
2. The Show Sample Data button shows the sample data of the JSon being interrogated.

In this example we can distinguish as JSon Object Turbine while JSon Attributes are Type, Number of Laps, Date, and AVG Power Detected.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds23.png)

1. For the mapping, select the Turbo Object as Row Element.This means that a row in the table containing the information mapped in the attributes will be created for each turbine.
2. The table will therefore have the same structure as that displayed in the Table Definition section.
   1. Select the table key.
   2. Select the type for each attribute. By default, the system associates the type that corresponds to that of the type of JSon.

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds24.png)

3.After the mapping is completed, press the Finish button and test the data source “Test the Datasource” from the main screen. By convention, you should enter an alias-name (Main section property). This will then serve to recognize the data source during the cube and dimension creation phase
{% endtab %}

{% tab title="Step 4" %}


For dimensional mapping for the remote data source, see Dimensions / Name and Data Source (STEP 1)

· For cube mapping on the remote data source, see the Cube and Measurements / Name and Data Source (STEP 1) section.
{% endtab %}

{% tab title="Step 5" %}


**Report File JSON**

![](https://docs.decisyon.com/wp-content/uploads/2021/01/ds25.png)

The example shows how JSon data is displayed in a report. It should be noted that for each turbine all the information contained in the JSon attributes is shown.

For the attribute that contains the array of numbers (N ° of Laps), the position element 0 was considered as specified at the mapping stage.
{% endtab %}
{% endtabs %}
