# ScatterPlot 1.2

## Overview <a href="#toc64560873" id="toc64560873"></a>

Use the **ScatterPlot** widget to show and observe the relationship between variables, plot multiple scatter series in a single chart to compare different data sets starting from a simple report.

<div align="left"><img src=".gitbook/assets/0" alt=""></div>

In the picture, the **ScatterPlot** widget is built with a simple report. The data are displayed as points in the chart. A point is placed based on the coordinates for the x-axis and y-axis. This chart shows height and weight by gender, showing a clear trend where men are on average taller and heavier than women.

The **ScatterPlot** widget is a chart that uses points to represent values for different variables. A point is placed based on the coordinates for the x-axis and y-axis. You can use the **ScatterPlot** widget to observe the relationships between variables or plot multiple scatter series to compare different data sets.

<div align="left"><img src=".gitbook/assets/2" alt=""></div>

You can select a single data point or multiple data points at the same time. When selecting a data point, the widget based on the type of selection configured, will export a parameter with the collection of selected data points that can be used within the page.

{% hint style="info" %}
The selected points will have a deeper color. To deselect a point, click on it again.
{% endhint %}

The widget allows showing individual marks, useful when there are many data points in the chart. You can use mark labels to hide marks and show only the values of specific marks of interest.

<div align="left"><img src=".gitbook/assets/3" alt=""></div>

The widget's interface provides a toolbar that can be optionally disabled with some options to:

* Enable the crosshair in the chart.
* Show a tooltip for displaying information when hovering on a data point.
* Show a cluster tooltip for displaying cluster information useful when in the widget there are multiple series.
* Print the chart.
* Export the chart as a file in different formats (PDF, PNG, JPEG, SVG).

It is possible to customize its functionality and behavior, using the specific configuration properties in the Page Design.

See the **Properties** section for all applicable configurations.

## Report Mapping <a href="#toc64560874" id="toc64560874"></a>

The **ScatterPlot** widget is a Data Presentation type widget. Its data source consists of a report that requires the following **mandatory fields:**

1. **DATA\_X:** indicates the value of the x-axis attribute determining the position on the horizontal axis of the chart.
2. **DATA\_Y:** indicates the value of the y-axis attribute determining the position on the vertical axis of the chart.
3. **DATA\_ID**: it is the identifier of the data used to manage the selection and export of parameters. It can be the same field used for the x-axis or the y-axis (in this case, the x-axis or the y-axis field must contain unique values).

<div align="left"><img src=".gitbook/assets/1" alt=""></div>

You can add to the report optional fields, especially to manage multiple series:

1. **SERIES\_ID:** It is the identifier of the series used to manage the selection and export parameters.
2. **SERIES\_NAME:** It is the name of the series. Use this field in the report to assign a specific name to the series. In the case of a single series, you can use both this field in the report that the property of the widget **single series name**. The use of the field **SERIES\_NAME** in the report will prevail over the configuration of the property **single series name**.
3. **SERIES\_COLOR**: It is the color of the series. Use this field in the report to assign specific colors to the series. You can use it also in the case of a single series. When no specified will be used default colors.
4. **AXIS\_NAME**: It allows managing multiple vertical axes in the chart (one for each series), in addition to the primary DATA\_Y axis. Series can be associated with this field by mapping with the unique name of the axis.

Each row of the report will become a single dot in the **ScatterPlot** widget with position according to the column values. The spread of dots on the chart shows the relationship between the two dimensions.

The widget supports:

* More than one report.
* Single and multiple series of data.
* High number of data points.

## Properties <a href="#toc64560875" id="toc64560875"></a>

The properties that are specific for the configuration of the **ScatterPlot** widget on **Decisyon App Composer** are listed below:

