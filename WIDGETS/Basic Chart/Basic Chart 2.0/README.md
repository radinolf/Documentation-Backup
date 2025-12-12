# Basic Chart 2.0

## Overview <a href="#toc68163465" id="toc68163465"></a>

The **Basic Chart** widget can be used to display one or more than one series of data configuring the type of chart to use or a combination of them. Supported charts are **line**, **column**, or **stacked columns**.

![](<.gitbook/assets/image (16).png>)

In the picture, the **Basic Chart** widget is associated with simple reports. The data are displayed using stacked columns and line. The chart shows the yield, locked, and locked target values as metrics.

You can use the **Basic Chart** widget for comparing the frequency, count, total, or average of data in different categories.

The widget supports:

* More than one report;
* Single and multiple series of data;
* A combination of line and column or stacked column series;
* A high number of data points (more than 30K).

It is possible to customize its functionality and behavior, using the specific configuration properties in the Page Design.

See the **Properties** section for all applicable configurations.

## Report Mapping

The **Basic Chart** widget is a Data Presentation type widget. Its data source can consist of one or two reports.&#x20;

* The first report must contain the **data points** of all series and requires the following **mandatory fields:**

1. **DATA\_X:** indicates the value of the x-axis attribute determining the position on the horizontal axis of the chart.
2. **DATA\_Y:** indicates the value of the y-axis attribute determining the position on the vertical axis of the chart.
3. **DATA\_ID**: it is the identifier of the data. It can be the same field used for the x-axis or the y-axis (in this case, the x-axis or the y-axis field must contain unique values).

![](<.gitbook/assets/image (1).png>)

Each series can have additional attributes which are used to configure options in the chart, such as the color to apply to the chart or the axis name. Each of these properties can be associated with the widget using a dedicated column in the report that contains the value of the property to use. **You need to include the following columns in the report only if you want to use a single report; as an alternative, you can create a second report just to configure the chart property.**

{% hint style="success" %}
It is strongly recommended to use a second report that contains only chart options to avoid data redundancy, improve performance, and have a report dedicated only to properties.
{% endhint %}

1. **SERIES\_ID:** It is the identifier of the series.
2. **SERIES\_NAME:** It is the name of the series. Use this field in the report to assign a specific name to the series. In the case of a single series, you can use both this field in the report that the property of the widget **single series name**. The use of the field **SERIES\_NAME** in the report will prevail over the configuration of the property **single series name**.
3. **SERIES\_COLOR**: It is the color of the series. Use this field in the report to assign specific colors to the series using the HEX format. You can use it also in the case of a single series. When no specified will be used default colors.
4. **SERIES\_TYPE**: Allows configuring for each series the type. You can use **Line**, **StakingColumn**, and **Column** (case-insensitive) types to render the series. The Column is the default type.
5. **AXIS\_NAME**: It allows managing multiple vertical axes in the chart (one for each series), in addition to the primary DATA\_Y axis. Series can be associated with this field by mapping with the unique name of the axis. (By default shows the value of the column related to the DATA\_Y axis).

* The second report is optional. You can add columns related to the **series description.** This report, to be valid must contain the **JOIN\_INFO\_SERIES\_ID** field:

1. **JOIN\_INFO\_SERIES\_ID:** It is the identifier of the series. The logical name of this column must match the **‘SERIES\_ID’** column of the first report. If not associated, the report will not be valid (the widget will not consider any **JOIN\_INFO\_SERIES\*** fields used for the series description).
2. **JOIN\_INFO\_SERIES\_NAME:** It is the name of the series.
3. **JOIN\_INFO\_SERIES\_COLOR**: It is the color of the series.&#x20;
4. **JOIN\_INFO\_SERIES\_TYPE**: It is the type of the series (**Line**, **StakingColumn**, **Column).**&#x20;
5. **JOIN\_INFO\_AXIS\_NAME**: It allows managing multiple vertical axes in the chart (one for each series), in addition to the primary DATA\_Y axis.

