# Widget Settings

## Introduction

The **Settings** panel in the Widget Editor contains the properties to configure the widget. It is located in the left section of the Widget Editor and is visible after selecting the **SETTINGS** tab at the bottom right.&#x20;

In the panel, the properties are organized into groups, sub-groups, and subsets to improve the organization and facilitate the search.

<figure><img src="../../../.gitbook/assets/image (1513).png" alt=""><figcaption></figcaption></figure>

The properties contained in the groups **Main**, **Preview mock generation** and **Page Integration** may change depending on the type of widget selected.

## Main Settings

The **Main** settings group contains the main properties for configuring the widget, grouped in&#x20;

* **MAIN** **DEPS**
* **DATA MODEL** (only for Data Presentation widgets )
* **ADVANCED**&#x20;

### MAIN

The **MAIN** sub-group has the properties grouped into **Main**, **Error management** and **Data Connector** subsets.

<figure><img src="../../../.gitbook/assets/image (1801).png" alt=""><figcaption></figcaption></figure>

It contains the following properties:

<table data-full-width="true"><thead><tr><th width="132">Subset</th><th width="165">Name</th><th width="436">Description</th><th width="187" align="center">Type</th><th width="190" align="center">Default Value</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td><strong>Published</strong></td><td>Publish the widget that will then be visible in the widget catalog of the Page Design, located in the respective folder. The same operation can be executed from the <a href="../widget-catalog.md#contextual-menu">contextual menu of Widget Catalog</a>.</td><td align="center">SWITCH</td><td align="center">0</td></tr><tr><td><strong>Main</strong></td><td><strong>Rest-api-to-call</strong></td><td>Allows you to associate to the widget a <a href="../../sdk-and-api/rest-api-client.md">REST API Client</a> previously defined, in order to invoke the REST API from a Page using the widget.</td><td align="center">SELECT</td><td align="center"></td></tr><tr><td><strong>Main</strong></td><td><a href="widget-settings.md#logical-name"><strong>Logical name</strong></a></td><td>Defines the widget's logical name, which is used as the identifier for the relevant associations. Only one widget with the same logical name may be published. </td><td align="center">TEXTFIELD</td><td align="center"></td></tr><tr><td><strong>Main</strong></td><td><strong>Default reference name</strong></td><td>Allows you to set a default value for the <strong>baseName</strong> of the widget.</td><td align="center">TEXTFIELD</td><td align="center"></td></tr><tr><td><strong>Error management</strong></td><td><strong>Handling mode</strong></td><td><p>Allows you to set how to display the error message caused by an incorrect configuration of the widget, choosing between:</p><ul><li><strong>Default (auto):</strong> the error message is displayed inside a box provided by App Composer.</li><li><strong>Template error:</strong> The data that populate the widget include the error message. The management of the error should be implemented inside the widget's code.</li></ul></td><td align="center">SELECT</td><td align="center">Default (auto)</td></tr><tr><td><strong>Data Connector</strong></td><td><strong>Use data connector</strong></td><td><p>Enables the use of a Data Connector for the widget. Once activated, the following property is enabled:</p><ul><li>Connector API ID: enter the ID of the corresponding Data Connector.</li></ul></td><td align="center">SWITCH</td><td align="center">0</td></tr><tr><td><a data-footnote-ref href="#user-content-fn-1"><strong>Excel integration</strong></a>  </td><td>For Excel integration</td><td>This property has to be activated if the widget (File Uploader for our needs) is used for execute an Excel integration via Execute Button.</td><td align="center">SWITCH</td><td align="center">0</td></tr></tbody></table>

####

#### Logical Name

**Logical Name** is used as the identifier for widgets. When a new widget is created the system automatically assigns a default and unique logical name to the widget.&#x20;

<figure><img src="../../../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

We suggest changing the default logical name and assigning the widget a meaningful logical name in order to be recognized in various contexts.&#x20;

{% hint style="info" %}
It is very important to assign a self-explanatory and unique logical name, because:

* In the presence of multiple widgets or shared libraries with the same name, only one can be published.
* A self-explanatory logical name helps you access and use the Decisyon API to manage the widget information in your code.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (634).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
The logical name may only be changed if the widget hasn't been published.&#x20;

In order to modify the logical name of an already published widget, it is necessary to unpublish it first.
{% endhint %}

Only one widget with the same logical name may be published. Publishing a widget with the same logical name as an already published widget, the system will immediately "unpublish" the previously published widget and all connected pages (or libraries) will refer to the newly published element.

### DEPS

The **DEPS** sub-group contains the properties for the definition of all dependencies, grouped into **CSS** and **JS** subsets.

<figure><img src="../../../.gitbook/assets/image (1110).png" alt=""><figcaption></figcaption></figure>

It contains the following properties:

<table data-full-width="true"><thead><tr><th width="120">Subset</th><th width="209">Name</th><th width="436">Description</th><th width="187" align="center">Type</th><th width="190" align="center">Default Value</th></tr></thead><tbody><tr><td><strong>CSS</strong></td><td><strong>Css dependences</strong></td><td>Allows you to load one or more CSS files developed in the widget or shared library to define their style.</td><td align="center">SELECT</td><td align="center"></td></tr><tr><td><strong>JS</strong></td><td><strong>Js dependences</strong></td><td>Allows you to load one or more Javascript files developed in the widget or shared library required to define their display and behaviour.</td><td align="center">SELECT</td><td align="center"></td></tr></tbody></table>