<table><thead><tr><th width="237">Group</th><th width="256">Name</th><th width="435">Description</th><th width="191" align="center">Type</th><th width="225" align="center">Default Value</th><th align="center">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Animation (Settings/Other)</strong></td><td><strong>Chart animation</strong></td><td>Enable or disable an initial animation of the series of data when opening the page. <strong>For best performance, it is recommended to disable this feature in the case of big datasets</strong></td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Chart (Settings/Other)</strong></td><td><strong>Chart title</strong></td><td>Allows you to specify a custom title to display on the chart, especially useful when exporting the chart as a file. You can use the %REPORT TITLE% keyword to inherit the title of the associated main report</td><td align="center">TEXTFIELD</td><td align="center">%REPORT_TITLE%</td><td align="center"></td></tr><tr><td><strong>Crosshair settings (Settings/Interaction)</strong></td><td><a href="./#crosshair"><strong>Crosshair</strong></a></td><td>Enable/disable the crosshair option</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Title</strong></td><td>Sets a default title for the y-axis of the chart. When no title is specified, the report column header will be used as a title</td><td align="center">TEXTFIELD</td><td align="center">Undefined</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Generic label format VIZ</strong></td><td>Sets the label format for numbers or text to be displayed on the y-axis of the chart. You can set custom labels or select among the <strong>Value</strong>, <strong>Dollars</strong>, <strong>Percentage</strong>, and <strong>Euros</strong> options available in the drop-down list</td><td align="center">SELECT</td><td align="center">Value</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Time label format VIZ</strong></td><td>Sets the label format for data time to be displayed on the y-axis of the chart. You can use one of the Unicode Technical Standard custom formats. Please refer to the site <a href="https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table">http://www.unicode.org/</a>)</td><td align="center">SELECT</td><td align="center">Month year (e.g. Oct 2020)</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Range minimum (number or date)</strong></td><td>Sets the minimum value (number or date) to show on the y-axis range. It must be the same format used for the y-axis and in the <strong>Date-time format IN</strong> property</td><td align="center">NUMERIC</td><td align="center">0.0</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Range maximum (number or date)</strong></td><td>Sets the maximum value to show on the y-axis range. It must be the same format used for the y-axis and in the <strong>Date-time format IN</strong> property</td><td align="center">NUMERIC</td><td align="center">0.0</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Interval size</strong></td><td>Defines the data interval, the number of periods on the y-axis. In the case of data-time, you have to configure also the <strong>Interval time unit</strong> property</td><td align="center">NUMERIC</td><td align="center">0.0</td><td align="center"></td></tr><tr><td><strong>Default Y axis properties (Settings/Axes)</strong></td><td><strong>Interval time unit</strong></td><td>Defines the unit of time, with its value being expressed in years, months, days, hours, or minutes. The default setting (Auto) defines the interval of the axis based on your report data. Configure this property only in the case of date-time on the y-axis</td><td align="center">SELECT</td><td align="center">Auto</td><td align="center"></td></tr><tr><td><strong>Multiple value axes configuration (Settings/Axes)</strong></td><td><a href="./#axes-configuration-json"><strong>Axes configuration JSON</strong></a></td><td>Allows you to configure additional vertical axes in the chart</td><td align="center">TEXTFIELD</td><td align="center">Undefined</td><td align="center"></td></tr><tr><td><h4><strong>Selection settings</strong></h4></td><td><a href="./#selection-mode"><strong>Selection mode</strong></a></td><td>Sets different type of selection mode for selecting data</td><td align="center">SELECT</td><td align="center">Disabled</td><td align="center"></td></tr><tr><td><h4><strong>Selection settings</strong></h4></td><td><strong>Multiple selection</strong></td><td>Allows you to select multiple data points on the chart at the same time</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Series (Settings/Other)</strong></td><td><p></p><p><strong>Single series name</strong></p><p></p></td><td>Allows you to specify a name for the data series to be used when the data have only one series</td><td align="center">SELECT</td><td align="center">Series</td><td align="center">Yes</td></tr><tr><td><strong>Series (Settings/Other)</strong></td><td><strong>Marker size (px)</strong></td><td>Allows you to specify the dimension of the marker in pixel</td><td align="center">NUMERIC</td><td align="center">10.0</td><td align="center"></td></tr><tr><td><strong>Toolbar settings (Settings/Interaction)</strong></td><td><p><strong>Show toolbar</strong></p><p></p></td><td>Enable/disable the display of the toolbar on the chart containing the interaction tools (crosshair, tooltip, cluster tooltip) and the print and export buttons</td><td align="center">SWITCH</td><td align="center">1</td><td align="center"></td></tr><tr><td><strong>Tooltip settings (Settings/Interaction)</strong></td><td><p></p><p><strong>Tooltip</strong></p><p></p></td><td>Allows the administrator to enable/disable the display of the tooltip that shows information when hovering the data. The end-user can change the default setting by the "<strong>Tooltip</strong>" button shown on the chart's toolbar</td><td align="center">SWITCH</td><td align="center">1</td><td align="center"></td></tr><tr><td><strong>Tooltip settings (Settings/Interaction)</strong></td><td><p><strong>Tooltip format</strong></p><p></p></td><td><p>Sets a format to display data in the tooltip. You can set custom formats or select among the options:</p><ul><li><strong>Series name: X value – Y value:</strong> the tooltip shows both the series name and axes' values.</li><li><strong>X value – Y value:</strong> the tooltip shows only axes' values</li></ul></td><td align="center">SELECT</td><td align="center">Series name: X value - Y value</td><td align="center"></td></tr><tr><td><strong>Tooltip settings (Settings/Interaction)</strong></td><td><strong>Cluster tooltip</strong></td><td>Allows the administrator to enable/disable the display of the cluster tooltip that shows the tooltip for the data points that are closer to the point where you touch on the chart area. This feature, especially, can be used when you cannot show data labels for all data points due to space constraints. The end-user can change the default setting by the "<strong>Cluster tooltip</strong>" button shown on the chart's toolbar</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><h4><strong>X axis data (Settings/Data)</strong></h4></td><td><a href="./#x-axis-data-settings-data"><strong>Data type</strong></a></td><td>Allows selecting the type of value to be displayed on the x-axis</td><td align="center">SELECT</td><td align="center">Text</td><td align="center"></td></tr><tr><td><h4><strong>X axis data (Settings/Data)</strong></h4></td><td><strong>Date-time format IN</strong></td><td>Configure this property only when the <strong>Data type</strong> property is set on <strong>Data and time</strong>. It set the format to be used to parse data in the data source report. You can use the formats available in the drop-down list (ISO format, Epoch, and Epoch milliseconds) or one of the Unicode Technical Standard custom formats. For the custom formats, please refer to the site <a href="https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table">http://www.unicode.org/</a>)</td><td align="center">SELECT</td><td align="center">ISO format</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><p></p><p><strong>Title</strong></p><p></p></td><td>Sets a title for the x-axis of the chart. When no title is specified, the report column header will be used as a title</td><td align="center">TEXTFIELD</td><td align="center">Undefined</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><strong>Generic label format VIZ</strong></td><td>Sets the label format for numbers or text to be displayed on the x-axis of the chart. You can set custom formats or select among the <strong>value</strong>, <strong>dollars</strong>, <strong>percentage</strong>, and <strong>euros</strong> options </td><td align="center">SELECT</td><td align="center">Value</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><strong>Time label format VIZ</strong></td><td>Sets the label format for date-time values to be displayed on the x-axis of the chart. You can use one of the Unicode Technical Standard custom formats. For the custom formats, please refer to the site <a href="https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table">http://www.unicode.org/</a>)</td><td align="center">SELECT</td><td align="center">Month year (e.g. Oct 2020)</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><p></p><p><strong>Range minimum (number or date)</strong></p><p></p></td><td>Sets the minimum value (number or date) to show on the x-axis range. It must be the same format used for the x-axis and in the <strong>Date-time format IN</strong> property</td><td align="center">NUMERIC</td><td align="center">Undefined</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><strong>Range maximum (number or date)</strong></td><td>Sets the maximum value to show on the x-axis range. It must be the same format used for the x-axis and in the <strong>Date-time format IN</strong> property</td><td align="center">NUMERIC</td><td align="center">Undefined</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><p></p><p><strong>Interval size</strong></p></td><td>Allows you to define the data interval, the number of periods on the x-axis. In the case of data-time, you have to configure also the <strong>Interval time unit</strong> property</td><td align="center">NUMERIC</td><td align="center">0.0</td><td align="center"></td></tr><tr><td><strong>X axis properties (Settings/Axes)</strong></td><td><strong>Interval time unit</strong></td><td>The default setting (Auto) defines the interval of the axis based on your report data. Configure this property only in the case of date-time on the x-axis</td><td align="center">SELECT</td><td align="center">Auto</td><td align="center"></td></tr><tr><td><strong>Y axis data (Settings/Data)</strong></td><td><p></p><p><a href="./#y-axis-data-settings-data"><strong>Data type</strong></a></p><p></p></td><td>Allows selecting the type of value to be displayed on the y-axis</td><td align="center">SELECT</td><td align="center">Number</td><td align="center"></td></tr><tr><td><strong>Y axis data (Settings/Data)</strong></td><td><strong>Date-time format IN</strong></td><td>Configure this property only when the <strong>Data type</strong> property is set on <strong>Data and time</strong>. It set the format to be used to parse data in the data source report. You can use the formats available in the drop-down list (ISO format, Epoch, and Epoch milliseconds) or one of the Unicode Technical Standard custom formats. For the custom formats, please refer to the site <a href="https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table">http://www.unicode.org/</a>)</td><td align="center">SELECT</td><td align="center">ISO format</td><td align="center"></td></tr><tr><td><strong>Zoom settings (Settings/Interaction)</strong></td><td><p></p><p><a href="./#zoom-settings-settings-interaction"><strong>Selection zooming</strong></a></p><p></p></td><td>Enable the zooming selection on the chart</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Zoom settings (Settings/Interaction)</strong></td><td><p></p><p><strong>Mouse wheel zooming</strong></p><p></p></td><td>Enabling the property, you can zoom in and zoom out the chart by scrolling the mouse wheel.</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Zoom settings (Settings/Interaction)</strong></td><td><strong>Pinch to zoom</strong></td><td>Enabling the property, you can zoom the chart through pinch gestures on touch-enabled devices</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Zoom settings (Settings/Interaction)</strong></td><td><a href="./#zoom-settings-settings-interaction"><strong>Zoom direction</strong></a></td><td>Allows you to specify whether the chart is allowed to scale along the horizontal axis or vertical axis</td><td align="center">SELECT</td><td align="center">X and Y</td><td align="center"></td></tr></tbody></table>

