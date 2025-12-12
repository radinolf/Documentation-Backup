# Pie Chart 1.0

## Overview <a href="#toc57294676" id="toc57294676"></a>

The Pie Chart Widget is designed to **visualize proportions** within a dataset by dividing a whole into **slices**, each representing a category’s contribution. It is ideal for **quick comparisons** and **distribution analysis** in various contexts, including manufacturing, quality control, and performance monitoring.

<figure><img src=".gitbook/assets/image (286).png" alt=""><figcaption></figcaption></figure>

#### **Key Features**

✅ **Data-Driven Visualization** → Displays data from reports in a pie chart format.\
✅ **Customizable Colors** → Supports custom slice colors from report data or default settings.\
✅ **Tooltips** → Displays detailed information when hovering over slices.\
✅ **Drill-Through Support** → Allows interaction by exporting parameters when a slice is clicked.\
✅ **Configurable Display** → Supports legends, data labels, and smart label positioning.\
✅ **Flexbox Layout** → Ensures responsiveness across different screen sizes.

**Easy Configuration & Interaction**

Page developers can easily configure the widget using a simple data source. When a user clicks on a chart slice, the widget exports the corresponding **ID value** as defined in the report. This unique identifier can be leveraged for further interactions and data processing within the page, enabling dynamic user experiences.

<figure><img src=".gitbook/assets/image (277).png" alt=""><figcaption></figcaption></figure>

### Customization through Widget Settings

The **Pie Chart Widget** provides different customization options to enhance readability and adaptability:

* **Series Color**: Set a custom default color for all the slices. When the white color is set, default= rgb (255, 255, 255), the widget will inherit the primary color configured in App Composer.

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

