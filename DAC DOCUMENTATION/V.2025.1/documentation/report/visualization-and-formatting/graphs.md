# Chart



The graphic display of data is important for targeted end users, as it allows a quick display of the\
results of the report values.

The graph can be customized by editing the property settings for the reports, which are collected in the **Chart** folder.

<figure><img src="../../../.gitbook/assets/image (923).png" alt=""><figcaption></figcaption></figure>

## Example : Customizing a Graph

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/image002.png)



![](https://firebasestorage.googleapis.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-Me9l9764sQiD6lw0m1F-1259855788%2Fuploads%2FDeU2RSdKLaSrMOks2R9y%2Ffile.gif?alt=media)

_Inside the figure the results of the properties set previously can be recognized through a label. This allows users to immediately identify the property and the corresponding result. In the graph, some properties belonging to the GraphStyle group have been set:_

* _plotAreaMargin: the margins of the graph area have been set to 30,115,100,100_

_In report properties, you can also customize:_

* _the graph_ _layout_
* _the axes_
* _the legend_
* _the display of the values (Layer group)_
* _the title (Graph Title group)_

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/image003.png)

## Graph Types

![](https://firebasestorage.googleapis.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-Me9l9764sQiD6lw0m1F-1259855788%2Fuploads%2FyndOgjb2bYwuVwQA9bEv%2Ffile.gif?alt=media)

The characteristics of the DAc graphs and their specific properties are described in the sections below. The graphs are divided by type -.

### Area

In an area graph the data is represented by zones of different color, according to the importance of the values.

This type of graph is particularly suitable for representing the data of a limited number of groups (_for_ _example, the percentage of the total of the sales in the quarters_).

The static area graph types can be selected in the _**graphStyle**_ property (Graphs section):

{% tabs %}
{% tab title="2D Area" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dArea.png)


{% endtab %}

{% tab title="2D Area Stack" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dAreaStack.png)


{% endtab %}
{% endtabs %}

### Bar

In the Bar graph the metrics are displayed as side-by-side bars.

{% tabs %}
{% tab title="2D Column" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dColumn.png)


{% endtab %}

{% tab title="2D Column Stack" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dColumnStack.png)


{% endtab %}

{% tab title="3D Column" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dColumn.png)


{% endtab %}

{% tab title="3D Column Stack" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dColumnStack.png)
{% endtab %}

{% tab title="2D Bar" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dBar.png)


{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="3D Bar Stack" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dBarStack.png)


{% endtab %}

{% tab title="Waterfall" %}
A **Bar Waterfall** graph is a type of graph that shows values as a function of the previous value: each value is represented starting from the final value of the previous one.

Therefore the first value starts from 0 of the x-axis, for the second value the starting base will be the final value of the first, and so on.

The graph ends by showing the sum of all the values. This way, you obtain instant visibility of the contribution of each component to the final sum, particularly useful in the presence of positive and negative values.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/Waterfall.png)
{% endtab %}

{% tab title="Scroll Stack Column" %}
A scroll stack column chart is used to compare the cumulative magnitude of multiple data categories. The presence of the scroll interactivity allows to plot a large number of data points, more than can be accommodated in a single view of the chart. The chart is rendered with columns belonging to multiple categories of data, with respect to a single quantity, stacked on top of each other.A horizontal scroll bar is rendered below the x-axis to navigate through the chart. This chart can be used to compare data like the monthly revenue earned from products and services for a period of two financial years.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/ScrollStackColumn.png)
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="2D Pareto" %}
**Pareto** graphs represent the evolution of a phenomenon, by highlighting the cumulative distribution of the percentage each item of the phenomenon is given.

_For example, if you look at the amount of products sold, the graph shows the volumes (decreasing trend) and the respective percentage weight (in cumulative mode)._

This type of representation aims to highlight the elements that have the greatest impact on the phenomenon studied: in our example, which products have an impact on the quantities sold.

This representation is particularly suitable for those phenomena where there are only a few elements with the highest percentage weight (think of the phenomenon of the distribution of wealth at a ratio of 80/20, where few elements account for 80% of the wealth, while the others only the remaining 20%).

