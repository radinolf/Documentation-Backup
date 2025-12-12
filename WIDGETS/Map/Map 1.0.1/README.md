# Map 1.0.1

## Overview <a href="#toc78540224" id="toc78540224"></a>

The **Map** is a powerful data visualization widget that shows information for a specific location. Using a simple report, the Map widget is ideal for rendering **Geographical maps** from OpenStreetMap or **Custom maps,** using an external [tile server](#user-content-fn-1)[^1] or a DAC Library (created by an administrator user) as a tile server.

<figure><img src=".gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

The picture illustrates how different Map types may be shown using a simple report and minimal widget settings.

Pins are used in the Map widget to indicate places with precise latitudes and longitudes. By referring to the [Material](https://material.io/icons/) website, you may use different shapes as pins and set custom colors.

It is possible to select the pins. When a pin is selected, the widget exports a parameter containing the ID of the clicked element on the map (or the Latitude and Longitude coordinates in case custom tiles are used). These parameters may then be used within the page.

The widget allows user interaction. Page developer may configure the report and the widget to:&#x20;

* Assign to the map an action to execute an object (Report, Page, and Web page) for each pin on the map, so that the business user can open a new dialog with more specific information.&#x20;
* Configure a second report with the KPIs information for the selected pin: a dedicated dialog box opens with this information when a pin is clicked.
* Disable any user interaction only for some pins.

There are several setting options for the Map widget. Its rich feature set includes pins, pin clustering, pin icons and colors, map zooming, map dragging, and much more.

See the **Properties** section for all applicable configurations.

## Report Mapping

**Map** is a widget of Data Presentation type that has to be associated with a report data source. Its data source is a required report that includes the following **mandatory fields**:

1. **R01\_item:** Indicates the unique identification number of the map element (pin).&#x20;
2. **R01\_latitude:** Indicates the latitude point of the map, which determines the latitude location of the pin.
3. **R01\_longitude:** Indicates the longitude point of the map, which determines the longitude location of the pin.
4. **R01\_active\_flag:**  Indicates the active or disabled map elements. 1 for an active element, 0 for a disabled one.

<figure><img src=".gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

You can include the following **optional** columns in this report:

1. **R01\_pin\_icon:** It is the icon to use for the pin. Enter the name of the icon by referring to the material icon name on [https://material.io/icons/](https://material.io/icons/). If the icon is not specified here, the default icon configured in the **default pin icon** property will be used.
2. **R01\_pin\_color**: Use this field in the report to assign a specific color to the pin icon. It accepts both RBG and HEX color code. If the color is not specified here, the default color configured in the **default pin color** property will be used.

<figure><img src=".gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Even if a custom color has been specified in the report, the disabled pin (**R01\_active\_flag** field set to 0) will be displayed in grey.
{% endhint %}

The second report is optional. In this report, the list of KPIs is organized into groups for each item, so that clicking a map's pin will open a dedicated dialog with information about that pin:

1. **R02\_item:** It is the identifier of the KPI. If you use the second report, the ID in this column must match the **ID** (R01\_item) column of the first report so that the join between the report works.
2. **R02\_kpi\_name:** It is the name of the KPI.&#x20;
3. **R02\_kpi\_unit:** Indicates the KPI unit (for example, meters, second, percent, etc.).
4. **R02\_kpi\_value:** It is the value of the KPI.
5. **R02\_kpi\_target:** It is the target value of the KPI.
6. **R02\_kpi\_icon:** It is the icon of the KPI.
7. **R02\_kpi\_color:** It is the color of the icon.

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Metrics may be used in both the rows and the columns of the report.
{% endhint %}

### User Interaction

The Business user can interact with the widget. When an active pin is clicked on the map, it is possible to associate an action to recall an object (Page, Report or Web page) and view detailed data inside a new window.

The[ **Show Pin dialog**](documentation/map-1.0.1/pin-setting.md#show-pin-dialog) property of the widget affects how the drill-through link is opened when an active pin is clicked:

When the **Show pin dialog** property is not enabled (default), the drill-through dialog will open the target object directly when the business user clicks the pin.&#x20;

<figure><img src=".gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

When the **Show pin dialog** property is enabled, the link to the drill-through will be displayed inside a dedicated dialog box.

<figure><img src=".gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

The App Developer can configure the drill-through feature directly on the first report from the **Report Editor**![](.gitbook/assets/3)

**Report Properties tab > Drill-Through**

{% hint style="warning" %}
The widget will use only the first drill-through activated on the first report, even if have been configured multiple drill-throughs.
{% endhint %}

The drill-through can be enabled in any positio&#x6E;**:** Any dimensional level can be used to configure the drill-through (**drill-through-position** property).

The widget supports the following drill-through rendering types (**show-on** property):

* **Link**
* **Kebab menu**
* **Icon and text**
* **Icon only**
* **context menu**
* **double click**

{% hint style="warning" %}
The widget will ignore the following rendering types even if they are enabled in the drill-through:

* **Top**
* **Command-column**
{% endhint %}

The properties **drillThroughImage** and **drillThroughDesc** are used only if the property **show pin dialog** is enabled in the map:

When the **Show pin dialog** property is disabled, the widget will ignore these properties even if configured because the drill-through will open directly when the map's pin is clicked.

When the **Show pin dialog** property is enabled, the widget will use the image specified in the **drillThroughImage** property as the button's icon to open the drill-through and the value specified in the **drillThroughDesc** property as the button's description.

{% hint style="info" %}
The drill-through's default icon and the name of the destination object will be displayed if **drillThroughImage** and **drillThroughDesc** properties are not set in the drill-through.
{% endhint %}

## Properties <a href="#toc78540225" id="toc78540225"></a>

The properties that are specific for the configuration of the **Map** widget on **Decisyon App Composer** are listed below:

<table data-full-width="true"><thead><tr><th width="217">Group</th><th width="202">Name</th><th width="361">Description</th><th width="141" align="center">Type</th><th width="178" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#zooming">Zoomable</a></td><td>If enabled the zoom is enabled.</td><td align="center">SWITCH</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#zooming">Initial Zoom</a></td><td>Sets the initial zoom value in the map.</td><td align="center">NUMBER</td><td align="center">-1</td><td>true</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#zooming">Max zoom</a> </td><td>Sets the maximum zooming value in the map.</td><td align="center">NUMBER</td><td align="center">3</td><td>true</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#center-longitude-and-latitude">Center longitude</a></td><td>Sets the longitude of the center position of the map.</td><td align="center">NUMBER</td><td align="center">0</td><td>true</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong> </td><td><a href="documentation/map-1.0.1/map-settings.md#center-longitude-and-latitude">Center latitude</a></td><td>Sets the latitude of the center position of the map.</td><td align="center">NUMBER</td><td align="center">0</td><td>true</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#dragging">Draggable</a></td><td>If enabled the map is draggable.</td><td align="center">SWITCH</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#horizontal-repeat">Horizontal repeat</a></td><td>If enabled the map is repeated horizontally.</td><td align="center">SWITCH</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Map Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-settings.md#export-coordinates-on-click">Export coordinates on click</a></td><td>If enabled, each click on the map exports the Latitude and Longitude coordinates of the selected point. This property will disable the drill-through and the dialog box opening for a better selection.</td><td align="center">SWITCH</td><td align="center">0</td><td>true</td></tr><tr><td><strong>Map Source (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-source.md#map-provider">Map provider</a></td><td>Sets the map provider (OSM, Tile Server, Shared Library).</td><td align="center">SELECT</td><td align="center">OSM (OpenStreetMap)</td><td>false</td></tr><tr><td><strong>Map Source (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/map-source.md#server-url">Server URL</a></td><td>Sets the URL of the server of the custom map tiles.</td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td></tr><tr><td><strong>Pin Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/pin-setting.md#default-pin-icon-and-default-pin-color">Default pin icon</a></td><td>Default pin icon to use in case it is not defined in the report.  Enter the name of the icon by referring to the website <a href="https://material.io/icons/">https://material.io/icons/</a></td><td align="center">TEXTFIELD</td><td align="center">place</td><td>true</td></tr><tr><td><strong>Pin Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/pin-setting.md#default-pin-icon-and-default-pin-color">Default pin color</a></td><td>Default color of the active pin in case it is not specified in the report.</td><td align="center">COLOR</td><td align="center">Rgb(255,255,255)</td><td>true</td></tr><tr><td><strong>Pin Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/pin-setting.md#clustering">Cluster enabled</a></td><td>If enabled the map clustering the neighboring elements.</td><td align="center">SWITCH</td><td align="center">0</td><td>false</td></tr><tr><td><strong>Pin Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/pin-setting.md#clustering">Cluster range</a></td><td>Range of the cluster.</td><td align="center">NUMBER</td><td align="center">10</td><td>false</td></tr><tr><td><strong>Pin Settings (Settings/General settings)</strong></td><td><a href="documentation/map-1.0.1/pin-setting.md#show-pin-dialog">Show pin dialog</a></td><td>If enabled, a specific dialog will appear when you click the pin.</td><td align="center">SWITCH</td><td align="center">0</td><td>false</td></tr></tbody></table>

## Widget Parameters <a href="#toc63261619" id="toc63261619"></a>

**Exported Parameters**

The following parameter is exported by the widget on click event:

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Note</th></tr></thead><tbody><tr><td>{baseName}</td><td>It is the <strong>base name</strong> of the widget. Set it in the <strong>base name</strong> property, Parameters group (the default base name is Map). Exports the identification code of the clicked element on the map. </td><td>It is not triggered when the <strong>Cluster enabled</strong> property is active.</td></tr><tr><td>{baseName}_selected_longitude</td><td>Exports the numeric value of the longitude when the business user clicks any point on the map.</td><td><ul><li>This parameter is exported only if the <strong>Export coordinates on click</strong> property is enabled. </li><li>Use this feature to retrieve the coordinates for placing your pins on custom map tiles.</li></ul></td></tr><tr><td>{baseName}_selected_latitude</td><td>Exports the numeric value of the latitude when the business user clicks any point on the map.</td><td><ul><li>This parameter is exported only if the <strong>Export coordinates on click</strong> property is enabled. </li><li>Use this feature to retrieve the coordinates for placing your pins on custom map tiles.</li></ul></td></tr></tbody></table>



[^1]: A map tile server is a server or service that provides map data in the form of small rectangular images called map tiles. Map tiles are the basic building blocks of online maps and are typically square images that represent a portion of a map at a specific zoom level.



    Map tile servers generate and serve these tiles in real-time, allowing users to access and display maps on various devices and applications. The tiles are typically served as a series of image files (e.g., PNG or JPEG) that are organized in a hierarchical directory structure based on the zoom level, row, and column coordinates. By retrieving and assembling these tiles, applications can create a seamless map view for users, enabling them to pan, zoom, and interact with the map.