* **Slice border**: Customize the border thickness between slices.
* **Radius:** Defines the outer radius of the chart as a percentage of the available space

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* **Legend**: Enables or disables the chart legend, define its position and alignment.

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
For a full list of configurable options, refer to the [Properties](./#toc57294678).&#x20;
{% endhint %}

### Customization via Report Properties

Beyond the standard widget settings, the **Report Properties** enable deeper customization, including:

* **Data Color Customization**: Assign **unique colors** to each slice by mapping values to the `R01_data_color` field, ensuring visual distinction between different categories.

<figure><img src=".gitbook/assets/image (283).png" alt="" width="563"><figcaption></figcaption></figure>

* **Tooltip Customization**: Customize the tooltip text for each slice of the Pie Chart, allowing business users to see specific information when hovering over the widget.

<figure><img src=".gitbook/assets/image (284).png" alt="" width="563"><figcaption></figcaption></figure>

* [**Interaction & data exploration**](documentation/pie-chart-1.0/interactive-pie-chart-drill-through-configuration.md)**:** Configure **Drill-Through** functionality directly within the report’s data source, allowing users to explore a detailed breakdown of values for deeper insights.

<figure><img src=".gitbook/assets/image (281).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Refer to the [Report Mapping](./#report-mapping) section for detailed configuration.
{% endhint %}

## Report Mapping

The **Pie Chart** widget is classified as a **Data Presentation** widget, supporting a single data source that provides the dataset needed to populate the chart.

**Required Report: REPORT 1**

**Mandatory Fields**

* **`R01_data_id`:** Unique identifier for the series. It must be unique and can be mapped to either the x-axis or y-axis.
* **`R01_data_x`:** Defines the slices. (represents different slice of the Pie chart).
* **`R01_data_y`:** Determines the size of each slice (represents the proportional value for each category).

**Optional Field**

* **`R01_data_color`:** Defines a **custom color** for each slice using a color name (e.g., `"blue"`) or a HEX/RGB code.
  * If not specified, the **primary color** set in the Web Application is applied.
  * If both the **widget property** (`series color`) and the **report field** specifies a color, the **report field** takes precedence.
* `R01_tooltip`**:** Displays detailed information on hover. Supports HTML content if the column type is HTML.

### **Field Mapping Example**&#x20;

In the following **report data source**, the fields correspond as follows:

* **`DATA_ID`** → `defect_id`&#x20;
* `DATA_X` → `defect_type`
* **`DATA_Y`** → `defect_count`
* **`COLOR`** → `defect_color`
* `TOOLTIP`→`tooltip_info`&#x20;

<figure><img src=".gitbook/assets/image (278).png" alt=""><figcaption></figcaption></figure>

Ensure that the fields in the Report are correctly mapped in the **Fields Association** property of the widget to ensure proper functionality.

<figure><img src=".gitbook/assets/image (279).png" alt=""><figcaption></figcaption></figure>

## Properties <a href="#toc57294678" id="toc57294678"></a>

The properties that are specific for the configuration of the **Donut Chart** Widget on **Decisyon App Composer** are listed below:

<table data-full-width="true"><thead><tr><th width="246">Group</th><th width="167">Name</th><th width="608">Description</th><th width="394" align="center">Type</th><th width="307">Select Value</th><th width="129" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td><code>report data source number</code></td><td>Allows you to define the number of report data sources that provide the dataset to the widget. When defining more than one report, then they should be associated with the <code>report datasource</code> properties.</td><td align="center">TEXTFIELD</td><td></td><td align="center">1</td><td>false</td></tr><tr><td><strong>Main</strong></td><td><code>report data source</code></td><td>Allows you to associate one or more reports to the widget, based on the number of data sources specified in the <code>report datasource number</code> property.</td><td align="center">SELECT</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>ObjectStyle</strong></td><td><code>fields association</code></td><td>Allows you to map the report columns with the specific fields.</td><td align="center">SELECT</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><code>show data label</code></td><td>Display the data labels.</td><td align="center">BOOLEAN</td><td>True, False</td><td align="center">True</td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><code>data label position</code></td><td>Position data labels <code>inside</code> or <code>outside</code> the chart.</td><td align="center">SELECT</td><td>Outside, Inside</td><td align="center">Outside</td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><code>series color</code></td><td><p>Assign a DEFAULT color to the series. Also configurable in the report by using the <code>R01_data_color</code> field to specify a different color for each slice.</p><p>Set this property only when it is not defined in the report associated with the widget. </p><p>Report settings will override the widget setting. <br>When the white color is set, default= rgb (255, 255, 255), the widget will inherit the primary color configured in App Composer.</p></td><td align="center">COLOR</td><td></td><td align="center">rgb (255, 255, 255)</td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><code>slice border width</code></td><td>Adjusts the border thickness between slices.</td><td align="center">NUMERIC</td><td></td><td align="center">0</td><td>false</td></tr><tr><td><strong>Appearance/Settings</strong></td><td><code>smart labels</code></td><td>Prevents label overlapping by repositioning labels intelligently. Useful when many slices have close values.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Tooltip/Settings Interaction</strong></td><td><code>tooltip</code></td><td>Enables/disables tooltips when hovering over slices.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Widget settings/Settings</strong></td><td><code>chart title</code></td><td>Sets a title for the chart.</td><td align="center">STRING</td><td></td><td align="center"></td><td>true</td></tr><tr><td><strong>Widget settings/Settings</strong></td><td><code>legend alignment</code></td><td>Sets the alignment of the legend to <code>center</code>, <code>far</code> or <code>near</code> of the chart.</td><td align="center">SELECT</td><td>Center, Far, or Near</td><td align="center">Near</td><td>false</td></tr><tr><td><strong>Widget settings/Settings</strong></td><td><code>legend position</code></td><td>Sets the position of the legend at the <code>left</code>, <code>right</code>, <code>top</code> or <code>bottom</code> of the chart.</td><td align="center">SELECT</td><td>Left, Right, Top, Bottom</td><td align="center">Right</td><td>false</td></tr><tr><td><strong>Widget settings/Settings</strong></td><td><code>null handling</code></td><td>Defines how to manage <code>null</code> Y values.<br> If <code>Drop</code> is set (default), Null values are <strong>excluded</strong> from the chart.</td><td align="center">SELECT</td><td>Zero, Drop, Average</td><td align="center">Drop</td><td>false</td></tr><tr><td><strong>Widget settings/Settings</strong></td><td><code>radius</code></td><td>Defines the outer radius of the chart as a percentage of the available space.</td><td align="center">NUMERIC</td><td></td><td align="center">80</td><td>false</td></tr><tr><td><strong>Widget settings/Settings</strong></td><td><code>show legend</code></td><td>Enables or disables the chart legend.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">1</td><td>false</td></tr></tbody></table>

## Widget Parameters

In the `base name` widget's property, it is possible to specify a baseName to identify the widget's parameters and compose them uniquely.

**Exported Parameters**

The following parameter is exported by the **Pie Chart** widget on the click event of the slice:

| Name                  | Description                                                              | Note                                                                           |
| --------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `{baseName}_selected` | Exports the identification code of the slice when the user clicks on it. | The ID code is defined in the data source report (see Report Mapping section). |

<figure><img src=".gitbook/assets/image (282).png" alt=""><figcaption></figcaption></figure>
