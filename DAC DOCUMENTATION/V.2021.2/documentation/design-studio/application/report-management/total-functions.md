# Total Functions

Totals can be calculated by setting different report functions, such as:

* simple aggregation (sum, average, etc..)
* total function complying with the formulation defined for composite metrics
* [weighted average](total-functions.md#weighted-average-weighted-avg)
* [different functions](total-functions.md#different-total-by-metric-composite), for each report metric
* [custom functions, using](total-functions.md#custom-totals-excel-like-section) Java interface classes, available in DAC

The totals are calculated with respect to the dimensional levels of the report by considering all the levels (**cumulative** totals) and some levels only (partial totals).

The interface allows you to customize the names associated with operations carried out on totals through aliases.

Totals can be applied to the data displayed in the report (which will change according to drill operations), or exclusively on detail data (which will not change) (details in Visualization or detail totals (calc-type) section.

It is also possible to set totals on report elements selected by the user, through the function of Customized totals.

_The_ _**total-calc-precedence**_ _property (Totals group) lets you perform this setting (\<standard-totals> to give precedence to standard total functions; \<custom-totals> to give precedence to custom totals (see_ _example)_

* _\<standard-totals> to give precedence to standard total functions;_
* _\<custom-totals> to give precedence to custom totals;_

![](<../../../../.gitbook/assets/0 (13).png>)Formatting for totals’ rows and/or columns is set from the Total group properties.

Report totals are set from the _Totals Definition_ window opened by the button (in the toolbar).

![](<../../../../.gitbook/assets/1 (24).png>)

![](<../../../../.gitbook/assets/2 (23).png>)In the _**Operations**_ section we choose the type of total function to apply to the report, divided in the following groups:

* _Simple_ aggregations where the most common total functions are listed
* [_Weighted Avg \[n\]_](total-functions.md#weighted-average-weighted-avg) for the calculation of weighted averages
* [_Composite \[n\]_](total-functions.md#different-total-by-metric-composite) to apply total functions specific to each report metric
* [_Custom Java \[n\]_](total-functions.md#java-custom-total) to associate custom functions, previously developed in Java

The central section defines the elements the total function is applied to:

![](<../../../../.gitbook/assets/3 (19).png>)

* At a cumulative level (check _**Cumulative**_), where the function is applied to all report values (excluding any partial totals or null values)

You can display the cumulative total at the top or the bottom of the report (selection limited to _**TOP of report**_ and _**BOTTOM of report**_)

* On single dimensional levels (check _**By**_ _**Level**_) for the calculation of partial totals, applied to ALL report levels.

In the _**levels**_ folder to select only the levels relevant to the calculation of the total.

* On rows, columns, or both (_**Apply location**_ section).
* In compact form (_**Compact**_ _**View**_ section), with respect to rows or columns: The aggregating levels are automatically hidden, leaving only the level of detail to be seen, on which all totals, both cumulative and partial, are reported (see following example).

Example: Formatting Totals Layout

![](<../../../../.gitbook/assets/4 (15).png>)

_In this example, the first report is displayed without Compact View. In the second, Compact View has been activated at row level (Row dimensions). Totals are grouped at a single column level._

### Partial Totals (for Dimensional Levels)

By ticking the _**By**_ _**Level**_ checkbox , in the central section, you can enable

partial totals for **ALL** report dimensions.

You can limit the partial totals to the desired levels, selecting them in the **levels** folder, where report levels are listed.

![](<../../../../.gitbook/assets/5 (17).png>)

Partial totals on dimensions in page-by can be obtained by simply applying cumulative totals. This is applied to the report section displayed; therefore every time the level value in page-by changes, a different report section is obtained, with the corresponding cumulative total.

Example: Partial Totals for Levels in page-by

![](<../../../../.gitbook/assets/6 (21).png>)

_In this example, a cumulative total has been set._

_By changing the value of the year in page-by, the cumulative total for the chosen year is recalculated ._

Here are two examples: one applies the total to all levels and the other only to specific levels.

Example: Partial Totals on ALL Levels

![](<../../../../.gitbook/assets/7 (12).png>)

_In this example, a partial total has been applied to ALL row levels._

_Note that for every aggregating level, the partial total of the levels it is the parent of is shown._

Example: Partial Total SOME Levels

![](<../../../../.gitbook/assets/8 (15).png>)

_In this other example the partial total has been applied only to the Year.Therefore, the total will only calculated for the YEAR level in the report._

### Setting Aliases for the Totals

The _**alias-total**_ section allows users to modify the name of the function chosen for the total, simply by inserting an alias for the function of interest. In the alias section all the functions for the totals are listed on the left, and a label can be set for any of them: this label will be used for the total in place of the standard name.

![](<../../../../.gitbook/assets/9 (14).png>)

For partial totals, you can only leave the level value and delete the function name: you must use the command %1. This command, on the cumulative total, has the effect of leaving the name empty.

Example: Aliases for the Total Sum

![](<../../../../.gitbook/assets/10 (13).png>)

_The report in the example shows for each year (in page-by) the budget for the quarter and business unit. A cumulative total (in sum) is applied, giving the budget total for each year. We now set an alias for the Sum total: Total budget Year. The report will use this tag instead of the standard name Sum._

Example: Alias with %1

![](<../../../../.gitbook/assets/11 (12).png>)

_We apply a sum total in sum, both cumulative and by level, to a report containing a budget analysis._

_Then an alias is applied with the command %1:_

_Total Budget %1_

_This has the effect of replacing %1 with the level value. For the cumulative, on the contrary, it remains empty._

### Display or Detail Totals Section (calc-type)

The totals are always calculated on the data _displayed_ in the report, please remember the various visualization modes:

* without aggregation, where you have the maximum level of detail of the report
* aggregation for the _drill_ operations (layout or dimension)
* aggregation on the values of the levels in page-by (with the \[Total] _item_)

In each of these cases, the function for the total is applied to the data displayed, respecting the aggregation chosen on the report.

This behavior may be changed by setting the rule according to which, to calculate the total, the detailed data must **ALWAYS** be considered, i.e. the data without aggregation. This is done by choosing the field of application of the total on the data _displayed_, or on the _detailed_ data of the report.

In order to determine the field of application of a total, in the _**Totals management**_ window you can do the following:

1. choose the function for the calculation of the total, in the left section
2. open the folder **calc-type** and we choose for the same function:

* _\<view>_ to apply the function to the data _displayed_ in the report
* _\<entire-_&#x72;esult> to apply the function to the data report _detail_

As you can see from the figure, you cannot change the field of application for all functions, but only for:

* _average, sum, maximum, minimum, count and weighted average_

![](<../../../../.gitbook/assets/12 (16).png>)

Step 1: Average of the Sales Displayed

![](<../../../../.gitbook/assets/13 (11).png>)

_In this example, we apply a total average of type \<view> on the Sales Val \[Avg] metric (sales average)._

_The results are compared by changing the type report view:_

* _WITHOUT AGGREGATION you get the average of all the quarters for the years displayed_
* _WITH AGGREGATION, you obtain the average of the years, whose values were already aggregated on the quarters._

Step 2: Detailed Sales Average

_Instead, byapplying the AVERAGE total of the type \<entire-result> to the same report you obtain:_

* _WITHOUT AGGREGATION, the same result of the previous case_
* _WITH AGGREGATION the result does not change, the function continues to be applied to the quarters (coinciding with the maximum degree of detail of the report) and not to the years (aggregating level)_

![](<../../../../.gitbook/assets/14 (10).png>)

Step 3: Page-by in Total on Disaggregated Data

![](<../../../../.gitbook/assets/15 (10).png>)

_In this example we show what happens to the same report, when the level in page-by is \[Total]._

_The report is in disaggregated form and there is now also the metric on sales in sum (in addition to that in average)._

_We compare the results of AVERAGE total for the two types:_

_with\<view> , data are first aggregated for the BU in each quarter and then divided by the number of quarters_

_with \<entire-result> , , they are not aggregated by BU, so we carry out a sum of the BU for_ ![](<../../../../.gitbook/assets/16 (11).png>)_all quarters () and then we divide by the BU of all quarters ()_![](<../../../../.gitbook/assets/17 (12).png>)_)_

_Note that for Sales Val \[AVG] the result does not change, in fact:_

_the average of the average BU (view) coincides with the average of each BU (entire-result_

_while for the sales in sum (Sales Val) we obtain a different result, because:_

_the average on the BU data already aggregated in sum (view) is different from the average on the BU not aggregated (entire-result)_

### Total Function Section

The _Total_ function is used to _**calculate the totals for composite metrics**_: this function applies the same formula defined in the composite metric directly on the values before aggregation of the metric components.

We’ll use an example of a composite metric defined as the ratio between two metrics, used to calculate the incidence:

![](<../../../../.gitbook/assets/image (44).png>)

the application of the _Total_ function follows these steps:

* First the aggregation function is applied to the metric components, a function set during their creation
* Then the formula is applied to the aggregated data



![](<../../../../.gitbook/assets/image (73).png>)

Without this type of function we could have applied an average function, but this would not have given us the results we wanted:

![](<../../../../.gitbook/assets/image (58).png>)

### Weighted Average (Weighted Avg)

![](<../../../../.gitbook/assets/image (39).png>)

Example: Weighted Average

![](<../../../../.gitbook/assets/29 (7).png>)

_In the report taken as example we have discount and quantity sold for the products of each Business Unit._

_We want to calculate the weighted average of the discount with respect to the quantity. This way, we give a greater weight to the discount applied to products sold in greater quantity._

1. _The totals window opens and we choose the first item of the weighted averages: Weight Avg 1. You can select the metric used as weight on the folder that will appear on the right: Sales Qty_
2. _We also define a Composite function to hide the calculation of the weighted average for the discount metric, which the system carries out automatically, even if it makes no functional sense:_

_in the Composite 1 folder, we choose the Empty item for the Discount metric, while for the Qty metric, we choose the Weight Avg 1 function already set._

_We apply also the function of simple average (Avg) to compare results:_

_on the totals applied to the discount, we see how the simple average differs from the weighted one, in the latter case the first product has a greater weight (greater quantity sold)._

### Different Total by Metric (Composite)

You can set a different function for each report metric:

1. we choose one of the five _Composite_ items, , in the left section of the functions
2. A folder will appear, in the right section, with the same name as the selected item
3. Open the folder, on which the report metrics are found
4. Select, for each metric, the function to apply to calculate the totals

![](<../../../../.gitbook/assets/30 (7).png>)

In the list of Composite totals, there is also the _Empty_ item, useful if we don’t want to apply any total function to the metric.

Example: Different Totals by Metric

![](<../../../../.gitbook/assets/31 (7).png>)

_In this example, we want to apply a total in sum for the budget and in average for the quantity sold. We set up an operation of type Composite, on the left: Composite 1_

_On the right the Composite 1 folder will appear, with the two report metrics, we choose the function:_

* _Sum for Budget_
* _Avg for Quantity_

_On the report we obtain totals that comply with the set functions._

### Java Custom Total

It is possible to associate a Java class (external and compiled independently), through which it is possible to perform the customized actions of the total.

The Java class must be inserted:

* in the DAC “_**EXT**_” folder
* in the _**lib**_ folder of DAC (it is necessary to restart the application server).

After defining the function, it is possible to apply it to the report as follows:

1. Select one of the _Custom Java_ items
2. A folder will appear on the right with the same name as the function selected
3. Inside it is possible to open a window with a list of custom functions
4. Select the desired function and apply the total

![](<../../../../.gitbook/assets/32 (7).png>)

The following parameters are those sent by DAC and allow the calculation of the custom total:

* **@param valueCells**: identifies the list of the values of the cells associated with the total;
* **@param row**: row number of the total;
* **@param col**: column number of the total;
* **@param additionalInfo**: map identifying the additional information on each value of the cells.

Below, the Java code is shown for the reference interface _**IExtReportCustomTotal**_:

package it.decisyon.ext.report.total;

import java.util.HashMap;

import Java.util.List;

/\* Interface relating to the generation of the java custom totals associated to the reports\*/

public interface IExtReportCustomTotal {

/\*\* It returns the totaling value relating to the values of the past cells such as

&#x20;\* subject of the call, for the crossing of row and column row-col

&#x20;\* @param valueCells the list of the values of the cells associated to the total

&#x20;\* @param row the row of the total

&#x20;\* @param col the column of the total

&#x20;\* @param additionalInfo additional information set for future developments

&#x20;\* @return

&#x20;\*/

&#x20;public String getTotalValue(List\<ExtValueCell> valueCells, int row, int col,HashMap\<String,Object> additionalInfo) ;

}

The _**ExtValueCell**_ class indicates the value of a cell consisting of a key-value pair.

The class consists of:

* The public builder ExtValueCell(String relativeElementID,String cellValue) with parameters:
  * **relativeElementID**: id of the cell of the report;
  * **cellValue**: value of the cell of the report.
* Methods:
  * **getRelativeElementID**(): It returns the ID of the cell.
  * **getCellValue**(): It returns the value of the cell.

Below an example is shown of building a class for the calculation of the total which concatenates the value and the id of the cells in the following format:

_**\<value1-id1>\<value2-id2>...\<valueN-idN>**_

package IT.Decisyon./ext.reports ( )Export;

import java.util.HashMap;

import Java.util.List;

import it.decisyon.ext.report.total.ExtValueCell;

import IT.Decisyon./ext.reports ( )TOTAL:IExtReportCustomTotal;

public class I\_TestCustomTotal implements IExtReportCustomTotal {

&#x20;@Override

&#x20;public String getTotalValue(List\<ExtValueCell> valueCells, int row, int col,HashMap\<String,Object> additionalInfo) {

&#x20;String result = "";

&#x20;for (ExtValueCell extValueCell : valueCells) {

&#x20;String cellID = extValueCell.getRelativeElementID();

&#x20;String cellValue = extValueCell.getCellValue();

&#x20;result += "<"+cellValue + "-" + cellID + ">";

&#x20;}

&#x20;return result;

&#x20;}

}

### Other Specific Properties of Totals

The following are also available under totals properties (_Total_ group):

* **Apply-to-single-element**, to insert a totals row or column, even when there is only one element on which to apply the total (enabled by default).

![](<../../../../.gitbook/assets/33 (7).png>)

* **Compact-Axis** In compact form with respect to rows or columns the aggregating levels are hidden, leaving only the level of detail to be seen and on this all totals, both cumulative and partial, are reported.

![](<../../../../.gitbook/assets/34 (7).png>)

If the report also contains a custom total Customized totals you need to define which total will take precedence in the calculation, via the total _**total-calc-precedence**_ property, which allows this setting to be executed :

* _\<standard-_&#x74;otals> to give precedence to standard total functions;
* _\<custom-totals>_ to give precedence to custom total&#x73;_;_

Example: total-calc-precedence

![](<../../../../.gitbook/assets/35 (7).png>)

_This report has two totals:_

* _Sum: returns the sum of the totals for the metrics Sales Qty and Sales Val._
* _TOTAL: calculates the sum of the values of column C._

_In the first report, precedence is given to standard totals (\<standard-totals>) and the sum refers to standard totals._

_In the second, precedence is given to calculating custom totals (\<custom-totals>) and the system finds the sum of the values for column C._

## Custom Totals ( Excel-like) Section

DAC allows you to analyze report data in a similar way to that used in an Excel spreadsheet. It is possible to create formulas, even complex, with the help of some preset functions made available by the system.

You can only use these functions after inserting a custom total inside a report. You can do this by right-clicking the Add custom total menu item together with the rows or columns of the report.

After inserting the total, the system automatically activates a bar with the commands to build a new formula.

![](<../../../../.gitbook/assets/36 (7).png>)

The line or column for the custom total will be added, respectively, above the line or to the left of the column that it was requested for.

Any errors occurred during the formula calculation will be notified to the user through a detailed message in the cell of the report (only the detail for the first error that occurred will be displayed; after a change in the formula any other inconsistency will be displayed).

The _**Remove total**_ item deletes the line or column for the total, while _**Modify total**_ allows users to modify the custom total, activating the command bar again.

When a total is applied, the system implicitly activates the property activat&#x65;_-sorting_ which makes it possible to modify the position of rows and columns.

The Excel-like functions also support Java commands in the formula, which greatly increases functionality. It is especially interesting the application that allows the _use_ of _the_ **col** and **row** variables, made available by DAC, to refer to report columns and rows.

The ![](<../../../../.gitbook/assets/37 (7).png>) button of the totals command bar opens the _**Custom Total**_ window where it is possible to select a series of functions grouped by topic:

* [Mathematical](total-functions.md#mathematical-functions) Functions for mathematical formulas
* [Report Re](total-functions.md#report-references)ference&#x73;**:** for the functions to reference the data in the report
* [SumFunctions](total-functions.md#sum-functions) for sum
* [Formatting](total-functions.md#formatting-functions) Functions for functions that format numeric values
* [Conversion](total-functions.md#conversion-functions-and-formulas-in-java-code) Functions for functions that convert data, used in complex operations.

In the _Report References_ and _Sum Function group,_ the functions can be applied, with both absolute and relative reference.

_An absolute reference_ _(with $ notation)_ refers to the absolute _position_ of a cell. If the position of the cell in the formula changes, the absolute reference remains unchanged, therefore changing the reference data.

_For example, if you move the cell to the rows below or to the columns to the side, the reference will not be adjusted._

_**An absolute reference or**_ _**OLAP**_ _(without $ notation)_ refers to the relative position _of_ a cell: if the position of a cell in the formula changes, the reference to the position changes automatically.

_For example, moving a cell from the position B3 to B5, the system will automatically change the reference inside the formula._

### Mathematical Functions

The _Math_ Functions category contains functions that apply purely mathematical calculations including both complex formulas, such as the calculation of trigonometric functions, and simpler ones, such as the search for a maximum or minimum number.

The functions are as follows:

* _**ABS:**_ absolute value. _E.g.: ABS(4.28)=4 , ABS(-7)=7_
* _**ATAN:**_ arctangent angle
* _**CQRT:**_ cubic root
* _**EXP:**_ power in base E
* _**FLOR:**_ rounding to nearest lower whole number (rounding down)
* _**HYPOT:**_ square root of the sum of squares

_E.g.: HYPOT(3,6)= SQRT(45) = 6.7_

* _**LOG:**_ natural base logarithm
* _**LOG10:**_ logarithm base 10
* _**MAX:**_ maximum between two numbers _E.g.: MAX(1,-22)=1_
* _**minimum:**_ between two numbers
* _**POW:**_ power of the number (base) raised to the exponent _E.g.: POW(2,6) = 64_
* _**REST:**_ division remainder _E.g.: REST(27,2)=1_
* _**RINT:**_ truncation of whole number _E.g.: RINT(6.01)=6 , RINT(12.86)=12_
* _**ROUND:**_ rounding to nearest whole number (up or down)

_E.g.: ROUND(4.45)=4 , ROUND(6.52)=7_

* _**RANDOM:**_ random decimal number between 0.0 and 1.0
* _**SIGNUM**_: function that returns the values +1 for positive numbers and -1 for negative ones
* _**SQRT:**_ square root of positive number &#x45;_**.**&#x67;.: SQRT(100)=10_
* **TANH:** hyperbolic tangent

The example shows how to use the mathematical function _**MIN**_ to calculate the minimum value between two numbers.

Step 1: Using (x)MIN

![](<../../../../.gitbook/assets/38 (7).png>)

_In the report in the figure we apply a custom total to a report row: we go to the desired row and right-click on Insert Total_

Step 2: Using (x)MIN

![](<../../../../.gitbook/assets/39 (7).png>)

The system enables the bar to determine the new total, where the title is inserted in the Title section and clicking on the ![](<../../../../.gitbook/assets/40 (7).png>) button we access the window for the selection of functions.

* In the Math Function section, you choose the function Min.
* Then you select the two cells B2 and B3 (double-click), which will be inserted in the formula area.

These are shown with the CELL function and the coordinates of the chosen cell.

Step 3: Using (x)MIN

![](<../../../../.gitbook/assets/41 (7).png>)

_Finally we click on the_ ![](<../../../../.gitbook/assets/42 (7).png>) _button to save the formula and add the custom total row to the report: the system calculates the minimum between the two values of the selected cells, highlighted by the formatting of the inserted total._

### Report References

In the _Report References_ category it is possible to find functions that allow users to refer to report data, in terms of cells, rows, columns, etc.

References to data are absolute if the reference has the notation $, otherwise it is relative to the selected data, identified by levels and metrics (OLAP coordinate).

We list here these functions with a description of the type of reference:

* **CELL and CELL$** cell value in the position specified through column and line index.

Double clicking the cell shows the CELL function _\[Example: CELL(B3)]_.

* **COL and COL$:** cell value referred to the column specified through column index

Double clicking on the column returns the function COL

_COL(B), the function returns the cell value of the column B row by row]._

![](<../../../../.gitbook/assets/43 (7).png>)

* **ROW** and **ROW$** cell value referred to the specified line in _alphanumeric format \[Example_: The position is preserved through OLAP coordinates
* **COLS$\_ID** ID code of selected column values

_For example, if you select the column containing the description of the products \[COLS$\_ID(B) ], this function returns the ID code for each individual product._![](<../../../../.gitbook/assets/44 (7).png>)

* **CURRENTCOL** and **CURRENTROW** show respectively the value of the current column and **row** _(can be used for functions subject to row or column number)_

![](<../../../../.gitbook/assets/45 (7).png>)

* **OLAPKEY(**(_X, N_), where X indicates the column and N the row:

the function provides the OLAP key for the cell specified by the given coordinates.

This function allows users to have a specific cell reference that, along with other Excel-like operations, allows them to apply different aggregation functions to each report level (see illustrative example)

* **OLAPCELL**, **OLAPCOL**, **OLAPROW** functions used automatically by the system, when references, respectively, to cells, columns or rows are lost. These show the cell value determined by the OLAP coordinates for the cell, column, row itself _\[Example: OLAPCELL(olap\_key), with olap\_key e.g. = BU01, Product 10, Sales\_Qty]_; for example when a function of _Report Reference_ contains references to hidden levels, as happens in a drill operation (see _following_ example)

#### Example Absolute Reference/Coordinate OLAP

The examples **CELL , CELL$** show function behavior with or without the $ notation.

Step 1: Function CELL

![](<../../../../.gitbook/assets/46 (7).png>)

_Create a report and enter a Custom Total which uses the CELL function. Specify the value you want to show on the total. In this case, the displayed value will be the one in the cell with coordinates B2 associated with the quantities of Product10 sold._

Step 2: CELL Function

![](<../../../../.gitbook/assets/47 (7).png>)

_We move the Product 10 to row 9. The system automatically updates the cell reference to the new position taken by the product._

_Changing in fact the total (Modify total item) we see that the system has updated the formula with the new product coordinates, in this case B9._

Step 1: CELL$ Function

![](<../../../../.gitbook/assets/48 (7).png>)

_We create a report and we use grouping by levels. We choose the total CELL$, which takes into account the absolute position of the cell specified in the formula. In the example we choose the cell C3, applied to the report column:_

_the cell value C3 will be reported for all report rows._

Step 2: Function CELL$

![](<../../../../.gitbook/assets/49 (7).png>)

_If we put together the values for the year 2005, in the cell C3 there will be a new value: no longer 57,358.00 but 134,816.00._

_In the Custom Total column, the new value will then be reported._

#### Example of Using OLAPCELL

Step 1: CELL/OLAPCELL Function

![](<../../../../.gitbook/assets/50 (7).png>)

_Apply the CELL function to a report with grouped levels: Business Unit and Product._

_We enter a custom total with the function CELL in the cell Sales Qty, Product 10 (cell B3): the cell value will be reported for all report rows._

Step 2.:CELL/OLAPCELL Function

![](<../../../../.gitbook/assets/51 (7).png>)

_If we close the Business Unit grouping, we lose the reference to the product and we cannot update it with a new position. The system then warns you and automatically uses the OLAPCELL function, which allows you to maintain the position and show Product 10 data correctly. The formula is displayed as a key, referred to line and column._

**OLAPCELL(("#@SALES\_QTY\_1\_Sum#Business\_Unit\~0#Product\~SKU\_10"))**

_The function OLAPCELL in fact allows users to keep using the values of the initial formula ._

### Sum Functions

Functions of _**Sum**_ type are used for sum calculation on report cells, rows or columns.

We remind users that references to data are absolute if it has the notation $, otherwise it is relative to the selected data, identified by levels and metrics (OLAP coordinate).

* **COLSUM, COLSUM$:** applies the sum of values for the specified column, for the last dimensional grouping.

![](<../../../../.gitbook/assets/52 (7).png>)

* **COLSUMTOTAL,** COLSUMTOTAL$**:** applies the sum of values for the specified column, for all the report rows

![](<../../../../.gitbook/assets/53 (7).png>)

* **ROWSUM, ROWSUM$:** applies the sum of the values of the specified row, for the last dimensional grouping
* **ROWSUMTOTAL, ROWSUMTOTAL$:** applies the sum of values for the selected row, for all the report columns
* **COLSUMGROUP** applies the sum of the values of the specified column for a dimensional level in the report. The dimensional level the sum is applied to is indicated in the formula:

_COLSUMGROUP(D,B)_

Where _D_ identifies the column the sum is applied to, while _B_ is the dimensional level the sum will be applied to.

![](<../../../../.gitbook/assets/54 (6).png>)

* **ROWSUMGROUP** allows you to execute the sum by row, grouping the values for a dimensional level in the report.

The dimensional level the sum is applied to must be specified in the formula. For example, ROWSUMGROUP(4,1), where 4 identifies the row the sum is applied to while 1 is the dimensional level the sum will be applied to.

* **COL\_RUNNING\_SUM,COL\_RUNNING\_SUM$** allows you to obtain the progressive sum of values in the selected column.

![](<../../../../.gitbook/assets/55 (6).png>)

### Formatting Functions

In the _**Formatting Functions**_ section, there are functions for the formatting of numeric values associated with the metrics:

* **NUM\_FORMAT(\[metric reference]):** inherits the style set in the metric, as defined in the _Metric_ folder of the _Metric Format_ window (see _Metrics and Filters Administrator ,_ _Style for the values section_).

![](<../../../../.gitbook/assets/56 (7).png>)

* **NUM\_FORMAT2(\[metric reference], \[x]):** setsthe number of decimal figures, indicated in \[x]
* **NUM\_FORMAT3(\[reference metric], \[x], ‘\[m]’,’\[**&#x64;**]’),** sets:
  * \[x], number of decimal figures,
  * \[m], character separating the thousands,
  * \[d], character separating the decimals.

Step 1: NUMFORMAT (Metric Format)

![](<../../../../.gitbook/assets/57 (7).png>)

_We define a custom total with the following formula: NUM\_FORMAT(COL(B))._

_This function returns the metric with the same formatting (note the additional character)._

Step 2: NUMFORMAT2 (Decimal Number)

![](<../../../../.gitbook/assets/58 (7).png>)

_We define a custom total with the following formula: NUM\_FORMAT2(COL(B), 2). This function returns the metric with two decimal figures._

Step 3: NUMFORMAT3 (Decimals and Thousands)

![](<../../../../.gitbook/assets/59 (7).png>)

_We define a custom total with the following formula: NUM\_FORMAT3(COL(B),2,"\*",".")._

_This function returns the metric with two decimal figures. The character separating thousands is the asterisk, while for decimals it is the period._

### Conversion Functions and Formulas in Java Code

In the _**Conversion**_ _**Functions**_ section there are conversion functions for values displayed in the report, which are by default of numeric type (type long). The conversions are typically used when we apply Java formulas in custom total formulas.

* **TOINT:** conversion of a double value (numeric) to whole value _\[Example: TOINT(CELL(B2))]_
* **TONUMBER$:** conversion of an alphanumeric value to a whole value _\[Example: TONUMBER("100")]_
* **TOSTRING:** conversion of a numeric value to alphanumeric (string) _\[Example: TOSTRING(100)]_
* _**PARAM\_VALUE:**_ this allows you to enter parameters in formulas for totals.

This function converts a parameter to its corresponding value, if defined.

If the parameter value does not have a value, or it is not numeric, the function returns '0'.

_For example: PARAM\_VALUE("?Business\_Unit?" ) to the selection of a Business Unit in the dashboard the parameter will be valued with that choice._

The examples below show how to build formulas which perform checks on the selected data through Java code and custom total functions.

### Illustrative Examples Excel-like

Below are some complex applications of Excel-like functions, where both DAC commands and simple Java code are used.

Of special interest are:

* the one for calculating the incidence of a level, with respect to a higher aggregation level (see application example).
* the one which uses _the_ _**col**_ and _**row**_ variables, made available by DAC to refer to report columns and rows (see application example).
* the one to determine separate and level-dependent aggregations, which in the example give an incidence at product level and a sum at region aggregating level (see illustrative example).

Below is an illustrative example on the enabling TAG for Drill-through. Another example can be found _in the Model_ Administrator, about TAG for link, again applied through a custom total.

Example of the Use of COL and COLSUM to Calculate Incidence

Step 1: Incidence Calculation

![](<../../../../.gitbook/assets/60 (7).png>)

_In this example, we want to calculate the incidence of Sales Val, of detail values (Business Unit) on parent level (Month)._

_The function we apply is the ratio between the value of detail, given by the function COL, and the total value of the level parent, given by COLSUM._

_The formula is indicated in the figure at the top. The value of the function COLSUM is also reported, which calculates the total of Business Unit, for each month._

_To verify calculations we apply a sum-type total: note that for each month, the incidences are divided by Business Unit (the sum of the incidences is always 100, for every month)._

Step 2: Incidence Calculation (with Multiple Aggregated Levels)

![](<../../../../.gitbook/assets/61 (7).png>)

_Adding another parent level (Year) and setting the display to an aggregated form (Drill), the calculation of incidence still takes place correctly:_

* _The report at the top shows aggregated data by year: in COLSUM we have the sum of the values of the last level, that is the sum of years (as highlighted by the calculation Sum of the total). The sum of incidences is 100, therefore for each year we calculate the incidence on the total._
* _The report at the bottom presents the aggregated data, with a drill on 2006 and a drill on the month of February. Note that:_
  * _For each month the incidence on the year is shown (sum of incidences for the year 2006 is 100)_
  * _For each Business Unit in February we calculate the incidence on the month total (sum of incidences for February 2006 is 100)_

_In conclusion, the COLSUM on aggregated data always shows the sum on the aggregating level immediately above: for BU it shows the sum on the month and for month it shows the sum on the year._

_This allows users to always obtain correct incidences without the need for complex metrics, defined with secondary divisions and aggregations, necessary to obtain correct results._

Example of Use of Row and Col Variables

Step 1:Use of the Variables Row and Col Use (x) CELL

![](<../../../../.gitbook/assets/62 (7).png>)

_In the report shown in the figure we have applied custom totals. For the metric Sales Val the ACTUAL total (2006) calculates sales for the current year (2006), while the LAST YEAR total (2005) calculates sales for the year before the current one. The same operation is applied to the metrics that calculates the incidence._

Step 2: Use of Row and Col Variables

![](<../../../../.gitbook/assets/63 (7).png>)

_The Actual VS Last Year total uses the Col variable that allows you to apply a different total to any specific column._

_The formula is read as follows:_

_if the column equals 2 (in this case the column with index 2 is Sales Val), apply the incidence formula,_

_otherwise, find the difference between the totals in rows 8 and 9_

Example Using OLAPKEY for Aggregation Functions Conditional on the Report Level

![](<../../../../.gitbook/assets/64 (7).png>)

_The report shows quantities sold (Sales Qty) by product, aggregated in turn by region._

_We want to present the incidence of sales of each product on the total for the region._

_We obtain a first total OlapKey 1 to obtain the OLAP key for sales (values in column B): the function is reported in the figure, note that to find the row we have used the row function (described in the previous example); the value of the cell with coordinates (B,2) has OLAP key (#@SALES\_QTY\_Sum#Product\~SKU\_10#Region\~701 ) that is the value in the metric (sales Qty) content in the cell corresponds to the Product 10 for the region with code 701 (Piedmont)._

_We obtain a second total, OLAP key 2, where we apply an IF statement (JavaScript) whose condition verifies that the row contains the keyword “Prod”. In this case, we apply a formula to calculate the incidence of the product on the total for the region (as described in the first example). Otherwise we show the value of column B for sales_

#### Example with JAVA command “SWITCH”

In this example we apply a function showing messages dependent on a metric value, specifically the number of bonuses acquired on the quantities sold to each customer group.

The function used is the Java function**s witch**, together with the function TOINT.

Step 1: Function TOINT and ROUND

![](<../../../../.gitbook/assets/65 (7).png>)

_Let's take a report including: Year, Customer Group, Sales Qty._

_We define a formula that extrapolates the decimal part of Sales Qty:_

* _function TOINT to trasform the value from numeric to whole_
* _function ROUND to round up the value_
* _function COL applied to metric column_

Step 2. Function TOINT and JAVA SWITCH

![](<../../../../.gitbook/assets/66 (7).png>)

_We define the switch command to assign bonuses as follows:_

* _Sales Qty=6 50 extra bonus_
* &#x20;_Sales Qty=25 150 extra bonus_
* _Sales Qty=36 500 extra bonus_
* _otherwise no bonus_

_Define a variable of integer type called “million” to which the value contained in column D will be passed (value relating to column C but with rounding). Note that you can use multiple Java commands in the formula area (they just need to separated by a ‘;’)_

0; **int million** = TOINT(COL(D));

**switch** (million)

&#x20;{**case**{case 6: result = 50 +" extra bonus";

&#x20;**break**;

&#x20;**case**case 25: result =150 +" extra bonus";

&#x20;**break**;

&#x20;**case**case 36: result = 500 +" extra bonus";

&#x20;**break**;

defaul&#x74;**:** result = "no bonus"; }

0; **int million** = TOINT(ROUND(COL(C)/10000000));

**switch** (million)

&#x20;{**case**{case 6: result = 50 +" extra bonus";

&#x20;**break**;

&#x20;**case**case 25: result =150 +" extra bonus";

&#x20;**break**;

&#x20;**case**c36: result = 500 +" extra bonus";

&#x20;**break**;

defaul&#x74;**:** result = "no bonus"; }

#### Example with JAVA “IF” Statement

It is possible to define totals which use the IF function of the Java code. In this example we want to verify the quantities sold to client groups (a message OK will be shown if above 100 pieces, KO otherwise).

Step 1: JAVA IF Function

![](<../../../../.gitbook/assets/67 (7).png>)

_Lets take a report including Year, Customer Group and Sales Qty._ _We define the custom total that will use as control IF:_

_The initial value set in the formula will be the one shown in case the next condition does not take place. IF verifies that the values in column C are greater than 100, if so, it will display the string OK in the total_

_Note: As you can see in the previous example, a return value of the function is always specified (in this case the “KO” value). This is because the formula must have an obligatory default return in case the possible condition of IF is not met._

#### Example with JAVA Command “Ternary”

This specific operator is defined as follows: _\[condition]?\[result if true]:\[result if false]_

Step 1.JAVA TERNARY Function

![](<../../../../.gitbook/assets/68 (7).png>)

_The report in the figure shows the quantities sold by month and year. We want to create a column that will return the string “Year 2005” only for quantities sold in the year 2005, otherwise the string will return ‘not year’. For comparison, we use the CURRENTROW function that returns the row ID (the year 2005 is between the rows 2 and 7)._

![](<../../../../.gitbook/assets/69 (7).png>)

#### TAG Drill-through

We remind users that the syntax of the TAG enabling Drill-through is of the type: _**<@DS1=1/> to enable the**_ Drill-through defined in group 1, while **<@DS2=1/>** enables the Drill-through in group 2.

Step 1: Excel-Like and Tag drill-through

![](<../../../../.gitbook/assets/70 (7).png>)

_A custom total has been created in the report in the figure, to verify whether quantities are above a threshold (200,000 pieces): if they are above this threshold, the message OK is inserted, otherwise we enable a drill-through to open a detail for the provinces._ _The drill-through setting is_ _carried out in the specific properties._

Step 2:Excel-Like and Tag Drill-through

![](<../../../../.gitbook/assets/71 (7).png>)

_It is possible to check on DAC the correct behavior of the set functions._
