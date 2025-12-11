---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/aYHQvgJiShX4tMBRzZ83/documentation/andon-line-1.0
---

# Pareto 1.0

## 📖Overview <a href="#toc57294676" id="toc57294676"></a>

The **Pareto Widget** visualizes cumulative values across different categories by combining a **Column Chart** and a **Line Chart**. The initial values are displayed as bars, while the cumulative totals are represented by a line. The cumulative line is automatically calculated based on the bar data, providing a clear view of the distribution and impact of each category.

The Pareto chart widget has two axes:

1. **Primary axis** for the Bars (frequency of occurrences).
2. **Secondary axis** for the Pareto line (cumulative percentage).

{% embed url="https://app.arcade.software/flows/SBVqABvSfrEbvbvFxQUN/view" %}

**Easy Configuration & Interaction**

Page developers can easily configure the widget using a simple report. When a chart column is clicked, the widget exports the corresponding column’s **ID** value, as defined in the report. This **unique identifier** can then be used for further interactions and data processing within the page.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### Customization Options

#### Customization through Widget Settings

The **Pareto widget** provides different customization options to enhance readability and adaptability:

* **Series Color**: Set a custom default color for all the Columns of the chart.

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Pareto Line Customization:** Define a custom fill color for the Line series, set a specific pattern and define its width (thickness).

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