#### **Crosshair**

The **Crosshair** property allows you to enable/disable the crosshair option. Crosshair is an interactive feature. When users hover over the data points on the chart, it displays the axes coordinates with labels. Horizontal and vertical lines link the point to facilitate reading it (see the picture below).

<div align="left"><img src=".gitbook/assets/4" alt=""></div>

#### **Axes configuration JSON**

The **Axes configuration JSON** property allows you to configure additional vertical axes in the chart, so you can do correlation analysis and analyze the factors driving the increase or decrease of other values.

Following the specification for the JSON configuration.

```j
// JSON Example
[
{
"name":"axisName1",
"minimum":0,
"maximum":100,
"exampleDescription":"Axis with manual minimum and maximum"
},
{
"name":"axisName2",
"labelFormat":"{value} units",
"exampleDescription":"Axis with custom label format"
},
{
"name":"axisName3",
"opposedPosition":true,
"exampleDescription":"Axis displayed on the right side"
},
{
"name":"axisName4",
"valueType":"Logarithmic",
"exampleDescription":"Axis with different value type"
},
{
"name":"axisName5",
"title":"Custom title",
"exampleDescription":"Axis with custom title"
},
{
"name":"axisName6",
"interval":5,
"intervalType":"Auto",
"exampleDescription":"Axis with custom intervals (intervalType is used for date grouping, ie. Months, Years, Days etc.)"
}
]
```