In the graph, each factor of the phenomenon is represented by bars, each one with a different color and arranged in descending order, while a line represents the cumulative percentage distribution: each point shows the cumulative incidence of the phenomenon until 100% is reached on the last element.

The Pareto graph types can be selected in the _**graphStyle**_ property&#x20;

* Pareto 2D
* Pareto 3D

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dPareto.png)
{% endtab %}

{% tab title="3D Pareto" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dPareto.png)


{% endtab %}
{% endtabs %}

### Lines

In a line graph the data is represented as a series of points joined by a line.

This type of graph is particularly suited to representing the data of a large number of groups (_for_ _example, the total sales of the last few years_), outlining the trends by category.

{% tabs %}
{% tab title="Line" %}
###

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/Line.png)

###
{% endtab %}

{% tab title="Zoom Line" %}


![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/ZoomLine.png)
{% endtab %}

{% tab title="Line Spline" %}


![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/LineSpline.png)
{% endtab %}

{% tab title="Line Step" %}
&#x20;

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/LineStep.png)
{% endtab %}

{% tab title="Line Trend" %}
&#x20;

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/LineTrend.png)
{% endtab %}
{% endtabs %}

### Various

{% tabs %}
{% tab title="Bubble" %}


In a _**bubble**_ graph the data points are replaced with bubbles. This type of graph does not use any category axis, therefore both the horizontal axis and the vertical axis are used for values. The Z values (dimension) are traced in addition to the X and Y values.

To use a bubble graph, you must have a minimum of three data series. The dimensions of the bubbles are calculated from the values in the third series.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/Bubble.png)

In a _**bubble**_ graph the data points are replaced with bubbles. This type of graph does not use any category axis, therefore both the horizontal axis and the vertical axis are used for values. The Z values (dimension) are traced in addition to the X and Y values.

To use a bubble graph, you must have a minimum of three data series. The dimensions of the bubbles are calculated from the values in the third series.

The bubble graph type can be selected in the _**graphStyle**_ property:

* _**Bubble**_

In flash type bubble graphs, you can set the scale for the bubble dimension (_GraphStyle_ group):

* _**bubble-scale:**_ property to manage the dimensioning of each bubble (default 1);

this property is applied in the next example

You can enable the display in **four quadrants** using the properties (_GraphStyle group_):

* _**show-quadrants:**_ enables the display of the quadrants
* _**vertical-line position:**_ allows you to set the position of the vertical line
* _**horizontal-line-position:**_ allows you to set the position of the horizontal line
* _**top-left-label:**_ allows you to set the label relative to the top left quadrant
* _**top-right-label:**_ allows you to set the label relative to the top right quadrant
* _**bottom-left-label:**_ allows you to set the label relative to the bottom left quadrant
* _**bottom-right-label:**_ allows you to set the label relative to the bottom right quadrant
* _**lines-color**_**:** allows you to associate the color associated with the vertical and horizontal lines. By default the color is black.

The properties are also available for defining the **maximum and minimum values and the steps for the axes**:

