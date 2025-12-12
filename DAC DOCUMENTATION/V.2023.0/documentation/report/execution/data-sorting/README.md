# Data Sorting

Sorting allows you to organize report data set so that these can be displayed, updated or printed in a sequence that meets custom sorting criteria.

The advanced sorting function can be requested directly from the toolbar, or from the **advanced-sorting** property of the Main group.

![](<../../../../.gitbook/assets/image (241).png>)

The system displays the window for **Advanced sorting**, where the first column lists metrics and report levels: for each of them it is possible to specify **Position**, **Criteria** and **Type** **of sorting**.

**Position** indicates whether the element:

* must meet the preset sorting in the report (Inherit Report)
* &#x20;should not be considered (Ignore)
* in which position, relative to others, it should be considered (if sorted as first, second, third, etc.…)

Criteria are set in the Element column where we determine whether the dimensional level should be sorted on the ID (ID) or the description (DESC).

The **type of sorting** can be chosen from two options, increasing (ASC) or decreasing (DESC).

Sorting of the report matches the order set for dimensional levels, described in. Mapping of dimensional level (STEP 2).

We remind users that when creating levels, we decide whether the values are sorted by ID or description and whether in increasing or decreasing mode, in the **default**-**sort** and **sort-type** properties, shown in the figure.

![](<../../../../.gitbook/assets/image (175).png>)

The example shows the customers of each customer group sorted, starting from those with lower sales.

Step 1: Initial Report

![](<../../../../.gitbook/assets/image (300).png>)

The initial report shows the default sorting, set for each dimensional level.<br>

Step 2: Sorted Report

![](<../../../../.gitbook/assets/image (160).png>)

We choose as first element for the sorting Customer Group as second Sales Qty (increasing mode). In the report in the figure we show the result of these settings and that is precisely the sales for Customer Group, from the lowest to the highest value, for each Customer.

* **Step 1 :** Create a report in which the level Po\_od is sorted by default in Ascending mode.&#x20;
* **Step 2:** If we want the PO-ID level to be always sorted according to the Description of the Process Order set:&#x20;
  * **Default-sort:** select \<Custom\_order\_id> .
    * **Custom-column:** select the Process\_order\_Ds level.&#x20;
* **Step 3** we can see that the sorting is based on the description for process Order. Each time the Po\_id level is used in other reports it will always keep the same.

### Sorting level on a custom column

In addition to the classic selection, a level can be sorted by the values of another level .

We see the example below:

<figure><img src="../../../../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure>

We see the example below:

In addition to the classic selection, a level can be sorted by the values of another level .

* **Step 1 :** Create a report in which the level Po\_od is sorted by default in Ascending mode.&#x20;
* **Step 2:** If we want the PO-ID level to be always sorted according to the Description of the Process Order set:&#x20;
  * **Default-sort:** select \<Custom\_order\_id> .
    * **Custom-column:** select the Process\_order\_Ds level.&#x20;

<br>

* **Step 3** we can see that the sorting is based on the description for process Order. Each time the Po\_id level is used in other reports it will always keep the same.

###
