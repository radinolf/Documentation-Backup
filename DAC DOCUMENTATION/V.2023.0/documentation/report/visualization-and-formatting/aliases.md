# Aliases

### Introduction



Clicking the ![](<../../../.gitbook/assets/67 (2).png>)button opens a window which allows you to define the aliases of the levels and metrics.

This operation is crucial for obtaining clearer descriptive headings without being subject to database rules, which do not allow spaces and special characters in field names.

![](<../../../.gitbook/assets/68 (4).png>)

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

![](<../../../.gitbook/assets/0 (22).png>)

_This example shows how to set aliases for report levels and metrics._

_The report shows metrics and levels with the names defined at the moment of creation._

Step 2: Setting Aliases for Levels and Metrics

![](<../../../.gitbook/assets/1 (34).png>)

_Aliases are set in the window of properties of the report (Picture 2)._

_We have defined the following aliases:_

* _for the metric Sales Qty we have set the alias Sales Quantity,_
* _for the level Ds Customer we have set the alias Customer Description._

Step 3: Reports with Aliases Associated with Metrics and Levels

![](<../../../.gitbook/assets/2 (5).png>)

_The report shows how metrics and dimensions are displayed after_ _the alias has been associated._

#### Parametric Aliases

Metric and level aliases can also be defined parametrically, that is, it is possible to enter parameters within the corresponding properties. The parameter will be valued later in a selection or input component (see _Presentation Administrator_, _Selection and input objects_ section), or from an exported level (see _Presentation Administrator_, _Exporting dimensional levels_ section): the parameter value will later replace the alias of the metric/level.

The example below shows a solution of this type, where the name of a metric depends on the year, and is selected from a check list.

Step 1: Creating Reports and Defining Aliases

![](../../../.gitbook/assets/3.png)

_The report in the figure shows sales by region according to the year selected in page-by_

_A parametric alias has been set for the Sales Qty metric._

_The syntax is as follows:_

&#x20;_“SALES BY ?YEAR?”_

_where ?YEAR? is a parameter, which will be transferred from a check list, created in the next step_

Step 2: Creating Pages

![](<../../../.gitbook/assets/4 (13).png>)

_We build a Page with the following elements:_

* _Check List with a list of years (set in sql-formula)._

_The name of the component should be the same as the one defined in the alias parameter: “YEAR”._

* _Crosstab with previously created report_
* _Graph associated with the same report._

_Filter the level Year of the crosstab and of the graph for the parameter defined in Check List._

Step 3: Display in DAC

![](<../../../.gitbook/assets/5 (22).png>)

_STEP 1: Note that on first access the Sales by ?YEAR? metric, found both in the report and in the graph legend, still has not been valued, as no year has been selected._

_STEP 2: We choose the year 2005 from the Check List, and the metric with the parametric alias is valued with the selected year._

_This behavior is visible both in the report and in the legend._
