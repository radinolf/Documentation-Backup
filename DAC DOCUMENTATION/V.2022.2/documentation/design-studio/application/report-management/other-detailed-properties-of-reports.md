# Other Detailed Properties of Reports

There are also several properties that define:

* [the aliases for the metrics and the levels used](other-detailed-properties-of-reports.md#metric-aliases-and-report-levels) by the report
* the [positioning of lines/columns](other-detailed-properties-of-reports.md#row-column-positioning-activate-sorting)
* to define custom functions in addition to standard DAC functions
* defining [the type of](other-detailed-properties-of-reports.md#report-indexing) indexing to apply
* defining [the type of join](other-detailed-properties-of-reports.md#join-type) to apply to levels and metrics
* activating the [debug mode](other-detailed-properties-of-reports.md#debug-report)
* setting any [test parameters](other-detailed-properties-of-reports.md#test-parameters)
* copying the report on a [table](other-detailed-properties-of-reports.md#table-write)
* activating the [update of a recursive dimension](other-detailed-properties-of-reports.md#recursive-dimension-update) (see _Mapping on Levels with Recursive Hierarchy (Parent-Child) section_)
* starting [a](/broken/pages/-MjE95PeRg5AqHCpE5Xs#_Avvio_di_un) [custom program](other-detailed-properties-of-reports.md#tracking-report-execution)
* to enable report [tracking ](other-detailed-properties-of-reports.md#tracking-report-execution)on system LOG files
* disabling the [user filters](other-detailed-properties-of-reports.md#disabling-the-user-filters-on-the-report)
* configuring the [number of visible records on](other-detailed-properties-of-reports.md#configuring-the-number-of-visible-records-for-a-report) the report
* changing permissions [on report](other-detailed-properties-of-reports.md#permissions-on-web-functions) web functions
* defining SQL [interactions](other-detailed-properties-of-reports.md#sql-interactions) with the report
* Advanced properties of the Report

### Metric Aliases and Report Levels

DAC allows you to rename the metrics and the levels found in a report by defining aliases.

Aliases are very useful when metric or level names are long, hard to understand, because they were defined for general analysis on application reports, and are inappropriate for the type of analysis carried out.

This gives you the opportunity to use the same metric or level with different names without having to create a copy of the object for the sole purpose of changing its name.

Aliases for the levels and the metrics in a report are defined by setting the properties of the **Aliases** group in the report editing window.

This group includes the two properties:

* **alias-metric,** to set metric aliases
* **alias-level,** to set aliases for dimensional levels

By selecting the **alias-metric** property, the system displays all metrics found in the report. Using **alias-level**, the report levels are shown.

Step 1: Report with No Alias

![](<../../../../.gitbook/assets/0 (7).png>)

_This example shows how to set aliases for report levels and metrics._

_The report shows metrics and levels with the names defined at the moment of creation._

Step 2: Setting Aliases for Levels and Metrics

![](../../../../.gitbook/assets/1.png)

_Aliases are set in the window of properties of the report (Picture 2)._

_We have defined the following aliases:_

* _for the metric Sales Qty we have set the alias Sales Quantity,_
* _for the level Ds Customer we have set the alias Customer Description._

Step 3: Reports with Aliases Associated with Metrics and Levels

![](<../../../../.gitbook/assets/2 (18).png>)

_The report shows how metrics and dimensions are displayed after_ _the alias has been associated._

#### Parametric Aliases

Metric and level aliases can also be defined parametrically, that is, it is possible to enter parameters within the corresponding properties. The parameter will be valued later in a selection or input component (see _Presentation Administrator_, _Selection and input objects_ section), or from an exported level (see _Presentation Administrator_, _Exporting dimensional levels_ section): the parameter value will later replace the alias of the metric/level.

The example below shows a solution of this type, where the name of a metric depends on the year, and is selected from a check list.

Step 1: Creating Reports and Defining Aliases

![](<../../../../.gitbook/assets/3 (28).png>)

_The report in the figure shows sales by region according to the year selected in page-by_

_A parametric alias has been set for the Sales Qty metric._

_The syntax is as follows:_

&#x20;_“SALES BY ?YEAR?”_

_where ?YEAR? is a parameter, which will be transferred from a check list, created in the next step_

Step 2: Creating Pages

![](<../../../../.gitbook/assets/4 (10).png>)

_We build a Page with the following elements:_

* _Check List with a list of years (set in sql-formula)._

_The name of the component should be the same as the one defined in the alias parameter: “YEAR”._

* _Crosstab with previously created report_
* _Graph associated with the same report._

_Filter the level Year of the crosstab and of the graph for the parameter defined in Check List._

Step 3: Display in DAC

![](<../../../../.gitbook/assets/5 (27).png>)

_STEP 1: Note that on first access the Sales by ?YEAR? metric, found both in the report and in the graph legend, still has not been valued, as no year has been selected._

_STEP 2: We choose the year 2005 from the Check List, and the metric with the parametric alias is valued with the selected year._

_This behavior is visible both in the report and in the legend._

### Row/Column Positioning (activate-sorting)

DAC allows you to change the arrangement of rows and columns in a report, through simple drag & drop operations.

The sorting functionality for rows and columns should be activated through the report _**activate**-sorting_ property (_Main_ group) which allows users to shift the row/columns in the report (the shift is not performed on the aggregating levels, but only on the detail levels).

This property enables the following:

* _**sort-axis**_ to enable the shift of rows alone _\<rows-only_>, columns alone _\<cols-only_> or both _\<both>_
* _**index-by-levelKey**_ to maintain the chosen sorting even during a level shift; this property allows users to index rows or columns with respect to the shifted level only, rather than to the whole row. It is then possible to maintain the chosen sorting, even if the aggregating levels are shifted (see next example).

**Note:** The number of rows that are indexed for placement is equal to 1000.

If you insert a custom total, the activate-sorting property is automatically enabled. According to the position of the total (column/row), the system automatically sets the _sort-axis_ property with the corresponding sorting (row or column only).

![](<../../../../.gitbook/assets/6 (7).png>)

When the _**sorting**_ property is activated, an icon will appear on the top left corner of the report to indicate that it is possible to carry out sorting operations on the rows of that report .

Step 1: Sorting Rows and Columns

![](<../../../../.gitbook/assets/7 (26).png>)

_We activate the sorting function for rows and columns by selecting the activate-sorting property (flag selected)._

_In the report it is now possible to shift the rows of the level of detail (Product), whereas the rows of the aggregating level (Category) cannot be shifted. In the example, Product 14 of Product Family 10 is dragged under Product 124._

_The section highlighted in yellow shows the position the report cell is shifted to._

Step 2: Sorting Rows and Columns

![](<../../../../.gitbook/assets/8 (6).png>)

_If we shift in page by the aggregating level (Category), the report does not maintain the initial sorting:_

_Product 14 is no longer under Product 124, but goes back to its initial position._

Step 3: Sorting Rows and Columns

![](<../../../../.gitbook/assets/9 (24).png>)

_If we activate the index-by-levelKey property, we can instead fix the rows and columns of the report in the desired position._

_If we shift the column for the category in page by, the chosen sorting will be maintained._

### Report Indexing

DAC allows users to create indexes for reports carrying a high volume of information, which provides a quick and efficient way of processing data. The indexes are created in the table of the final datamart associated with the report and they are updated automatically every time you add filter criteria to the report relating to:

* Page-By
* User filters, only if applicable to the result of the report
* View filter

Indexes related to filter criteria are created in the course of the navigation of the report and even before this is executed. At every change of page-by or of data selection criteria, the system will then create an index, unless this can already be found inside the table. If the index for the columns in the report has already been created, the system will not create a new index, but it will use the one that already exists.

Indexing is done through the **indexingType** property (_Main_ group), where with:

* _\<no-index>_, default setting, indexing is disabled
* _\<Index-cache-only>_ indexes are created only for reports in cache. In this case, Indexes created on request by one user during navigation are made available to all the others
* _\<Index-_&#x61;lways> always indexes the report, whether in cache or not

Example: Report Indexing

![](<../../../../.gitbook/assets/10 (26).png>)

_In the picture, before executing the report, we can see how the system automatically creates indexes for the corresponding levels in page by, that is, for product and month:_

_MONTH\_ID, PRODUCT\_ID._

_If you insert a view filter in the report: Business\_Unit =2_

_a new index will be created:_

_MONTH\_ID,PRODUCT\_ID,BUSINESS\_UNIT._

### Join Type

It is possible to combine data for metrics and dimensions in a report by defining the type of join to carry out for each element.

The _**metricsJoin**_ and _**dimensionsJoin**_ properties, found in the report editing window, in the section for the Join group, allow you to select the type of join to perform on basic metrics and dimensions of a report. The possible values are _Inner_ and _Outer_ . By default the system uses _**Outer Join**_ excludes rows containing null values.

The _**metricJoin**_ property allows users to apply the type of join on the basic metrics of the report, while _**dimensionsJoin**_ applies the join to dimensions.

The outer join between the metrics can only be implemented for databases supporting the syntax of outer join with the operator (+) (such as Oracle and SQL Server). The inner join allows you to recover only the levels for which the basic metric is valued. The operation of outer join instead allows users to recover also the levels for which the basic metric is not valued.

The _**join-global-names**_ property activates the join of information based on the global name of the levels. If a level in the report cannot be grouped from a cube, a check will be performed on whether a level exists relating to a dimension associated with the cube and that has the same global name. If that is the case, thie global name will be used instead of the “missing” one.

The _**allow-cartesian**_ property, if activated, allows users to enable execution of the report even if the latter generates, on execution, a cartesian.

See the example below of the use of the _**metricsJoin**_ property and of the _**dimensionsJoin**_ property.

Step 1: Dimensions in INNER Join

![](<../../../../.gitbook/assets/11 (25).png>)

_Let’s assume we want to display the data for quantities sold of products 112-113-114-115 and 116 for month 200507. As you can see in the figure, only quantities sold for products 114 and 115, the only two valued, are displayed. This is due to the fact that the system automatically excludes NULL values inside the report because it uses by default the INNER JOIN on the dimensions._

Step 2: Dimensions in OUTER Join

![](<../../../../.gitbook/assets/12 (17).png>)

_If we wanted to display products that have no quantity sold for the month 200507, we would just have to set the OUTER JOIN property on the dimension of the product._

Step 1: Metrics in INNER Join

![](<../../../../.gitbook/assets/13 (16).png>)

&#x20;_Let’s assume we want to display the data for quantities sold of products 10-107-117 for year 2004. As we can see in the figure, only quantities sold for products 10, the only one valued, are displayed. This is due to the fact that the system automatically excludes NULL values inside the report because it uses by default the INNER JOIN on the metrics._

Step 2:Metrics in OUTER Join

![](<../../../../.gitbook/assets/14 (11).png>)

_If we wanted to display even products with no inventory quantity for \[the month] the year 2004 , we would just set the OUTER JOIN property on the metrics for the budget and the \[inventory]._

### Debug Report

The _**debug-mode**_ property (_Main_ group) allows users to display on request, in DAC, the code SQL generated for the report and the number of executions.

If the debug has been activated, we display in DAC the Debug Info property in the contextual menu of the report.

![](<../../../../.gitbook/assets/15 (14).png>)

When we select this item, a window will open with information on the report, such as:

* report name and ID
* use of cache with date of creation
* execution times
* rows found in datamart

The figure shows an example debug window.

![](<../../../../.gitbook/assets/16 (10).png>)

### Test Parameters

A report may contain parameters, inserted for example inside a metric or on a filter condition.

When you run the report in the DAC the system expects them to receive a value, for example, from parameters in the Page that publishes the report.

In the report development phase, you need to set the values of those parameters, in test mode: this will open a window of the type shown in the figure below, to provide these parameters with values.

![](../../../../.gitbook/assets/17.png)

These parameters may be defined before by opening the same pop-up with the property:

* _**testParams**_ (_Main_ group) to define any parameters in the report

The parameters, as mentioned above, may relate to:

* **Dimensional levels** in this case, you can either manually enter the value, or by selecting it from the pop-up menu. The menu is activated by clicking on the _**Value**_**,** which will display the list of all values associated with the level selected as a parameter.

![](<../../../../.gitbook/assets/18 (14).png>)

* **Metrics**: in this case you can enter the value manually only (see following figure)

![](<../../../../.gitbook/assets/19 (2).png>)

When the parameters are entered in [the prompts](/broken/pages/-MjE95PeRg5AqHCpE5Xs#_Prompt_dei_parametri) of your report, the **Init** and **Default** buttons are enabled. These allow you to save, respectively, the values entered as default or initialize the values to those defined as default. For details see [Report parameter prompts section](/broken/pages/-MjE95PeRg5AqHCpE5Xs#_Prompt_dei_parametri)

### Table Write

It is possible to activate the creation of a table that can contain a copy of the report using the property (_TableWrite_ group):

* _**activateTableWrite**_ enables the following properties for the creation and configuration of the table, which will contain the report data:
  * _**drop-create**_ enables the deletion and later creation of the table, on every report execution; if the property is not enabled the table is only emptied (DELETE-INSERT and repopulated).

This property is especially useful if the report is not _stable_, that is, if the report undergoes changes, such as addition of levels and/or metrics:

in these cases, if the _drop-create_ property is not enabled, the system notices a discrepancy between report and table columns and returns an error message.

Therefore, if you use the DELETE-INSERT mode (i.e. if the property is disabled) the report's structure cannot change after the first creation of the table.

*
  * _**write-content-type**_ sets the type of content of the table, i.&#x65;_**., the columns generated for the table:**_
  * with < _report-datamart > the_ columns coincide with those of the [datamart](/broken/pages/-MjE95PeRg5AqHCpE5Xs#_Report_datamart).
  * with < _report-body >_ the columns coincide with the report elements; therefore columns to contain composite metrics, not in the datamart, will also be created, while columns for component metrics will not be created.

Step 1: Creating Report

![](<../../../../.gitbook/assets/20 (14).png>)

_You can create a report with the dimensional levels and the desired metrics._

_In the report in the example the levels are Customer Group and Customer Description while the metric of reference is Sales Quantity._

_Enable the activateTableWrite property, in the table-name property enter “Customer\_Group”, the name of the table that will be created in the database. Finally the report is executed._

Step 2: Customer Group Table

![](<../../../../.gitbook/assets/21 (5).png>)

_Accessing the metadata database, we display the Customer\_Group table with the data for the previously created report._

_The names of the columns in the table correspond to the logical name set at the time when dimensions and metrics were created._

### Recursive Dimension Update

DAC dimensions also support the mapping of structures with recursive hierarchies. Used for structures on homogeneous elements, such as a company organizational chart (see _Mapping on Levels with Recursive Hierarchy (parent-child)_ section), dimensions of this type are supported by a denormalization table that contains information on the hierarchy, facilitating the management of asymmetric branches and preventing the drill to empty levels.

The table is generated during the creation of the dimension itself, but you may need to to update it. For example, an update may be necessary because a new branch was added to the structure, or a new child was added to one of the levels.

The table is updated each time the report is run (only if it is not in cache), if the _**denormalize-PC-hierarchies**_ property is enabled in the _Execution_ group.

Therefore, this property can be used to schedule the update of the denormalization table: we just have to enable the property on one of the reports that includes the recursive dimension, and to insert it in an updating rule _with the Scheduler_ module (see the _Scheduler_ chapter).

We remind users that it is possible to configure on the dimension the type of creation of the denormalization table, whether the table is created from scratch or repopulated. If the table is created from scratch, structural modifications to the dimension, such as the addition of another level to the recursive hierarchy, are supported. If the table is repopulated, only the value or number of branches is updated inside the structure.

### Tracking Report Execution

It is possible to choose whether execution of a report should be tracked on the table of Log of the system (table FT\_OBJECT\_EXECUTION found in the Data Model). We choose how execution should be tracked by selecting the _**log**_-_**execution**_ property (_Main_ group).

The values that can be set are:

* _**\<log disabled**_>: no report execution will be tracked.
* _**\<out of cache only>:**_ only the execution of reports not in cache will be tracked. This allows users to highlight only high-cost executions.
* _**\<every execution>:**_ the execution of all reports, both those accessing the cache and those that do not, will be tracked.

The properties can be set at application level, so that a default is applied to all reports in the application.

### Disabling the User Filters on the Report

In DAC, user filters allow you to manage the visibility of data with _respect to groups._

There may be cases where the report does not need to have this type of constraint, for example, because you need to make visible the totals of the data on which the security constraints are placed (for example, totals of asset are visible, while you can only access one region).

This operation is performed through the property (_Main_ group):

* _**advanced**_ which opens a pop-up with the property:
  * _**disable-sec-filters**_ (_Filters_ group) to enable at report level, the use of the security filters; in this case the security filters for the report will be ignored, for each user accessing the same report

### Disabling Temporary Tables in Single Step

For reports that do not require multi-step execution, the use of temporary tables can be disabled:

* _**create-temp-table**_ (_Main_ group) if unchecked, disables the use of temporary tables for the report (disabled by default)

In these cases, the report result not will be saved in the temporary table (table of type FX…) and cache use is disabled.

This property is ignored if the report includes the execution of more than one query (multi-step).

Reports executed in this mode will display in the levels in page-by all the values found in the level registry.For example, if a report has produced results for only three products, all the products found in registry will be listed in page-by anyway.

### Configuring the Number of Visible Records for a Report

Reports in DAC show a maximum number of rows to avoid excessive data loads, which would affect performance.

This limit is set in

* bodyMaxElements (Body _group_) to set the maximum number of elements to display in the report, independently from those extracted (by default it is set to 3,000, the maximum that can be set is 30,000)

If you want the report to contain all data, even in cases where it exceeds the maximum of 30,000, you activate the properties:

* db-paging (large results) (_Body_ group): which enables the paging of the database on the report result, instead of loading the entire data to memory.

The feature considerably speeds up the opening of reports with large amounts of data: only a subset of data from the result is loaded to memory.

In page exchange operations, if necessary, the system loads other result data, by using database functions that allow you to do this.

**Paging** enabled via this property is only compatible with the following databases: Oracle, Sql Server, DB2, AS400, MySQL.

### Permissions on Web Functions

At a single report level, DAC allows users to enable or deny access to some functions, such as data refresh or cell formatting, metric changes, etc. These limitations are added to those granted by the single license.

You can access function or event permissions through the **event-permission** property, in the _**Main**_ group. The events in this window are grouped by type of web license. Each event may be granted or not, by selecting the corresponding check in the _Grant_ and _Deny_ boxes.

![](<../../../../.gitbook/assets/22 (1).png>)

### SQL Interactions

Reports in DAC accept the SQL statements to be run before and/or after execution of the report itself.

These properties are in the SQL group:

* _**sql-pre-execution**_ to define the statement to execute BEFORE the report. Multiple statements are also accepted (separated by '; ')
* _**sql-post-execution**_ to define the statement to execute AFTER the report. Multiple statements are also accepted (separated by '; '). In this statement, you can use the "% DATAMART\_TABLE% variable associated with the datamart generated for the report.

_For example:_

_"Alter session set nls-format = 'yyyy-mm-dd'; Alter table %DATAMART\_TABLE% cache;"_

_To change the date format of the datamart being displayed._

### Advanced properties of the Report

**Export**&#x20;

* **zip-export-file** if enable all report exported will be compressed in zip forma
* **disable-export-limit** if enabled it doesn't check report rows limit during the export

**Filters**&#x20;

* **disable-all-security-filters:** Disable the use of all Security Filter
* **disable-security-filters:** Sets the list of Security Filters to exclude

**SQL-custom**

* **having-clause:** Sets a custom HAVING condition, added to the report read query



## Accessing Reports from External Systems Section

You can call reports defined in DAC with an URL with the following syntax:

_http://<**HOST>:<**:**PORT>/<**/**CONTEXT>/**&#x63;assiopeaWeb/report/report.jsp.cas?revent=_ _LW\_RSTATE\_LAUNCH\_REPORT\&csUsrn=**\<UTENTE**>\&csPass=**\<PWD**>\&csMLO=**\<OWNER**>\&idReportRequest=**\<idReport>**_

where:

_**\<HOST>**_ = name host or application server IP

_**\<PORT>**_ = port of application server

_**\<CONTEXT>**_ = name of DAC application

_**\<USERNAME**_> = username

_**\<PASSWORD>**_ = user password, encrypted (parameter "crypted" set to 1)

_**\<OWNER>**_ = model ID

<_**\<idReport> ID**_ code of the report

The password can be encrypted manually with encrypting mode "encrypt”, found in the "DecisyonCrypter” Java class. You’ll find this class in the library "cassiopea.jar" available in the "lib" folder of DAC.

This allows you to dynamically link DAC reports to external (web-type) applications, for example, by requesting the report filtered by the parameters of the source application.

This type of access opens the DAC interface with a minimized navigation bar, as shown in the diagram.
