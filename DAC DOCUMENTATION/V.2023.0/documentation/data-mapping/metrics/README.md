# Metrics

In the context of the Digital Factory, the metrics of a BI cube represent the measures used to evaluate the performance and activities of the company. A BI cube is a multidimensional structure that organizes data logically and allows for analysis to extract useful information to make informed decisions.

Metrics represent the numerical measures that have been selected to describe the activities of the company. For example, a metric could be the number of sales made in a certain period of time, the number of acquired customers, the churn rate, revenue, market share, profit margin, and so on.

Metrics are used to create reports and pages that provide an overview of the company's performance and identify any trends or issues. These reports can be used to make informed decisions and improve the company's activities.

Therefore the metrics process, in a more or less complex manner, the _quantitative_ values in the data warehouse, to present them in the report.

DAC provides numerous ways to manipulate these _quantitative_ values, such as:

* set various types of [primary aggregate](./#primary-aggregation) such as sum, average, maximum, count, etc. In addition in DAC it is also possible to define different operations for the [secondary aggregates](./#secondary-aggregation);
* applying a filter (like the last quarter or a particular region);
* select a time rule, among those available on the system, as a way to obtain, for example, the data of the previous year or month, or from the beginning of the year to today's date, and so on;
* choose among the functions supported by DAC to obtain:
  * the best/worst values or the classification with the methods such as the rank, the tile, etc. (advanced functions)
  * incremental sums, previous or subsequent values, etc. (functions on data windows)
  * forecasting assessments, by applying regression rules or time series;
* exploit the ROLAP approach to find the data efficiently, with the dimensioning.

The quantitative dimensions on which to perform analyses, such as turnover, is information in the fact table.

Let us remember that these are the tables used in the mapping of the **cubes**. The **measures** necessary for the analysis are defined in the cubes (_see_ _Cubes and measures_ chap.).

<figure><img src="../../../.gitbook/assets/0 (1).png" alt=""><figcaption></figcaption></figure>

When a Cube is created, the Metrics are also created. They aggregate the sum of the measures selected in the Cube itself, and take the name of First Level Metrics.

All the other processing types, applied to each measure, are instead called advanced metrics.

Finally the metric combinations, through mathematical operations or SQL instructions, are called composite metrics.

Metrics can also be formatted with different colors depending on the pertinent interval of the Metric values.

A graph format can also be chosen for the Metric, such as an indicator, bar or graph.

Other customizations of the metrics concern:

* managing the null values of the Metrics (at both database and datamart level)
* managing the visibility of the Metric for the end users if you want to prevent its use when reports are created or modified, and at the same time make it visible in the reports published on DAC
* disabling Security Filters on particular dimensional levels (particularly useful for showing users the incidence on the total of data pertinent to them, for which they do not have read permission)

The metric management takes place in a window (Metrics Wizard) accessed from the menu item:

**Data Model >> Metrics Management** or from the![](<../../../.gitbook/assets/1 (26).png>) button on the main bar.

![](<../../../.gitbook/assets/2 (2).png>)

The Metrics created in the system are to the left (**Metrics** panel). The details of each Metric are shown on the right when it is selected.

There are three types of Metrics:

* First Level
* Advanced
* Composite

_**First Level**_ and _**Advanced**_ Metrics are hierarchically divided according to the layout indicated in the figure.

Both the folders consist of **CUBE** and **MEASURE** elements. Therefore, for each measure, the related **METRICS** are listed.

As you can see, each element (CUBES, MEASURES and METRICS) is depicted with a specific icon.

CREATING A METRIC involves valuing the following fields:

* **Logical name:** only used by the system
* **Display name:** to define the name to be shown in the report
* **Description**: for the developer's notes
* **Aggregation:** to select the type of primary aggregation you want to set

**Note:**

_We strongly advise against using the same title, even if the system allows it._

_The system warns you when you assign a name that was already used for another Metric by highlighting it in yellow. A tooltip also informs you that the name entered is a duplicate._

_If a Metric with a duplicated name is used in a formula (in Composite Metrics), it will be displayed as the logical name and not the title._

![](<../../../.gitbook/assets/3 (3).png>)

The metrics may be cataloged in folders and subfolders: for the First Level, Advanced and Composite metrics, the folder is created by clicking on the measure with the right button of the mouse. The system activates the pop-up menu containing the create new folder item.

By dragging the metrics it is possible to move them into the subfolders you created.

![](<../../../.gitbook/assets/4 (21).png>)

A pop-up menu can be activated (right-click) on Metrics, for the functions of:

* edit as copy (not available for the first level metrics)
* exchange of the logical name
* object information

The _**Edit as copy**_ function creates a new metric of the same type. However, the logical name and title must be changed since the system requests that the metrics be univocal.

The _**Logical name exchange**_ function exchanges the logical name between two Metrics.

The first Metric is the one used to recall the function. A warning message opens and after you close it, you can select the second Metric.

At the end of this operation, you will find the metrics with the logical names exchanged and all the references to them present in the system (e.g. reports, filters, indicators) will be automatically updated.

When _**object information**_ is requested, a window opens listing the objects used by the Metric. It indicates the type, name and ID.

## First Level Metrics

The **First Level** metrics are associated with the measures chosen in the cube. These are created by the system, at the same time of creating the cube, which generates the sum aggregation metrics of the measures of the cube.

It is not possible to delete a first level metric: to delete one it is necessary to edit the affected cube, access the step of the measure selection (see _Cubes and measures_ chap._)_ and deselect those that you do not want to use anymore.

For example, in the Orders cube, the SALES QTY and SALES VAL measures were chosen.

![](<../../../.gitbook/assets/5 (28).png>)

DAC automatically generates First Level Metrics, that is the sum aggregation (SUM) of the respective column of the Fact Table.

You can make the following modifications on First Level Metrics:

* to the **Display name**
* to the [For](/broken/pages/-MfHs_PiXlCm3eSy1MKC#_Formattazione_delle_metriche)mat
* to the Secondary aggregation

However, we do not advise editing this type of metric, apart from the title. If necessary, you can always recreate a first level metric through the advanced metrics: just select the SUM values (sum) in the primary aggregation field, then make any modifications.

## Advanced Metrics

Advanced Metrics set the functions available on DAC for the measures defined on Cubes. The functions are divided into:

the figure.0‑1

* First Level Aggregation (different from the sum and average of the first level metrics);
* Secondary Aggregation different from the default one;
* Dimensioning;
* Direct filter;
* Time functions;
* Other Functions available on DAC.

Advanced Metric functions are applied to the field associated with the measure selected.

![](<../../../.gitbook/assets/6 (28).png>)

You can create an **Advanced** Metric by right-clicking on the measure, and selecting “Create Advanced Metric” (see the next example).

Step 1: **Start Creating an Advanced Metric**

![](<../../../.gitbook/assets/7 (17).png>)

_Below is an example of the initial steps required to create an Advanced Metric on the sold quantity measure._

* _Select the measure to apply the processing functions to (Sales Qty)._
* _click with the right button of the mouse_
* _select the Create advanced metric item_

Step 2: **Functions Applied to Advanced Metrics**

![](<../../../.gitbook/assets/8 (13).png>)

_When you create an Advanced Metric on the quantity sold, it means that a function will be defined to be applied to the field associated with this measure._

_In this example, the quantity sold is associated with the QTY\_SOLD field in the SM\_FACT\_SALES Fact Table._

_Any function chosen will be applied to the values of this field._

_So the primary SUM aggregation (default) will result in the sum of the SM\_FACT\_SALES and SALES\_QTY, aggregated for the dimensions chosen in the report._

## Composite Metrics

The **Composite** metrics are created starting from simple (first level) or advanced metrics in the application and may combine numeric values, constants, mathematical operators and logics, relating to SQL syntax or to SQL extended to the property language of the database.

The functions supported by DAC may also be applied to the composite metrics.

The creation of a **Composite** metric takes place by clicking with the right button on the _Composite_ folder and selecting the “Create composite metric” item.

When you make the request to create the Composite Metric, fields are enabled for defining the Metric. This is where you also enter the **Formula** used to calculate the Metric values, in addition to the logical name and title.

![](<../../../.gitbook/assets/9 (17).png>)

All Metrics defined (First Level, Advanced or Composite) can be used in the formula. Simply double-click on the one you want to use to move it to the formula area. The Metrics entered are called Component Metrics.

The operators and the brackets will help the user correctly write a formula allowing him to enter the correct spacing. For this reason, we recommend using this method as much as possible when writing a formula.

Whether or not this method is used, the green check button will let the user control the syntactic correctness.

In a formula of a composite metric it is also possible to use some parameters which show the dimensional levels in a report:

* **%REPORT\_LEVELS%**: shows the names of all levels in the report containing the Metric (see the example below)
* **%SELECT\_LEVELS%**: shows the names of the levels on the rows of the report
* **%PAGE\_BY\_LEVELS%** shows the names of the levels in page-by in the report
* **%PAGE\_BY\_FILTER\_LEVELS%**: shows all the levels in page-by in the report for which a value different from ‘\[Total]’ was selected

Step 1: **Creating a Composite Metric**

![](<../../../.gitbook/assets/10 (11).png>)![](<../../../.gitbook/assets/11 (6).png>)

_The following example defines a standard Metric which shows the weight of the actual sales relative to the budget (Actual versus Budget) and which consists in turn of two Metrics._

_These two Metrics are those of the first level (Qty sold and Budget qty), both with sum aggregation._

_By selecting the 2 abovementioned metrics (Qty sold and budget qty) in the tree of the metrics and clicking twice on each of them, these are reported in the formula area._

Step 2: **Composite Metric with SQL FORMULATION**

![](<../../../.gitbook/assets/12 (21).png>)

_In the following example a composite metric is defined, created with the SQL language._

_The composite metric QTA\_Sales\_case\_when is defined, as shown in the figure, which will put._

_all sales below 500, to 0_

_those between 500 and 600, to 1_

_leave the others unaltered_

_To see the behavior of the Composite Metric, a report is built with the Metric just defined and the First Level Metric it contains._

Step 3: **Example of a Report with a Composite Metric**

![](../../../.gitbook/assets/13.png)

_In the figure you can see how the values Sales Qty – case when respect the formulation of the composite metric._

Step 1: **Using LEVELS parameters in Composite Metrics**

![](<../../../.gitbook/assets/14 (1).png>)

_Let us define a composite metric simply containing the %REPORT\_LEVELS% parameter. The parameter is entered manually in the bottom white area reserved for creating the formula. Another three metrics with the parameters will be defined in the same way: %SELECT\_LEVELS%, %PAGE\_BY\_LEVELS%, %PAGE\_BY\_FILTER\_LEVELS%._

_Then the four Metrics are indicated in a report (figure below)._

Step 2: **Using LEVELS Parameters in Composite Metrics**

![](<../../../.gitbook/assets/15 (1).png>)

_In the report the following levels have been entered:_

_Product on rows, Business Unit and Month for the page-bys._

_The composite metrics created previously will show the following information:_

_Select Level: \[Product] information relating to the Dimension entered on the rows_

_Page by Filter Levels: \[Business\_Unit]\[Month] The report was filtered in the page by for the business levels_

_Page-by Level: \[Business\_Unit]\[Month] levels in the page-by_

_Report Levels: \[Product] \[Business\_Unit]\[Month] total levels in the report._

## Formatting Metrics

Customization of the metrics format establishes:

* a style for the values
* a formatting depending on a threshold value
* a decoration through indicators, bars and reports

When you enter modify Metric in the **Metric management** window, the _**Metric Format**_ button accesses the Metric format setting window.

![](<../../../.gitbook/assets/16 (18).png>)

Metric formatting can also be defined at **application level.** DAC sets the formatting of the decimal and thousand separator _depending_ on the _language_ selected by the user on DAC.

### Style for the Values

The global formatting parameters are established in the right section of the Metric folder:

* _**size**_ of the character)
* number of decimal places (_**Decimal Digits**_)
* thousand separator (_**Grouping char**_) and the decimal places (_**Decimal Separator**_)
* character to be entered after the value, for example for the currency or percentage (_**Additional char**_)

You can display Component Metrics from Composite Metrics. This function may be disabled through the _**drillable**_ property (_Format_ group).

Example:Drillable Property

![](<../../../.gitbook/assets/17 (11).png>)

_This example shows a Composite Metric (Act Vs. LY) with the drillable property enabled (default behavior). Note that by selecting +, the report also indicates the Component Metrics used to calculate the Composite Metric._

**Property on the thousand decimal separators (compared to the user language)**

### Separator Characters Depending on the Language of the Web User

From the **Application>>Application Properties** menu item access the properties window at application level. the _**Format-as-local**_ property is in the _Metric_ section.

When exporting a report in CSV or EXCEL, on which this property has been enabled or the local format applied, the formatting might not be maintained when:

• for EXCEL, the cells of the spreadsheet are set as numerals;

• for CSV, the data setting in the "_Csv export settings_" is different, since the latter always has a higher priority compared to the metrics formatting.

We recommend formatting and setting the files with the proper format.

Property on the Thousand Decimal Separators (compared to the user language)

![](<../../../.gitbook/assets/18 (7).png>)

_The example shows the application of the Format-as-local property._

_This property is enabled in the Metric of the report in the figure (if the language is set to Italian, the Metric appears with the period as thousand separator. If it is changed to English, the thousand separator is automatically replaced with a comma)._

### Formatting Compared to the Threshold Values

Different colors can be defined based on the value assumed by the Metric:

* **Positive values** if they exceed a positive threshold, defined in the _Metric Positive_ _folder_ _(**Threshold**_)
* **Negative values** if lower than a negative threshold, defined in the _Metric Negative folder_ _(**Threshold**_)
* **Central values** those ranging between the positive and negative threshold

Each of the three types of values assumes the color (_**Background, Foreground**_) and style (_**Bold, Italic, Underlined**_) set in the respective folder. Central values inherit the style and colors set in the _Metric folder._

**Note:** _The underlined style is not visible on DAC, but only on DAC._

![](<../../../.gitbook/assets/19 (7).png>)

The color of the metric may be extended to the entire row of the report, by selecting the _**expand-row**_ property of the _Format_ group. This property is only applied when the Metrics of the report are on columns.

![](<../../../.gitbook/assets/20 (6).png>)

The _**Active Formatting**_ check conditions the coloring of the style by priority threshold values relative to report level formatting (see _Report Administrator,_ _Table layout section_, _Formatting example \<Body Metrics> section_). By default, the check is deselected.

An additional _**three intervals**_ [_with higher priority are also available_](/broken/pages/-MfHs_PiXlCm3eSy1MKC#metric_format3). These are characterized by:

![](<../../../.gitbook/assets/21 (7).png>)

* the high and low thresholds, set in _**from-value**_ and _**to-value**_ respectively
* the color of the background and the character (_**background**_ and _**foreground**_)

Each of these intervals is enabled on the respective conditio&#x6E;_-\[i] items_ which appear in the _Property_ pane (_Conditions_ group).

These intervals prevail over those set by the positive, negative and central thresholds.

**Note:** _For empty cells, you can set the_ _**from-value**_ _property to “null”. This setting allows you to format all cells without a value._

Color and style settings for the three types of Metrics (positive, negative and central) are also provided at application level. Simply access the property window using the **Application>> Properties** menu item. In the _Metric>>Positive_ and _Metric>>Negative_ section, set:

* background color (_**backGroundColor**_)
* color of the character (_**foreGroundColor**_)
* style of the character:
  * italics (_**fontStyle**_) enabled (<_italic>)_ or disabled (_\<normal>_)
  * bold (_**fontWeight**_) enabled (<_bold>)_ or disabled (_\<normal>_)
  * underlined (_**textDecoration**_) enabled (<_Underline>)_ or disabled (_\<None>_)

### Format with Decoration

You _**define the decoration of Metrics**_ (only visible from DAC) in the _**decoration**_ property of the _Format_ group. This is to depict the Metric using:**:**

* bars (_\<Bar>_)
* indicators (_\<Indicator>_)
* reports (_\<Report>_)
* the value _\<None>_

### Decorate Using Bars

You can personalize the property of bars on the maximum value (**target**).

The bar color inherits the background color of the central Metrics.

Step 1: Decorate Using Bars

![](<../../../.gitbook/assets/22 (1).png>)

_This example shows a Metric (Sales Qty) with the bar decoration._

![](../../../.gitbook/assets/23.png)_You select the background color to be attributed to the bar. The 200 target provides you with a good resolution for comparing the bars with each other. The Metric on DAC is shown at the bottom._

### Decorate Using Indicators&#x20;

To be able to represent a metric through an indicator you must set the typical parameters of this object (see _Dashboard and Indicators Administrator, Indicators chap._):

* the style of the indicator (_**indicator-style**_) – is selected from a list
* the minimum (_**min)**_, maximum (_**max**_) thresholds and the ones for the central zone (_**max-threshold**_ and _**min – treshold**_)
* the dimension (_**size**_)
* the direction of the objective, if it is positive for high values or negative for low values (_**inverted**_)
* show/hide the value of the Metric (**show-value**)

The thresholds may be defined in absolute or dynamic mode:

* in **absolute** mode just enter the value in the respective properties. Default is min: 0, max:100, minthresh:33, maxthresh:66
* in **dynamic** mode, by selecting a metric of the application: the value it assumes inside the report associated with the indicator will be the applied dynamic threshold

Select the metric by opening a window with the metrics of the application (see the figure below).

![](<../../../.gitbook/assets/24 (11).png>)

**Note:** _The background of the indicator is always transparent._

Step 1: Decorate Using Indicators

![](<../../../.gitbook/assets/25 (11).png>)

_In the example below, the Act Vs LY Metric was depicted with the indicator._

_An arrow was chosen as style, whose dimensions were set in consideration of the height of the row (size property). The value of the Metric is also displayed (show-value)._

_The direction of the objective was not inverted and therefore, the setting of the thresholds establishes that:_

* _the values between min and min-thresh will belong to the red zone_
* _those between min-thresh and max-thresh will belong to the yellow zone_
* _finally between max-thresh and max to the green_ _zone_

### Decorate Using Reports

The representation of a metric as report consists of replacing a report with the metric. Therefore, the functions defined in the same metric are not applied when you use this type of format.

Using a report in place of a Metric is very useful when there is a graph form. The graph will present trends depending on the dimensions of the main report.

Example: Decorate Using Reports

![](<../../../.gitbook/assets/26 (6).png>)

_In this example the graph entered in the report shows different trends, depending on the value of the Business Unit and Year levels of the main report._

_If you want to edit the graph trend, it must have the same dimensional levels as the report containing it (positioned in page-by)._

This depiction involves the following steps:

1. Create a report (preferably as a graph) that is suitable to _be_ displayed within another report (for example by deleting the legend, title, axes...).

**Note:** _The flash graphs are resized based on the size of their container. Because of this property, if the metric is decorated with a flash graph it is possible to enlarge or reduce the wiDSh of the cell of the report that contains it. The graph will readapt as a result, thus containing all the information._

1. Create a Metric decorated with a report (_**decoration**_ property _= \<Report>_)
2. Associate the report created previously at step 1 (_**report**_ property)
3. Select which dimensional levels of the report must be updated to those of the report that will contain it. A window opens from the _**level-filters**_ property with the report levels. This is where you establish whether each level must be updated (_\<Filter_>) or remain unchanged (_\<Ignore>_)
4. Create a new report, where you enter the decorated metric (created at step 2) and, preferably containing the levels chosen at point 4; this way, the report of the decorated metric is edited by using the values of the main report as filters
5. Through the _**transparency**_ propert&#x79;_**,**_ the crosstab that will be printed inside the cell of the report will have a transparent background color

Step 1: **Creating a Report for the Decorated Metric**

![](<../../../.gitbook/assets/27 (9).png>)

_In this example you want to show a graph for the monthly trend of the ordered quantity, compared to the year, the business unit and the product category._

_Create the “Number of Orders” report, where the levels are entered in page by: Category, Business Unit and Year. The Month level and the Ord Qty\[Sum] Metric are entered in rows and columns, respectively._

_Choose the graphical form (_![](<../../../.gitbook/assets/28 (7).png>) _button): In the graph leave only the part reserved to the trend, without axes and key:_

_plotAreaMargin = 0,0,0,0._

Step 2: **Creating a Decorated Metric with Report**

![](<../../../.gitbook/assets/29 (8).png>)

_After creating the report (step 1) move on to creating the decorated metric (Order 12 month), where the report is associated and is set only for the month level that is not considered in the filters:_

* _Open the window for the Metric format (Format button)_
* _Set decoration to \<Report>_
* _Associate the report of step 1 in report_
* _Set the Filters for the levels (level-filters): select \<Ignore> for the Month level_

Step 3: **Creating a Main Report**

![](<../../../.gitbook/assets/30 (9).png>)

_In step 3, create the main report which will contain the decorated Metric. The report will have all the dimensional levels selected as Filter (level-filter) in the previous step._

Step 4: **Creating a Main Report**

![](../../../.gitbook/assets/31.png)

_The decorated metric is only visible from_ _the web, so access DAC and open the report created in the previous step. Please note that the report shows the graph, where the dimensional levels chosen as filter (level-filter at step 2) modify the trend. The figure shows how, by performing a drill on Business Unit 01, the graphs related to each product family are presented._

## Primary Aggregation

You can use the **Aggregation** drop-down menu to specify the aggregation function to be applied to the Metric, such as the average, sum, minimum or maximum, standard deviation, etc. (other proprietary aggregations of the DBMS of the Data Model are also indicated).

The modification of the primary aggregation is only applicable to the advanced metrics.

![](<../../../.gitbook/assets/32 (4).png>)

By predefined setting, DAC creates all the metrics through the SUM aggregation function.

The Distinct checkbox allows you to apply the DISTINCT function to extract distinct (unique) values from within a set of data.

Step 1: **Sales Maximum Advanced Metric**

![](<../../../.gitbook/assets/33 (8).png>)

_Create a new Advanced Metric by selecting the folder relating to the sales Cube (Sales Qty) from the Metric menu. Define the new Metric by entering the name of the Metric (Max Sales) in the logical name and title section. Select max from the drop-down menu of the Aggregation section. Save the Metric using the save button._

Step 2: **Report with Advanced Metric**

![](<../../../.gitbook/assets/36 (9).png>)

_Build the report containing the dimensions Business Unit and Product, grouped by dimension._

_Enter the base Sales Qty metric which will show the quantities sold for the products belonging to the different Business Units. Enter the Max Sales Metric created previously._

_Note that the highest level (Business Unit 01) shows the value relating to the quantity of product which sold the highest quantity._

## Secondary Aggregation

When data is aggregated, the values of the metrics are recalculated exactly with the same function in which they are defined. You can modify the function to be applied to the aggregated data, because of the secondary aggregation function.

Step 1: Primary Aggregation

![](<../../../.gitbook/assets/37 (4).png>)

Let’s take the example of a Metric that calculates the sum of sales and apply it to a report with levels on the business unit and product. The sum of sales is shown for the Product level. When you aggregate the data by business unit, the Metric is recalculated using the same function (Sum) with which they were defined. Thus you obtain the sum of the sales of the products.

You define the secondary aggregation for a Metric as follows:

1. Open the advanced settings window using the _**Advanced**_… (bottom right).
2. Select the Aggregation _rule_ flag.
3. Enter the command for the aggregation function, with the same notation accepted by the RDBMS system of the data warehouse.

**Note:** _Only enter the aggregation function (AVG, MAX, SUM….) without mentioning the Metric (see example below)._

1. If necessary, select the _Distinct_, flag to exclude events with the same value.

![](<../../../.gitbook/assets/38 (4).png>)

Step 1: **Secondary Aggregation**

![](<../../../.gitbook/assets/39 (4).png>)

_We set the secondary aggregation to calculate the Average of the sales on the products, for each business unit, using the Advanced... button._

_The function established is:_

_for each product it will be necessary to calculate the total value of the sales and subsequently apply the average on the total values. Therefore, for the Average Sales Metric, you will have:_

* _As primary aggregation, the sum applied to the disaggregated data (Product x) and established in the Aggregation field_
* _As secondary aggregation, the average applied to the aggregated data (Business Unit y)._

Step 2: **Secondary Aggregation**

![](<../../../.gitbook/assets/40 (1).png>)

_As shown in the figure, the Average sales metric applies to:_

* _the primary aggregation on the product (detailed data), providing the sum of the sales_
* _the secondary aggregation on the business unit (aggregated data), by providing the average of sales, by product._

## Dimensioning

Dimensioning indicates the group level On which the calculation of the associated metric is based. For example, it is possible to choose to perform the calculations at a monthly or annual level, provincial or regional.

To specify dimensioning for an _Advanced_ Metric, you must select the ![](<../../../.gitbook/assets/41 (6).png>) button.

The system shows the dialog window (Dimensions) which determines the grouping level based on which the Metric is calculated. Double-click on the level involved on the tree on the left.

To remove the selected level, click twice on it in the area to the right of the window.

Once the dimensioning is confirmed (OK button), the system shows the level selected by entering a row in the central panel (description) of the Metric Wizard screen.

![](<../../../.gitbook/assets/42 (8).png>)

Dimensioning will not be applied to the Metric if:

* The level of the report is higher than the one of the metric (e.g.: report calculated by month, dimensioning of the metric calculated by day)
* the related dimension is not in the report

You can set more than one dimensioning per metric.

In the central panel, by selecting the first of the two buttons to the right of the defined dimensioning, the system shows the dialogue window to specify whether to group the values of the metric for the dimensioning indicated (_Group values_) and whether to make the metric inherit the filters set in the report where it will be used (_Inherit filters_).

![](<../../../.gitbook/assets/43 (3).png>)

### Example of a Dimensioned Metric

This example shows how to create and use a dimensioned advanced metric.

Step 1: **Creating an Advanced Metric that Returns the Quantity Sold by Week**

![](<../../../.gitbook/assets/44 (9).png>)

_Create a new advanced metric (Qty For Week), inside the Sales cube folder, which calculates the quantity sold by week._

_Dimensioning by week is performed by accessing the Dimensions panel through the_ ![](<../../../.gitbook/assets/45 (2).png>) _button and selecting the Week level from the Sales cube._

Step 2: **Creating the Report Using the Dimensioned Metric**

![](<../../../.gitbook/assets/46 (1).png>)

_The report in the figure shows the behavior of a metric dimensioned for a level._

_The Week level was entered, together with the hierarchically lower Day level._

_The Sales Qty\[sum] Metric calculates the quantities sold for the respective days of the week._

_The Sales Qty for week metric, created in the previous step, will sum the quantities sold of the days of the week, returning in this way the total of the sales for the week._

### Examples of a Dimensioned Metric with/without Inheritance on the Filters

These examples show the use of the _Group values_ and _Inherit filters properties on a_ report which analyzes for each month the quantities of products sold.

Step 1: **Inherit Filters and Group Values**

![](<../../../.gitbook/assets/47 (4).png>)

_Create as first step the Qty Category metric dimensioned by Category. During creation, you establish that the Metric must inherit the Filters ( (Inherit filter= true)) and group the values (Group (value= true)). During the creation of the report, enter a filter which only considers products 120 and 128. As shown in the figure, a quantity equal to 1 was sold for product 120 of Product Family 13 in January 2005. For the month of January 2005, the QTY Category Metric returns the total of the quantity sold for the Product Family 13 (because it is dimensioned by Category) of only products 120 and 128 (it inherits the Filter of the report)._

Step 2: **Verifying the Accuracy of the Previous Report**

![](<../../../.gitbook/assets/48 (6).png>)

_The report on the side verifies that the Metric was accurately calculated by highlighting that for January 2005, 4 units for the Product Category were sold among the products specified in the Filter._

Step 1: **Inheriting the Filter Set to False**

![](<../../../.gitbook/assets/49 (7).png>)

_As shown in the figure, for product 120 of Product Family 13 in January 2005, a quantity was sold equaling 1, while the QTY Category metric returns for January 2005 the total of the quantity sold for Product Family 13 (since dimensioned by Category) of all the products (since it does not inherit the filter of the report)._

Step 2: **Verifying the Accuracy of the Previous Report**

![](<../../../.gitbook/assets/50 (4).png>)

_The report on the side verifies that the Metric was accurately calculated by highlighting that for January 2005, 130 units for the category 02 were sold among all the products of Product Family 13._

### Example of Dimensioned Metrics With/Without Value Grouping

Let’s hypothesize three Advanced Metrics, calculated on the basis of three aggregation levels (Italy, Region and Province) and on the QTY\_SOLD\_Sum First Level Metric of the Sales Cube.

Step 1: **Metric Dimensioned by Region**

![](../../../.gitbook/assets/51.png)

The first metric, Sales Qty Region, returns the quantity of products sold by region. You define a dimensioned Metric for the Region level.

Step 2: **Dimensioned and Not Grouped Metric**

![](<../../../.gitbook/assets/52 (6).png>)

_The second metric, Sales Qty Italy, returns the quantity of product sold for all regions in Italy. You again define a dimensioned Metric for the Region level, and select the Group Values property of the dimensioning._

Step 3: **Creating the Report**

![](<../../../.gitbook/assets/53 (7).png>)

_The report uses the two dimensioned metrics, in addition to the first level one._

_Note that the one dimensioned by region provides the total for the provinces of each region, while the one where grouping was disabled (Sales Qty Italy) shows the total for all provinces._

## Direct Filter Association

A Direct Filter associated with a Metric represents a condition when you calculate the Metric. It also implies a restriction in the data extraction criterion which is only applied to the Metric (not to the report containing the Metric).

![SNAGHTML5d61e2](../../../.gitbook/assets/54.png)

Once you have confirmed the Filter, the system displays the Filter selected by inserting a row in the central panel of the Filters window.

By selecting the ![](../../../.gitbook/assets/55.png) button located on the main screen to the right of the defined filter, the system shows the Properties window which makes the metric inherit the filters available in the report where it will be used (check on the _Inherit filters_ item).

The settings defined for the _Inherit filters_ parameter are displayed in the _Description_ area below the specified filter.

![SNAGHTML5e2be9](<../../../.gitbook/assets/56 (3).png>)

Step 1: **Filtered Metric**

![](<../../../.gitbook/assets/57 (9).png>)

The following is an example of how you create an Advanced Metric that returns the quantity sold in January 2006.

*
  1. Create a Direct Filter with _MONTH@ID = 200601 condition_
  2. Create an Advanced Metric on the _Sales Qty_ measure (_Sales_ Cube)
  3. Select the filter created at point a
  4. Create a report with the non-filtered Metric (Sales Qty \[Sum]) and the one with the Filter (_Sales Qty (filter_ _January 2006_)

Step 2: **Creating the Report**

![](<../../../.gitbook/assets/58 (3).png>)

_Create a report with the first level metric relating to the quantities sold (Sales Qty \[Sum]) and advanced with the direct filter (Sales Qty (filter January 2006) created in the previous step. Note that the quantities sold in January 2006 for products 120,128 and 129 are 10, 9 and 20 units respectively._

Step 3: **Check the Accuracy**

![](<../../../.gitbook/assets/59 (8).png>)

_In the report shown in the figure, the correctness of the data is checked._

_Delete the “Sales Qty Filter January 2006” Metric and keep the Sales Qty First Level Metric. This way, the report does not have any filter for the month._

_By introducing the Year level you will notice that in January 2006 for products 120, 128 and 129 the quantities 10, 9 and 20 units respectively. The result is equal to the one of the metric with filter calculated in report 2._

## Time Functions

You can define data aggregation which respects a specific time rule. For example, you can display the aggregated data as compared to the previous year, or the previous period, or aggregated from the first day of the year up to the current day, etc.

The time rules available on DAC are defined for the TIME predefined time dimension (see _Time Dimension_ section)_._ Therefore, you must create and associate this dimension with the Cube to which you want to apply a time calculation.

You can also define customized time rules, starting from the predefined ones.

The report which uses a metric to which a time function is applied must contain at least one level of the TIME dimension.

Once the conditions are met to measure the cube, to apply a time function just create an advanced metric on the same measure, and choose one of the time functions from the window opened with the ![](<../../../.gitbook/assets/60 (8).png>) button: with a double click, select the function, which is entered in the panel to the right of the window. By closing the window with the OK button, the procedure ends.

![](<../../../.gitbook/assets/61 (3).png>)

The functions available and listed in the window are:

* **Last period**

Previous time period compared to the lowest level in the report

_For example if in the report there is the day level, the function presents the data of the previous day, instead if there is the week the data of the previous week is shown, etc._

* **Last year**

This function displays the data relating to the previous year relative to the level in the report.

_For example if there is the month level in the report, the function shows the data relating to the same month, a of the previous year, for the quarter level, instead the data of the same quarter is shown, but of the previous year_

**Last 2 Months, Last 3 Months**

These functions show the data relating to the previous two or three months respectively. The MONTH level must in the report and be the lowest TIME Dimension level entered.

* **MAT**

The function aggregates the data relating to the 12 months before the current one. The MONTH level must be shown in the report and be the lowest TIME Dimension level entered.

* **Last year MAT**

Like MAT, only it is applied to the current month of the previous year.

* **Month to date**

This function aggregates the data from the start of the month to the current date. The DAY level must be in the report.

* **Last year MTD**

Like _Month to date_, only it is applied to the data of the previous year: from the start of the month to today's date of the previous year.

* **Year to date**

This function aggregates the data from the start of the year to the current date. The DAY level must be in the report.

* **Last year YTD**

Like _Year to date_, only it is applied to the data of the previous year: from the start of the previous year to today's date, still referring to the previous year.

* **Year to month**

This function aggregates the data from the start of the year to the current month. The MONTH level must in the report and be the lowest TIME Dimension level entered.

* **Last year YTM**

Like _Year to month_, only it is applied to the data of the previous year: from the start of the previous year to the current month, still referring to the previous year.

The example shows how to use the Last Year time function.

Step 1: Advanced Metric with Time Function

![](<../../../.gitbook/assets/62 (2).png>)

_Creating an advanced metric which returns the value of sales of the previous year._

_Select the Sales Val measure (Sales Cube) and create an Advanced Metric._

_Open the window with the list of the time functions by pressing_ ![](<../../../.gitbook/assets/63 (8).png>)

_Double-click on the Last Year time function._

Step 2: **Report with Time Advanced Metric**

![](<../../../.gitbook/assets/64 (5).png>)

_Create a report with the first level metric (Sales Val \[Sum]) and the advanced metric created previously._

_Select the TIME Dimension levels (YEAR and MONTH)._ _Please note that in January 2006 the value of sales is reported relating to the previous year in the same month._

### Custom Time Functions

In addition to the time functions provided in DAC, you can also create customized time functions starting from those that are provided. For example, from the _Last Year_ function it is possible to easily define the one which presents data relating to two or three previous years, or from the _Last Period_, the one which presents the data compared to another time period (previous 5 days, previous 6 months, etc.).

The predefined functions which may be modified are:

* _**Last period**_
* _**Last year**_
* _**Year to month**_
* _**Month to date**_
* _**Year to date**_
* _**Year to month**_

These are listed in the window of the DAC time functions, indicated with the prefix **CUSTOM\_** followed by the function and a progressive: up to three custom functions may be defined for each type.

![SNAGHTML72b9df](<../../../.gitbook/assets/65 (4).png>)

You must enter the data relating to each rule in the time tables or in the transition tables which were generated and populated when the TIME Dimension was created.

The editable functions, with the related reference table, are reported below:

* **CUSTOM\_LP\_\[n]** equivalent to the _Last Period_. The reference tables are all the time tables (LK\_DATE, LK\_MONTH, LK\_QUARTER, LK\_YEAR), since this function takes the data from the TRANS\_PREV field, in all the time tables.

Select the most suitable table based on where you want to apply the function (for example, the reference table for a previous period of 5 days is LK\_DATE).

* **CUSTOM\_LY\_\[n]** equivalent to the _Last Year_. The reference tables are all the time tables (LK\_DATE, LK\_MONTH, LK\_QUARTER, LK\_YEAR), since this function takes the data from the TRANS\_LY field, in all the time tables.
* **CUSTOM\_YTM\_\[n]** equivalent to the _Year to month_. The reference table is TRANS\_YTM
* **CUSTOM\_YTD\_\[n]** equivalent to the _Year to date_. The reference table is the TRANS\_YTD table.
* **CUSTOM\_MTD\_\[n]** equivalent _to the Month to_ date The reference table is TRANS\_MTD

The data relating to the new time rule must be entered in a new column of the reference table, which will have the same name of the function you want to use.

In this example, you want to create a customized function that calculates the quantities sold in the previous three years relative to those examined.

Step 1: **Editing Reference Tables**

![](<../../../.gitbook/assets/66 (6).png>)

_The data relating to the previous three years is entered in the LK\_YEAR table, since the function will be used only at an annual level. Create the new column with the same name as the function equivalent to the Last Year: CUSTOM\_LY\_Step 1: Populate the field by calculating the corresponding previous 3 years for each year in the table._

Step 2: **Metric with a Customized Time Function**

![](<../../../.gitbook/assets/67 (1).png>)

_Create a new advanced metric Sales L3Y, by associating the custom time function CUSTOM\_LY\_1._

Step 3: **Creating the Report**

![](../../../.gitbook/assets/68.png)

_Create a new report._

* _Enter the Sales L3Y metric and the first level metric Sales Qty._
* _Enter the Product in the rows and the year in the columns._

_After performing the report, the result will be as shown in the figure._

_For example, the Sales Qty of the previous three years is 590,673 for year 2008. Note that for 2006, the quantity is actually the one indicated in the customized Metric. Just like for 2006, 2007 and 2009._

##

## _Null_ Value Management

You can replace the _Null_ values of the Metrics with a predefined value (typically 0).

This function is particularly useful in case the _Null_ metrics are used as components in the formulas of the composite metrics. In these cases, if one of the component metrics is null, the total calculation is automatically null. However, replacement with a predefined value obtains a result.

Let’s take for example, a Metric which calculates a deviation as the difference between two Component Metrics:

Deviation = Actual value – Budget Value

If one of the two metrics is Null, the deviation will also assume the same value;

The possible methods are distinguished according to which the new value is replaced during or after the query necessary to find the data of the metric.

In the first case, the new value is written on the datamart. In the second case, the _Null_ values remain on the datamart and the replacement with the new one takes place when the datamart is read. For the datamarts see _Presentation Administrator._

In addition, the writing on the datamart of the value to be replaced may take place before or after the aggregation of the data:

For example, before applying an average, value the Null data to 0, and subsequently perform the aggregation: this way, the Null values also contribute to the average.

In an Oracle environment, you express assigning the 0 before or after the average aggregation as follows:

* Before: AVG (NVL(Sales\_Val,0))
* After: NVL(AVG(Sales\_Val),0)

The writing on the datamart is possible only for the metrics which access the database to be calculated, i.e. those of the first and advanced levels.

However, Composite Metrics are calculated directly on the datamart. This means that writing on the datamart will not be possible for them, but accessed in read only. The replacement of the _Null_ value therefore will take place on the datamart and the new value will be shown on the report.

The following examples explain the different _Null_ management methods. The configuration on DAC is set in the formatting of the metrics (_**Metric Format**_ button); in the section to the left of the window, access the **Null** property group.

Step 1: **Composite Metric with Null Value Management: Reading from the Datamart**

![](<../../../.gitbook/assets/129 (2).png>)

_Create a Margin Val-Bdg Composite Metric as the difference between the two First Level Metrics indicated in the figure._

_Activate the replacement of the Null values by enabling replace-null-value and leaving the value to be replaced at 0 in when-null-values._

_Create a report with the two component and composite metrics, obtaining the result in the figure:_

_For each null value of one of the Component Metrics, the Composite Metric also has a null result (in the datamart), which was replaced with 0._

Step 2: **Component Metric with Null Value Management: Writing on the Datamart**

![](../../../.gitbook/assets/130.png)

_If you set the writing on the datamart for Component Metrics to replace Null values, you get the result in the figure._

_The margin is calculated, because all the component metrics are valued._

_You enable writing on the datamart by setting the Sales Val. Enable the replace-null-datamart property and leave the others with the default setting._

## Customizing Metrics

When you customize Metrics, you can establish:

* the application of the security filters for the calculation of the metric, relating to specific dimensional levels (for the security filters see _Security filters_ chap.). This is particularly useful when users need to see the incidences of the data they are responsible for, and on which a Security Filter is applied that would stop the calculation of the total (on which they do not have reading permission). The next example shows an application of this type.
* the visibility of the metric for the end users, in case you want to stop the metric for being used in the creation or modification of reports while remaining visible in the reports published on DAC.

In the **Metric management** window, when you enter in edit metric, with the _**Properties**_ button, yo can access the window of the metric properties.

![](<../../../.gitbook/assets/131 (2).png>)

### Disable the Security Filters at Metric Level

To disable the security filters, select the _**disabled-sec-filters**_ property (_Security Filters_ section), which in turn enables the _**disabled-levels**_ property through which the dimensional levels may be indicated on which to disable the security filters:

![](<../../../.gitbook/assets/132 (2).png>)

by default all the levels in the security filters () are disabled.

Below are two application examples of the function.

#### Access to Total Values in the Presence of Security Filters

If a group of users has a Security Filter applied, the group cannot access the data excluded by the Filter, even when they are aggregated. This prevents the group from displaying any incidences on the levels implied in the Filter.

In the example, a customer type security filter is applied to a user, conditioning the viewing of the data to only the Insurance customers.

If a report is published with the incidence of sales for INSURANCE, the user will see a result of 100%. In fact, the Filter will prevent access to data other than insurance and total sales, which is required for the calculation (INSURANCE Sales/Total Sales). This will always coincide with the insurance sales.

If you want to publish the correct incidences for the user, you must define a Metric for the total sales, where the Security Filter is disabled on the customer type level.

The two Metrics are published in the example. One total is when the Security Filters are applied and one has the Filters disabled.

Step 1: **Security Filter**

![](<../../../.gitbook/assets/133 (1).png>)

_The Security Filter on the customer type was applied for user Jennifer Tilly: Customer Type =INSURANCE_

Step 2: **Disabling a Filter on the Metric of the Total**

![](<../../../.gitbook/assets/134 (1).png>)

_Create a Sales Val \[no filter] metric, identify the first level one (primary sum aggregation) and disable the security filters at Customer Type level:_

* _Open the window of the metric properties (Properties button)._
* _Disable the Security Filters (enable the disable-sec-filters property, in the Security Filter section)._
* _Disable the Customer Type level only (from the disabled-levels property, select the level)._

Step 3: **Publishing Incidence With and Without Security Filters**

![](<../../../.gitbook/assets/135 (1).png>)

_The report in the figure shows the two metrics on the calculation of the incidence of the sales by Insurance customer type, on the total, both calculated in the same way:_

_INSURANCE Sales/ Total Sales_

_Where INSURANCE Sales is an advanced metric to which a direct filter was applied to the Insurance customer type (same condition of the security filter), while Total Sales is the first level metric which provides the total data (since not filtered)._

* _In the first metric of the incidence, for the Total Sales the first level was chosen, which by default has the security filters enabled._
* _In the second Metric of the incidence, the Metric defined in the previous step was selected for Total Sales. The Security Filters were disabled._

_Note how the first Metric always shows 100%, because the two Component Metrics coincide. In the second case, the correct incidences are presented, even though the user has no access to the detail data of other Customer Types, but only to the aggregated data._

#### Access to Total Values in the Presence of Security Filters

This example defines two Metrics for calculating the sales of the previous years. One has Security Filters enabled and the other has Security Filters disabled. The Security Filter conditions the users to only view the data on one month alone.

The report that publishes the two Metrics underlines how the default Metric only shows the data for the enabled month.

Step 1: **Creating Metrics**

![](../../../.gitbook/assets/136.png)

_Two Metrics are created in the example: Sales Ly 1 and Sales Ly 2 to which the Last Year time function is applied._

_The Security Filters are left enabled (disable-sec-filter disabled) for the first Metric (Sales Ly 1) and disabled for the second Metric._

**.**

Step 2: **Security Filter**

![SNAGHTML70d159](../../../.gitbook/assets/137.png)

Step 3: **Publishing Metrics**

![](<../../../.gitbook/assets/138 (2).png>)

Step 4: User Mario Rossi Accesses DAC

_Please note that for Sales Ly 1 metric (metric with security filter active) has calculated the sales compared to the previous year for the month selected in the filter. The Sales Ly 2 Metric completely ignored the Security Filter._

### Metric Visibility on DAC

The metrics defined in the application are available to the end users on DAC: they may be entered in the reports published or in new ones.

![](<../../../.gitbook/assets/139 (2).png>)

If you don’t want a Metric to be visible to the end user, disable the _**catalog-web-visibility**_ property from the Metric formatting window (_**Metric Format**_ button).

This setting does not affect the visibility of the same Metric on published reports.

Use the _**catalog-web-visibility**_ property to enable the _**groups-enable**_ property. You can use it to select user groups or individual users who will be enabled to see the Metric.
