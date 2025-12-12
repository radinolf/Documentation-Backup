# Custom filters

The filters for exclusive use on the report can be defined:

* On the elements of the report (_**View Filter**_), therefore applied AFTER the execution of the report, directly on the datamart which is the result of the query to the data warehouse
* On the dimensional levels of the application (_**Custom**_ _**Filter**_), therefore applied DURING the query to the data warehouse

These filter categories are associated only with the report and cannot be reused or saved.

To define a custom filter, in the Custom Filters folder, place the cursor on _Filters_ and right click to open the menu. There will be two items on the menu: one creates a Custom filter and the other creates a View Filter.

![](<../../../.gitbook/assets/16 (3).png>)

Selecting either item opens a window to define the filter condition. This window has the same functions as the one for direct filters _(_&#x73;ee _Presentation Administrator, Filters section)._

Choosing _**Define Custom**_ _**Filter**_ allows you to choose any level in the application. If you choose levels found in the report, the condition will be applied during the query and not afterwards.

![](<../../../.gitbook/assets/17 (1).png>)

The option _**Define View Filter**_ opens the filter window, restricting level selection to those levels which are in the report. Note that in Define View Filter, you can also set conditions on the metrics of the report itself.

![](<../../../.gitbook/assets/18 (10).png>)

In defining a _View Filter_, you can apply the condition by selecting the property _**Apply as “Having” condition**_.

In this way the system will apply the filter on the aggregated values in drill, rather than on the datamart (see the following example). The property is enabled only if metrics, rather than levels, are selected.

Once created, the filter appears in the _Elements_ area: to change it, just select it and select _**Edit**_; to delete it, double-click on the row corresponding to the filter (in _Type_).

![](<../../../.gitbook/assets/19 (9).png>)

Parameters can be used in Custom Filters (both Custom and View):

* defined in a dashboard
* user parameters

For details, see _Presentation Administrator._

Example: View Filter in HAVING

![](<../../../.gitbook/assets/20 (5).png>)

_Report N°1 presents the Product Family level which aggregates the Product level, while the metric calculates sales quantities._

_A View Filter is applied on the Sales Qty metric to filter values greater than 9,000,000 and the HAVING flag is enabled._

_In report N°2 the filter has been applied; it can be seen that only product families meeting the filter condition are displayed._

_If the same condition is applied with HAVING disabled, the report would not show any result: no product (detailed data from the datamart) has values for Sales Qty greater than 9,000,000._