* **XAxis-min-max-value minimum** and maximum value for the **X axis** **(default ”** -1, -&#x31;**“)**
* **YAxis-min-max-value minimum** and maximum value for the **Y axis** ( **(**&#x64;efault **”** -1, -&#x31;**“**)
* **XAxis-values-step value** of the steps for the **X axis** (default “&#x31;**“)**
* **YAxis-values-step value of the steps for the Y axis** (default “&#x31;**“)**
{% endtab %}

{% tab title="Scatter" %}
A scatter graph is often used when one of the variables is under control. A parameter that is systematically increased and/or decreased is called a **control parameter** or independent variable, and is placed arbitrarily on the horizontal axis. The **measured** (or dependent) variable is arbitrarily placed on the vertical axis. If there are no dependent variables, each variable may be placed on any axis.

Scatter graphs are useful to show the level of **correlation** (i.e. linear dependency) between the two variables.

The representation of this type of graph requires a report with at least two metrics:

·                 the values of the first metric are placed on the x-axis

·                 those of the second metric on the y-axis.

The color of all the points is the same and coincides with the first of the palette.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/Scatter.png)
{% endtab %}

{% tab title="Radar" %}
The _**graphs created to**_ _**show the achievement of an objective**_ belong to this category.&#x20;

In a _**radar**_ graph, also called a spider or star graph due to its appearance, the values of each category are traced along a separate axis that branches off from the center of the graph to the external ring. The **radar** graph is particularly useful for comparing several elements measured on more than two variables. The advantage of this graph is its ability to highlight the differences between one element and another in a simple and immediate manner. Each element assumes a type of form which distinguishes it from the others.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/Radar.png)
{% endtab %}

{% tab title="Gantt" %}
A GANTT-type graph can be used in reports where the metrics are dates corresponding to the beginning and the end of an activity. These dates are used to define the time period and display it in the graph.

For a consistent GANTT-type graph it is necessary that the aggregation function used for the beginning and end dates be respectively MIN and MAX (the accepted format is _YYYYMMDD_). It will be then necessary to use advanced metrics.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/Gantt.png)

The static Gantt chart type can be selected in the _**graphStyle**_ property (_Static Chart_ section):

* _**Gantt**_

The properties for this type of graph are:

* _**auto-scale**_, if selected, the graph has a default time interval for the analysis that is between the minimum and the maximum date, of the first metric (used as the start of the period) and the second (used as the end of the period) respectivel&#x79;_**.**_
* _**scale-start-end,**_ (when the _auto-scale_ property is selecte&#x64;_),_ this allows users to choose the type of period considered instead of using the minor/major date of the report.

The available periods are those shown in the above figure. For example, if the report interval is February 4/November 25, and a monthly period is chosen (_**scale-start-end**_ per to _**<**_&#x4D;onth>), the system will suggest as the interval February 1/November 30.

* If _auto-scale_ is deselected it will be instead possible to choose any period as the period for the analysis: the properties _**from**_ and _**to**_ will be enabled (beginning and end of current year are suggested as dates).
* _**show-today**_ allows you to display or to hide the current day on the graph (selected by default).
* _**major-tick**_ and _**minor-tick**_ define, respectively, the major and minor significance periods to be displayed in the graph. These can be chosen from a list, among beginning of year, of month, of week, or daily. You can then choose the format for the display of the time period, using _**major-tick-format**_ and _**minor-tick-format**_ propertie&#x73;_**.**_
* _**seriesFontSize**_ sets font size for the Y-axis (in other words for the activities, not the dates).
* _**barsPattern sets**_ the look for the bars in the GANTT graph. It is possible to set up to ten bar series and for each of them a different coloring style can be chosen:
* uniform fill ()
* striped, arranged vertically (\<Lin&#x65;_-straight>) or diagonally,_ to the left or to the _right (,_ )

Each bar series is associated with a pair of dates (beginning and end interval), the number in brackets (\[n]) indicating the position occupied (\[1], for the first pair, \[2] for the second, and so on). If there is more than one bar at the same time and the display is not clear, it is better to use the _**barsWiDSh**_ property to set their dimension.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="3D Column Line	" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dColumnLine.png)


{% endtab %}

{% tab title="2D Column Stack Line" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dColumnStackLine.png)


{% endtab %}

{% tab title="3D Column Stack Line" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dColumnLineDualAxis.png)


{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="3D Column Line Dual YAxis" %}

{% endtab %}

{% tab title="3D Column Stack-Line Dual Yaxis" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dColumnStackLineDualAxis.png)


{% endtab %}

{% tab title="Custom Layer" %}
As with static graphs, you can also create advanced graphics with flash graphs, where different graphic styles are associated with the metrics in the report: these include the **Custom Layer** graph types.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/CustomLayer.png)

The Custom flash graph type can be selected in the _**graphStyle**_ property&#x20;

* _**Custom Layer**_

This selection enables the property:

* _**customLayer**_ for the configuration of the graph layers.

The configuration is similar to that of Custom Layer static, although there are differences concerning:

* the absence of graphic subtypes; only the main types of graph can be selected (lines, columns and areas)
* properties that can be assigned (_Properties_ section). There are:
  * _2 Ax_, option for the double axis, available for all types and subtypes
  * _dashed_, option available for the Line type layers; by activating this option, it is possible to view the lines of the graph in dashed mode. By default the option is disabled, the lines of the graph are continuous.
{% endtab %}
{% endtabs %}

### Pie

In a **pie** graph, data is displayed through a circular graph, divided into different colored slices, whose [angular length](http://it.wikipedia.org/wiki/Angolo) is proportional to the corresponding dimensions.

The values represent the percentage share of the metric with respect to the total.

{% tabs %}
{% tab title="2D Pie" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dPie.png)


{% endtab %}

{% tab title="3D Pie" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dPie.png)


{% endtab %}

{% tab title="2D Donut" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/2dDonut.png)


{% endtab %}

{% tab title="3D Donut" %}
![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/3dDonut.png)


{% endtab %}
{% endtabs %}

Specific properties are available for pie graphs (_GraphStyle_ group):

* _**pieRadius**_ outer radius of the graph (in pixels). With the _< auto >_ setting (default value), the system automatically calculates the best radius suitable for the graph.
* **labels-and-values style** enables the display of the labels and values. The selected values for this property are:
  * _\<Label>_ label of the element
  * \<Value> absolute value of the element
  * _\<Percentage>_ percentage value of the element compared to the total
  * _\<Label, percentage>_ label of the element and percentage value compared to the total
  * _\<Label, value>_ label and absolute value of the element
  * _\<none>_ to not display any label or value.
* **enable-smart-labels** enables the lines between the label and the pie (enabled by default)

## Common Properties

In the sections below, the properties common to all graphs are explained

### Graph Style

The _**Graph Style**_ group has the property:

* _**graphStyle**_ for choosing the style.

You can select **graph** **styles** from the report properties, which you can access either from the editing window (_Graph_ folder), or from the

<div align="left"><img src="https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/image005.png" alt=""></div>

button, located on the toolbar.

Other graph properties allow you set (_GraphStyle_ group):

* _**graphHeight, graphWiDSh:**_ graph height and wiDSh (values between 1 and 3000).
* _**plotAreaMargin:**_ the margins of the graph area with respect to the outermost container (borders: top, left, right, bottom).
* _**swapXY**_: swaps values between the x and y axe&#x73;_._
* _**autoMinWiDSh:**_ enables the automatic resizing of the graph wiDSh, according to the number of elements to show.

### Graph Layout

With regard to the graph layout, you can customize:

* the graphic display area, in terms of the background and colors of the bars/lines/areas,
* the area which contains the graphic content, always in terms of the background.

The application of properties depends on the graphic style chosen and some styles require additional properties (such as transparency for certain types of flash graphs).

More specifically, the properties are (_GraphStyle_ group):

* _**graphBackground**_: this is the background color of the graph (see example below)
* _**background-effect**_ (just for 2D chart) enables a particular effect for the graph background. _&#x54;_&#x68;e effects are:
* _\<gradiant>_
* _\<gradient-transparent>_
* _\<none>_&#x6E;o effect is applie&#x64;_._

_**Note:**_ _No effect can be applied in Flash 3D graphs._

The linear and radial effects enable the properties:

* **start-color** and **end-color**: Sets the start and end color of the gradient
* **start point** and **end point:** sets the coordinates for the start and end point of the gradient

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/bg1.png)



![](https://firebasestorage.googleapis.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-Me9l9764sQiD6lw0m1F-1259855788%2Fuploads%2F6zd1PApC0JHppC14dAWV%2Ffile.gif?alt=media)

If the effect \<none> is selected for a flash graph, the color set in the **graphBackground** property is applied to the background.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/Graph/bg2.png)

* _**graphBorderColor ,**_ this sets border color for the window containing the graph.

This property does not apply to pie graphs.

* _**raised:**_ shading level for the window containing the graph (from 0 to 20)
* _**palette**_: color of graph elements associated with each metric displayedc
  * _**palette-effect**_ to apply a two color gradient effect to the graph bars. You can also apply the gradient effect in transparent mode. The property values are:
    * <_none>_, <_gradient>_ (default) and _\<gradient transparent>._
* The gradient _and gradient transparent values_ enable the properties:
  * _**gradient color**_ for selecting the second color to be mixed with the palette one. By default the color is white
  * _**use-**_**round-edges**: allows setting the glass effect, with shading and rounded corners.
*   If the property is active, the gradient set with **palette-effect** and **gradient-color** is not applied

    **Note:** _The appearance of the graph displayed in a browser which supports HTML5 is different compared to the one obtained in a browser which does not support it (e.g. IE8)_
* **color-palette:** specified the color of the elements in the graph
* **color-palette:** sets the colors for the column of the graph

### Graph Axis

DAC graphs set by default the values of the metrics on the Y axis and dimensional levels on the X axis. The ordering of the axes is changed through the **swapXY** property (GraphStyle group, for some graphic styles it is disabled).

Pie graphs have no axes, while radar graphs have only the vertical axis.

The properties available for the axes are:

· **axisFont** for the font type

· **axisFontColor** for the color

· **yAxisFontSize** and **xAxisFontSize** to change y- and x- axis font size

· **axisLabelRotation** (only static graphs) to change the slant of labels on the Y-axis (or dimensional levels)

· **axisAutoScale** represents a set of three figures, specifying:

– empty space above maximum value,

– empty pace in the lower part,

– tendency to start from zero rather than the minimum.

· **linearScaleA1** and **linearScaleA2** for the gradation of the scale for the first and second x-axis, represent a set of four figures, specifying:

– Start and end position (default -1,-1, indicating that minimum and maximum values are determined automatically by the system)

– large and small gradation scale

· **YAxis-min-max-value** and **Y2Axis-min-max-value** for the start and end position of the first and second axis (default -1,-1, indicating that minimum and maximum values are determined automatically by the system).

This property does not apply to pie graph

· **showLabels:** displays the labels in the graph. This property enables:

– **labelStep** to define how many steps to enter the graduation signs and the respective values of the level (graduation signs are small measurement lines, intersecting the axis).

Therefore this property shows a lower number of values on the axes, in order to make the graph visibly clearer when the labels are too close.

– **rotateLabels** if enabled it rotates the labels of the x axis.

The three previous properties are not applicable for the pie graph

· **xAxisTitle- yAxisTitle- y2AxisTitle** header on the axes.

This property does not apply pie graph

### Graph Title

Every graph can be identified by inserting a title.

You can enable the property _**titleRendered**_ from the report editing window in the _**Graph-> Graph Title**_ section. The system activates the display of the graph title, and it will use the name

associated with the report as the name.

If _**titleRendered**_ is enabled, you will be able to see the secondary properties used to customize the title layout:

* **fontSize**: this sets the font size;
* _**foregroundColor**_ sets the color.

It is possible to apply effects to the title through the _**effect**_ property and to set both the border color for the title box, _**borderColor**_, and the background color, _**background Color.**_ If no effect is desired for the title you can set the background color and the color of the title box as it is shown in the figure below.

### Graph Layer

The properties for the _Layer_ group allow users to set the display all of values inside the graph:



* **show-anchors:** enables the display of the points on line type graphs (enabled by default)
* _**showValues**_ enables the display of values on the graph, for which it is possible to set
  * _**values-format**_ , if enabled, it modifies the value format adding K for thousands and M for millions, to make the displayed values more compact
  * &#x20;**value-rotation** to rotate values displayed vertically (\<vertical>) or horizontally _(\<horizontal>)_)
  * &#x20;**values-position** is activated to display the data inside _(\<values_)-inside>) or outside _(\<values-outside_>) the bar.
  * **decimal-separator:** Decimal separator applied to all chart series&#x20;
  * **thousand-separator:**&#x54;housand separator applied to all chart series
  * &#x20;**additional-chars**:Additional chars applied to all chart series
* Values displayed on the graph can be cut off after n _decimal_ places by setting the _**decimalScale**_ property.
* font-color: sets the color of labels

### Graph Legend

It is possible to display or hide a legend inside a graph.

The legend always contains one or more elements, each of which is composed of a colored box which represents the displayed metric, and its name.

From the _**showLegend**_ property, you can display or hide the graph legend.

If this property is enabled, it is possible to set the following characteristics:

* Make the Transparency legend transparent or less
* Font size for the legend _**legendFontSize**_.
* Font color for the legend _**legendFontColor**_.
* Legend position: from upper/right border _**legendPosition**_.
* Background color for the legend. _**legendBackground**_ _(\<none>,\<glass>,\<light>)._
* Shading for the legend box
* Effect applied to the legend,
* Border color for the legend box _**legendBorderColor**_.
* Size of the legend box,