| Property          | Description                                                                                                                                                                                                                                                                            |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "name"            | Unique name of the axis.                                                                                                                                                                                                                                                               |
| "minimum"         | Specifies the minimum value to show on the axis range.                                                                                                                                                                                                                                 |
| "maximum"         | Specifies the maximum value to show on the axis range.                                                                                                                                                                                                                                 |
| "labelFormat"     | Provides custom formatting for axis label. Numeric values can be formatted with **Dollars**, **Percentage**, and **Euros**.                                                                                                                                                            |
| "opposedPosition" | Specifies whether to render the axis at the opposite side of its default position.                                                                                                                                                                                                     |
| "valueType"       | <p>Define the type of axis:</p><ul><li><strong>Number:</strong> sets numeric values as axis.</li><li><strong>Logarithmic:</strong> sets values in a logarithmic scale as axis.</li><li><strong>DateTime:</strong> sets the timestamp as axis.</li></ul>                                |
| "title"           | Specifies the custom title of the axis.                                                                                                                                                                                                                                                |
| "interval"        | Specifies a custom interval for the axis range.                                                                                                                                                                                                                                        |
| "intervalType"    | <p>Define the interval type of datetime axis:</p><ul><li><strong>Auto</strong></li><li><strong>Years</strong></li><li><strong>Months</strong></li><li><strong>Days</strong></li><li><strong>Hours</strong></li><li><strong>Minutes</strong></li><li><strong>Seconds</strong></li></ul> |

