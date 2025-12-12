# Grouping levels

## Grouping of levels

When a report is created and it has many levels on the rows and/or columns, by default the report is **not grouped**. Grouping the report means that you will be able to display only one level at time and then you could drill down in the other levels available in the report.&#x20;

Grouping can be configured:

* by **layout:** grouping is applied on all dimensional levels on rows and/or columns
* by **dimension:** grouping is execued only on levels that belong to the same dimension
* no grouping: it is the default option of the report. Levels are not grouped.&#x20;



<figure><img src="../../../.gitbook/assets/image (300).png" alt=""><figcaption></figcaption></figure>

Default grouping is applied both to row levels and to column levels: using the property _**group-drill-axis**_ of the report you can configure axis of the report must be groped: \<row&#x73;_-only> or_ \<cols-_only_>.



The examples below show reports displayed according to the kind of grouping configured.

{% tabs %}
{% tab title="No grouping" %}
<figure><img src="../../../.gitbook/assets/image (1094).png" alt=""><figcaption></figcaption></figure>

By default, the report is displayed **without grouping**. The report displayed here includes one metric and three dimensions; of these, Category and Product belong to the same dimensional level, while Customer group belongs to a different level.
{% endtab %}

{% tab title="Group by Layout" %}
<figure><img src="../../../.gitbook/assets/image (1000).png" alt="Group by Layout"><figcaption></figcaption></figure>



When the report is **grouped by layout**, levels are grouped (from the first one to the last one) regardless the dimension they belog to. A dedicated icon allows drilling down or rolling up.
{% endtab %}

{% tab title="Group by Dimension" %}
<figure><img src="../../../.gitbook/assets/image (1221).png" alt=""><figcaption></figcaption></figure>

When the report is **grouped by dimension**, levels are grouped only if they belong to the same dimension.
{% endtab %}
{% endtabs %}

## Hierarchical Drill

The drill down operation when the grouping is enabled can be executed in two different ways:

* preserving the hierarchy link in the report
* hiding the _calling_ level from the report and showing it in an external path, so that it will be possible to later roll up.

This behavior is set using the _**hierarchical-drill**_ property (in the _Drill_ group)

**Step 1: Hierarchical-drill \<active>**

![](<../../../.gitbook/assets/50 (7).png>)

For drill-down, we just have to select the point in the graph and this will update, giving the lower level. In the example, by selecting the HEALTHCARE Customer Group, the graph widens to include a section with the products of the selected Customer.

For roll-up, you again select the point of the parent level (HEALTHCARE).

**Step 2: Hierarchical-drill \<NO active>**

![](<../../../.gitbook/assets/51 (4).png>)

![](<../../../.gitbook/assets/52 (4).png>)

In this second example, the Drill-down on the Customer Group FINANCIAL involves:

* Deleting the Customer Group level and displaying only the products related to that group.
* Activating a path external to the report ( \Main\FINANCIAL ). By clicking on Main the report will revert to the initial state and display only the Customer Groups.