![](<.gitbook/assets/image (20).png>)

{% hint style="warning" %}
When using two reports to map your **Basic Chart** widget, the **SERIES\_ID** field is required on both reports and the logical name of this column must be the same in both reports because it is used to match the data series and its properties. If not associated, the second report will not be valid and the widget will not consider any **JOIN\_INFO\_SERIES\*** fields used for the series description.
{% endhint %}

## Properties

The properties that are specific for the configuration of the **Basic Chart** widget on **Decisyon App Composer** are listed below:

<table><thead><tr><th width="214">Group</th><th width="174">Name</th><th width="342">Description</th><th width="191" align="center">Type</th><th width="225" align="center">Default Value</th><th align="center">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Animation (Settings/Other)</strong></td><td><strong>Chart animation</strong></td><td>Enable or disable an initial animation of the series of data when opening the page. <strong>For best performance, it is recommended to disable this feature in the case of big datasets</strong></td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Chart (Settings/Other)</strong></td><td><strong>Chart title</strong></td><td>Allows you to specify a custom title to display on the chart, especially useful when exporting the chart as a file. You can use the %REPORT TITLE% keyword to inherit the title of the associated main report</td><td align="center">TEXTFIELD</td><td align="center">%REPORT_TITLE%</td><td align="center"></td></tr><tr><td><strong>Series (Settings/Other)</strong></td><td><p></p><p><strong>Single series name</strong></p><p></p></td><td>Allows you to specify a name for the data series to be used when the data have only one series</td><td align="center">SELECT</td><td align="center">Series</td><td align="center">Yes</td></tr><tr><td><h4><strong>X axis data (Settings/Data)</strong></h4></td><td><a href="./#x-axis-data-settings-data"><strong>Data type</strong></a></td><td>Allows selecting the type of value to be displayed on the x-axis</td><td align="center">SELECT</td><td align="center">Text</td><td align="center"></td></tr><tr><td><h4><strong>X axis data (Settings/Data)</strong></h4></td><td><a href="./#x-axis-data-settings-data"><strong>Date-time format IN</strong></a></td><td>Sets the format to be used to parse data in the data source report</td><td align="center">SELECT</td><td align="center">ISO format</td><td align="center"></td></tr><tr><td><strong>Y axis data (Settings/Data)</strong></td><td><p></p><p><a href="./#y-axis-data-settings-data"><strong>Data type</strong></a></p><p></p></td><td>Allows selecting the type of value to be displayed on the y-axis</td><td align="center">SELECT</td><td align="center">Number</td><td align="center"></td></tr><tr><td><strong>Y axis data (Settings/Data)</strong></td><td><a href="./#y-axis-data-settings-data"><strong>Date-time format IN</strong></a></td><td>Sets the format to be used to parse data in the data source report</td><td align="center">SELECT</td><td align="center">ISO format</td><td align="center"></td></tr></tbody></table>

#### **X axis data (Settings/Data)**

* **Data type:** Allows selecting the type of value to be displayed on the x-axis. In the drop-down list, you can select:
  * **Text:** Sets text as x-axis.
  * **Date and time:** Sets the timestamp as x-axis.
  * **Date and time (non-linear):** Sets the date-time values with non-linear intervals as x-axis. For example, the business days alone depicted in a week.
  * **Number:** Sets numeric values as x-axis.
  * **Logarithmic number:** Sets values in a logarithmic scale as x-axis. It is useful in visualizing data when they have numerical values, both in the lower order of magnitude (eg: 10-6) and in the higher order of magnitude (eg: 106).