#### **Selection mode**

The **Selection mode** property allows you to set different type of selection mode for selecting data. When selecting data points, you can export their values on the page. To deselect a point, just click on it again. **For best performance, it is recommended to disable this feature in the case of big datasets.**

In the drop-down list, you can choose:

* **Disabled:** no type of selection is set. Default setting.
* **Point:** you can select single data points.
* **Cluster:** you can select the points that correspond to the same index in all the series.

**This feature requires that series have the same number of values and their values must be synchronized (see the example below).**

<div align="left"><img src=".gitbook/assets/5" alt=""></div>

The example shows how cluster selection allows you to select values from series that belong to the same index.

In the example, by selecting the “Nintendo” point belonging to the year 2016, the cluster selection automatically selects the other series of the same year.

Note how the values of all series corresponding to the year 2016 are exported to the page.

* **X axis:** allows you to enable the drag selection of data with respect to the horizontal axis.
* **Y axis:** allows you to enable the drag selection of data with respect to the vertical axis.
* **Area:** allows you to enable the drag selection to select data under a particular region with respect to the horizontal and vertical axis.
* **Lasso:** allows you to select a region by drawing freehand shapes to fetch a collection of data.

{% hint style="warning" %}
When the **selection mode** property is set on **X axis, Y axis, Area, or Lasso**, the chart does not support any **zoom feature** even if the property is enabled.
{% endhint %}

#### **X axis data (Settings/Data)**

* **Data type:** allows selecting the type of value to be displayed on the x-axis. In the drop-down list, you can select:
  * **Text:** sets text as x-axis.
  * **Date and time:** sets the timestamp as x-axis.
  * **Date and time (non-linear):** sets the date-time values with non-linear intervals as x-axis. For example, the business days alone depicted in a week.
  * **Number:** sets numeric values as x-axis.
  * **Logarithmic number:** sets values in a logarithmic scale as x-axis. It is useful in visualizing data when they have numerical values, both in the lower order of magnitude (eg: 10-6) and in the higher order of magnitude (eg: 106).

#### **Y axis data (Settings/Data)**

