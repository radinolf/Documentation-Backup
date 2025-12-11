---
description: How to create Filters
---

# Filters

A filter specifies the conditions that the data must meet so that:

* it may be displayed in a report
* or it may be used in the calculation of filtered metrics.

The difference between the two types of application is that in the first type all the metrics will be affected by the filter, while in the second type the condition is only applied to the filtered metric.

The filters are subdivided into two groups:

* [Direct filters](filters.md#direct-filters) where the condition is expressed on the dimensional levels, used to limit the data on the analysis lines (dimensions);
* [Range filters](filters.md#range-filters) where the condition is expressed on the values of the metrics

In these filters, in addition to expressing the condition, data partitioning may also be defined on which it must be applied. Range Filters cannot be applied to Metrics.

In case data filters are necessary depending on the user, you must define the user filters, which are of the same type as the direct filters, but are applied to the groups , and remain valid for any report displayed by the end user on RunTime (please see chap.[ User filters](filters.md#user-filters)).

DAC also defines the filters exclusively used by the single repor&#x74;_._

You can use a [parameter in the condition](filters.md#content-assist-on-filter-conditions) in Filters. In these cases, the condition is applied after you have valued the parameter.

Making a Filter parametric is especially useful when a report (or Metrics) is used on Pages. The parameter can be valued with one of the form objects or by a level exported from a report.

## Direct Filters

A direct filter is defined in the window opened from the menu item:

**Data Model>>**>>**Direct Filters management**, or the ![](<../../../.gitbook/assets/0 (2).png>) button on the tool bar.

![](<../../../.gitbook/assets/1 (5).png>)

Formula definition area

Dimensional level selection area

Selecting dimensional level values

The [filter condition](filters.md#content-assist-on-filter-conditions) may be expressed compared to the dimensional levels of the application. When typing the formula, you are supported by a [Content Assist](filters.md#content-assist-on-filter-conditions).

The system defines the formula of the filter by combining various conditions relating to the different dimension levels. Example: _Product@ID = ‘1’ AND MONTH@Description = ‘JANUARY’_.

Since the application of a filter in a report implies that all the levels in a filter are applicable to at least one metric of the report, using filters with many conditions may reduce their applicability in the reports: therefore we advise creating base filters to be applied to the report at the same time. The filter of the previous example may actually be divided into 2 filters:

Filter 1: _Product@ID = ‘1’_ Filter 2: _MONTH@Description = ‘JANUARY’_

To obtain the AND condition, just associate both filters with the report.

In the formula of the filter it is possible to enter a SQL instruction: for example, a filter with the products belonging to categories 1 and 2.

![](<../../../.gitbook/assets/2 (5).png>)

## Filter Condition on Dimensional Levels

If you want to apply a Filter condition on dimensional levels, you must select the level you want on the left side of the page.

![](<../../../.gitbook/assets/3 (3).png>)

Dimensional levels are structured for Cubes. You must first select the Cube at the top of the hierarchy, and then the levels.

The “field @ID” key fields and “Field@DS ” description field are indicated for each level. You set these fields when you are creating the Dimension (see _Mapping dimensional levels section_). The Filter condition can be expressed on the “ID” or on the “Description”.

Double-click to display the selected dimensional level in the formula definition field area. This is where you can enter a Filter condition.

**Note**: The names of the levels listed in the selection area correspond to the displayed names set when you created the Dimension. An exception is made if the dimensional levels use the same name displayed. In this case, the logical name of the level is indicated.

_For example, if you define two levels with the displayed name “Customer Type”, the following respective logical names appear on the list: Customer\_Type1@Description, Customer\_Type2@Description._

![](<../../../.gitbook/assets/4 (3).png>)

Comparison operators

Text functions

Functions for value sets

Logical operators

As shown in the figure, several functions and operators are available if you want to create a new Filter. You can also manually enter the SQL instructions in the formula definition area (the green check allows you to validate the formula entered).

The top button ![](<../../../.gitbook/assets/5 (4).png>) allows you to select the values of the key field or description of the level selected. A window opens listing the values of both fields. The value selected appears in the foreground. The figure below shows that the _Customer Type@Description_ field has been selected.![](<../../../.gitbook/assets/6 (3).png>)![](<../../../.gitbook/assets/7 (3).png>)

A search field also allows you to quickly narrow the search area.

Once you have identified the values to be filtered, check them. When you close the window, they will be indicated in the formula definition area.

The predefined functions to be used to write the Filter condition are in the **formula definition area** at the top.

![](<../../../.gitbook/assets/8 (1).png>)

* The _String function_ section contains functions for managing strings. These functions return the following values:

_**Starts with**_ - they start with a specified value

_**End with**_ - they end with a specified value

_**Matches**_ they are equal to the specified word (for the characters).

_**Contains**_ which contain the one specified

* The _Set Function_ section contains the set operators, which verify:

_**in**_ and _**in values**_ - the value equaling one of the values of a specified list (pertinent operator).

The second operator automatically opens the value window of the selected level.

_**not in**_ the value does not equal one of the values in a specified list (non- pertinent operator).

_**between**_ the value belonging to an interval, defined by a lower and upper limi&#x74;_**.**_

* The section to the right lists the _**logical operators:**_

_**AND**_ among several conditions, to return the elements that satisfy all conditions at the same time

_**OR**_ among several conditions, to return the elements that satisfy at least one of the conditions

_**AND NOT**_ among several conditions, to return the elements which do not satisfy the condition after the instruction

_**OR NOT**_ among several conditions, to return the elements that satisfy at least one of the conditions (the second is denied).

## Content Assist on Filter Conditions

A _content assist_ is active when you define Filter conditions. It suggests possible commands such as the list of dimensional levels, entering certain operations, DAC tags or user variables.

With an **initial mouse** **click** on the formula definition area, you activate a menu with the dimensional levels of the application (in alphabetical order).

![](<../../../.gitbook/assets/9 (2).png>)

When you **select the level**, you activate _content assist_ to select certain special operations:

![](<../../../.gitbook/assets/10 (3).png>)

* **IN()** allows you to enter a list of values between brackets.

If the dimensional level is descriptive, the system adds quotation marks inside the brackets. Otherwise the values will be entered with no quotation marks.

![](<../../../.gitbook/assets/11 (2).png>)

* **IN(...)** if you have selected it, the system displays the list of values for the selected level in a new window in multi selection.

![](<../../../.gitbook/assets/12 (2).png>)![](<../../../.gitbook/assets/13 (2).png>)

* **IN(?NAME\_LEVEL?)** If you have selected it, when the report is run the system will automatically transform the level into parametric Filter.

![](<../../../.gitbook/assets/14 (2).png>)

**When you type the "%"** string, you activate a menu with the list of USER VARIABLES (see _System Administrator User , User variables section_).

Example: USER variables %...

![](<../../../.gitbook/assets/15 (2).png>)

_In the example, you enter the keyword % for the user variables and select the one relating to the email. "%" %U\_mail%_

## Range Filters

Range filters define conditions on the metrics, already defined with the [Metrics Management](metrics.md) module.

Filters are then associated with the reports, which apply the conditions defined to the set of data as a whole.

The dimensioned range filters apply the filter condition on the data previously [partitioned for one or more dimensional levels](filters.md#partitioning-for-dimensional-levels); on this partitioning it is possible to [apply additional filters, of the direct type](filters.md#parametric-filter), to refine the filter criterion further.

A range filter is created in the window opened from the menu item:

**Data Model>>Range Filter**

or from the toolbar, using the ![](<../../../.gitbook/assets/16 (2).png>) button.

![](<../../../.gitbook/assets/17 (2).png>)

In the _Metrics_ folder, select the metrics on which to apply the filter condition; with a double click, it is reported automatically in the formula definition area (bottom, right).

The system also specifies the mathematical, comparison and logical operators to be entered in the formula using the correct buttons at the top of the lower text box.

Select the dimensional levels for the [data partitioning](filters.md#partitioning-for-dimensional-levels) in the _Dimensions_ folder.

In the _Direct Filter_ folder, select the [direct filters](filters.md#direct-filters-on-partitioning) to be applied to the partitioned data.

In the next example, a simple Range Filter is defined to obtain the years with sales below a target, in a report which only has the year level.

Step 1: Simple Range Filter

![](<../../../.gitbook/assets/18 (1).png>)

_Create a simple range filter where the filter condition of the sales lower than a target of 50 million is defined: Select the Sales Val sales Metric (double-click) and enter the formula in the area provided._

Step 2: Simple Range Filter

![](<../../../.gitbook/assets/19 (1).png>)

_Create a report with the Year level and the metric Sales Val. the range filter is associated and the report is performed: the result will only give the years with sales below the 50 million target. The figure also shows the report prior to the application of the Range Filter._

### Partitioning for Dimensional Levels

A Range Filter applies the Filter condition on the partitioned data according to the levels in the report.

_For an annual level report, for example, a condition on the sales above a target is applied to the values of each year. If month is added to the report, the same condition is applied to the values of each month, which will be very different from the annual ones._

The next example shows this type of application: to obtain the years with sales lower than a target, in a report which has the year level and the month level.

Step 1: Dimensioned Range Filter

![](<../../../.gitbook/assets/20 (3).png>)

_Create a filter range dimensioned by year, on the same condition of the previous example (simple range filter), this conditions the sales lower than a target of 50 million, however in this case at annual level:_

_Select the Sales Val sales Metric (double-click) and enter the formula in the area provided._

_Select the Year level from the Dimensions folder._

Step 2: Dimensioned Range Filter

![](<../../../.gitbook/assets/21 (3).png>)

_To the report of the previous example (Standard range filter) add the Month, level to obtain the report in the figure._

_Associate the dimensioned range filter in place of the previous one: the result will only give the years with sales below the 5 million target, exactly as in the previous example (only the year 2006 is excluded)._

_However, if the undimensioned Filter were to be applied to this report, the result would be a report with all elements, because it would be applied to monthly sales (no month has values below 50 million)._

#### **Direct Filters on Partitioning**

In case the filter condition is applied to a specific data partitioning, as shown in the previous paragraph, it is also possible to filter the partitioned data.

The proposed example explains the use of this method: to obtain the years with sales, in the SOUTHERN area, lower than a target, in a report which has the year level and the month level.

Step 1: Dimensioned and Filtered Range Filter

![](<../../../.gitbook/assets/22 (2).png>)

_Create a range filter dimensioned by year, and filtered for the SUD area, with condition on the sales that are lower than a target of 15 million:_

* _Select the Sales Val sales Metric (double-click) and enter the formula in the area provided._
* _Select the Year level from the Dimensions folder._
* _select the Filter on the SOUTHERN area, created in a previous phase._

Step 2: Dimensioned and Filtered Range Filter

![](<../../../.gitbook/assets/23 (1).png>)

_Create a report with the Area, Year and Month levels and the metric Sales Val._

_The report for the SUD area identifies only the years 2004 and 2007 as years with turnover below 15 million._

_Associate the Range Filter created in step 1 and run the report._

_The result will only provide the years with sales below the target of 15 million for the SUD area even though the turnover for the same years for the other areas (such as the NORD area) is higher than the specified target._

## Parametric Filter

Regarding the parametric filters, please note that it is possible to use the logical operator **\[OR]** in addition to the usual logical operators (AND, OR, NOT). OR implements a particular behavior of the filter which is described short below.

If the Filter is defined as follows:

_Level\_01@ID IN (**?Par\_1?**)_ _**\[OR]**_ _Level\_02@ID IN (**?Par\_2?**)_

the Filter conditions will be applied when at least one of the parameters is valued, otherwise the system behaves as if no condition were to be applied.

**Note:**

_When parametric Filters are used, you cannot use the cache if the level is not in the report._

User parameters can be used in **Direct Filters**. Then data will be filtered according to which user is currently logged in the application. The parameters that can be used are described in detail in the User management, Attributes section. They are:

* _%SUBJECT\_ID%_ : User ID
* _%U\_username%_ : Username of the user
* _%U\_subjectName%_: Full name of user
* _%U\_mail% and_ %U\_phone%_: user_ e-mail address and phone number
* _%U\_attribute\_\[n]% (\[n]=1-5)_: five attributes associated with the user

**Note:**

_If Parametric Filters are on user parameters, the automatic cache is only generated for the user who created it. The same cache cannot be used by other users running the same report._

_The absolute cache can NEVER be used by the report._

Step 1: Parametric Filter

![](<../../../.gitbook/assets/24 (2).png>)

_In this example in the filter condition a parameter on the region is used._

_When you validate the formula, the system asks you to value the parameter and then it performs the validation (an error message also appears for parameter values that are not in the data warehouse)._

Step 2: Parametric Filter

![](<../../../.gitbook/assets/25 (1).png>)

_Create a metric to which you apply the previous filter._

Step 3: Parametric Filter

![](<../../../.gitbook/assets/26 (1).png>)

_Create a report with the sales compared to the region (level in the filter), with the metric just created._

_The parameter is requested when the report is run (it is no longer requested when you run it in the future; you can modify it in the testParams property of the report \[Presentation Administrator, Report section, Other specific report properties section]._

_On the report, note that the metric is only valued for the region entered._

### User Filters <a href="#user-filters" id="user-filters"></a>

User Filters restrict data viewing by users on all logical objects published in Decisyon Web, such as crosstabs, charts, indicators, etc.

To start the User Filter editor from the tool bar select the button

![](<../../../.gitbook/assets/image (146).png>)

&#x20;

The Filter condition is applied to the **Groups** selected in the bottom left pane.

In the example User Filter was created which limits, for all the users of the **Regional User** role,  the display of the data only relating to the status of competence (\[<#Action\_Status\_Id/>@ID]=1 ).

![](<../../../.gitbook/assets/image (151).png>)

The User Filter will be applied to each analysis containing at least one Metric, which belongs to a Cube containing the selected dimension.

The User filter is applied also when the analysis is not directly requested for the dimension involved in the condition: for example using the User filter proposed previously, if a user with the **Guest** goup requests an analysis on performances for the year, without including the geographic area, in any case the system applies the condition set in the User filter.

Please note, however, that in the case shown above, if the report requested is enabled to use the absolute cache ([Cache ](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2361819137/WIP-+Built-In+Parameters)section), it will not be possible to use it because the **Guest** area only cannot be distinguished, as the User filter in the example would request. Therefore the system is forced to make a new request to the DWH in order to have the correct data.

Thus to exploit the potential of using the cache, on the execution speed of the reports, it is worth entering the dimensional levels used in the User filter conditions.

In addition, if the report is enabled to use the **automatic cache**, **in no case will this cache be created**.

In the user filters section the **OLAP parameters** can be used. They are described in the **Built-In Parameters**

The use of these parameters is especially useful to define dynamic User Filters.

For example if you have to enable a user with regard to a specific province, you may work in two ways:

* **STATIC**, where the phases are:
  1. create a group for each province,
  2. associate the competent users
  3. define a User Filter on the province for this role
* **DYNAMIC:**
  1. create an authorization group, by RunTime module, for the users concerned with the enabling on the province,
  2. create a table where the users are associated to the competent province,
  3. create a dimensional level (or a new dimension) on this table
  4. create a dynamic User Filter containing the condition like the one shown in the figure.

&#x20;

In this last case, maintenance is certainly less expensive than for the static case. In addition, the creation of a user-province association table is less expensive in the definition phase than the creation of a group and a security filter for each province.\
<br>

<br>
