---
description: Indicators are created by using the Indicator Designer module.
---

# Indicator Designer

A KPI (Key Performance Indicator) provides an immediate view of the trend of a critical variable. This variable encompasses significant parameters for describing the target to be achieved; specifically there are thresholds to indicate the positioning of the variable with respect to the target.The coloring indicates the direction of the target (towards low or high values).

![](<../../../.gitbook/assets/0 (10).png>)![](<../../../.gitbook/assets/1 (11).png>)![](<../../../.gitbook/assets/2 (8).png>)![](<../../../.gitbook/assets/3 (6).png>)

The KPI variable is defined in DAC by means of a metric and then is valued in a report.

Before creating an indicator, it is necessary to create a metric that represents the KPI variable; a report is then created with the metric, so values are obtained that can be monitored using the object indicator.

The metric will define:

* the thresholds, for which the KPI metric is monitored: if the value is in a reached (green), failed (red) or warning area (yellow) target zone.

Thresholds can also be defined using other metrics, thus making the range of values between the three zones dynamic;

* the _direction of the target_, indicating if the target was reached by near-maximum threshold values (high values) or by near minimum threshold values (low values);
* the correlation with other data, which can provide more detailed information on the trend of the KPI metric: a new Page will open with the information of interest;
* whether to include a single value for the KPI metric or several values, dependent on levels selected in the report that values it. For example, monitoring the sales trend compared to the previous year, with respect to the Business Units.

![](<../../../.gitbook/assets/4 (10).png>)

* the data presentation method, indicating a format, type of aggregation,…

The indicator can only be published on a Page by associating it with the component with the same name:

one of the specific properties allows the user to choose the graphic display from among those available.

Indicators are created by using the **Indicator Designer** module, which is opened from the _Application_ menu item.

![](<../../../.gitbook/assets/5 (6).png>)

The _Main Settings_ contain the title (name given to the indicator), which cannot be edited, and the description.

Do the following to create an indicator:

* _**Reports Name…**_

Select the report that contains the KPI metric (the report must have already been defined)

* _**Selected Metric**_

Select the KPI metric, among those contained in the report chosen under the previous point

* Define either fixed or dynamic thresholds;
* _**Operation**_

Set the type of aggregation to be applied to the values of the metric in the report; the report may contain multiple rows/columns, while only one value is to be displayed (except multi-row indicators, which are described below);

We recommend using the Total function if the KPI metric is a composite metric. This function applies the same formula defined in composite metric to component metrics, following their aggregation (_see Presentation Administrator, Total Function section_).

* _**Inverted**_

Set the direction of the target: by default, the target is achieved for high values (close to the maximum threshold).

![](<../../../.gitbook/assets/6 (8).png>)

A preview of the indicator is available in the lower pane, by using the _**Run Preview**_ button. Please note that publication is only possible on a Page, where other graphic displays can also be selected.

Other settings allow the user to further customize the indicator:

* on the format and presentation of KPI values
* to display the KPI metric with multiple values (multi-row), dependent on the levels selected in the report
* for correlation with other data

## Fixed and Dynamic Thresholds

Threshold values are shown in numeric mode in the fields _**Min**_ _**Value**_ and _**Max**_ _**Value**_ for the full scale, and in _**Min threshold**_ and _**Max**_ _**threshold**_ for intermediate thresholds (in the yellow zone).

Intermediate thresholds are calculated automatically by the system, so as to divide the green-yellow-red indicator areas into three equal sections. To _change the intermediate threshold values_, simply click on the lock icon and the fields will be write-enabled.

Step 1: Fixed Thresholds

![](<../../../.gitbook/assets/7 (4).png>)

Step 2: Fixed Thresholds

![](<../../../.gitbook/assets/8 (5).png>)

_The intermediate thresholds have changed, because the target is already achieved if the incidence of the customer reaches 50% of sales. Moreover, the failed target threshold occurs at a lower value lower than the default value: under 25%._

_Select the padlock and enter the new thresholds._