* **Data type:** allows selecting the type of value to be displayed on the x-axis. In the drop-down list, you can select:
  * **Number:** sets numeric values as y-axis.
  * **Logarithmic number:** sets values in a logarithmic scale as y-axis. It is useful in visualizing data when they have numerical values, both in the lower order of magnitude (eg: 10-6) and in the higher order of magnitude (eg: 106).
  * **Date and time:** sets the timestamp as y-axis.
  * **Date and time (non-linear):** sets the date-time values with non-linear intervals as y-axis. For example, the business days alone depicted in a week.

#### **Zoom settings (Settings/Interaction)**

* **Selection zooming:** Enable the zooming selection on the chart. After zooming the chart, a toolbar will appear with zoom, zoom in, zoom out, pan, and reset buttons. Selecting the Pan option will allow panning the chart, and selecting the Reset option will reset the zoomed chart.

<div align="left"><img src=".gitbook/assets/6" alt=""></div>

* **Zoom direction:** allows you to specify whether the chart is allowed to scale along the horizontal axis or vertical axis. In the drop-down list, you can select:
  * **X and Y:** both axis (default setting)
  * **X:** allows you to zoom the chart horizontally
  * **Y:** allows you to zoom the chart vertically

{% hint style="warning" %}
When the **selection mode** property is set on **X axis, Y axis, Area, or Lasso**, the chart does not support any **zoom** **feature** even if the property is enabled.
{% endhint %}

## Widget Parameters <a href="#toc64560876" id="toc64560876"></a>

**Exported Parameters**

The following parameters are exported by the widget when selecting data in the chart:

| Name                                           | Description                                                          | Note                                                                                                                      |
| ---------------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| \<baseName>\_\<single\_series\_name>\_selected | Exports the ID values of the selected points for the default series. | This parameter is used when there are points that do not belong to one of the specified series or no series is specified. |
| \<baseName>\_\<series\_name>\_selected         | Exports the ID values of the selected points for each series.        |                                                                                                                           |

## Example <a href="#toc64560877" id="toc64560877"></a>

**Configuration:** Using the following specific properties:

**Selection mode, Data Type, Time label format VIZ**

**Description:** The example shows the use of the **ScatterPlot** widget to observe the relationship between data in two dimensions. This case uses multiple series of data.

* Create the data source report of the widget. The report must have three mandatory fields **(DATA\_X, DATA\_Y, DATA\_ID).** This example uses the optional fields **SERIES\_ID, SERIES\_NAME,** and **SERIES\_COLOR.**

![](.gitbook/assets/7)

{% hint style="info" %}
In this example, the DATA\_ID field matches with one axis field, as the y-axis field contains unique values.
{% endhint %}

* Create a new Page in the Page Design and use the **ScatterPlot** widget. Associate the report created in the first step to the widget.
* Map the columns of the report in the **fields association** property of the widget.

<div align="left"><img src=".gitbook/assets/8" alt=""></div>

* Specify in the page the parameters exported by the **ScatterPlot** widget:

In the **ScatterPlot** properties, enter the **basename** for the widget. In this example “**ScatterPlot**”;

On the page, add two “**Text Area**” widgets. Specify in each of them the parameter exported by the **ScatterPlot** widget when selecting data in the chart. Each parameter name must respect the syntax created by the widget basename and the series nam&#x65;**:**

**\<baseName>\_< series\_name>\_selected**

The series name is the series mapped in the columns of the report in the previous step. See the picture.

<div align="left"><img src=".gitbook/assets/9" alt=""></div>

* Configure the following specific properties of the widget:

**Chart title:** Enter a title to display on the top of the chart (i.e. “Height Versus Weight by Gender”).

**Selection mode:** Select **Point** option for selecting single data points.

**Multiple selection:** Enable the property.

**Marker size:** Set 10 px

* Display the **ScatterPlot** widget in the Web Application.

<div align="left"><img src=".gitbook/assets/10" alt=""></div>

* Select the data points that, as a configuration, will be exported as parameters within the page.

<div align="left"><img src=".gitbook/assets/11" alt=""></div>

{% hint style="info" %}
&#x20;The selected points have a deeper color than the other points. To deselect a point, just click on it again.
{% endhint %}
