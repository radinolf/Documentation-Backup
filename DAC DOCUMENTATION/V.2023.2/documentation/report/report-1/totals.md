# Totals

### Total Functions <a href="#toc498423813" id="toc498423813"></a>

You can calculate totals by setting the various types of **simple aggregation** functions in the reports (sum, average, etc...).

**Note**_**:**_ The total definition functions are disabled on Tablet devices.

By contrast, the reports may have been published with more complex functions, such as the weighted average or others created by the developers in a fully customized way. In addition, at publication level, specific functions may have been applied for each report metric.

The totals are calculated with respect to the dimensional levels of the report by considering all the levels (**cumulative totals**) and some levels only (**partial totals**).

You can apply the totals to the data shown in the report (which changes according to the drill operations), or on the detailed data (which does not change in the drill operations).

You can also set totals on elements of the report chosen by the user, through Excel-like functions.

The totals on a report are set from the window opened with the _**Totals**_ _**definition item**_ (_Objects explorer_ section).

![](<../../../.gitbook/assets/0 (5)>)

By selecting the item, the window opens to define the cumulative or partial totals to be entered in the report.

![](../../../.gitbook/assets/1)

In the **Totals** panel, you can select the operations to be applied in order to calculate the total.

In the **Type** area, you can specify whether the total must be cumulative, shown at the top (_TOP of report_) or at the bottom (_BOTTOM of report_) of the report, by level (_By Level_).

In the **Apply location** area you can specify whether the calculations must be performed on the data _in rows_ (Apply to ROWS), columns (_Apply to COLUMNS_) or to both (_Apply to BOTH_).

In the section to the right, **Levels** sets whether the partial totals must be applied to all levels or not.

The figure below shows an example of how to use totals into the report:

* **cumulative total** placed at the **top** (setting _Cumulative_ and _TOP of report_);
* **partial total** (setting _By Level_):
* applied to the **rows** only;
* calculation of _the Sum_.

![](<../../../.gitbook/assets/2 (9)>)

When you select the **Total** function, the result in the report will always respect the aggregations of the field selected while defining the composite metric.

Let us look at the example of the _**%Province Vs Region**_ composite metric calculated as so:

_**(Qty sold Prov/Qty sold Reg)\*100**_.

where the single component metrics were both selected with sum aggregation.

By applying the **Total** function you get:

_**(Sum(Qty sold Prov)/Sum(Qty sold Reg))\*100.**_

While with the function **Sum**:

_**Sum((Qty sold Prov/Qty sold Reg)\*100).**_

#### Weighted Average (Weighted Avg) <a href="#toc34301133" id="toc34301133"></a>

The Weighted Avg function defines a **weighted average** compared to one of the metrics in the report. You can define up to three totals of this type.

In the _weighted arithmetic average_ of the values ![](<../../../.gitbook/assets/image (405).png>), a _weight_ ![](<../../../.gitbook/assets/image (1459).png>) is assigned to each value: ![](<../../../.gitbook/assets/image (456).png>).

The **weight** of each value is in general represented by the number of times when the values occur (frequency), but may also mean the (objective or subjective) importance the single value plays in the distribution.

The calculation of the average requires you to sum the weighted values and divide![](<../../../.gitbook/assets/image (323).png>) them, not with respect to the number of the values but rather to the sum of the weights. Therefore the formula of the weighted average ![](<../../../.gitbook/assets/image (697).png>)is:

![](<../../../.gitbook/assets/8 (10)>)

To apply a weighted average the report must have the metric on which to apply the weighted average, and the metric to be used for the weights.

Example: Weighted Average

![](<../../../.gitbook/assets/9 (2)>)

_The report in the example contains the discount and the quantity of the products sold._

_A weighted average of the discount was applied with respect to the quantity; because of this, greater weight was given to the discount applied to those products that were sold in greater quantity._

_The simple average is also reported for comparison purposes. On the totals applied to the discount, we see how the simple average differs from the weighted one; in the weighted average, the first product had a greater weight (greater sold quantity). The value of the weighted average on the discount is not visible in the report because that value was published in hidden mode._

#### Visualization or Detail Totals <a href="#toc34301134" id="toc34301134"></a>

The totals are always calculated on the data _displayed_ in the report. Please remember the various visualization modes:

* without aggregation, where you have the maximum level of detail of the report
* aggregation for the _drill_ operations (layout or dimension)
* aggregation on the values of the levels in page-by (with the \[Total] _item)_

In each of these cases, the function for the total is applied to the data displayed, respecting the aggregation chosen on the report.

You can change this behavior by setting the rule according to which, in order to calculate the total, the detailed data must **ALWAYS** be considered. In other words, the data without aggregation must be considered by choosing the **field of application** of the total on the data _displayed_, or on the _detailed_ data of the report.

Example: Visualization or Detail Totals

Step1: Average of the Sales Displayed

![](<../../../.gitbook/assets/10 (2)>)

_In this example a displayed AVERAGE was applied. The results are compared by changing the type of report view:_

* _WITHOUT AGGREGATION, you get the average of all the quarters for the years displayed_
* _WITH AGGREGATION, you obtain the average of the years, whose values were already aggregated on the quarters_

Step 2: Detailed Sales Average

![](<../../../.gitbook/assets/11 (9)>)

_Instead, by applying the AVERAGE total of the type \<entire-result> to the same report you obtain:_

* _WITHOUT AGGREGATION, the same result of the previous case_
* _WITH AGGREGATION the result does not change, the function continues to be applied to the quarters (coinciding with the maximum degree of detail of the report) and not to the years (aggregating level)_

## Tutorial

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/20.Total%20Funtions/TotalFunctions.mp4" %}