### DATA MODEL

The **DATA MODEL** sub-group is visible only for Data Presentation widgets. It contains the properties to define the data structure and data binding, organized into the subsets **Data structure** and **Additional attributes**.

<figure><img src="../../../.gitbook/assets/image (907).png" alt=""><figcaption></figcaption></figure>

It contains the following properties:

<table data-full-width="true"><thead><tr><th width="161">Subset</th><th width="209">Name</th><th width="436">Description</th><th width="187" align="center">Type</th><th width="190" align="center">Default Value</th></tr></thead><tbody><tr><td><strong>Data structure</strong></td><td><strong>Fields definition</strong></td><td>Allows you to define the fields that can be used to map structured data related to the associated data source reports.</td><td align="center">TEXTFIELD</td><td align="center"></td></tr><tr><td><strong>Data structure</strong></td><td><strong>Full report data</strong></td><td>Allows you to enable data population with the entire report content. If disabled, limits the population to only defined rows and columns.</td><td align="center">SWITCH</td><td align="center">0</td></tr><tr><td><strong>Additional attributes</strong></td><td><strong>Cell span</strong></td><td>Provides you with information on the grouping state of the cells with the same value.</td><td align="center">SWITCH</td><td align="center">0</td></tr><tr><td><strong>Additional attributes</strong></td><td><strong>Cell drill</strong></td><td>Provides you with information on the display state of the drill on the cells.</td><td align="center">SWITCH</td><td align="center">0</td></tr><tr><td><strong>Additional attributes</strong></td><td><strong>Cell decoration</strong></td><td>Provides you with information on the style of the cells.</td><td align="center">SWITCH</td><td align="center">0</td></tr></tbody></table>

{% hint style="info" %}
It is recommended to activate just the necessary settings to reduce the time required to load the widget.
{% endhint %}

### ADVANCED&#x20;

The **ADVANCED** sub-group contains the properties to specify the version and compatibility of the widget. All the properties are included in the subset **Version & Compatibility.**

<figure><img src="../../../.gitbook/assets/image (1537).png" alt=""><figcaption></figcaption></figure>

TIt contains the following properties:

<table data-full-width="true"><thead><tr><th width="161">Subset</th><th width="209">Name</th><th width="436">Description</th><th width="187" align="center">Type</th><th width="190" align="center">Default Value</th></tr></thead><tbody><tr><td><strong>Version &#x26; Compatibility</strong></td><td><strong>Version</strong></td><td>Sets the value of the widget version</td><td align="center">TEXTFIELD</td><td align="center">1.0</td></tr><tr><td><strong>Version &#x26; Compatibility</strong></td><td><strong>Minimum API level</strong></td><td>Sets the minimum API level that DAC must have to run the widget</td><td align="center">SELECT</td><td align="center">0</td></tr><tr><td><strong>Version &#x26; Compatibility</strong></td><td><strong>Maximum API level</strong></td><td>Sets the maximum API level that DAC must have to run the widget</td><td align="center">SELECT</td><td align="center">0</td></tr><tr><td><strong>Version &#x26; Compatibility</strong></td><td><strong>Target API level</strong></td><td>Sets the API level of DAC that the widget is built to run on</td><td align="center">SELECT</td><td align="center">0</td></tr></tbody></table>

{% hint style="info" %}
API levels help determine whether the widget is compatible with a specific DAC instance in order to install or upgrade it.

The widget will be compatible with all the versions of DAC which are falling between the Minimum and Maximum API level range and the Target API level.
{% endhint %}

## Preview mock generation

In the **Preview mock generation** group there are the properties for the generation of data used for simulating the behavior of the widget when using the "preview" button.

These properties will be displayed in the Page Design based on the widget type:

* For the **Generic** widget type, these properties are grouped in the **SUPPORTED SETTINGS** sub-group and **Supported settings value.**

<figure><img src="../../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

* For the **Data Presentation** widget type, the properties are grouped in **DATA GENERATION** and **SUPPORTED SETTINGS** sub-groups.&#x20;

Under **DATA GENERATION** there are the properties to select the report and the application to be used to generate the [`mockData.json`](/broken/pages/MiCT76B6ZkB1Pa89UHGf#mockdata.json) when developping the widget.

<figure><img src="../../../.gitbook/assets/image (1508).png" alt=""><figcaption></figcaption></figure>

## Page integration

The **Page integration** group contains the properties that allow the widget to be integrated into the Page Design. These properties are grouped in **SUPPORTED SETTINGS** and **PARAMATERS** sub-groups.

<figure><img src="../../../.gitbook/assets/image (1518).png" alt=""><figcaption></figcaption></figure>

The widget developers may set the parameters **Imported** and **Exported** by the widget in the **PARAMATERS** sub-group. The paramaters configured in this section will be available in the **Widget Parameters** dialog in the Page Design, which will appear by right-clicking the widget.

<figure><img src="../../../.gitbook/assets/image (1500).png" alt=""><figcaption></figcaption></figure>

[^1]: This property is available from version 2023.2.2
