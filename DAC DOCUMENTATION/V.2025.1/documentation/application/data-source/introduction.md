# Introduction

### What is a data source <a href="#what-is-a-datasource" id="what-is-a-datasource"></a>

In App Composer, a **Data Source** is a connection that allows the applications to read and write data from various systems or applications. It serves as a pathway for data to flow into and out of these systems. and DAC&#x20;

Data sources are essential for presenting information on [pages](../../page-designer/) using [widgets](../../widgets/). Through configured data sources, App Composer facilitates the visualization and representation of data from external sources directly on the application's pages through reports and widgets.\
\
In a single instance of App Composer, you can create multiple data sources, and within the same application, you can use more than one data source associated to [reports](../../report/) or [widgets](../../widgets/). For example, you can retrieve data from a database in one widget and use the same data to filter a REST request associated with another widget. Using multiple data source, your application is able to fetch and combine data from various sources.\
\
You can configure various types of data sources, including:

* **Relational Databases**: establish connectivity via JDBC with supported relational databases to read and write data. See the dedicated page for the supported database.
* **Flat Files**: read-only connectivity to flat files, such as Excel or CSV files
* **REST JSON**: external services that expose data via REST using a JSON payload can be mapped as App Composer data sources. This capability allows the application to read data exposed through RESTful APIs in JSON format.

It's important to note that the data source stores the settings and parameters for connecting to the remote data source, but it doesn't generate the SQL query itself. Any App Composer object needing a connection to a data source retrieves the connection parameters from the associated data source. This offers exceptional flexibility, as modifying any connection parameter can be done in a single editor.\
\
Additionally, DAC Environment Variables can be used to avoid hard-coding parameters in the editor, providing even more flexibility in the configuration. For example, you can inherit connection properties such as the host, username, and password from a DAC Environment Variable rather than hard-coding it as a property of the data source. When the value of the DAC Environment Variable is modified, the data source will also inherit the new value. This is particularly convenient when you need to synchronize the data source in a production environment or when you have security policies such as password rotation. Using a DAC Environment Variable prevents the need to change the data source every time the value is modified. Please refer to the[ advanced configuration](advanced-configurations-and-properties.md#using-dac-env-in-a-data-source) for more information.

{% hint style="warning" %}
When creating a data source in App Composer, ensure that both Design Studio and Runtime can establish a connection with the data source. Infrastructure configurations or security policies, such as VPN, firewalls, network restrictions, ACL, etc., may potentially prevent a successful connection.
{% endhint %}

### Data Source Editor

Connections are created in the **Data Source Editor**, which you can access from the **Tools** menu in **Design Studio**. Data Sources are created in Design Studio and are used by both Design Studio and runtime.

The data source interface is divided into three main sections:

<figure><img src="../../../.gitbook/assets/image (431).png" alt=""><figcaption></figcaption></figure>

1. **Data sources catalog:** this section lists all the Data Sources that have been previously created in the current DAC instance.
2. **Main Properties:** in this section, you can configure the main properties for the selected data source. When you select the **Database Type**, the configuration panel will change accordingly to the type of data source, allowing you to enter the required information. Please refer to the dedicated [chapter ](data-source-type/)for more details.
3. **Advanced Properties**: this section includes advanced properties that you can configure for the selected data source. Some properties are shared across all types of data sources, while others may be specific to the selected database type.

In the main properties section you can configure the most important properties for the data source, such as:

<figure><img src="../../../.gitbook/assets/image (1920).png" alt=""><figcaption></figcaption></figure>

1. **Database Type:** select the desired data source type, such as relational databases, REST APIs, or flat files.
2. **Database Connection:** configure here the necessary credentials/connection parameters to establish the connection to the destination database. This section may change accordingly to the selected database type.
3. **JDBC String:** as alternative to the connection parameters, you can manually input the JDBC connection string, providing more flexibility or the usage of advanced parameters in the connection configuration.
4. **Test Connection:** This function allows testing the connection to the data source to ensure that all settings are correct and that the connection to the database occurs successfully.
5. **Configuration Properties:** This step allows defining additional properties of the data source, such the alias or more specific properties.

### Creating a data source <a href="#creating-a-datasource" id="creating-a-datasource"></a>

Here is a step-by-step guide to creating the first data source:

1. Open the Data Source Editor from the Tools menu in the Design Studio.
2. Select "New" to create a new data source.
3. Insert the name and click enter.

<figure><img src="../../../.gitbook/assets/image (1921).png" alt=""><figcaption></figcaption></figure>

4. &#x20;In the central section, select the desired Database type.

<figure><img src="../../../.gitbook/assets/image (1922).png" alt=""><figcaption></figcaption></figure>

5. Insert the database credentials to establish a connection to the database.
6. Click on "**Test Connection**" to verify the validity of the connection parameters.
7. Set an alias for the data source&#x20;
8. Configure additional properties of the Data Source, if necessary.
9. Save

{% hint style="success" %}
To know in detail how to configure the properties in the step 5,7 and see the chapter [Datasource Type](data-source-type/)
{% endhint %}

### App Composer objects associated to a data source <a href="#app-composer-objects-associated-to-a-datasource" id="app-composer-objects-associated-to-a-datasource"></a>

The objects in the DAC that can be associated with a Data Source are:

<table data-full-width="true"><thead><tr><th width="263">Object</th><th>It is used</th></tr></thead><tbody><tr><td><a href="../">Application</a></td><td>As default data source for the selected application</td></tr><tr><td><a href="../../data-mapping/cubes-and-measures/">Cube</a></td><td>As data source where to execute the SQL query automatically generated by DAC</td></tr><tr><td><a href="../../data-mapping/dimensions/">Dimension</a></td><td>As data source where to execute the SQL query automatically generated by DAC</td></tr><tr><td><a href="../../report/sql-report.md">Report SQL</a></td><td>As data source where to execute the SQL query automatically generated by DAC</td></tr><tr><td><a href="https://widgets.decisyon.com/smart-grid/documentation/smart-grid-10.0.3/editing/advanced-configurations#auditing">Report / Property "auditing"</a></td><td>As target data source where to store auditing information of the Smart Grid widget</td></tr><tr><td><a href="../../sdk-and-api/code-snipped-editor/">Code Snippet</a></td><td>In the Java code to establish the connection the data source, preventing the hard-coding of connection parameters</td></tr><tr><td>Page / Pre-selection vales</td><td>In the SQL query of pre-selection values to specify in which data source the SQL query must be executed</td></tr><tr><td>Widget "Textfield"</td><td>As data source where to execute the defined query</td></tr><tr><td>Widget "Execute Button"</td><td>As data source where to execute the defined query</td></tr></tbody></table>