* **Date-time format IN:** Configure this property only when the **Data type** property is set on **Data and time**. It set the format to be used to parse data in the data source report. You can use the formats available in the drop-down list (ISO format, Epoch, and Epoch milliseconds) or one of the Unicode Technical Standard custom formats. For the custom formats, please refer to the site [http://www.unicode.org/](https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table)).

#### **Y axis data (Settings/Data)**

* **Data type:** Allows selecting the type of value to be displayed on the x-axis. In the drop-down list, you can select:
  * **Number:** Sets numeric values as y-axis.
  * **Logarithmic number:** Sets values in a logarithmic scale as y-axis. It is useful in visualizing data when they have numerical values, both in the lower order of magnitude (eg: 10-6) and in the higher order of magnitude (eg: 106).
  * **Date and time:** Sets the timestamp as y-axis.
  * **Date and time (non-linear):** Sets the date-time values with non-linear intervals as y-axis. For example, only business days in a week.
* **Date-time format IN:** Configure this property only when the **Data type** property is set on **Data and time**. It set the format to be used to parse data in the data source report. You can use the formats available in the drop-down list (ISO format, Epoch, and Epoch milliseconds) or one of the Unicode Technical Standard custom formats. For the custom formats, please refer to the site [http://www.unicode.org/](https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table)).

## Examples <a href="#toc68163468" id="toc68163468"></a>

### **Example - 1** **How to configure the Basic Chart widget with Single series of data**&#x20;

Here is an example that shows the **Basic Chart** widget to render a single series of data using a simple report. In this example are used **columns** as series type (default) and a **custom color** to represent the monthly yield of a manufacturing company.

* Create the data source report of the widget. The report must have three mandatory fields **(DATA\_X, DATA\_Y, DATA\_ID)**

![](<.gitbook/assets/image (30).png>)

{% hint style="warning" %}
**In this example, the DATA\_ID field matches with one axis field, as the X-axis field contains unique values.**
{% endhint %}

* Create a new Page in the Page Design and use the **Basic Chart** widget. Associate the report created in the first step to the widget.
* Map the columns of the report in the **fields association** property of the widget.

![](<.gitbook/assets/image (34).png>)

* In the **Basic Chart** properties, enter the **Chart title** for the widget. In this example “**Basic Chart - Example 1**”;
* Save your page and display the **Basic Chart** widget in the Web Application.

![](<.gitbook/assets/image (35).png>)

### **Example - 2** **How to configure the Basic Chart widget with Multiple series of data and Multiple vertical axes**&#x20;

Here is an example that shows the **Basic Chart** widget to render multiple series of data using two simple reports. In this example are used a **combination of stacked columns and line series** and **custom colors** for representing the monthly yield of a manufacturing company.

* Create the **first data source** report of the widget. In this report, you can enter your data points. In addition to the mandatory fields **(DATA\_X, DATA\_Y, DATA\_ID)**, it must contain the identifier of the series **(SERIES\_ID)**.

![](<.gitbook/assets/image (28).png>)

To get a widget mapping similar to this example using **Metrics**, you need to reorder the Metrics on the report rows (see the picture).&#x20;

![](<.gitbook/assets/image (5).png>)

In this way, you can use the value of metrics "**Column of Values**" to map the **DATA\_Y** and the name of metrics to map the **DATA\_ID** and the **SERIES\_ID**.&#x20;

In the second report, you will need to use the logical name of the Metrics to map the **JOIN\_INFO\_SERIES\_ID**.&#x20;

* Create the **second** **data source** report of the widget. In this report, you can enter the description of the series. It must contain the identifier of the series **JOIN\_INFO\_SERIES\_ID. The logical name of this field must match the SERIES\_ID field of the first data source.**&#x20;

In this example, the **SERIES\_ID** column will contain the logical names of the **Metrics** (see the picture above).

![](<.gitbook/assets/image (19).png>)

* Create a new Page in the Page Design and use the **Basic Chart** widget. Associate the two reports created in the first step to the widget.
* Map the columns of the reports in the **fields association** property of the widget.

![](<.gitbook/assets/image (25).png>)

* In the **Basic Chart** properties, enter the **Chart title** for the widget. In this example “**Basic Chart - Example 2**”;
* Save your page and display the **Basic Chart** widget in the Web Application.

![](<.gitbook/assets/image (32).png>)
