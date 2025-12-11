# GraphStyle

## Overview

The administrator can set the type of chart by using the property **graphStyle**. There are many different charts that may be selected:

1. **2D Area**
2. **2D Area Stack**
3. **2D Bar**
4. **2D Bar Stack**
5. **2D Column**
6. **2D Column Stack**
7. **2D Column stack-Line**
8. **2D Donut**
9. **2D Pareto**
10. **2D Pie**
11. **3D Bar Stack**
12. **3D Column**
13. **3D Column Stack**
14. **3D Column stack-Line**
15. **3D Column stack-Line dual YAxis**
16. **3D Column-Line**
17. **3D Column-Line Dual YAxis**
18. **3D Donut**
19. **3D Pareto**
20. **3D Pie**
21. **Bubble**
22. **Custom Layer**
23. **Gantt**
24. **Line**
25. **Line Spline**
26. **Line Step**
27. **Line Trend**
28. **Radar**
29. **Scatter**
30. **Scroll Stack Column**
31. **Waterfall**
32. **Zoom Line**

In the Chart widget, the properties of **GraphStyle** group are similar to those available in the Chart folder of the Report Editor <img src="../../.gitbook/assets/image (20).png" alt="" data-size="line">

{% hint style="info" %}
Refer [here](https://documentation.decisyon.com/documentation/report/visualization-and-formatting/graphs) for more about the Chart feature on the Report Editor.
{% endhint %}

## **Chart Types**&#x20;

All of the supported charts listed in the property **graphStyle** can be divided into the following **types**:

### Area

In the **Area** type, the data are represented by various color zones according to the relevance of the values. This type of chart is very appropriate for presenting the data of a limited number of groups.

{% tabs %}
{% tab title="2D Area" %}
<figure><img src="../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="2D Area Stack" %}
<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Bar

**Bar** Chart type presents categorical data with rectangular bars. The bars can be plotted vertically or horizontally. The vertical bar chart is called Column chart. This type of chart is used to show comparisons among categories. One axis of the chart shows the specific categories being compared, and the other axis represents a measured value.

{% tabs %}
{% tab title="2D Column " %}
<figure><img src="../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="2D Column Stack" %}
<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="2D Bar" %}
<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="2D Bar Stack" %}
<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="3D Column " %}
<figure><img src="../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Column Stack" %}
<figure><img src="../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Bar Stack" %}
<figure><img src="../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Scroll Stack Column" %}
A **Scroll Stack Column** chart is used to compare the cumulative magnitude of multiple data categories. The presence of the scroll interactivity allows to plot of a large number of data points, more than can be accommodated in a single view of the chart. The chart is rendered with columns belonging to multiple categories of data, concerning a single quantity, stacked on top of each other. A horizontal scroll bar is rendered below the x-axis to navigate through the chart.

<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Waterfall

A **Waterfall** chart is a type of chart that shows values as a function of the previous value: each value is represented starting from the final value of the previous one. As a result, the first value begins at 0 on the x-axis, the second value starts at the last value of the first, and so on. The chart ends by showing the sum of all the values. This method provides immediate visibility of each component's contribution to the final result, which is particularly helpful when there are positive and negative values.

{% tabs %}
{% tab title="Waterfall" %}
<figure><img src="../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Pareto

**Pareto** charts represent the evolution of an event by emphasising the cumulative distribution of the percentage of each phenomenon-related item.&#x20;

This type of representation focuses on the factors that have the most impact on the event under study (consider the phenomenon of the distribution of wealth at a ratio of 80/20, where few elements account for 80% of the wealth, while the others only the remaining 20%).&#x20;

Each factor of the phenomenon is represented by bars, each of which is coloured differently and arranged in descending order. A line in the chart represents the cumulative percentage distribution, and each point on the line represents the cumulative incidence of the phenomenon until 100% is reached on the last element.

{% tabs %}
{% tab title="2D Pareto" %}


<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Pareto" %}
<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Lines

In a **Line** chart data is shown as a collection of points connected by a line. This type of chart is useful for presenting data from a large number of groups outlining the trend by category.

{% tabs %}
{% tab title="Line" %}
<figure><img src="../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Line Spline" %}
<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Line Step" %}
<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Line Trend" %}
<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Zoom Line" %}
<figure><img src="../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Pie

In a **Pie** chart, data is shown as a circular chart with slices of varying colours, whose angular lengths are proportionate to the respective dimensions. The values show the percentage share of the metric with respect to the total.

{% tabs %}
{% tab title="2D Pie" %}
<figure><img src="../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Pie" %}
<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="2D Donut" %}
<figure><img src="../../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Donut" %}
<figure><img src="../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Various

{% tabs %}
{% tab title="Bubble" %}
In a **Bubble** chart, bubbles are used in place of the data points. Because there is no category axis in this type of chart, data are shown on both the horizontal and vertical axes. The X and Y values are plotted together with the Z values (dimension). You need at least three different data series in order to utilize a bubble graph. The dimensions of the bubbles are calculated from the values in the third series.

<figure><img src="../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Scatter" %}
A **Scatter** chart is often used when one of the variables is under control. In this type of chart, a **control parameter** (or independent variable) is a variable positioned on the horizontal axis that is systematically increased and/or decreased. The **measured** (or dependent) variable is arbitrarily placed on the vertical axis. Any axis may be used to plot each variable if there are no dependent variables.&#x20;

Scatter charts are useful to show the level of **correlation** between the two variables.&#x20;

This chart must be represented by a report with at least two metrics:&#x20;

* The first metric's values are plotted on the x-axis.&#x20;
* The second metric's values are shown on the y-axis.

<figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Radar" %}
A **Radar** chart is sometimes referred to as a spider or star chart. In a radar chart, the values of each category are traced along a single axis that extends from the chart's centre to the outer ring.&#x20;

The radar chart is helpful for comparing several elements measured on more than two variables.&#x20;

This chart has the advantage of being able to quickly and easily show the differences between several elements.

<figure><img src="../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Gantt" %}
A **Gantt** type chart can be used in reports where the metrics are dates matching the start and end of an activity. These dates are used to define the time period and display it in the chart. The aggregation function used for the start and end dates must be, respectively, MIN and MAX (the accepted format is YYYYMMDD) in order to create a consistent Gantt type chart. The use of advanced metrics will then be required.

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Mixed Charts

{% tabs %}
{% tab title="3D Column Line" %}
<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="2D Column Stack Line" %}
<figure><img src="../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Column Stack Line" %}
<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="3D Column Line dual YAxis" %}
<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="3D Column stack-Line dual YAxis" %}
<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

### Custom Layer

{% tabs %}
{% tab title="Custom Layer" %}
<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}