**Axis customization:** Define custom titles for both the x-axis and y-axis and toggle the display of the secondary axes of the chart to enhance clarity.

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Refer to the [Properties](./#toc57294678) section for a full list of configurable options.
{% endhint %}

#### Customization via Report Properties

Beyond the standard widget settings, the **Report Properties** enable deeper customization, including:

* **Data Color Customization**: Assign **unique colors** to each column by mapping values to the `R01_data_color` field, ensuring visual distinction between different categories.

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

* [**Interaction & data exploration**](https://github.com/radinolf/Documentation/blob/cb6401656d76d8fbc936eeeb0d93ffc19532fb7c/WIDGETS/Pareto/documentation/pareto-1.0/interactive-pareto-drill-through-configuration.md)**:** Configure **Drill-Through** functionality directly within the report’s data source, allowing users to explore a detailed breakdown of values for deeper insights.

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Refer to the [Report Mapping](./#report-mapping) section for detailed configuration.
{% endhint %}

## 📊Report Mapping

The **Pareto** widget is classified as a **Data Presentation** widget, supporting a single data source that provides the dataset needed to populate the chart.

**Required Report: REPORT 1**

**Mandatory Fields**

* **`R01_data_id`:** Unique identifier for the series. It must be unique and can be mapped to either the x-axis or y-axis.
* **`R01_data_x`:** Determines the **positioning** of each segment along the **horizontal (x) axis**.
* **`R01_data_y`:** Determines the **positioning** of each segment along the **vertical (y) axis**.

**Optional Field**

* **`R01_data_color`:** Defines a **custom color** for each column using a color name (e.g., `"blue"`) or a HEX/RGB code.
  * If not specified, the **primary color** set in the Web Application is applied.
  * If both the **widget property** (`series color`) and the **report field** specifies a color, the **report field** takes precedence.

#### **Field Mapping Example**

In the following **report data source**, the fields correspond as follows:

* **`ITEM`** → `R01_data_id` and `R01_data_x`
* **`VALUE`** → `R01_data_y`
* **`COLOR`** → `R01_data_color`

<figure><img src=".gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

The sequence of columns in the chart **mirrors the order of rows in the report**. The **first row** in the report corresponds to the **first column on the left** in the chart, the **second row** to the **second column**, and so forth, maintaining a direct one-to-one mapping.&#x20;

Ensure that the fields in the Report are correctly mapped in the **Fields Association** property of the widget to ensure proper functionality.

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

## ⚙️Properties <a href="#toc57294678" id="toc57294678"></a>

The properties that are specific for the configuration of the **Pareto** widget on **Decisyon App Composer** are listed below:

<table><thead><tr><th width="246">Group</th><th width="167">Name</th><th width="608">Description</th><th width="394" align="center">Type</th><th width="800">Select Value</th><th width="129" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td><strong><code>report data source number</code></strong></td><td>Allows you to define the number of report data sources that provide the dataset to the widget. When defining more than one report, then they should be associated with the <code>report datasource</code> properties.</td><td align="center">TEXTFIELD</td><td></td><td align="center">1</td><td>false</td></tr><tr><td><strong>Main</strong></td><td><strong><code>report data source</code></strong></td><td>Allows you to associate one or more reports to the widget, based on the number of data sources specified in the <code>report datasource number</code> property.</td><td align="center">SELECT</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>ObjectStyle</strong></td><td><strong><code>fields association</code></strong></td><td>Allows you to map the report columns with the specific fields.</td><td align="center">SELECT</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><strong><code>dash array</code></strong></td><td>Sets the dash pattern for the Pareto line. It controls the appearance of the line by defining the lengths of the dashes and gaps. Enter a sequence of numbers separated by spaces or commas, where each number represents the length of a dash or gap. You can use custom values or choose from the suggested options in the dropdown.</td><td align="center">STRING</td><td><ul><li><strong>Solid Line</strong>: "0"</li><li><strong>Dashed Line with Equal Spacing</strong>"5,5"</li><li><strong>Dotted Line</strong> "2,2"</li><li><strong>Irregular Dash Pattern</strong> "10 5 2"</li></ul></td><td align="center"><strong>Solid Line</strong>: "0"</td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><strong><code>line color</code></strong></td><td>Define the fill color of the Pareto line. When the white color is set, default= rgb (255, 255, 255), the widget will inherit the secondary color configured in App Composer.</td><td align="center">COLOR</td><td></td><td align="center"><p>White (255, 255, 255):</p><p>It will inherit the Secondary App Composer color if white is set.</p></td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><strong><code>line width</code></strong></td><td>Defines the stroke width (thickness) of the Pareto line, affecting its visual prominence in the chart.</td><td align="center">NUMERIC (measured in pixels)</td><td></td><td align="center">3</td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><strong><code>series color</code></strong></td><td><p>Assign a DEFAULT color to the series. Also configurable in the report by using the <code>R01_data_color</code> field to specify a different color for each column.</p><p>Set this property only when it is not defined in the report associated with the widget.</p><p>Report settings will override the widget setting.<br>When the white color is set, default= rgb (255, 255, 255), the widget will inherit the primary color configured in App Composer.</p></td><td align="center">COLOR</td><td></td><td align="center">rgb (255, 255, 255)</td><td>false</td></tr><tr><td><strong>Widget settings/Setting</strong></td><td><strong><code>show axis</code></strong></td><td>Controls whether the <strong>secondary axis</strong> (cumulative percentage) for the Pareto line is displayed.</td><td align="center">SWITCH</td><td>0,1</td><td align="center">1</td><td>false</td></tr><tr><td><strong>dget settings/Setting</strong></td><td><strong><code>show markers</code></strong></td><td>Enables or disables markers on data points.</td><td align="center">SWITCH</td><td>0,1</td><td align="center">1</td><td>false</td></tr><tr><td><strong>X axis data /Settings /Axis Data</strong></td><td><strong><code>data type</code></strong></td><td>Sets the type of value to be displayed on the x-axis field.</td><td align="center">SELECT</td><td><ul><li><strong>Text</strong>: Sets text as x-axis.</li><li><strong>Date and time (non-linear):</strong> Sets the date-time values. It can not follow a consistent interval or sequence (Irregular gaps between times, such as 12:00, 12:05, 12:20, 12:35).</li><li><strong>Number:</strong> Sets numeric values as x-axis.</li><li><strong>Logarithmic number:</strong> Sets a logarithmic scale instead of a traditional linear scale. On a logarithmic scale, the values increase exponentially. For example, values on the axis might progress as 1, 10, 100, and 1000, instead of 1, 2, 3, and 4 (linear progression).</li></ul></td><td align="center">Text</td><td>false</td></tr><tr><td><strong>X axis data /Settings /Axis Data</strong></td><td><strong><code>date-time format IN</code></strong></td><td><p>Sets the format to parse data in the data source report. Configure this property only when the <strong>Data type</strong> property is set on <strong>Data and time (non-linear)</strong>.</p><p>You can use the formats available in the drop-down list or one of the Unicode Technical Standard custom formats. For the custom formats, refer to the site <a href="https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table">http://www.unicode.org/</a>).<br>The drop-down lists suggestions. The developer can input other values in this property.</p></td><td align="center">TEXTFIELD</td><td><ul><li>ISO format</li><li>Epoch</li><li>Epoch (milliseconds)</li><li>year</li><li>year-month</li><li>year-month-day</li></ul></td><td align="center">ISO format</td><td>false</td></tr><tr><td><strong>X axis title /Settings /Axex title</strong></td><td><strong><code>generic label format VIZ</code></strong></td><td>Sets the label format for data type <strong>Number</strong> or <strong>Logarithmic number</strong> to be displayed on the value-axis of the chart. You can set custom labels or select the options in the drop-down list. When the <code>data type</code> is set to <strong>Date and time (non-linear),</strong> this setting will be ignored by the widget. You need to configure the <code>Time label format VIZ</code> property.<br>The drop-down menu lists suggestions. The developer can input other values in this property.</td><td align="center">STRING</td><td><ul><li>Value</li><li>Dollars</li><li>Percentage</li><li>Euros</li></ul></td><td align="center">Value</td><td>false</td></tr><tr><td><strong>X axis title /Settings /Axex title</strong></td><td><strong><code>time label format VIZ</code></strong></td><td>Defines the label format for <strong>Date and Time (non-linear)</strong> data on the time-axis. You can select a suggested option from the dropdown or enter a custom format using the Unicode Technical Standard formats. Please refer to the website <a href="https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table">http://www.unicode.org/</a>).<br>For <strong>Number</strong> or <strong>“Logarithmic number</strong>, this setting is ignored. Instead, use the <code>generic label format VIZ</code> property.<br>The dropdown provides suggestions, but the developer can input other values manually.</td><td align="center">STRING</td><td><ul><li>month year (e.g. 2020)</li><li>month day (e.g. October 21)</li><li>month year (Oct 2020)</li><li>quarter year (e.g. Q3 2020)</li><li>day/month (e.g. 21/10)</li><li>hours:minutes AM/PM (e.g. 2:26 PM)</li><li>year (e.g. 2020)</li></ul></td><td align="center">month year (e.g. 2020)</td><td>false</td></tr><tr><td><strong>X axis title /Settings /Axex title</strong></td><td><strong><code>x axis title</code></strong></td><td>Defines a title of the x-axis for the x-axis of the chart.</td><td align="center">TEXTFIELD</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>Y axis title /Settings /Axex title</strong></td><td><strong><code>generic label format VIZ</code></strong></td><td>Defines the label format for the value axis of the chart. You can choose a suggested option from the dropdown or enter a custom label (eg. <code>{value}£</code>).</td><td align="center">TEXTFIELD</td><td><ul><li>Value</li><li>Dollars</li><li>Percentage</li><li>Euros</li></ul></td><td align="center">Value</td><td>false</td></tr><tr><td><strong>Y axis title /Settings /Axex title</strong></td><td><strong><code>y axis title</code></strong></td><td>Defines a title for the y-axis of the chart.</td><td align="center">TEXTFIELD</td><td></td><td align="center"></td><td>false</td></tr></tbody></table>

## 🔗Widget Parameters

In the `base name` widget's property, it is possible to specify a baseName to identify the widget's parameters and compose them uniquely.

**Exported Parameters**

The following parameter is exported by the **Pareto** widget on the click event of the segment:

| Name                  | Description                                                               | Note                                                                           |
| --------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| `{baseName}_selected` | Exports the identification code of the column when the user clicks on it. | The ID code is defined in the data source report (see Report Mapping section). |

<figure><img src=".gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