If dynamic thresholds are set, in addition to containing the KPI metric, the report associated with the indicator must contain the metrics which represent the desired threshold values.

The threshold will then be associated with the properties:

* _**minLimit**_ and _**maxLimit**_ for the minimum and maximum value of full scale
* _**minThreshold**_ and _**maxThreshold**_ for the minimum and maximum intermediate thresholds; these two properties are only enabled if the _padlock opens._

With the _\<number>_ value, the fixed numeric values will beused. Otherwise, choose one of the metrics of the report: in this case enable the _**aggregation**_ property to select the type of aggregation that it must be calculated with (required if the report contains more than one row).

Step 1: Dynamic Thresholds

![](<../../../.gitbook/assets/9 (5).png>)

_In this example, you want to monitor sales as compared to the target value, which is given by the Sales Val target metric, and also want to highlight whether they fall within 80% of the target (reached) or 50% of the target (failed)._

_Therefore, two other metrics are created for the intermediate thresholds:_

* _Sales Min KPI as 50% of the target_
* _Sales Max KPI as 80% of the target_

_The 4 metrics will be included in the report: the KPI (Sales Val) metric, the target metric and the intermediate threshold metrics_

Step 2: Dynamic Threshold

![](<../../../.gitbook/assets/10 (6).png>)

_Then create the indicator by selecting the report above, and setting the value of sales as the KPI metric (Selected Metric field). Set the thresholds as follows:_

* _Sales Val target in maxLimit_
* _Sales Min KPI in minThreshold_
* _Sales Max KPI in maxThreshold_

_Select the average as an aggregation for them all._

## Format and Presentation of Values

Selecting one of the three icons in the _**Symbology**_ field indicates the symbol to be displayed next to the value of the indicator (%, € and $).

![](<../../../.gitbook/assets/11 (7).png>)

To inherit the **format of the metric** that was set when it was created (see _Presentation Administrator,_ _Metric formatting_ section), select, in the _**valueFormat**_ property, the _\<metric>_ value; if the _\<default>_ value is used instead, the format indicated in _Symbology_ is taken.

To hide the values of all four thresholds, select the check in the _**viewThresholds**_ property.

![](<../../../.gitbook/assets/12 (6).png>)

An **alternative metric can be specified to the KP metric**:

In the _**metricViewed**_ property, select a metric different than the one used for calculating the position of the pointers, options that can be selected are those that are included in the report associated with the indicator. In this case, the value of the selected alternative metric is used in view.

## Multi-line

DAC offers the ability to create complex indicators through which more information can be provided with one single indicator, relating to the dimensional levels in the report.

By selecting the _**multiRow**_ property on the indicator, all the values in the table are displayed and the aggregated value is no longer displayed.

![](<../../../.gitbook/assets/13 (5).png>)

A legend indicates the coordinates of the cell. The same color is used for the arrow and for the indicator.

Note that the report to be created for this purpose must have the dimensional levels in rows (or columns) of the value to be displayed. We recommend putting the metric in page-by, otherwise it will be repeated throughout the legend.

![](<../../../.gitbook/assets/14 (6).png>)

We also recommended not entering too much information in a table, by limiting the number of levels on the rows/columns. Otherwise, reading KPI monitoring becomes difficult.

![](<../../../.gitbook/assets/15 (5).png>)

## Data Correlation

It is possible to connect the indicators with the correlated data to perform additional reporting and analysis processes by simply associating a Page with the indicator.

By selecting the _**linkPage**_ property, the following properties are enabled:

* _**associatedPage**_: to select a Page to associate with the indicator. The page must have been defined previously with the _Page Designer_ module.
* _**openAllPage:**_ when enabled, it opens the Page (full screen) correlated with the indicato&#x72;_**.**_

In DAC, the icon (represented by a table) ![](<../../../.gitbook/assets/16 (4).png>)appears under the indicator; this icon is the link to the correlated Page.

![](<../../../.gitbook/assets/17 (5).png>)
