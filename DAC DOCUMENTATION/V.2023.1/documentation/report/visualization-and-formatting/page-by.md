---
description: >-
  The group of PageBy properties of the report allows users to customize the
  behavior of the elements placed in page-by
---

# Page-By

The group of PageBy properties of the report allows users to customize the behavior of the elements placed in page-by, in terms of:

* [Selection mode of](page-by.md#making-selections) the elements (single, multiple, with partial search)
* Which [page-by values must be displayed during](page-by.md#automatic-placing-of-values-in-page-by) the opening of the report and later user selections
* Apply [filters for page-by values](page-by.md#filters-on-values-load-type-load-filters), to show a list different from the standard one, making them independent from the report result (load-type) or from previous page-by (load-filter).
* Entering[the item for ](page-by.md#totals-in-page-by)the total, so that data for all level values can be obtained . It is advisable to save reports by selecting the TOTAL item in page-by, because DAC optimizes the data loading query, speeding up execution: The system will not load, during report execution, the list of level values, putting this off to the moment when the user will choose a value as filter. This behavior is active only in DAC and if the page-by is in single selection mode with search, or in multiple selection mode.
* Customize the [page-by layout in DAC.](page-by.md#totals-in-page-by)

<figure><img src="../../../.gitbook/assets/image (723).png" alt=""><figcaption></figcaption></figure>

## Making Selections

The settings of this property only affect the report display in DAC. The page-by mode allows users to execute filters on single columns inside a report.

The elements in page-by in the report are listed in a drop-down menu, as shown in the following figures. In the report, you can carry out three different types of selections:

* Simple single selection
* Single selection with element search. You can can type part of the name of the element in the menu, so that only elements that include the typed text are listed. You will then be able to choose only one of the filtered elements
* Multiple selection with element search

![](<../../../.gitbook/assets/0 (20).png>)

To set the desired page-by mode, you must access the properties of the report of the page-by group and configure the properties

* _**default-selection-type**_ sets the type of selection you want to assign by default at all levels in page-by, chosen from the following options:
  * _**\<single>:**_ enables simple single selection
  * _**\<single (search)>:**_ enables single selection with search
  * _**\<multiple>:**_ enables multiple selection with search
* _**selection-type**_ to change the default setting, which is defined in the previous property.

A window opens with a list of report levels, plus the metrics axis; for each one you can define a different mode of selection from those already defined in the previous property.

Step 1: Metrics Selection Method

![](<../../../.gitbook/assets/1 (33).png>)

_We set the value \<multiple> in the selection-type for the item “-Metrics-”_

_By setting the metrics to \<multiple>, you can also use the property selected -metrics. This allows you to select the metrics that will be displayed (in this case Due Date \[Max]). The metrics, if multi selection is active, should not be placed in page-by. Indeed, in this example, they are found on the report columns (default setting)._

Step 2: Selection Procedures for the Metrics

![](<../../../.gitbook/assets/2 (13).png>)

_Opening the report in DAC, we note that the only metric displayed in the report is the one previously selected (step 2)._ _It is possible, however, to change the metric selection in DAC. If, in addition to the metric Due Date \[Max], we also select Start Date \[Min] from the page-by menu (or, equivalently, we check “Select All”) and confirm our choice, the system will display both._

## Automatic Placing of Values in Page-by

The selection of the values in the page-bys can be customized separately at each report level, using the property:

* _**opening-selection**_ lets you define the page-by value to be presented for each report level. A pop-up opens with the list of the levels. One of the following items can be selected for each of them:

![](<../../../.gitbook/assets/3 (11).png>)

*
  * _\<level default setting>_ accepts the selection set in the level definition (see _Levels mapping_ section)
  * _Selection_ to save the selected values
  * _First_ or _Last_ to present the first or last value
  * _Total_ to select the totaling element.
  * _Page-by-content_ to automatically select all the elements in the list
  * _Query_ defines the page-by value as the result of a query. The query should be entered manually in the _Value_ field (see figure below).

![](../../../.gitbook/assets/4.png)

If the query returns more than one value, the level will be automatically placed in multi selection and the values will be preselected (multi selection can be seen only in DAC).

In the query definition it is possible to use:

* the _System Parameters_ (see Presentation Administrator, System Parameters section) the parameters on the Page;
* for example, it is possible to define the query "SELECT YEAR\_ID FROM LK\_YEAR WHERE YEAR\_ID IN (?YEAR?)" where ?YEAR? is a parameter deriving from a Page.

Before report execution, we activate a mask to set the parameter values. The values set will then be then stored in the testParams property (_Main_ group)

If the parameter is not valued, it is just ignored.

If the values chosen for the levels are not accessible, the setting for that value is ignored and the page-by displays the value set in the property _default-onChange_.

## Filters on Values (load-type, load-filters)

It is possible to set if the level in page-by should present only the values the report has results for: that is, there is in the report at least one metric valued for that level, or **to display all values in the registry**.

_For example, if a report has produced results for sales for only three customers, if the customer level is in page-by, all the customers in the registry will be displayed. If you select a customer other than the one of the report result, sales will be empty._

This behavior is set in the _**load-type**_ property: it opens a pop-up with report levels and for each it is possible to set:

* _\<report-result>_ to leave the default result and to list in page-by only the values in the datamart (and dependent on the value of the level in the previous page-by)
* _\<entire-result>_ to show all elements of the level in the registry

Another option is to make **independent** **the** **values of a level from those of the previous page-by**; in fact a page-by displays only the values that meet the filter conditions set by the previous one. From the _**load-filter**_ property, a pop-up opens with report levels and for each one you can define:

* _\<Filter>_ to leave the default behavior on and display only the values filtered by the previous page-by
* _\<Ignore>_ to show all values in the datamart, independently from the choice in the previous page-by

Example

Step 1: Ignore Filters for Levels in page-by

![](<../../../.gitbook/assets/image (1146).png>)

_In the example, we see in page-by the Product and Day levels (in this order)._

_If you choose the value “Product 10” for Product, the Day page-by will display only the days for which there is a metric with a value for that product._

Step 2: Ignore Filters for Levels in page-by load-filters

![](<../../../.gitbook/assets/6 (4).png>)

_If we need to see in the page-by Day all available values , independently from the choice made for Product (therefore also days with no sales for “Product 10”), we need to set differently the load-filters the property :_

_in this case on the dimension TIME (and then on Day), we ask the system to ignore the filters of previous page-bys, obtaining the result shown in the figure. Here we see listed all the days available in the Day level , even if there was no product sales for them– “Product 10”._

## Totals in Page-by

In a page-by the _**\[Total]**_ value denotes the complete set of values displayed inside the list. By default, the item for the total is enabled in page-by, placed as first value in the list.

You can disable the item \[Total] for all levels in page-by, or only for some, which you can select through the _**total-visibility**_ property:

* _\<level default setting>_ accepts the selection set in the level definition (see _Model Administrator , Levels mapping_ section)
* _\<all-levels> (_&#x64;efault) the \[Total] item can be found on all report page-by
* _\<none-_&#x6C;evels> disables the total for all page-by
* _\<selection>_ enables the total only for some levels chosen by the user. This selection enables the following properties:
  * _**levels**_, where the levels are selected which must have the item \[Total] visible.

## Layout in DAC

In DAC, the page-by layout is customized through some properties which produce a clearer display, especially when the report is inserted in a Page among other objects.

The properties to set the page-by layout are:

* _**max-elements**_ sets the maximum number of elements to enter in page-by. By default it is set to 500.
* _**selector-width (web)**_ sets the wiDSh (in pixels) of the page-bys, only for single type page-bys. By default the wiDSh is adjusted to the text (_\<auto>_).

In the event of multiple or single page-by with search, the wiDSh is preset and cannot be modified. Longer text will be cut.

* _**num-elements-row (web)**_ indicates the number of page-bys to be displayed on the same row. By default the system places six page-by in a row, before starting a new row.
* _**show-initializer (web)**_ allows you to display a button (highlighted in the figure below), to the side of the levels in page-by. Clicking on this button resets them to their initial values.

![](<../../../.gitbook/assets/7 (26).png>)

* _**hidden-pageBy**_ lets you hide the levels or the metrics:

just select the single levels or metrics to be hidden, in the window associated with the property

If the report metrics are found in multi-selection or in page-by, the window shows the **-Metrics-** item that allows users to hide in DAC the page-by corresponding to the metrics.
