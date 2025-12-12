# Totals

Totals can be calculated by setting different report functions, such as:

* simple aggregation (sum, average, etc..)
* total function complying with the formulation defined for composite metrics
* [weighted average](total-functions.md#weighted-average-weighted-avg)
* [different functions](total-functions.md#different-total-by-metric-composite), for each report metric

The totals are calculated with respect to the dimensional levels of the report by considering all the levels (**cumulative** totals) and some levels only (partial totals).

The interface allows you to customize the names associated with operations carried out on totals through aliases.

Totals can be applied to the data displayed in the report (which will change according to drill operations), or exclusively on detail data (which will not change) (details in Visualization or detail totals (calc-type) section.

It is also possible to set totals on report elements selected by the user, through the function of Customized totals.

_The_ _**total-calc-precedence**_ _property (Totals group) lets you perform this setting (\<standard-totals> to give precedence to standard total functions; \<custom-totals> to give precedence to custom totals (see_ _example)_

* _\<standard-totals> to give precedence to standard total functions;_
* _\<custom-totals> to give precedence to custom totals;_

![](<../../../.gitbook/assets/0 (29).png>)Formatting for totals’ rows and/or columns is set from the Total group properties.

Report totals are set from the _Totals Definition_ window opened by the button (in the toolbar).

![](<../../../.gitbook/assets/1 (13).png>)

![](<../../../.gitbook/assets/2 (10).png>)In the _**Operations**_ section we choose the type of total function to apply to the report, divided in the following groups:

* _Simple_ aggregations where the most common total functions are listed
* [_Weighted Avg \[n\]_](total-functions.md#weighted-average-weighted-avg) for the calculation of weighted averages
* [_Composite \[n\]_](total-functions.md#different-total-by-metric-composite) to apply total functions specific to each report metric

The central section defines the elements the total function is applied to:

![](<../../../.gitbook/assets/3 (5).png>)

* At a cumulative level (check _**Cumulative**_), where the function is applied to all report values (excluding any partial totals or null values)

You can display the cumulative total at the top or the bottom of the report (selection limited to _**TOP of report**_ and _**BOTTOM of report**_)

* On single dimensional levels (check _**By**_ _**Level**_) for the calculation of partial totals, applied to ALL report levels.

In the _**levels**_ folder to select only the levels relevant to the calculation of the total.

* On rows, columns, or both (_**Apply location**_ section).
* In compact form (_**Compact**_ _**View**_ section), with respect to rows or columns: The aggregating levels are automatically hidden, leaving only the level of detail to be seen, on which all totals, both cumulative and partial, are reported (see following example).

Example: Formatting Totals Layout

![](<../../../.gitbook/assets/4 (3).png>)

_In this example, the first report is displayed without Compact View. In the second, Compact View has been activated at row level (Row dimensions). Totals are grouped at a single column level._

### Partial Totals (for Dimensional Levels)

By ticking the _**By**_ _**Level**_ checkbox , in the central section, you can enable

partial totals for **ALL** report dimensions.

You can limit the partial totals to the desired levels, selecting them in the **levels** folder, where report levels are listed.

![](<../../../.gitbook/assets/5 (28).png>)

Partial totals on dimensions in page-by can be obtained by simply applying cumulative totals. This is applied to the report section displayed; therefore every time the level value in page-by changes, a different report section is obtained, with the corresponding cumulative total.

Example: Partial Totals for Levels in page-by

![](<../../../.gitbook/assets/6 (21).png>)

_In this example, a cumulative total has been set._

_By changing the value of the year in page-by, the cumulative total for the chosen year is recalculated ._

Here are two examples: one applies the total to all levels and the other only to specific levels.

Example: Partial Totals on ALL Levels

![](<../../../.gitbook/assets/7 (4).png>)

_In this example, a partial total has been applied to ALL row levels._

_Note that for every aggregating level, the partial total of the levels it is the parent of is shown._

Example: Partial Total SOME Levels

![](<../../../.gitbook/assets/8 (20).png>)

_In this other example the partial total has been applied only to the Year.Therefore, the total will only calculated for the YEAR level in the report._

### Setting Aliases for the Totals

The _**alias-total**_ section allows users to modify the name of the function chosen for the total, simply by inserting an alias for the function of interest. In the alias section all the functions for the totals are listed on the left, and a label can be set for any of them: this label will be used for the total in place of the standard name.

![](<../../../.gitbook/assets/9 (4).png>)

For partial totals, you can only leave the level value and delete the function name: you must use the command %1. This command, on the cumulative total, has the effect of leaving the name empty.

Example: Aliases for the Total Sum

![](<../../../.gitbook/assets/10 (24).png>)

_The report in the example shows for each year (in page-by) the budget for the quarter and business unit. A cumulative total (in sum) is applied, giving the budget total for each year. We now set an alias for the Sum total: Total budget Year. The report will use this tag instead of the standard name Sum._

Example: Alias with %1

![](<../../../.gitbook/assets/11 (20).png>)

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

![](<../../../.gitbook/assets/12 (13).png>)

Step 1: Average of the Sales Displayed

![](<../../../.gitbook/assets/13 (18).png>)

_In this example, we apply a total average of type \<view> on the Sales Val \[Avg] metric (sales average)._

_The results are compared by changing the type report view:_

* _WITHOUT AGGREGATION you get the average of all the quarters for the years displayed_
* _WITH AGGREGATION, you obtain the average of the years, whose values were already aggregated on the quarters._

Step 2: Detailed Sales Average

_Instead, byapplying the AVERAGE total of the type \<entire-result> to the same report you obtain:_

* _WITHOUT AGGREGATION, the same result of the previous case_
* _WITH AGGREGATION the result does not change, the function continues to be applied to the quarters (coinciding with the maximum degree of detail of the report) and not to the years (aggregating level)_

![](<../../../.gitbook/assets/14 (4).png>)

Step 3: Page-by in Total on Disaggregated Data

![](<../../../.gitbook/assets/15 (4).png>)

_In this example we show what happens to the same report, when the level in page-by is \[Total]._

_The report is in disaggregated form and there is now also the metric on sales in sum (in addition to that in average)._

_We compare the results of AVERAGE total for the two types:_

_with\<view> , data are first aggregated for the BU in each quarter and then divided by the number of quarters_

_with \<entire-result> , , they are not aggregated by BU, so we carry out a sum of the BU for_ ![](<../../../.gitbook/assets/16 (11).png>)_all quarters () and then we divide by the BU of all quarters ()_![](<../../../.gitbook/assets/17 (10).png>)_)_

_Note that for Sales Val \[AVG] the result does not change, in fact:_

_the average of the average BU (view) coincides with the average of each BU (entire-result_

_while for the sales in sum (Sales Val) we obtain a different result, because:_

_the average on the BU data already aggregated in sum (view) is different from the average on the BU not aggregated (entire-result)_

### Total Function Section

The _Total_ function is used to _**calculate the totals for composite metrics**_: this function applies the same formula defined in the composite metric directly on the values before aggregation of the metric components.

We’ll use an example of a composite metric defined as the ratio between two metrics, used to calculate the incidence:

![](<../../../.gitbook/assets/image (721).png>)

the application of the _Total_ function follows these steps:

* First the aggregation function is applied to the metric components, a function set during their creation
* Then the formula is applied to the aggregated data



![](<../../../.gitbook/assets/image (650).png>)

Without this type of function we could have applied an average function, but this would not have given us the results we wanted:

![](<../../../.gitbook/assets/image (1554).png>)

### Weighted Average (Weighted Avg)

![](<../../../.gitbook/assets/image (456).png>)

Example: Weighted Average

![](../../../.gitbook/assets/29.png)

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

![](../../../.gitbook/assets/30.png)

In the list of Composite totals, there is also the _Empty_ item, useful if we don’t want to apply any total function to the metric.

Example: Different Totals by Metric

![](<../../../.gitbook/assets/31 (1).png>)

_In this example, we want to apply a total in sum for the budget and in average for the quantity sold. We set up an operation of type Composite, on the left: Composite 1_

_On the right the Composite 1 folder will appear, with the two report metrics, we choose the function:_

* _Sum for Budget_
* _Avg for Quantity_

_On the report we obtain totals that comply with the set functions._

### Other Specific Properties of Totals

The following are also available under totals properties (_Total_ group):

* **Apply-to-single-element**, to insert a totals row or column, even when there is only one element on which to apply the total (enabled by default).

![](<../../../.gitbook/assets/33 (4).png>)

* **Compact-Axis** In compact form with respect to rows or columns the aggregating levels are hidden, leaving only the level of detail to be seen and on this all totals, both cumulative and partial, are reported.

![](<../../../.gitbook/assets/34 (3).png>)

If the report also contains a custom total Customized totals you need to define which total will take precedence in the calculation, via the total _**total-calc-precedence**_ property, which allows this setting to be executed :

* _\<standard-_&#x74;otals> to give precedence to standard total functions;
* _\<custom-totals>_ to give precedence to custom total&#x73;_;_

Example: total-calc-precedence

![](<../../../.gitbook/assets/35 (1).png>)

_This report has two totals:_

* _Sum: returns the sum of the totals for the metrics Sales Qty and Sales Val._
* _TOTAL: calculates the sum of the values of column C._

_In the first report, precedence is given to standard totals (\<standard-totals>) and the sum refers to standard totals._

_In the second, precedence is given to calculating custom totals (\<custom-totals>) and the system finds the sum of the values for column C._
