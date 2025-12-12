# Filters

### Introduction <a href="#introduction" id="introduction"></a>

‌The filters are used to select the data for the calculation of the metrics and to limit the data to be included in the report.‌

DAC uses the filters created by the administrator and associates them with a new report or existing reports.‌

You can also create new filters by expressing the conditions on the dimensional levels and/or metrics in a report. These will be used exclusively by the report and cannot be made public.‌

Two types of filters can be defined:‌

* [View Filter ](filters.md#view-filter)applied after the execution of the report, where it is possible to define a condition on the dimensional levels and the metrics in the report.
* [Custom Filter,](filters.md#custom-filter) which is a direct filter that sets a condition on any dimensional level, including those not in the report. When this filter is defined, a new query will be made to the data warehouse.

‌

### View Filter <a href="#view-filter" id="view-filter"></a>

‌A **View** **Filter** applies the filter condition after the execution of the report. Therefore it is only applicable to the metrics and levels in the report.

The filter creation window is opened from the _**New View Filter**_ item and is subdivided into two sections:

* On the left, you can select the dimensional levels and the metrics of the report.
* On the right, you can set the filter condition

![](<../../../.gitbook/assets/image (722).png>)

### Tutorial - View Filter



{% embed url="https://bitbucket.org/decisyon/manual/downloads/ViewFilter.mp4" %}



## ​‌Custom Filter

‌ **Custom Filter** allows you to define a condition on the dimensional levels, as well as any dimensional levels not in the report. The filter creation window is opened from the _**New Custom Filter**_ item and is subdivided into two sections:

* On the left, you can select the dimensional levels, structured by cubes. First, you need to select the cube at the top and then the levels.
* On the right, you can set the [filter condition](filters.md#filter-condition).

![](<../../../.gitbook/assets/image (1364).png>)

### Video - Custom Filter

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/19.Filter/Custom%20Filter/CustomFilter.mp4" %}

### Filter Condition

The filter condition on a dimensional level may be expressed on the ID or on the description of the dimensional level.

To define the filter condition in the View filter and Custom filter you can access the values in the data warehouse:

![](<../../../.gitbook/assets/image (1168).png>)

Just place the cursor on the ID or descriptive part of the level and right-click the mouse. This will open a window with a list of the corresponding values in the table.

You can select the values by single and total elements (_**Select All**_) item. The search on the value is active (at the top).

The  ![](<../../../.gitbook/assets/image (349).png>)button closes the window, reporting the values chosen in the filter formula area.

The section in which you define the filter condition contains some useful features for creating the new filter.

![](<../../../.gitbook/assets/image (1220).png>)

The _String Functions_ section contains string management functions, which return the values

* **Starts With** which start with the specified value;
* **Ends With** which end with a specified value;
* **Matches** they are equal to the specified word (for the characters);
* **Contains** which contain the one specifie&#x64;_**.**_

In the _Set Functions_ **section** there are the set operators, which check whether:

* _**in**_ the value equals one of the values in a specified list (pertinent operator);
* _**not in**_ the value does not equal one of the values in a specified list (non-pertinent operator);
* _**between**_ the value belonging to an interval, defined by a lower and upper limit;
* _**in values**_ the value equals one of those listed.

The _**in**_ and _**in values**_ operators have the same function associated with them. If the in values operators are selected, the window opens with the list of the values associated with the level entered in the formula..

The section to the right lists the _logical operators_:

* _**AND**_ among several conditions, to return the elements that satisfy all conditions at the same time;
* _**OR**_ among several conditions, to return the elements that satisfy at least one of the conditions;
* _**AND NOT**_ among several conditions, to return the elements which do not satisfy the condition after the instruction;
* _**OR NOT**_ among several conditions, to return the elements that satisfy at least one of the conditions (the second condition is denied).

<br>



​‌
