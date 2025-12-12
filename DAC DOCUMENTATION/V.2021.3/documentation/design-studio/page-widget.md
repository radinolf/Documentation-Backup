---
description: >-
  Widgets are the fundamental bricks of a page and provide specific
  functionalities that you can leverage to build your page.
---

# Page Widget

**Widgets** are the fundamental bricks of a page and provide specific functionalities that you can leverage to build your page. Each widget has its own configuration properties; a page contains one or more widgets and you can also create interactions on them and they can leverage the same data.

Watch the video showing a brief overview of widgets

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/Widget/Widgets.mp4" %}

Main widgets groups that can be used in a page are:

* [Data Visualization](page-widget.md#data-visualization): set of widgets to visualize the data
* [Form](page-widget.md#form): set of widgets used to insert a text or select page by
* [Button](page-widget.md#button): set of widgets used to perform the operations which interact with other systems or other DAC objects
* Containers: set of widgets used to define a Page layout in a more complex manner than the simple grid available on the Page Designer
* [Discussion](page-widget.md#discussion): set of widgets use for discussions to be opened, possibly on a specific topic
* [Resource](page-widget.md#resource)**:** set of widgets to insert in the page image JavaScript or text
* [Social Spaces](page-widget.md#social-spaces): set of widgets used in the social space.

## Data Visualization

Data presentation widget to display the reports created in the application using:

* a table, with the [Crosstab component](page-widget.md#crosstabs)
* a [Chart](page-widget.md#chart)
* an [**Indicator**](page-widget.md#indicator-component)
* a [Map](page-widget.md#map-google-maps)
* a Tag [Cloud](page-widget.md#cloud-type)

DAC has a geo-analysis component available on Google Maps by acquiring the Google license.

This element includes the selection of the associated report or the indicator (for the Indicator component): the selection is made in the _**reportAssociated**_ property. For this type of component the DAC user may access the associated report.

Parameters can be defined within the dashboard page; these are used by the data display objects within filter conditions (**Filter** property), to change the display of the data.

**Page-by note:**

_If the length of the page-bys exceeds that of the container, these will be re-adjusted, arranged on several rows._

**Common properties for Data Visualization widgets**

**Datasource**_:_ Property is visible only if Data Presentation group widgets have been mapped to Data Source REST

• **Input-params-mapping:** Use the variables used in the definition of the [data source](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Data_Source_REST) to associate a page parameter.

If you select the \<default> value, the system associates the value defined during the datasource configuration phase.

### Crosstabs

The Crosstab component inherits the properties defined in the report; those that can be changed in the component are those relating to the _ObjectStyle_ grou&#x70;_._

The properties which can be customized on the Crosstab component in the Page are:

* _**show-page-by**_ enables the header of the report
* _**show-body**_ enables the display of the content of the report (page-by is excluded)
* _**rowsLocked:**_ locks the rows of the report while scrolling
* _**colsLocked:**_ locks the columns of the report while scrolling
* _**object-**_&#x74;ransparency defines the transparent color for the cells of the crosstab
* _**< none >**_ no transparency
* _**< body >**_ transparency only for the cells of the body of the report
* _**< body & header >**_ transparency for the body of the report and the headers

The property is applicable and visible only if the row and column lock properties are not enabled.

* **force-auto-expand-height (Group Page PDF Export)** sets the auto-expand value in the container during exportation of the PDF Page, so that all the values in the crosstab are printed.
* _**show-rows-cols-numbers:**_ enables the display of the number of rows and columns of the report. The information is visible in the toolbar of the report. Therefore the show-toolbar property must be enabled.

### Chart

For a chart object, the properties set in the report can only be inherited if the Apply graph style item is selected (from the pop-up menu for the object).

Custom properties are those relating to the:

* Style (_GraphStyle_ group)
* Axes (_Axis_ group)
* Legend (_Legend_ group)
* Value display mode (_Layer_ group)
* Graph title (_GraphTitle_ group), which is _separate_ from the one defined in the _Title_ group. In the case of graphs, both _the Title_ and the _GraphTitle_ coincide with the name of the report. To define a different title, insert the graph in a table and set the title in the title for the table.
* Object style (_ObjectStyle_ group)

The properties of these groups are similar to those in the report.

For the flash type graphs, the property to define the wiDSh is not available (**graphWiDSh**), but it is calculated depending on the wiDSh set in the container in order to favor automatic re-dimensioning in wiDSh.

### Map (Google Maps)

The **Map** component integrates _**Google**_ _**Maps**_ into the DAC Page. The use of _Google Maps_ involves activating the service through the key provided by Google.

![](<../../.gitbook/assets/0 (22).png>)

The map is associated with a report containing geographical levels, which are interpreted by Google Maps as markers to be placed in the area indicated by the level. So if there are regions in the report, markers will be entered for each region; if, instead, the geographical level has provinces, the markers will be positioned on the coordinates of the provinces.

The **report associated** with the _Map_ component must have the following structure:

*
  * A single geographic dimensional level positioned on the rows
  * Metrics are positioned on the columns.

Georeferencing is applied to the description of the dimensional level.

Reports are also supported with multiple levels on the rows, but only if grouped according to _layout_: in this case, the map will represent the most aggregate level. Non-geographical levels can be inserted in the report at page-by level.

Description of the dimensional level can also be configured as follows:

* _**Notation with coordinates**_

_**\<description\_location>#LOCATION#\<latitude>, \<longitude>**_

* _**Text notation**_
* _**\<description\_location>#LOCATION#\<address/city>**_

Where:

*   \<description\_location> is the description displayed


*   \<latitude>is the latitude coordinate (with a dot as decimal point)


*   \<longitude> is the longitude coordinate (with a dot as decimal point)


* \<address/city> is text containing a territorial location that can be interpreted by Google Maps

For example, the reading "Decisyon office Latina@41.466735, 12.891650" will appear with "Decisyon office Latina" corresponding to the pointer associated with the Google map, and the pointer will be aligned with the geographic coordinates "41.466735, 12.891650".

The same position of the marker is obtained with the notation "Sede Decisyon Latina@piazzale nervi n.100, latina”.

The markers can also inherit the color of the metric, which is especially useful if different colors are used, depending on positive/negative thresholds:

* The color inherited by the metrics is the one defined as foreground.

Each marker is associated with a _tooltip_ that indicates the geographical location and the value of the first metric, while the other metrics are listed in a window associated with the marker. A drill-through can also be enabled in this window, similar to the one in the reports:

* On the metrics window, enable the _**Details>>**_ item to open a new page that contains the object associated with the drill-through (a report, Page, URL, etc.); this can be made to be dependent on the region that requested it.

![](<../../.gitbook/assets/1 (24).png>)

Google Maps has zoom, move, view type, overview and search tools.

All the map features can be customized using the specific properties of this component.

#### Google Map activation

Before being able to use _Google Maps_, the key to use the service needs to be requested, the terms and conditions of which are set by Google.

In the Tools property (_**Tools>>Properties**_):

* **googleMapKey** (_GoogleMap_ group) enter the URL code that contains the _Google Maps_ service activation key.

**Note:** _Google Maps provides different activation keys based on whether the HTTP or HTTPS protocol is used_.

The maps cannot be used in html pages displayed off-line.

#### Specific Map properties

The specific properties of the map relate to the customization of the same map (_Map_ group), and also to the configuration of a drill-through recalled by the marker window (_drill-through group_).

Map group properties are:

* _**type**_ type of initial view of the map, selected among:
  * _Map_ road map (default)
  * _Satellite_ satellite image
  * _Hybrid_ hybrid with both modes
  * _Terrain_ displays the orographic trend of the ground
* _**wiDSh height**_ wiDSh and height of the map
* _**zoom**_ zoom level for viewing the map (default is 2)
* _**address**_ place around which the map is centered: it is a blank field, the text inserted is interpreted by Google Maps
* _**typeControl**_ enables the map type panel (default disabled); if enabled, the following is defined:
  * _**typeControlPosition**_ position of the map type panel (default _Top\_Right_).
* _**overviewControl**_ enables the overview window (default disabled).
* _**scaleControl**_ enables the scale panel (default disabled).
* **streetViewControl** enables the street View panel, this property enables
  * **streetViewControlPosition** position of the street view control in the map.
* _**panZoomControl**_ for the zoom panel: _Large, Small, Only\_Zoom._ The _**blank**_ item is selected by default, to indicate the zoom is disabled. If it is not disabled, the following is defined:
  * _**panZoomControlPosition**_ for the zoom panel (default _Bottom\_Right_).
* _**searchControl**_ enables search window (default disabled)
* _**eventMarker**_ event to enable the Default marker information window:
* _**metrics-tab**_ enables the information window, containing the values of the metrics of the associated report (default disabled)
* _**cellFormatAssociated**_ Enables the color of the marker icon to the formatting of the metric (default disabled)

![](<../../.gitbook/assets/2 (23).png>)

The properties of the **drill-through** group are similar to those of the report, except for the property which enables the opening of the drill-through in the same page (**open-in-same-window**).

The page defined for the drill-through is displayed in a new window, opened from the _**Detail>>**_ (in the information window associated with the marker).![](<../../.gitbook/assets/3 (23).png>)![](<../../.gitbook/assets/4 (23).png>)

### Indicator Component

An indicator is published using the Indicator component, which is always in the Presentation _group._ Indicators are defined in advance with the **Indicator Designer module.** Also the indicator may share the datamart of the report presentation components and configure the access to the associated report. In the Form group, the _**form-object-ID**_ property which specifies the identification of the component.

Publishing an indicator specifically involves selecting the graphic display.

DAC has **STATIC** and **FLASH** TYPE graphic **forms.**

The _**static type**_ styles are those reported in the following figure.

![](<../../.gitbook/assets/5 (22).png>)

![](<../../.gitbook/assets/6 (19).png>)

Interesting characteristics, for the graphic choice, are those concerning the presence or absence of threshold values and the position of the metric value compared to them:

* the values of all the thresholds (on details and on zone shifts) and the position of the KPI metric value (such as analog types)
* only the thresholds of the details and the position of the KPI metric value (such as the circle type)
* only the thresholds of thresholds without a position of the KPI metric value, but only belonging to one of the three zones (such as shape types)
* thresholds are not valued, but the position of the KPI metric is present (such as for arrow types)
* no values are present for the thresholds or the KPI metric position, but only the pertinence to a zone (such as the led and stop light types)

While the styles of the _**Flash type indicators**_ are much more versatile than the static ones and allow a greater customization.

The styles available are as follows:

* [Angular Gauge](page-widget.md#angular-gauge-indicator)
* [Bulb Gauge](page-widget.md#bulb-gauge-indicator)
* [Bullet Horizontal Gauge and Bullet Vertical Gauge](/broken/pages/-MgjDmy7ZG1x9SPLST_g#bullet-horizontal-gauge-and-bullet-vertical-gauge-indicators)
* [Cylinder Gauge](/broken/pages/-MgjDmy7ZG1x9SPLST_g#led-horizontal-gauge-and-led-vertical-gauge-indicators)
* [Led Horizontal Gauge and Led Vertical Gauge](page-widget.md#led-horizontal-gauge-and-led-vertical-gauge-indicators)
* [Linear gauge](page-widget.md#linear-gauge-indicator)
* [Thermometer Gauge](page-widget.md#thermometer-gauge-indicator)

When the _Indicator_ component is added to the Page Designer, the indicator is associated in the _**indicatorAssociated**_ property (_Main_ group).

An indicator published on a Page is made interactive only by passing parameters that filter its value (see the example on the dependence of indicators on form objects).

The specific properties of the Indicator _object_ allow it to be further customized by specifying (_ObjectStyle_ group):

* _**indicatorSize**_ the size of the indicator
* _**arrow-palette**_ the colors of the arrows are defined, which will be more than one in the case of multi-row indicator

The legend is enabled for multi-row indicators with the _**showLegend**_ property (_Legend_ group), where the following can be set:

* _**legendBackground**_ the background color
* _**legendFontColor, legendFontSize**_ the color and the dimension of the font used
* _**legendBorderColor border**_ color of the pane
* _**multiRowLegendPosition**_ the position of the legend (TOP, DOWN, LEFT, RIGHT) in the case of a _multi-row indicator_

For NON multi-row indicators, displaying the **value of the KPI** **metric** can be enabled through the showValue property (_Value_ group), which enables the following:

* _**valueFontSize,**_ dimension
* _**valueFontStyle, valueFontWeight**_ italic or bold style
* _**valueBackgroundColor,**_ valueForegroundColor background and foreground colors

Another property belonging to the _Value_ group is _**transparency**_, to make the legend transparent when required. By default the property is not active.

#### Common properties among the flash indicators

The common properties relate to the font in the indicator scale, the background color and border (_ChartLayout_ property group):

* _**font-color, font-size**_ set the color and size of the font, displayed in the indicator scale.
* _**use-gradient**_ applies the gradient to the background of the indicator, set in the following properties:
* _**bg-gradient-start**_ and _**bg-gradient-end**_**:** start and end color of the gradient
* _**background-color**_ background color, enabled only if the gradient is not used (&#x69;_**.**_&#x65;. _**use**-gradient_ disabled)
* _**show-border**_ enables the border of the object indicator, which is set in the following properties:
* _**border-color**_ and _**border-thickness**_ color and thickness of the border.
* _**show-shadow**_ shows the shadow of the graph. (_not visible for the Bubble Gauge indicator_)
* _**show-gauge-border enables**_ the indicator border, which is set in the following properties:
* _**border-color, border-thickness**_ and _**border-alpha**_ color, thickness and transparency of the indicator border. Transparency has values from 0 to 100.

Border indicator properties are absent for Cylinder Gauge, Bullet Horizontal Gauge and Bullet Vertical Gauge

#### Example: Gradient, Object Border and Indicator Border

![](<../../.gitbook/assets/image (161).png>)

_Indicator No. 1: the gradient was enabled (use-gradient) and using the bg-gradient-start, bg-gradient, -end property, the color was defined for the background of the indicator (from blue to yellow)._

_Indicator No. 2: the object border was enabled (show-border) and using the border-color, border-thickness property, the color and thickness were defined for the indicator container._

_Indicator No. 3: the indicator border was enabled (show-gauge-border) and using the border-color, border-, thickness and border-alpha property, the color, thickness and transparency for the indicator outline were defined._

Other common properties customize the scale of values for the indicator (ChartTickMarks _group_ ), which however are not enabled for the _Bulb Gauge indicator_ (except the one on the suffix).

The properties for the scale are:

* _**show-tick-marks**_ enables the display of the indicator scale
* _**show-tick-values**_ enables the display of the values of the indicator scale
* _**number suffix**_ text used as a suffix in the scale values (also used for _Bulb Gauge_ type indicators)
* _**major-tm-number**_ sets how many sections to divide the scale into (level 1 division)
* _**minor-tm-number**_ sets level 2 division
* _**tick-mark-distance**_ sets distance between the scale and indicator
* _**tick-value-step**_ every n steps, the values are to be displayed on the level 1 division
* _**tick-value-**_&#x64;istance distance between the values and scale
* **place-values-inside** (_ChartTickMarks_ group) positioning of values within indicator; property only enabled for indicators (_Angular, Linear Gauge_)
* **ticks-below-gauge (**_ChartTickMarks_ group) positioning of values and scale below the indicator; property only enabled for indicators _(Linear Gauge, Led Horizontal)_
* **ticks-on-right** (_ChartTickMarks_ grou&#x70;**)** positioning of values and scale to the right of the indicator (default); property only enabled for indicators (_Thermometer Gauge,_ _Cylinder,_ _Bullet Vertical, Led Vertical_
* **ticks-below-graph** (_ChartTickMarks_ group) shows the signs and their values below the graph (_Bullet Horizontal Gauge_**)**

The following example clarifies the use of this group of properties.

Example: ChartTickMarks properties

![](<../../.gitbook/assets/8 (17).png>)

_The following properties were set in the indicator in the figure:_

* _Display indicator scale (show-tick-marks):) :_
* _Display scale values (show-tick-values)_
* _A suffix (Sales) to the values of the scale (number-suffix)_
* _Division of level 1 (large ticks) set to 10 (major-tm-number)_
* _Division of level 2 (small ticks) set to 10 (minor-tm-number)._

#### Example: ChartTickMarks Properties

![](<../../.gitbook/assets/9 (17).png>)

_By setting the tick-value-step to 2, the values of the division of level 1 are shown every 2 ticks. However, by setting the tick-value-distance to 20, the values are offset from the indicator by 20 pixels._

#### Angular Gauge Indicator

This indicator type shows the values in angular mode, on circles, semi-circles, donuts, etc.

Customization is therefore applied to the angle, the radius and the display of the values within or outside the scale.

Angles can have the following properties (_ChartLayout group_):

* _**gauge-start-angle**_ start angle, where the beginning of the indicator scale starts (start value). The permitted values are from 0 to 360.
* _**gauge-end-angle**_ end angle, for the maximum value of the indicator scale (end value). The permitted values are from 0 to 360.

#### Example: Gauge-Start-Angle and Gauge-End-Angle![](<../../.gitbook/assets/10 (18).png>)![](<../../.gitbook/assets/11 (17).png>)![](<../../.gitbook/assets/12 (15).png>)![](<../../.gitbook/assets/13 (16).png>)

_In the example above, some ways of displaying the indicator are shown. The dotted surrounding circle only serves to graphically show how the degrees set by the gauge-start-angle and gauge-end-angle properties were calculated on the plane._

_For the first indicator, 270° was set as the start angle (gauge-start-angle) and the end angle (gauge-end-angle) was set to 0°._

_For the second indicator, 130° was set as the start angle and the end angle was set to 20°._

_The third has a start angle of 360° and an end angle of 0°. This way the indicator is round._

_The fourth indicator has a start angle of 90° and an end angle of 0°._

The properties for the radius are (_ChartLayout group_):

* _**gauge-inner-radius and**_ gaug&#x65;**-outer-radius inner and** outer radius, conditioned by the property relative to the size of the indicator

#### Step 2: Inner and outer radius

![](<../../.gitbook/assets/14 (11).png>)

_A donut indicator is shown in the figure. This representation is given by setting the gauge-inner-radius and gauge-outer-radius properties._

Other properties for the scale and color of the indicator are:

* **place-values-**&#x69;nside (_ChartTickMarks_ group) positioning of values within indicator

**Note:** Values are positioned along the inner radius (gaug&#x65;**-**_**inner-radius)**_ and also depend on the distance from the scale (_**tick-mark-distance**_).

* **gauge-fill-**&#x72;atio (_ChartLayout_ group) glass color effect

#### Step 3: Gauge-fill-ratio

![](<../../.gitbook/assets/15 (11).png>)

_The gauge-fill ratio property sets the softening effect within the indicator._

The properties of the _ChartSpecifics_ group allow the indicator pointers to be customized.

* _**dial-show-border enables**_ the border of the dial, which is set in the following properties:
  * _**dial-border-**_, _**color, border-dial-**_&#x74;hickness and _**dial-border**_-alpha the color, thickness and transparency of the dial border
* _**dial-radius**_**:**: sets the length of the dial
* _**dial-base-wiDSh and**_ dia&#x6C;_**-top-wiDSh wiDSh of**_ the initial end (base) and final end (tip) of the dial

**Note:** _The Angular Gauge style is a graphically complex style, with properties that may affect one another. The default values set are those which were identified as ideal for the representation most frequently displayed. If you encounter problems displaying the values of the indicator, we advise increasing the_ _**wiDSh**_ _size of the container (ContainerSize group), or setting the properties of the_ _**gauge-inner-radiu**s and_ _**gauge-outer-radius**_ _graph (ChartLayout group)._

#### Bulb Gauge Indicator

The _**Bulb**_ **Gauge** indicator is a LED-shaped indicator with animation. Its specific properties are:

* _**gauge-radius**_ (ChartLayout _group_) radius
* _**gauge-fill-alpha**_ (ChartLayout _group_) transparency for the bulb (maximum values 0-100)
* _**3**_**D** (ChartSpecifics _group_) enables displaying the indicator in 3D
* **place-values-**&#x69;nside (_ChartTickMarks_ group) positioning of values within indicator

Example: Bulb Gouge Indicator

![](<../../.gitbook/assets/16 (11).png>)

_The figure shows two indicators; in the first, 3D property is disabled, so the indicator is flat. 3D property is enabled for the second, so there is a three-dimensional effect._

#### Bullet Horizontal Gauge and Bullet Vertical Gauge Indicators

_Bullet_ type indicators show the value using a bar or dot inside the indicator, which is rectangular horizontal or rectangular vertical.

![](<../../.gitbook/assets/17 (10).png>)

The properties allow you to set how the value is displayed (with a bar or dot) and customize the color and border. The specific properties are (_ChartSpecifics_ group):

* _**plot-as-dot**_ displays value as a bar (property disabled) or as a dot (property enabled)
* _**plot-fill-**_&#x63;olor and _**plot-fill-alpha**_ color and transparency of the bar/dot fill
* _**plot-fill-**_&#x70;ercent scale bar/dot scale wiDSh (percentage value)
* _**show-plot-border**_**:** enables the _**border**_ of the bar or do&#x74;_**, representing**_ the value of the indicator, which is set in the following properties:
* _**border-color, border-thickness and**_ borde&#x72;_**-alpha color**_ , thickness and transparency of the border
* _**show-color-range-border enables the**_ border of _**the three color ranges,**_ which is set in the following properties:
* _**border-color, border-thickness**_ and _**border-alpha**_ border color, thickness and transparency of the color range

**Note:** If configured in multi-row, the Bullet Horizontal/Vertical Gauge indicator only shows the value of an element. Therefore we advise only using this indicator for single row representation.

Example: Bullet Horizontal Gauge

![](<../../.gitbook/assets/18 (9).png>)

_The indicator was customized as follows:_

*
  * _plot-as-dot property enabled for the left indicator and disabled for the right one_
  * _dot/bar fill color purple (plot-fill-color)._
  * _border of dot/bar (show-plot-border) in a light purple color (border-color)_
  * _border of the three ranges in blue (border-color) with thickness equal to 2 (border-thickness)_

#### Cylinder Gauge Indicators

A **Cylinder Gauge** indicator shows a cylinder, whose fill level is the value of the indicator.

![](<../../.gitbook/assets/19 (7).png>)

The specific properties are (ChartSpecifics _group_):

* _**cyl-radius radius**_ of the cylinder
* _**cyl-height height**_ of the cylinder
* _**automatic-fill-color**_ enables the automatic setting of the cylinder fill color, with the one for the metric. If the property is disabled, the following is enabled:
* **cyl-fill-color** for the fill color of the cylinder

Example: Automatic-fill-color

![](<../../.gitbook/assets/20 (8).png>)

_The cylinder fill color in this example was customized by setting the following properties:_

_the automatic-fill-color property was disabled and the system automatically enables the sub-property_

_cyl-fill-color from which the desired color can be selected._

#### LED Horizontal Gauge and LED Vertical Gauge Indicators

LED horizontal and vertical indicators represent the value of the indicator by colored fluorescent bars (LED) from the start of the scale, up to the value to be reached.

![](<../../.gitbook/assets/21 (5).png>)

The specific properties are (_ChartSpecifics group_):

* **led-size:** size of each LED bar
* **led-gap** distance between two LED bars
* **gauge-fill-**&#x63;olor background fill color of the indicator
* **use-same-fill-bgcolor** all non-active LED blocks use the same background color.

Example: Chart Specifics

![](<../../.gitbook/assets/22 (4).png>)

_The indicator in the figure was customized by setting the properties:_

* _led-size wiDSh of LED,_
* _led-gap: distance between the LEDs_
* _gauge-fill-color: background of the indicator._

#### Linear Gauge indicator

This type of indicator represents the values using a pointer that can be customized.

![](<../../.gitbook/assets/23 (4).png>)

* _**pointer-on-top**_ (_ChartSpecifics_ group) pointer on top
* _**pointer-radius**_ and _**pointer-sides:**_ (ChartSpecifics group) radius and number of angles of the pointer
* _**pointer-show-border (**_&#x43;hartSpecifics group) enables the display of the pointer border, by setting
* _**pointer-border-color, pointer-border-thickness**_ and pointe&#x72;_**-border-alpha color**_ , thickness and transparency of the border
* _**round-radius**_ (_ChartLayout_ group) the rounding of the angles (in pixels) of the indicator
* **gauge-fill-ratio** (_ChartLayout_ group) _glass_ color effect

Example: Chart Specifics

![](<../../.gitbook/assets/24 (4).png>)

_If the point-on-top property is selected, the pointers are displayed on top, while if it is not selected, they are displayed at the bottom of the indicator._

_Point-radius and point-side properties are respectively set to 15 for the size of the pointer and 4 angles were defined to display it in rhomboidal shape._

#### Thermometer Gauge Indicator

The thermometer indicator shows the value in a bulb.

The following properties can be customized:

* **thm-bulb-radius** (_ChartSpecifics_ group) radius of the thermometer bulb
* **thm-height** (_ChartSpecifics_ group) height of the thermometer
* **automatic-fill-color** (_ChartSpecifics_ group) enables the automatic setting of the fill color of the bulb, with the one of the metric. If the property is disabled, the following is enabled:
* **cyl-fill-color** for the fill color of the bulb
* **gauge-fill-**&#x61;lpha (_ChartLayout_ group) bulb transparency

![](<../../.gitbook/assets/25 (4).png>)

### Tag Cloud

The **Tag Cloud** is a visual representation of the values in a report.

This list is generally presented either alphabetically or randomly, with the special feature of presenting the most important words in a bigger font size. Therefore, we are talking about a weighted list.

The weight of the labels (or TAGs) depends on the frequency of use of the data you are reading. The larger the font, the higher the frequency of the key word.

![](<../../.gitbook/assets/26 (2).png>)

The Tag **Cloud component** is contained in the Presentation folder.

The properties relating to the choice of the data to be represented are grouped in _cloud data Tag_ (_Object folder_):

* _**keywordReportItem**_: keywordReportItem: metric or level from which to extract the key words to be represented in Tag Cloud
* _**occurrencesReportItem**_**:** metric or level to calculate the frequency
* _**descriptionsReportItem**_**:** metric or level from which to extract the description which will be shown as the tooltip for the key word

The properties to configure the layout are grouped in _cloud style Tag_ (_Object folder_):

* _**cloudBackground:**_ background color
* _**cloudMinimumColor**_**&#x20;and&#x20;**_**cloudMaximumColor**_: color of the key word with minimum and maximum value, respectively
* **cloudMinimumFontSize and cloudMaximumFontSize**: size of the key words with minimum and maximum value, respectively
* _**typology**_**:** type of graphic display of the component:
* Cloud, with the values shown in a random manner
* List with the values presented in order of dimension
* Sphere graphically arranging the values in a circular manner

#### Cloud Type

The _**Cloud**_ type is the most classic representation. The values are shown in a random manner inside the window that contains them.

This mode is activated through the property

* _**typology**_**:** by selecting _cloud_

Selecting this type enables the following:

* _**randomKeywordPosition**_ (_Tag cloud style_ group): specifies whether to display the values randomly. In other words, every time the page is refreshed the values will assume a different position inside the window containing them. If the property is not enabled, these will always be shown in the same position regardless of refreshing the object.

#### List Typology

Displaying the list form allows three types of sorting for values contained in the Cloud.

This mode is activated through the

* _**typology**_**:** by selecting _list_

Selecting this type enables the following (Tag _cloud style group_):

* _**sort**_: defines the value sorting type:
* _NONE_ casual (default)
* _NAME_ in alphabetical order
* _VALUE_ with order that depends on the weight of the value

Select NAME and VALUE to enable the following

*
  * _**order**_ to set the sorting type (_Ascendant, Descendent,_ _**Random)**_

Below are some examples of setting the properties for the list type (_**typology**_: _list_)

#### Sphere Typology

The Sphere typology displays the data by arranging values graphically in a circular fashion.

This mode is activated through the

* _**typology**_**:** by selecting _sphere_

Selecting this typology enables the following (Tag _cloud style group_):

*
  * _**power radius:**_ sets the _power of the_ radius of the sphere (values admitted between 1 and 40)

#### Example of a Tag Cloud

Step 1: Creating Pages

![](<../../.gitbook/assets/27 (2).png>)

_Create a new Page containing the Styled Selector and Tag Cloud components._

* _Styled Selector publishes a selector of the project phases (in level-associated select the Ds\_Project level)_
* _Tag Cloud presents the activities of each project phase_
* _reportAssociated: associate a report with the Style Selector level in page-by (Ds\_Project) and the activities associated with each phase in rows. The metric calculates the number of tasks for each activity._

_In the report a DS is activated towards a detail Page on the distribution of the resources of the tasks relating to the selected activity._

* _keywordReportitem: as key word for the Cloud, select the description of the activity (Ds\_activity level)_
* _occurrencesReportItem: to calculate the frequency, select the metric which calculates the number of the Tasks_
* _descriptionsReportItem: the same metric is chosen to show the value associated with the key word_

Step 2: Page Preview

![](<../../.gitbook/assets/image (166).png>)

_The figure shows the Page preview._

_In the upper part, the Styled Selector is shown where a different project phase is specified for each TAB. Selecting one of these will let you filter the respective activities._

_Note how the different activities, based on the number of tasks, assume a different size. It is possible to check the data by consulting the associated report (on the right)._

Step 3: Viewing Page with DS

![](<../../.gitbook/assets/29 (3).png>)

_This step shows the DS associated with the report:_

* _Select a project (CONCEPTUAL SCHEME)_
* _Select an activity Verify ER Quality. This activity has a number of Tasks equal to 24._
* _Access the detailed Page through DS._
* _The data inside the Page are filtered by the selected activity. Note that the total of the tasks in the report corresponds to those displayed in the Cloud._

## Form

The entry components available are:

* [Text field](page-widget.md#text-field) of text type, such as simple strings, numbers, dates or codes
* [Text area](page-widget.md#text-area) to enter the subject text



The values of the components are the result of a query, executed either on the connected database or any data source defined in the system section. The query is defined in the _Query_ group, where:

* _**custom-datasource enables/**_&#x64;isables the selection of a data source other than the one of the application; selecting this property enables the
  * _**datasource**_ to select the DB where the query is to be executed.
* &#x20;_**sql-formula**_ where the query can be set based on the methods described in the Appendix.

The following is defined for this type of object:

* _**Param base name**_ the name of the component which will be used as the parameter in the Page
* _**disabled**_ enable/disable component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered.![](<../../.gitbook/assets/30 (3).png>)

* characteristics of the text that appears next to the object:
  * _**formFontSize**_ font size (the height of the text field is adjusted to that of the font, chosen in this property)
  * _**formForegroundColor**_ font color
  * _**formBackGroundColor**_ background color
* _**textField effect**_ type of layout effect:
* _(none):_ no effect is applied
* _page default:_ inherits the effect [set at page level](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Stile_di_default) (reported between parenthesis)
* _shadow_: shading
* _rounded:_ rounding effect
* _gradient:_ effect with gradient

![](<../../.gitbook/assets/31 (4).png>)

**Note:** _The shadow and rounded effect are not supported by the IE8_ _browser._

_In addition the shadow effect is not displayed correctly (the right external side is missing) if the auto-expand property is disabled. This is the property that automatically expands the length of the component._

* _**placeholder**_ enters display only text when the field is empty (see figure below); as soon as the user clicks inside the field, the text is eliminated.

![](<../../.gitbook/assets/32 (2).png>)

### Text Area

The Text Area component is a text field consisting of multiple rows and columns, where you can enter unlimited free text.

The specific properties of the component are (Form _Group_):

* _**enable-validation**_ enables the following properties for validation through _Pattern_
* **objectInputPattern** Lets you define a text format which respects a regular expression

_For example A{3}\[0-9]{8} defines the rule that the text entered is to contain the letter A repeated 3 times, followed by an 8-digit numerical code: a valid code can be AAA12345678._

* **objectInputPatternError:** Specifies the message to be shown in the case of an invalid code. The error messages of the PATTERN support the multilanguage (see similar property for Text Filed)

The height of the Text Area is a few pixels lower than the [height defined in the container](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Dimensionamento_componente_\(Contain)

**Note:** _The border turns yellow when writing._

![](<../../.gitbook/assets/33 (2).png>)

### Text Field

The Text Field component is a text field on a single line, where you can type text that matches the rules set up on the component, as explained later in this manual.

The specific properties of the component are (Forms _Group_):

* _**txtMaxLength**_ maximum length of the text (while the wiDSh is defined by the _wiDSh_ and _height_ property of the _ContainerStyle_)
* **text-align:** alignment of the text inside the Text Field. The values available are: left(default), center, right.

![](<../../.gitbook/assets/34 (3).png>)

* _**objectInputType**_ field format:
* _STRING_ simple text
* _NUMBER_ numeric text
* _DATE_ date format;
* _PATTERN_ text on a regular expression

&#x20;**Note:** _The border turns yellow when writing._

![](<../../.gitbook/assets/35 (3).png>)

#### Text Field of the DATE type

A Text Field of the date type is defined with the property (_Form_ group):

* _**objectInputType**_ with selection of the _**DATE item**_

The field configured in this way will show, on DAC, a calendar for the date selection.

![](<../../.gitbook/assets/36 (2).png>)

This selection enables:

* _**inputDateFormat**_, date field format, defined via a configuration pop-up

The format of the date field is the one admitted for the parameter associated with the text field, used on any filter.

This format must also be respected in case there is a field population through loading queries.

* **selection-start-date** and **selection-end-date**: establish the time range within which the date may be set.

These properties can also be managed by using a parameter and must comply with the format specified by the _inputDateFormat_ property. In this case the date range which may be selected will be conditioned by the value assumed by the parameter.

Example: DATE type Text Field with date range![](<../../.gitbook/assets/37 (2).png>)![](<../../.gitbook/assets/38 (2).png>)

_The days in the calendar of the Date text field are managed by the values entered in the Start Date and End Date text fields_

#### Text Field of the PATTERN type

A Text Field of the PATTERN type is defined with the property (_Form_ group):

* _**objectInputType**_ with selection of the _**PATTERN**_ _item_

In this case the field is subject to a validity check of the entered text, which must respect a specific format. This selection enables:

* _**objectInputPattern**_ regular expression that must respect the field

&#x20;_For example A{3}\[0-9]{8} defines the rule that the text entered is to contain the letter A repeated 3 times, followed by an 8-digit numerical code: a valid code can be AAA12345678._

* _**objectInputPatternError**_ customized message in case an invalid code is entered. An error pop-up is opened by default, which reports the text validity rule.

The error messages of the PATTERN support the Multilanguage.

By entering the ID of a label in the ML\_LANGUAGE\_STRINGS table (ID\_STRING field) in the property mentioned above, and having it precede by the sequence of characters "**###%%%**", the system will display, DAC, the message associated with the specified label translated according to the language of the connected user.

![](<../../.gitbook/assets/39 (3).png>)

The selection of values, which can be used to filter Page components, is defined using the following components:

* [PageBy Selector](page-widget.md#pageby-selector) for selections on a list via a rather similar object to the page-bys of the reports
* [StyledSelector](page-widget.md#styled-selector) for selections on checklist type lists through customized command keys

Other selectors are the page-by of the crosstabs and images.

### Styled Selector

The **Styled** Selector offers an object that has selector characteristics, where you can associate an attractive graphic style.

The list of values may be loaded _through_ a dimensional level (OLAP) or through a QUERY.

Different styles are available to present the elements of the list, when set the property:

* **style** (_Style_ _Settings_ group)
  * [Tab Menu](page-widget.md#tab-menu-style)
  * [Tooltip Selector](page-widget.md#tooltip-selector-style)
  * [List Selector](page-widget.md#list-selector-style)
  * [Radio Button](page-widget.md#radio-button-style)
  * [Table Selector](page-widget.md#table-selector-style)
  * [Checkbox](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Stile_Checkbox) (default)
  * [Toggle Button](page-widget.md#toggle-button-style)

For each of these, specific customization properties are available. Those present for almost all the components are:

* **show-label-noSelection**

enables the management of the absence **of a selection**, defined in the property:

*
  * **custom-label-noSelection** text to be displayed in case the selection of a value has not be made (default “_No selection_”)

The _Check List_ and _Table Selector_ styles do not manage the selection absence, for which these properties are not enabled

* **object-transparency:** sets the transparent background for the elements which make up the object, except for the selected elements or those on which the mouse is positioned; in these two cases the background of the elements is the same as the one for the selected theme.

The _Check List_ and _Radio Button_ styles are always transparent and do not have this property enabled

**Note:** _The transparency of the Styled Selector widget is not supported on IE8._

* **disabled** Enables/disables the component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered (disabled for the value entry components).

An application example is shown at the end of this section.

#### Loading values from dimensional level (OLAP)

Selecting list values from a dimensional level is set using this property:

* **load-type** (_Form_) group by selecting _\<Olap>_

this selection enables the _Olap_ group properties:

* **level-associated**

selecting the dimensional level to load the values in the list.

After selecting the level, in the properties **Filter** (_OLAP_ group) ONLY the hierarchies levels will be presented, in which that level is present.

**Note:** _The param base name property is not editable in this case._

#### Loading values from QUERY

Selecting list values from a selection query is set through the property:

* **load-type** (_Form_) group by selecting _< SQL Query >_ which enables the following
* **exportType**

type of exported data from the query (_NUMBER_ or _STRING_)

Selecting _< Query >_ enables the properties of the group with the same name:

* _**custom-datasource**_ in the case of queries on data sources different from the one for the process
* _**sql-formula**_ where the query is defined.

#### Tab Menu Style

The **Tabbed&#x20;**_**Menu**_ style displays a menu, where each piece of data is entered in a special TAB.

This type of menu is single-selection (one item at a time), and you can enable the item for no selection. You can also customize the orientation.

![](<../../.gitbook/assets/40 (3).png>)

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _Tab Menu_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **display orientation** orientation (default _on top_)

#### Tooltip Selector Style

The **Tooltip Selector style** displays the data available in a tooltip, open to the selection of a specific box, where the item selected in a previous phase is highlighted (see figure below).

![](<../../.gitbook/assets/41 (3).png>)

Data is selected by single element, which is shown on the box.

Set this style using the property:

* **style** ( _Style Settings_ group) by selecting _Tooltip Selector_

#### List Selector Style

The _List Selector_ style displays a menu opened by selecting the arrows placed to the side. You can select a value by ticking the checkbox; multiple selection and enabling of the element search in the value list are available. The other features are shown in the figure.

![](<../../.gitbook/assets/42 (3).png>)

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _List Selector_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **multi-selection** enables the multiple selection (disabled by default)
* **showFilter** it shows a text filter

#### Radio Button Style

The _**Radio Button**_ style displays a list that can be selected via radio button.

The list is single-selection (one element at a time), and you can enable the item for no selection. You can also customize the orientation.

![](<../../.gitbook/assets/43 (2).png>)

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _Radio Button_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

*
  * **formAlign** sets the type of alignment (VERTICAL or HORIZONTAL)

#### Table Selector Style

The _**Table Selector**_ style allows you to have two adjacent lists, one containing the data available and one containing the selected data.

![](<../../.gitbook/assets/44 (2).png>)

Data selection occurs:

* by single element

Clicking on the element to be selected moves it to the list of the selected ones.

Clicking on the selected elements moves it to the list of the available ones.

The ![](<../../.gitbook/assets/45 (3).png>) button opens a field for the rapid search of the element to be selected.

* On all the elements

Clicking the ![](<../../.gitbook/assets/46 (2).png>) button moves all the elements to be selected into the list of those selected.

Clicking the ![](<../../.gitbook/assets/47 (2).png>) button puts all the selected elements back in the list of the available ones.

Data is selected by single element. You can search the data in the list, and you can transfer data from one section to another in massive or single mode.

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _Table Selector_

#### Checkbox Style

The _**Checkbox**_ style displays a list that can be selected through a checkbox. The list is single-selection, and you can enable the item for no selection. You can also customize the orientation.

![](<../../.gitbook/assets/48 (3).png>)

Set this style using the property:

* **style** ( _Style Settings_ group) by selecting _Checkbox_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **formAlign** sets the type of alignment (VERTICAL or HORIZONTAL)

#### Toggle Button style

The _Toggle Button_ style displays a menu, where each value is entered in a special TAB and you can also customize the orientation.

![](<../../.gitbook/assets/49 (2).png>)

Set this style using the property:

* **style** ( _Style Settings_ group) by selecting _Toggle Button_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **formAlign** sets the type of alignment (VERTICAL or HORIZONTAL)
* **disabled** Enables/disables the component (enabled by default)
* **multi-selection** enables the multiple selection (disabled by default)

### PageBy Selector

A particularly useful object is the _**PageBy Selector**_, of the same type as the drop-down menu, but much easier to define and more flexible to use. For all intents and purposes, the pageby selector corresponds to the page-by of a report as regards its definition and features, because most of the properties of the Page-bys of the reports are actually present in the selector.

The _**PageBy Selector**_ object, belonging to the Form _group_ of the Page Designer _components_, lets you build a selector starting from one or more dimensional levels.

The selected levels will be displayed as real page-bys and will behave in the same way as the page-bys defined in a report.

The levels defined in this object are available as filter parameters for the other objects contained in the Page.

The **specific properties** of the object are:

* **levels-associated** (_Main_ group)

to select the dimensional levels to be used as selectors.

A window opens listing the levels of each application cube; use the double arrow keys to move those to be associated with the object.

![SNAGHTML7ee2d9](<../../.gitbook/assets/50 (2).png>)

* **alias-level** (_Main_ group)

associates the aliases to the dimensional levels selected in the previous property.

**default-select-type** and **selection-type** (_Page-by group_)

similar to those of the reports for the selection method where you set the selection type, among single, single with research or multiple with research; in _default-select-type_ set the default one to be assigned to all the elements in Page-By, while in _selection-type_ change the default for some of these elements.

* _**opening-selection**_ (_Page-by_ group)

same as the one of the report, for the positioning of the values in the list.

* _**num-elements-row (web)**_, _**selector-wiDSh (web)**_ and _**show-initializer (web)**_ (_Page-by_ group)

similar to those of the report for the layout on DAC, where _num-elements-row (web)_ indicates the number of page-by to be displayed on the same row before using the enter button; _selector-wiDSh (web)_ the wiDSh of the page-bys; _show-initializer (web)_ enables the reset button of the page-bys to the opening values of the report.

* _**total-visibility**_ and _**levels**_ (_Page-by_ group)

similar to those of the report for the page-by totals, where in _total-visibility_ you set the presence of the item \[Total] for all, no or just some of the levels, (chosen in _levels_)

**Below is an example of configuring the PageBy Selector object**

#### Step 1: PageBy Selector

![](<../../.gitbook/assets/51 (2).png>)

_A Page was created in the example where the PageBy Selector component is configured._

_From the levels-associated property, the levels YEAR and MONTH are selected._

_These will become the selectors that filter all the objects on the page, which in turn contain the same levels._

_Aliases were configured for the levels: ‘Select Year’ for YEAR and ‘Select Month’ for MONTH._

_The selection types for page-bys are multiple for the Month level and single for the Year level (set in selection-type)._

#### Step 2: PageBy Selector

![](<../../.gitbook/assets/52 (2).png>)

_The figure shows how the Page created in the previous step is displayed. Note that the levels defined in the PageBy Selector object are displayed as page by. The selection is single for the year and multiple for the month and the report and graph below are valued based on the selection._

### File Selector (file selection)

The File Selector component allows a file to be selected by the Client, then allows it to be uploaded and associated with a setting used in the Page page.

![](<../../.gitbook/assets/53 (3).png>)

The file can be loaded in two ways:

* **Easy**, for files uploading, where you specify the allowed types.
* **Excel Integration**, to load an Excel file, which will then be uploaded into a database table. The component that transfers the file data into the table is the Execute button, Excel Integration type.

The File Selector component is available under the _Form_ group. The specific properties are as follows:

* **Upload-type** (group _Form_), type of upload:
  * EXCEL\_INTEGRATION to upload an Excel file, to be integrated into the data table.

Files with the "xlsx" extension are permitted (mime-type: _application/vnd.openxmlformats-officedocument.spreadsheetml.sheet_).

*
  * SIMPLE\_UPLOAD to load a generic file. This selection enables the following properties:

**mime-type,** for the selection of the mime-type allowed for the Files to be uploaded.

Several mime-types can be selected and, if none are selected, the system will allow any type of file (default).

![](<../../.gitbook/assets/54 (2).png>)

It is possible to add the mime-type if not present in the predefined list. In order to add a new mime-type, it is necessary to enter the new mime-type using the list of standard mime-types ([http://www.iana.org/assignments/media-types/media-types.xhtml](http://www.iana.org/assignments/media-types/media-types.xhtml)).

* **maxUploadFileSize (MB)** (_Form_ group), maximum size permitted for the file to be uploaded (default 50 MB, maximum value 200 MB).

The file uploaded with the File Selector by the user is entered in the repository, thereby creating a new resource.

The system generates two settings associated with this resource:

* The first has a name that coincides with the name assigned to the property _param base name_ for the componen&#x74;_._

This type of setting will contain the **identification of the resources associated with the file** uploaded by the user.

* The second has a name that coincides with the first, to which "\_NAME" is added and which will include the **name of the file** uploaded by the user.

![](<../../.gitbook/assets/55 (3).png>)

These settings can be used in the Page page. For the SAMPLE UPLOAD type, the setting may be used:

* in an Execute button type of Query, referencing the setting in the query

_One example is uploading the image resources to be associated with a size: it is assumed that the uploaded images correspond to a product. The entry query may be set with respect to the product, resources, or image type._

For the EXCEL INTEGRATION type, the setting is used directly in the following configuration:

* from the Execute button [Excel Integration](page-widget.md#excel-integration)

All of the uploaded resources are automatically deleted after 7 days, except for those resources used in the Executive Object component for the _QUERY_.

For the use of the component _(file selection)_ section.

## Button

### Execute button

The **Execute button** component lets you perform operations which interact with other systems or other DAC objects.

The execution of the _Execute button_ is only allowed after having assigned values to the parameters defined as mandatory.

The type of operation is set in the **execution**_**-type**_ property (_Execution group_):

* _**QUERY**_ performs one or more queries
* _**CODE\_SNIPPET**_ _execution_ of a code snippet.
* **NOTIFICATION** starts notifications
* **DLR** starts data transfer. This property enables:
  * _**DLRS**_ associates data transfer processes, previously defined

**Note:** _The system also supports passing parameters from the Page page to any parametric filters of the source report_.

* **REFRESH RULE** _execution_ of the scheduled updating in DAC. This property enables:
  * _**refresh-rules**_ associates the refresh-rules, previously defined.

**Note:** _The system also supports the passage of parameters from the Page page to any parametric filters used as components of the refresh-rule._

* **DRILL THROUGH**_,_ to open a page in drill-through
* **APPLY\_SELECTIONS\_OPENER\_PAGE** applies the selections made in a page opened in a pop-up to the underlying page. This makes it possible to open a secondary Page in drill-through, when starting from a main Page. The secondary page selections are then applied to the main Page on the click of the button. The secondary Page will thus be the selector, and what is selected will be applied to the main Page.
* [**EXCEL\_INTEGRATION**](page-widget.md#excel-integration) allows an Excel file to be generated and for the data from that file to be entered in a database. The files are uploaded using the [File Selector](page-widget.md#file-selector-file-selection) component, with the Excel Integration procedure.
* [**TALEND\_INTEGRATION**](page-widget.md#talend-integration), allows the start of a Talend JOB.
* **JAVASCRIPT\_ONLY** allows you to run JavaScripts that are only set in the _**javaScript-code-before**_ and _**javaScript-code-after**_ property

It is possible to enter the JavaScript code to be run before and/or after the execution of the operation associated with the component:

* **javaScript-code-before JS** code run BEFORE the operations of the component
* **javaScript-code-after JS** code run AFTER the operations of the component

The properties support the use of parameters within them.

For Pages open in _**drill-through**_ and containing the _Execute button_:

* _**close-on-execution-success sets**_ the closing of the Page, when component execution has completed;
* _**refresh-opener-report specifies**_ the refresh of the _calling_ report (the one which opened the Page in drill-through).

Using the properties:

* _**post-execution-button**_ Sets another Execute button, present in the Page page, executed immediately after the action associated with this Execute button. The other configurations defined in the Execute button chosen in this property are ignored.

_For example, if this property is on Execute button A, and Execute button B is chosen in this property, the following actions will be executed in sequence: the action defined in Execute button A and the action defined in Execute button B. Any settings of Execute button B, such as the JavaScript code to be run before or after the action, are ignored._

This enables you to define a chain of executions.

For the text properties:

* _**button-text**_ (_Main_ group) for the button text (default “_Execute"_).

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button

Finally, the properties:

* **disabled** Enable/Disables the component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up where the name of the parameter is entered.

#### Mandatory Parameters

The _**mandatory**_-params property (Execution group) enables the various types of mandatory parameters:

* _**\<all-parameters>**_ specifies that all the parameters used are considered mandatory. The button may be run only after all the parameters have been valued.
* _**\<none>**_ specifies that no parameter used is considered mandatory. The button may be run whether or not the parameters are valued.
* _**\<selection>**_ specifies that only some of the parameters used are considered mandatory. This type activates:
  * the parameters property which specifies the mandatory parameters.

While running the Execute button:

* a pop-up will be shown next to the mandatory parameters that do not have values.
* in the case of mandatory parameters inherited from other pages, or for which a selector is not explicitly present in the page, a window will be opened instead which indicates the parameters to be valued.

If the _Execute button_ is associated and run in a **Wizard**, and executed at the end of the flow, DAC checks that the mandatory parameters for each step are valued. If not, access to the next step will be prevented.

#### Starting a Query

Starting a query is set by selecting _QUERY_ in the **execution-type** property: the _**sql-formula**_ property is enabled to define the query.

The query can either be added or updated, allowing you to interact with the data warehouse or other databases.

The query statement allows the use of parameters. In this case, using the property:

* _**mandatory-params**_ you can define if the parameters are mandatory (property selected, default) or not (property unselected).

**Note:** _If, the mandatory parameters are not valued before clicking on Execute query, the system shows the fields, and signals an error message._

![](<../../.gitbook/assets/56 (3).png>)

If the application interacts with databases other than the data warehouse (set in the application), initially a data source is defined for the connection to the database, using the _Datasource Designer_ module (see _Connections to remote data sources section_).

Then the data source is associated with the component:

* the _**Custom-datasource**_ property is selected
* the _**datasource**_ property is enabled, with which the previously created datasource can be selected

Also see Appendix I for more details on the settings of the SQL statement and the reference to the data source.

#### Starting a Notification

The _Execute button_ component allows you to start a notification previously defined using the _Notification Designer_ module (see _Notifications_ section).

When notifications are being executed, the parameters currently selected in the Page can be used within email notifications to customize the content.

The recipients of the notification can also be made dynamic by adding users selected within the Page to those set in the notification itself. New recipients selected in the Page should be defined as follows:

* A selection or input _form_ object is inserted, to which the special name **NOTIFICATION\_RECEIVERS** is assigned
* For selection objects (Select or Checklist), the query is entered to load DAC users (from the Data Model database), which is defined as:

**Select&#x20;**_**SUBJECTS.SUBJECT\_ID,SUBJECTS.SUBJECT\_NAME**_ _\[or SUBJECTS.USERNAME]_

**From&#x20;**_**\[metadati].SUBJECTS**_

To associate one or more notifications with the _Execute button_ component, simply

* select the NOTIFICATION _item_ in the **execution-type** property
* enable the notifications property, which allows associating notifications created previously

There is an example below of sending an e-mail notification from the Page.

#### Opening a page using Drill-Through

Using the Execute button object, you can open a Page page in Drill-Through.

Starting from a main Page, you can open a secondary Page through drill-through.

The Page opened in DS may be displayed in a new page or in a modal type window.

When the **execution-type** property is set to **DRILL\_THROUGH**, the following properties are enabled:

* **openNewWindow:** by default it is disabled and therefore the Page is opened in the same page.

If you select the openNewWindow property, the Page is opened in a new page, and the following subproperties are enabled:

* **full-screen:** opens the whole screen
  * **open-in-same-window:** opens the new page in the current page
  * **window-wiDSh:** sets the wiDSh of the window (visible if the full-screen property is not enabled)
  * **window-height**: sets the height of the window (visible if the full-screen property is not enabled)
* **modal-window:** if enabled the Page will be opened in a modal type window.
* **openActionType**: sets the type of action to be associated out of:
* **Page Page**: for the opening of a Page page. If selected enables the subproperty:
* **Page** selects the Page that will be opened by the DS
* **Report** for the opening of a report. If selected enables the subproperty:
* **Report:** selects a specific report
* **clear-params:** if selected, cleans all the parameters in the destination report.
* **Open URL: opens a web page**. If selected enables the subproperty:
* **url:** lets you enter the internet address of the page you want to open.
* **mandatory-params:** lets you establish which parameters must be mandatory, if any.
* **< all-**&#x70;arameters >all the parameters in the page.
* **< selection >**&#x6F;nly the selected parameter&#x73;**.**
* **< none >** no parameter.

#### Excel Integration

The type of Excel Integration allows the files to be processed and for data to be entered in a table from a database.

The files are Excel files and are uploaded using the [**Files Selector**](page-widget.md#file-selector-file-selection), configured for Excel integration, i.e. with:

* **upload-type** (_Form_ group set to EXCEL\_INTEGRATION

When the user clicks on _Executive Object_ the transfer of the data from the Excel files is started (uploaded with the _Files Selector_) in a database table:

The selection of the database is carried out on the Manual level and may be modified with the _Executive Object_ properties.

The properties for the configuration of the Execute button component for the EXCEL\_INTEGRATION are (_Execution_ group):

* **integration-name:** name of the setting that univocally identifies the last data imported from the Excel file.
* **file-selector-name:** name of the File Selector component used to upload the Excel file.

It is selected from a list of all of the Page File Selectors, which have the _**upload-type**_ property set for the _EXCEL\_INTEGRATION_.

* **destination-table-name**: name of the [integration table](page-widget.md#excel-integration), to which the Excel spreadsheet data is transferred.
* **Sheet-to-copy**, name of the Excel spreadsheet containing the data to be transferred to the table.
* **destination-table-definition**: open a window for the configuration and validation of the destination table
* **custom-datasource**: to edit the system database
* **post-import-procedures**: procedures that are carried out after uploading the data, in order to carry out the different SQL operations on the same data source as for the imported table.

The post-import operations may work for the last rows inserted or modified in the integration table: the setting is assigned a value in the _integration-name_ properties that identifies it univocally.

The Excel file is uploaded in the table until the first empty row is reached:

* The row is considered empty when all of the cells in the row, corresponding to the columns defined for import, are empty.

**Selection of the database for table integration**

The database that needs to contain the integration table is selected from the system level in the _**Tools**_ properties:

* **excel-integration-tables** (_Storage table schema_ group): overview of the database that will contain the integration table with the Excel files, uploaded using the _File Selector/Execute button_ **components**.

The scheme may be selected from those for the default Data Model databases and configured based in the Data Model scheme.

In the individual _**Execute button**_, for the _**Excel Integration**_, another database can be set, in the following properties:

* **custom-datasource**: to activate a database selection that is different from that for the system.

The activation of this property enables the following:

*
  * **datasource**: to select the data source that will contain the integration table.

A pop-up is opened with the list of the editable data sources (_not read only_) defined by the administrator in the Datasource Designer.

In the _**Datasource Designer**_ , when a data source is defined that needs to be associated with the Executive Object, in the properties:

* **Excel-integration-tables** (_Storage table schema_ group): select the screen where the integration table will be saved

**Creating an integration table**

The integration table is entered manually in the properties for the **destination-table-name**.

For the name, the prefix "EI\_" is always entered, so that the Data Model tables are not involved, in fact, the default database for saving these tables is the Data Model schema.

If the table still does not exist a Page save is created, so that the table already exists at the time of import.

The table is created using the settings defined in the **destination-table-definition** properties, and, the following columns are added:

* USERNAME\_ID: user identification
* DATE\_OPERATION: date of the operation
* EXPORT\_PARAMETER: operational identification, related to the Page setting.

If the table exists, the system, requesting confirmation, will delete the existing table and replace it with the structured defined in the **destination-table-definition**.

**Configuration of the Integration Table**

From the properties _**destination-table-definition**_ , a window is opened, such as the one in the figure below, which allows the table columns to be defined manually or using an Excel file that is used as a template.

![](<../../.gitbook/assets/57 (3).png>)

To **define the columns in the Excel file**, select the key indicated in the figure, which opens a window to select the file.

![](<../../.gitbook/assets/58 (3).png>)

Remember that there needs to be an ".xlsx" extension. After selecting the file, the spreadsheet containing the data must be selected.

![](<../../.gitbook/assets/59 (3).png>)

After selecting the Excel file, the rows in the configuration window are assigned a value as follows:

![](<../../.gitbook/assets/60 (2).png>)

* **Name** of the column for the **Excel spreadsheet**, corresponding to the first row in the spreadsheet that is not empty.
* **Name** of the column for the **table integration**, automatically defined by the system
* **Type** of column, automatically evaluated by the system. The data supported are NUMBER, STRING and DATE.
* **Requirement**, evaluated by the system on the values of the row following the header;

if not empty, it is set as required.

This procedure can be repeated by selecting another file/Excel spreadsheet. The system will manage the changes introduced by the new template.

**Note:** _The header columns in the Excel spreadsheet cannot be numerical_.

**Manual configuration** can be carried out by entering the column name in the appropriate space and by clicking on the “+“ key (see the figure below).

![](<../../.gitbook/assets/61 (2).png>)

The name entered may have a maximum of 60 characters and does not have constraints regarding the type of characters.

Even in this case, a row is added to the window, with the following assigned values:

* Name entered in the top field
* Name of the table integration table, as automatically defined by the system
* STRING column type
* Selection requirement

By selecting the _**Column Type**_ key, a pop-up is opened to define the following:

* **data-type**: modify the column type using the default setting.

The selection of the type of enabled STRING:

*
  * **validation-pattern**: to define a pattern for the column data.

The selection of the enabled type of NUMBER:

*
  * **precision**: maximum number of decimal places (default 5)
* **length**: maximum length (default for STRINGS: 4000, default for NUMBERS: 18)

**Note:** _In order to load the columns defined by the type of number, the empty cells are managed by entering a null value._

**Change in the Integration Table**

When a new Excel template is loaded, the system manages the structural differences and the types of incongruent data, based on the following definitions:

* the columns present in the first definition are highlighted in RED but are no longer present in the new template. The columns that are manually entered and not present in the template are highlighted in RED.
* the columns that have **a different type of data** with respect to the previous definition are highlighted in YELLOW.

If there is a change in the type of data, and/or length, and/or required criteria, with respect to that defined in this database table, and the database does not allow this operation to be carried out, the system will provide a warning, asking for confirmation that _the table will be recreated and that all of the data contained therein will be lost_.

In the event that a column is added or deleted, the system updates the table present in the database, in order to be able to reflect the settings made during the configuration phase.

If the database does not lead to the termination of the operation to update the table (for example: _insufficient_ tablespace or missing privileges), the user is advised that it isn’t possible to create the table, and the exception is reported.

The following is an example of a template modification for the circumstances described in the preceding paragraph.

![](<../../.gitbook/assets/62 (3).png>)

**Validation of the Integration Table**

After configuring the integration table, any validations are executed.

The key indicated in the figure allows the columns that have already been defined to be validated with the columns in a file.

![](<../../.gitbook/assets/63 (3).png>)

By clicking on the validation key, a window is opened for file selection.

After selecting the file and the Excel folder, the system checks that the fields match for the first row and that the name of the _**Files Column> Name**_ match, verifying the following:

* Type of data
* Requirements

If an error message indicating the type of error is displayed, the table is generated anyway if a save operation is carried out.

#### Talend Integration

The Talend Integration type allows you to start a Talend Job through Execute button.

The Job, created on Talend, should be loaded as a resource in the Resource Catalog, which will recognize it as a Talend Job resource type. A series of variables, used during the execution of the job, can be defined in Talend. Together, these variables define the context; a default value can be assigned to the variables.

Besides the default value, these Job parameters can be configured to assume the values of the Page parameters.

If the associated resource contains multiple jobs, the one associated with the Main Class, recognized by DAC (contained in the bat file), will be executed. If the associated resource contains a job with multiple child jobs, the parent job will be executed first and, in sequence, the child jobs.

Selecting the **TALEND\_INTEGRATION** option in the _**execution-type**_ property will enable the following:

* job, opens a pop-up for the selection of the job to execute. The window lists all Talend Job resource types loaded in the Resource Catalog.
* input-params-mapping, opens a pop-up for the mapping of the job context. For every parameter of the context, the following can be assigned:
  * \<Default>, in order to consider the given definitions as default in the Talend Job context.
  * One of the Page parameters. All parameters present in the dashboard are, in fact, listed

![](<../../.gitbook/assets/64 (2).png>)

If one or more of the context parameters were not configured, or rather the Page parameters have not been assigned values, then the default values will be assigned when the Job is executed.

If the resource associated with the job contains multiple child jobs, parameters can be passed directly only to the parent job. The parent job will then propagate them to the child jobs.

#### An Example of Opening a Page in Drill-Through

The example below explains the use of the execute button inside a Page.

Specifically, it describes how to use this object in the following instances:

* to open a new page of a Page (_**DRILL\_THROUGH**_)
* to enter the data through SQL query (**QUERY**) and at the same time _**(**_**post-execution-button**) to start a second button to automatically send a notification e-mail (**NOTIFICATION**).

Step 1: Execute button as DS and use the post-execution-button

![](<../../.gitbook/assets/65 (3).png>)

_The Page in the figure is an Order form._

1. _The user enters his personal data in the User Information and Address section._

_Through the New Order button, open a Page page, where you can select the type of product you want to order._

1. _After closing the window ("OK" button), the fields of Your Order section will be valued, through the automatic passing of the parameters._
2. _The third step is the confirmation of the order request that takes place via the Confirm Order button._

_This button, in addition to saving data entered by the user inside the database, will execute a second object (invisible to the user) which will send an e-mail relating to the order request_

Step 1:Execute button as DS and use the post-execution-button

![](<../../.gitbook/assets/66 (2).png>)

_The Page consists of many objects. The example below shows how the three Execute buttons are configured._

1. _The first execute button (New Order) opens the Page page for selection of the new order through the DS._

_The object was configured as follows:_

* _the execution of the object of the DRILL\_THROUGH type (execution-type)_
* _the Page will open in a new page but in the same window (openNewWindow and Open-in-same-window)._
* _The new page will have a size of 900 by 700 (window-wiDSh and window-height)._
* _From the openActionType property, select the Page Page option and in a Page, select the Page which will be opened by DS._

1. _The second execute button (Send E-Mail) automatically sends an e-mail. This button will not be visible to the end user since it was created to be used by the third button, after sending data to the database._

_The object was configured as follows:_

* _the execution of the object is of the NOTIFICATION type (execution-type)_
* _from the notification property select the notification to send the e-mail._
* _select all the parameters available in the Page \<all-parameters> (mandatory-params)._

1. _The third execute button (Confirm Order) enters the data of the form in a table of the database._

_The object was configured as follows:_

* _the execution of the object is of the QUERY type (execution-type)_
* _the entry query was entered through the sql-formula property_

_After entering the data, the second execute button will be automatically enabled, which will send the e-mail._

_This is possible by recalling the execution object Send Mail inside the post-execution-button._

_Thus with a simple click, the system automatically sends the e-mail and enters the data in the database._

Step 3: Execute button as DS and use the post-execution-button![](<../../.gitbook/assets/67 (3).png>)![](<../../.gitbook/assets/68 (3).png>)![](<../../.gitbook/assets/69 (3).png>)![](<../../.gitbook/assets/70 (2).png>)

_The figure shows the configuration of the Page opened through DS by the New Order button._

_The Page consists of several objects including Checklists and Text Fields. parameter , the same Form Name as the one of the corresponding objects in the calling Page was assigned._

&#x20;_the Execute button was configured in order for it to pass the parameters to the Page page called._

_The object was configured as follows:_

* _the execution of the object is of the APPLY\_SELECTION\_OPENER\_PAGE type (execution-type). This setting will let you pass all parameters (mandatory-params) to the requested page. In this case the parameters will populate the Your Orders section of the main Page._

Step 4:Execute button as DS and use the post-execution-button

![](<../../.gitbook/assets/71 (3).png>)

_The figure shows the final Page._

_When accessing the Page for the first time, the user enters his data in the User Information and Address section._

_The New Order button opens the Page to select the products to be ordered. The user selects the desired product, specifies the quantity, and saves the order by pressing OK._

_The window closes and the main Page automatically values the fields referring to the order (Your Orders)._

_Finally the user confirms the order (Confirm Order button) and the system automatically enters the data in the database and sends an e-mail with the information relating to the user and chosen product._

#### Example of Database Update (QUERY) and Sending an E-mail (Notification)

The Page in the figure was designed to plan the working activities of the DAC users.

The system will be able to inform users, via an e-mail notification, of the activities they have been assigned.

Step 1: Page

![](<../../.gitbook/assets/72 (2).png>)

_The Page in the figure was designed using the following components:_

* _a Checklist (Select Activities) for selecting one or more work activities_
* _another Checklist (Select User) for selecting the user, to assign these tasks to_
* _two Text Fields (Start Date/End Date), set as calendar (date type), which allow selecting the period when the task is to be carried out_
* _the Assign Task button which assigns a task to a user , and which updates the tasks/appointed user table (the respective size is mapped on that table)_
* _the report (User Activities), built on the tasks/appointed user size, which shows the tasks with the associated user_
* _a Gantt chart, which provides an immediate perception of the tasks established_
* _by using the Send e-mail button, the notification is e-mailed to the selected user initially on the tasks the user was assigned to_

Step 2: Page

![](<../../.gitbook/assets/73 (1).png>)

_The following are main properties set for the components shown in the figure:_

* _The first Checklist (Ds\_Attivita) displays a list of tasks and allows selecting multiple tasks since it is set to multi-selection mode (multi-selection)._

_Population was executed using a query._

* _The second Check List ( (NOTIFICATION\_RECEIVERS) will let you select the users to send the notification e-mail to._

_For correct operation, the name NOTIFICATION\_RECEIVERS must be assigned in the \<formname>._

_The query used to load the DAC users is entered (from the Data Model database), which is defined as:_

_select SUBJECTS.SUBJECT\_ID,SUBJECTS.SUBJECT\_NAME \[or SUBJECTS.USERNAME]_

_From \[metadati].SUBJECTS._

* _The Text Fields (Start Date and End Date) are set as calendar and are used to select the period when the selected task is to be performed._
* _The report will contain the dimensional levels relating to tasks and users._
* _The graph will display the tasks assigned to each user and the start and end date of the schedule._

Step 3: Page

![](<../../.gitbook/assets/image (162).png>)

_The Execute button, called Assign Task, uses a query to update the table used by the User Task report, and assigns the user to the selected task._

_From the \<execution-type> property, the type of operation is selected, which is to be assigned to the Execute button, which in this case will be of Query type._

_The update query is entered in the sql-formula, and will be of the type:_

_UPDATE table-name_

_SET_

_field1-table='?Name\_User?_

_field2-table=?Start\_Date?,_

_field3-table=?End\_Date?_

_WHERE field-table IN ('?Ds\_Task? ')_

_Note that the relative parameter transferred in the Page was assigned to every field in the table._

Step 4: Notification Designer

![](<../../.gitbook/assets/76 (1).png>)

_The notification is created, which will then be associated with the Execute button object on the Page._

_Access Notification Designer from the Application section of the DAC._

_A new e-mail notification is created._

_Right-click on the root and select Create Mail Notification. ._

_Assign a name to the notification (in this case, Assign Task mail)._

_In the Title section, a title is entered and in this case, the attribute % SUBJECT% was entered to make the title of the notification dynamic, based on the user to whom it is sent._

_An HTML code was entered in the Body section to create a table that will contain the information about the user name, the task and the start and end date._

_This information will be made dynamic since the code contains the exported parameters of the Page components._

**The following HTML code is entered:**

![](<../../.gitbook/assets/77 (1).png>)

```
<table wiDSh=50 border="3" bordercolor=#616f79 >
  <tr>
       <td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">User Task</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date%SUBJECT%?</td>
</tr>
    <tr> 
       <td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">List Of Assigned Tasks</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date?Ds_Attivita?</?</td>
   </tr>
<tr>
      <td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">Start Date</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date?Start_Date?</?</td>
</tr>
   <tr>
<td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">End Date</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date?End_Date??</td>
 </tr>
</table>

```



**THE PARAMETERS ARE HIGHLIGHTED IN RED.**

Reports or Pages can be attached to the e-mail.

In the _Attachments_ section, you can either select a report from the ![](<../../.gitbook/assets/78 (2).png>) button or a Page by selecting the.![](<../../.gitbook/assets/79 (2).png>) button.

In this case, a detail report was selected.

Step 5: Notification Designer

![](<../../.gitbook/assets/80 (2).png>)

_The Execute button named (Send e-mail) is a button that allows sending an e-mail to the recipient, after the tasks have been selected. In \<execute-type>, the operation to be assigned to the object is selected, which will be of the NOTIFICATION type. The \<notification> property is enabled from which, using a selection window, the notification created previously (Assign Task mail) is selected._

Step 6: E-mail

![](<../../.gitbook/assets/81 (2).png>)

_Based on the graphical settings set using HTML code, the Body of the notification e-mail will be displayed as shown in the figure._

### Submit

The action of the **Submit** component consists of making the page parameter changes effective on the data presentation objects.

In the Analysis by pane _of this_ Page, we select the values, which are filter parameters for the two graph and table objects.

Selecting the parameters has no effect on the two presentation objects. Whereas, if you click the _Send_ button (**Submit** component), the values of the parameters are applied to the graph and table, which will show the result of this filtering.

Also the **Submit** action is only enabled for data presentation components with the **refreshMethod** property set to _OnSubmit_.

For the text properties:

* _**button-text**_ (Group _Main_(Text) for the button (DEFAULT “_Submit_”)

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button

Finally, the properties:

**disabled** Enable/Disables the component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered .

### Parameters Cleaner

This object serves to restore the parameters of the page to the initial conditions.

![](<../../.gitbook/assets/82 (2).png>)

The configuration of this component takes place through the properties of the _Main_ group:

* _**clean-type**_ type allows you to select whether to apply the reset operation to all parameters of the page (_\<all-params>_) or to a subset of them (_\<selection>_), which enables the property:
  * _**param-selection**_ for the selection of the parameters to be reset.
* _**reinit-page-By**_ to restore initial conditions, also of the values of the page-bys on the Page
* _**Custom-JS-code-after-params-clean**_ JavaScript code to be executed when the component is selected.

Restore the initial values of the parameters at the page level can also be enabled, rather than from the _Params Cleaner component._

For the text properties:

* _**button-text**_ (Group _Main_(Text) for the button (DEFAULT “_Settings cleaner_”) .

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button.

## Containers

The container components define a Page layout in a more complex manner than the simple grid available in the Page Designer.

In the containers, you can select a theme to be applied to them and to all of the contained components:

The components available are:

* the table,
* the container of rows and columns
* container of panels which can be selected (Tab control)
* Wizard
* Inner container

**Note:** _In the copy of a container, requested through the commands of the pop-up menu, it is possible:_

* _to copy the container, including the objects contained in it (Copy item)_
* _copy the empty container, i.e. the structure only (Copy structure item)_

![](<../../.gitbook/assets/83 (2).png>)

### Container Theme

For the Page, the section and the components for the type of container make it possible to apply a theme which defines a layout style of the page and its components.

The _**theme**_ property in the _**ContainerStyle**_ group will let you choose the theme among those made available by DAC.

If the default style is set at page level all the components will have the _**Default**_ value selected for the _**theme**_ property.

Example: Container theme

Step 1: Theme selection

![](<../../.gitbook/assets/image (164).png>)

_The figure shows a Page page to which Dark was applied as theme. This will be used in all the Page components, since the respective theme property will not be changed for any themes. Therefore all the components inherit the style of the page, i.e. the Dark theme (default(Dark)) will be applied to the table titles, the Style Selector and the Submit button_

Step 2: Viewing in DAC

![](<../../.gitbook/assets/85 (2).png>)

_Note how all the components have inherited the Dark style defined in the Page creation phase._

### Column Container and Row Container

The **Column Container** and **Row Container** are objects that, when used in a combined mode, create Pages that re-adapt to the resolution of the screen.

In the _Row Container_ the components contained in them may be hidden (collapsed), to have a cleaner view of the page.

The characteristic of the _Column container_ is that the components contained in it will automatically be wrapped in case the wiDSh is outside the wiDSh of the same container.

For example if you restrict the browser window containing the Page, and the dimensions of the objects of the column container are too big compared to the overall space of the page, these will be wrapped.

![](<../../.gitbook/assets/86 (2).png>)

The specific properties for the **Column Container** are (_Object_ group):

* **cells-number:** number of container columns
* **wrap-content:** if active, in case the wiDSh of the contained objects is outside the wiDSh of the same container, these will be wrapped.

The specific property for the **Row Container** is (_Object group_):

* **cells-number:** number of container rows

Step 1: Column Container using the wrap-content

![](<../../.gitbook/assets/87 (1).png>)

_The example shows how the components contained in the Column Container will be repositioned in the page if the window changes wiDSh and height size._

* _Enter the Column Container object_
* _Set the number of cells Cells-number_
* _Enable the property to wrap the components \<wrap-content>_
* _Set the size of the container. In this case it will take up 100% of the page._
* _Enter the reports which will all have a wiDSh equal to 400 pixels._

Step 2: Page - Column Container

![](<../../.gitbook/assets/88 (2).png>)

_Access DAC. Restrict the wiDSh of the window of the browser (from right to left)_

_The reports are automatically wrapped since their size is too big for the page which contains them._

### Table

The _**Table**_ component is a table, entered in the cell in the Page design area.

For tables, the number of rows and columns can be defined that are required to contain the Page components, which will be entered in the cells of the table.

![](<../../.gitbook/assets/89 (1).png>)

In addition, the components in a table can span multiple cells and have a specific alignment.

This feature is particularly useful when an object spans multiple rows/columns compared to the others. See the example.

There are custom properties for tables, such as color, borders, etc.

#### Specific properties of the Table component

The table object is characterized by the number of rows and columns, distance between cells, contents of the cell from its border, and the background colors that can be set.

Characteristic properties are in the Table group, where the following are set:

* _**col-number, row-number**_ for the number of columns and rows
* _**border-**_&#x73;ize for the border wiDSh
* _**cellPadding**_ for the distance, in pixels, between elements in cells and cell borders
* _**cellSpacing**_ for the distance between one cell and another and between the cell and the outside border of the table

#### Objects contained in a Table, Row Container and Column Container

For each object entered in the _Row Container_ and _Column Container_ the property (_Container_ folder) is activated:

* **collapsible** (_Layout_ group) to activate the collapse of the object. The property enables:
* **startCollapsed** enables the publication of the object in closed mode, making only the title visible

![](<../../.gitbook/assets/90 (2).png>)

_In the figure a Column Container with three elements, in the last cell a graph is entered with two active properties: in the first instance it is in closed form, with an arrow which lets you open the graph._

For the components entered in a _Table_ and _Row Container_ the following is available:

* **horizontal-align** (_ContainerStyle_ group, _Container_ folder) for the horizontal alignment, which may be of the _Center, Top and Left type_

![](<../../.gitbook/assets/91 (1).png>)

For the components entered in a _Table_ it is possible to define the grouping of cells in rows and/or columns and the vertical alignment via the properties (_Table-Cell group,_ _Object_ folder):

* **rowSpan**, **colSpan** number of rows and columns which the object must span
* **vertical-align** vertical alignment of the object compared to the cell it is contained in

Step 1: Aligning objects in a table

![](<../../.gitbook/assets/92 (1).png>)

_The following example publishes a table near two graphs, where the graphs occupy the same space/height as the crosstab._

_Insert the Table object in the first cell, with_

* _dimensions 2x2: row-number=2, col-number=2_
* _a title_

_Insert a crosstab in the first cell of the table; in the second column insert the two graphs, as indicated in the figure._

_For the crosstab component, access the properties of the Table Cell group and set_

* _rowSpan at 2, so that it occupies 2 rows_

Step 2: Aligning objects in a table

![](<../../.gitbook/assets/93 (1).png>)

_The Page is published in DAC as shown in the figure. Notice how the crosstab occupies two rows, while the graphics are aligned next to it._

Step 1: Page - Column Container & Row Container

![](<../../.gitbook/assets/94 (1).png>)

_The figure shows the configuration of a Page where the Row Containers were embedded with the Column Containers. In this Page you can collapse individual components, for each section and for all the sections._

_Also, the wrap of the components was enabled._

Step 2: Page - Column Container & Row Container

![](<../../.gitbook/assets/95 (1).png>)

_The figure shows the Page viewed in DAC._

_Step 1 and Step2: if you want to hide the filters for the brand and the product, just move to the side arrow. The section will be hidden with a click_

_Step 2 and Step 3: if you want to hide all the filters section, just select the arrow relating to the outside. This will hide the entire area dedicated to the filters, placing the graph and the report to be analyzed in the foreground._

### Tab Control

The _Tab Control_ is a Page container. It is inserted in a main Page and shows various Pages by simply selecting the TABs associated with them.

The parameters of the main Page may be used as a filter in the Pages contained in the Tab Control. Developers may define whether the filters are applied instantly (i.e. when choosing each value) or only when selecting the Pages of the Tab Control so there isn’t a refresh when selecting each parameter, but rather a single refresh requested after the selection of all the parameters of interest.

![](<../../.gitbook/assets/96 (1).png>)

You can change from one TAB to another in automatic mode, by respecting a default time-out; the opening of the different TABS can be set in different modes (fade-out, vertical or horizontal scrolling).

The initial TAB opened is also the default selection. In addition, moving from one tab to another can affect other page elements, and vice versa (selecting page elements can position a specific TAB).

If this element is open in drill-through from a report, it can receive the source parameters and filter the Pages associated with the _Tab Control_.

**Tab** **Control** consists of two components (in the _Containers folder_):

* _**Tab Selector**_ defines the TABS and the associated Pages
* _**Tab Panel**_ customizes the container of the Pages associated with the TAB of the _Tab Selector_ object

Below is an example of publishing the _Tab Control object_

_**Note:**_ _When images are associated with the Pages, these will be replaced in the TABs of the object._

#### Tab Selector

The specific properties of the **Tab** **Selector** component are (_Object folder_):

* _**Tab-pages**_ _(Tabs_ grou&#x70;_)_ selection of the Pages to be associated with the TABS: open a pop-up with the Pages of the application.

For each Page selected, the following is enabled:

*
  * _**Page(i)**_ reports the name of the Page selected in the previous property; the name of the Page is used as the name of the TAB.
  * _**description**_ the description associated with the TAB, shown as tooltip when passing the mouse over.
* _**tab-panel**_ (_Settings_ group) selection of the _panel_ which will count the Pages chosen in the _tab-pages_ property: open a menu with the list of the _Tab Panels_ present in the Page.
* _**auto-select-tab**_ (_Settings_ grou&#x70;_**)**_ select the TAB to be shown at first access

If the property is set to \<none> no TAB is active and selected; as a result the Tab Panel component is not displayed until you select a specific TAB.

* _**parameter-name**_ (_Settings_ group) parameter associated with the Tab Control:

the parameter will be valued with the cardinal number of the selected TAB (1 for the first TAB, 2 for the second, etc.).

This parameter may be used:

* when importing, valued by other components of the page or a source that opens it in drill-through; the value of the parameter pre-selects the TAB being displayed
* when exporting, valued by the _Tab Selector_ with the cardinal number of the TAB being selected and used by other elements; for example each TAB change could change the value selection in a _Select_, when this is conditioned by the value of the parameter of the _Tab selector_.
* **slider height:** _(Settings group)_ sets the height of the object. No percentage values are acepted
* _**auto-select-tab**_ (_Settings_ group) enables/disables automatic sliding.

if _**auto-select-tab**_ is set to _\<none>_; as a consequence it is not possible to set the automatic sliding if a specific TAB is not set upon the first opening.

If the automatic sliding is active, the following property is enabled:

*
  * _**interval-time**_ time interval to show the next TAB (in seconds); the time interval is applied after loading the current Page.
* **associatedImageSet :** Set the type and the size of the image.

#### Tab Panel

The specific properties of the **Tab** **Panel** component are (_Object_ folder):

* _**name**_ (_Main_ group) name of the object
* _**transitionEffect**_ (_Settings_ group) transition effect on the TAB change
  * _**none**_ no effect is applied
  * _**fade**_ makes it dissolve
  * _**slide**_ sliding from the top downwards
  * _**slide\_left**_ sliding from right to left

this effect is not available if the _Tab Panel_ has the auto-expand property active (_Container_ folder, _Container Size_ group).

* _**auto-refresh-on-params-change**_ makes the refreshing of the parameters used as filter sync, in the Pages of the Tab Control. If disabled, the Pages of the tab control are refreshed only when selecting the Page.

Example: Tab Control

Step 1: Page Creation

![](<../../.gitbook/assets/97 (2).png>)

_Create a new Page containing the Tab Selector and Tab Panel components. For the Tab Panel the following properties are set:_

* _name the name of the panel;_
* _Template-theme the theme of the container_
* _transitionEffect the type of transition for the TAB change_

_For the Tab Selector the following properties are set:_

* _tab-pages select the Page pages to be associated with the TABs_
* _tab-panel the panel name to be associated with the Tab Selector (defined before)._
* _Template-theme theme for the TABs._

Step 2: Page display

![](<../../.gitbook/assets/98 (2).png>)

_The figure shows the Page Preview. Note that:_

* _for each Page page, a specific TAB was created, which takes the same name._
* _the Page pages can be browsed by simply selecting the desired TAB._

_If the auto-sliding property of the Tab Selector object had been enabled, this would have made the sliding of the Pages automatic._

### Wizard

The **Wizard** object builds a succession of pages in order to define an application.

The Wizard object is shown as a container of a defined number of pages referred to as _Steps_. In each individual _Step_ of the Wizard, a Page is associated, containing one or more defined parameters in the appropriate property group. You can explore the wizard by clicking on each individual step or with the “back”, “forward” buttons.

![](<../../.gitbook/assets/99 (1).png>)

The **Wizard** object belongs to the _Containers_ groups. The properties of the **Wizard** are the following:

* _**wizard-pages**_ (_STEPS_ group) selection of the Pages to be associated with the STEPs: a pop-up opens with the Pages of the application.

For each Page selected, the following is enabled:

* _**page(i)**_ reporting the name of the Page selected in the previous property; the name of the Page is used as the name of the STEP.
* _**description**_ the description associated with the STEP, displayed as a tooltip when passing the mouse over it.
* _**required-parameters**_ defines the mandatory parameters which, only if a value is assigned, access the next STEP
* _**initialize**_ (_On-Enter_ group) enables the forced initialization of the Wizard if the Page containing it is accessed again (after browsing on other DAC pages). If it is disabled, the STEP prior to leaving the page will be shown when returning to the Wizard.
* _**execution-button**_ (Execution _group_) associates a button with the page whose execution will be referred to the last step of the wizard, or at its conclusion.
* _**template-style**_ (_Settings_ grou&#x70;_)_ template associated with displaying the application
* _**parameter-name**_ (_Settings_ group) sets the name of the parameter of the Page associated with the selection of the Wizard step.
* _**transitionEffect**_ (_Settings_ group) defines the effect that will be shown when passing from one step to another. The effects applicable to the pages are:
* _**none**_ no effect is applied
* _**fade**_ makes it dissolve
* _**slide**_ sliding from the top downwards
* _**slide\_left**_ sliding from right to left

### Inner Container

**The Inner Container** is an object which shows a box in a Page which points to a specific URL: for example, an application.

The URL may be defined in a dynamic manner by entering the parameters.

The only specific property is the one concerning the entry of the URL:

* _**url**_ (_Main_ group of the _Object_ folder) defines the URL address which will be displayed inside the component.

It is possible to define the URL parametrically: the object will be displayed only when all parameters are valued.

## Discussion

DAC provides a Collaboration solution to associate comments, production notes or other information to the data available in the reports. The users are given the ability to reply and initiate a discussion.

The components in the **Collaboration** group let you start the discussions among different user groups.

The components available are:

* ![](<../../.gitbook/assets/100 (1).png>) **Discussions**

Allows discussions to be opened, possibly on a specific topic.

* ![](<../../.gitbook/assets/101 (1).png>) **Discussions stream**

Collector of open discussions in various sections of the system and belonging to the same subjects.

The discussions can also be enabled for some of the Page components.

### Discussions

The _**Discussion**_ object allows users to publish one or more discussions.

These can also be linked to one specific subject; the subject to link the discussion to is defined by one or more dimensional levels, chosen from those exported to the Page page.

When you select a level value, you can display or create discussions relating to the selected value.

For example if _Discussions_ are defined with respect to the ‘Business Unit’ level, discussions may begin concerning one of the Business Units (in the example a discussion was opened concerning ‘Fridges and Freezers’).

This way, when selecting a level, only discussions opened for that specific value will be visible.

However, you do not need to set a level as a subject of the discussion.

In the event the **permissions are deleted** on the Page containing the discussions, the discussions will remain visible as long as no one enters comments in the discussion.

![](<../../.gitbook/assets/102 (1).png>)

The discussions are displayed in a “social network like” mode, i.e. from top to bottom, with replies _indented_ compared to the main subject.

Other users can reply by posting comments and attaching files, and thus have a real conversation on the subject.

The properties for configuring the object are (_Discussions_ group):

* **context-parameters**

It will be possible to select one or more dimensional levels exported by the page objects.

These levels identify the topic of the discussion, something that is not required.

* **context-root-ID**

ID generated automatically by the system, initially corresponding to the actual ID of the page in which it is included.

The ID can be changed manually. This makes the discussion easy to identify, so that it can be used by another _Discussion_ objec&#x74;_._

In fact, if two _Discussion_ objects have the _same context-root-ID_, they will display the same discussions.

This configuration is useful for displaying the same discussions on different Page pages.

**Note**: The discussions open on the object are linked to _the context-root-ID_. When this is renamed, all discussions linked to the modified name will be lost. You can restore them if _the context-root-id_ is assigned the previous value.

* **allow-discussion-remove**

This deletes the discussion. If this property is enabled, you can delete the entire discussion. Otherwise, it isn’t possible to remove the discussion, even if it is possible to remove individual messages.

![](<../../.gitbook/assets/103 (1).png>)

* **groups-post-enabled**

This sets the user groups authorized to post messages in the discussion. Unless otherwise specified, all groups are authorized to enter messages.

* **post-creation-execution-button**

This sets an action that will be executed after the _Discussion_ is created. You can choose an _Execute button_ object within the page. This will be executed after a new discussion is created.

**Note:** Once the execution of the Execute button is completed, a parameter is given a value that identifies the discussion just created.

The parameter is “?**lastCreatedDiscussionID?**“ and is available in the Page page. This is useful if you want to save the ID of the discussion together with the date or the user that generated it.

* **single-discussion**

This enables the creation of a single discussion. If this is activated, you cannot create multiple discussions associated with the same context.

* **activate-message-reply**

This allows you to reply to the discussion, by entering reply messages within the discussions.

* **enable-post-discussions-on-total:**

This enables a discussion to be created on a context parameter which has no value.

Step 1: Example:‘enable-post-discussions-on-total’

![](<../../.gitbook/assets/104 (2).png>)

_Page 1 has a Discussion object where the context is related to the values of the Business Unit._

_Pages BU-Shoes, BU-Clothing and BU-Accessories have the Discussion object with the same context-root-ID and context-parameters of Page 1. When a message is entered in Page1, on the \[Total] element, this message is displayed in all the other Pages, even if a user filter was applied in these for a specific context parameter (e.g.: Business Unit=Clothing)._

Step 1: Creating Pages

![](<../../.gitbook/assets/105 (2).png>)

_This example shows how to set properties so that objects can communicate between themselves. Let’s assume you want to start a discussion to analyze the Business Units included in a report._

1. _You export the Business Unit level from the ‘Business Unit’ report._
2. _For the Discussion object we set:_

* _as context-parameter the Business\_Unit level exported from the previous report_
* _in the groups-post-enabled property, you associate the user group enabled to enter messages_
* _you enable the show-title-field property so that users are able to enter a title for the discussion._

_The context-parameter and the context-root-id define the context of your discussion._

_Note: If you want to show the same discussions opened on this object in another dashboard, all you have to do is to make sure the other dashboard contains a Discussion object with the same context-root-ID assigned (in this example Sales\_BU)._

### Discussion Stream

The object of the _**Discussion Stream**_ Page allows you to view discussions opened in one or more _Discussion_ objects: it will act as a **collector for the discussions** opened in various sections of the system, and, for example, on the same subjects.

The _Discussions_ displayed in this object have the same features as the Discussion object and will be configured again, in a rather similar way to the _Discussion_ objec&#x74;_._

![](<../../.gitbook/assets/106 (1).png>)

The properties to configure the _Discussion Stream_ object (_Discussions stream_ group) are:

* **associated-collaboration-objects**

to select the _Discussion_ objects that will contribute to the stream:

Pages containing at least one _Discussion_ object are listed, with the context-root-ID of the Discussion itself in brackets.

* **context-parameters**

to select one or more dimensional levels exported by page objects.

These levels filter the discussion context and display only the discussions open at the chosen level.

Selecting a level is not required; if no level is selected, all open discussions of the Discussion objects associated with the stream will be presented.

* **allow-discussion-remove**

This deletes the discussion. If this property is enabled, you can delete the entire discussion. Otherwise, it will not be possible to remove the discussion, even if it is possible to remove individual messages.

* **groups-post-enabled**

This sets the user groups that are enabled to post messages in the discussion. Unless otherwise specified, all groups are able to post messages.

* **activate-message-reply**

This enables users to reply to the discussion, posting messages in the discussions.

By default, you can only view discussions on the Pages that you can access.

It is possible to allow users to also view dashboards they have no access to through the property (_Filter_ group):

* **filter-viewable-Pages**

This property is selected by default. If it is disabled, all discussions will be visible, even those open on Pages which users do not have access privileges for.

In the event **the permissions are deleted** on one of the Pages containing the discussions and the property **filter-viewable-Pages** is disabled, these will remain visible and active.

In addition, you'll be able to access the discussions associated with the cells of a report even if there are no permissions for accessing that report, but you won't be able to comment on, edit or create new discussions. Furthermore, notifications continue to be received in Incoming mail and in e-mail notifications if enabled.

The following example shows a possible configuration for the _Discussion Stream_ object.

Step 1: View in DAC

![](<../../.gitbook/assets/image (165).png>)

_Suppose you want to gather all the discussions opened in the Pages displayed in the figure (Discussion 1 and Discussion 2)._

_The Discussion object created in the ‘Discussion 1’ Page was named ‘Discussion1’, using the context-root-ID property. The Discussion object of the ‘Discussion 2’ Page was named ‘Discussion2’._

Step 2: Creating Pages

![](<../../.gitbook/assets/108 (2).png>)

_You can create a Page that includes the Discussion Stream object. For this to work, the following properties need to be set:_

_context-parameters select the Business unit level exported by the above report._

_associated-collaboration-objects from the menu window select the Discussion objects to be displayed in the Document Stream: Discussion 1 (Discussion1) and Discussion 2 (Discussion2)._

3.Display in DAC

![](<../../.gitbook/assets/109 (1).png>)

_The Discussion Stream object is displayed as in the picture._

_It will show the list of discussions open within the Discussion object._

_When you select a Business Unit from the report (which exports this level), it will act as a Filter. The Document Stream will display only the discussions linked to the selected Business Unit, but open on both the Discussion objects of the other Pages._

### Enabling Page Components

The Page components on which discussions can be used are:

* Table
* Crosstabs
* Graph
* Flag Setup
* Indicator

You can enable the use of discussions on these components in DAC by enabling the **activateDiscussions** property in the **Title** group.

This will allow DAC users to enter discussions. The icon identifying the discussions appears on the title of the component, and from this users can enter their messages.

Step 1: Enabling Discussion Page component

![](<../../.gitbook/assets/110 (1).png>)

_Enable a graph component to use annotations. Create a Page with a graph component._

* _Enable annotations: activateDiscussion property of the Title group_

Step 2: Using Discussions on DAC

![](<../../.gitbook/assets/111 (2).png>)

_Access the Page created in step 1. The Discussion icon will be on the graph title. Move to the icon and click it to open the callout and insert a message._

## Resource

Other components can be inserted in a dashboard:

* An image
* Some text, to enter free format text and especially useful for entering HTML code in the Page page, other than the one managed by the system
* An object dedicated to JavaScript code to be used in the page

### Image

The **Image** object lets you insert an image in any format (JPEG, GIF, BITMAP, etc.).

The specific configuration properties are as follows

* _**Image**_ (_Image_ group) to select the resource relating to the image;

The image file needs to be inserted ahead of time in the resource catalog.

* _**wiDSh**_ and _**height**_ (_Image_ group): wiDSh and height of the image.
* _**tooltip**_ (_Image_ group) tooltip to be associated with the image
* _**javascript-code-onClick**_ (_Events_ group) opens the window to enter the JavaScript code, which will be run by clicking on the image

### Plain text

The **Text** object enters the free text, particularly useful to enter HTML code in the Page page, unlike the one managed by the system.

The specific property is the following

* _**text**_: sets the text contained in the element

The following example shows an advanced use of the Text component, together with the publication of an image.

Step 1: Using Text and Image components

![](<../../.gitbook/assets/112 (1).png>)

_The example shows a Page page that contains a bubble graph. In addition to the Graph component, Image and Text components were also inserted. The first displays the Decisyon logo while the Text object was associated with an image that will serve as a button. Clicking on it will open another page (this is also an image) that displays detailed information about the type of graph. These operations are linked with each other through the HTML code._

Step 2: Using the Image component

![](<../../.gitbook/assets/113 (1).png>)

_A Page page is created that contains:_

_A Graph object, in this example a bubble graph is displayed._

_An Image object that will display the Decisyon logo._

_In the resource property, the name of the file ‘logoDcy.jpg’ was entered. This file is located in the DAC_

_customization/IMG folder._

Step 3: Using the Text component

![](<../../.gitbook/assets/114 (2).png>)

_The Text object will display the_ ![](<../../.gitbook/assets/115 (2).png>)_icon from which a second image can be accessed, that will display the detailed information on the bubble graph._

_Two images are inserted in the DAC customization/IMG folder, one relating to the icon named "1297265268\_info.png" and one relating to the detailed information on the graph, named "Info Bubble.jpg"_

_The HTML code for creating the link is inserted in the window that is enabled from the text property._

_The code is as follows:_

**\<a href="#images" onclick="window.open('../../customizations/img/Info Bubble.JPG','','wiDSh=1024,height=480')">**

**\<img src="../../customizations/img/1297265268\_info.png" border="0" alt="Info Bubble Graph">**

**\</a>**

_The first link opens the detailed image ‘Info Bubble.JPG'. The dimensions of the window will be 1024x480._

_The second link displays the icon_ ![](<../../.gitbook/assets/116 (1).png>)_((\<img src="../../customizations/img/1297265268\_info.png" border="0" alt="Info Bubble Graph">)_

### JavaScript

Use the JavaScript object to define the JavaScript code to be used in the same page, such as the Execute button.

The specific properties of this object are:

* _**javascript-code**_ which enables opening the window to enter the JavaScript code.

If some parameters of the Page are used in the JavaScript code, each time these parameters are valued the system runs the code in the component again.

An **example** of using this component is below.

The Page in the example is a mask to enter orders; when data is entered in _a mask_ in a suitable table via the _Execute button_ component, a report will show the data that was just entered (_Crosstab_ object).

For the report to be updated, the new data will be associated with a _JavaScript_ to select the function predefined to update the Page. The JavaScript will be performed after updating the data in the table. The WAIT icon is published while you wait for the updated report, as defined via the predefined JavaScript function.

Another JS code is added for printing the date including the time (top right).

![](<../../.gitbook/assets/117 (2).png>)

Step 1: Creating the Page

![](<../../.gitbook/assets/118 (2).png>)

_The figure shows the components which the Page consists of._

_JavaScript and Execute button are the components of interest._

_The first JAVASCRIPT (#1) serves as a container to declare the two functions:_

* _exec function():which recalls the updating function of the current Page:_

_extERefreshCurrentDashbaord()_

* _Wait() Function: which recalls the display function of the wait image:_

&#x20;_extShowWait()_

_EXECUTE BUTTON (#2) runs the query to update the data entered in the mask._

_In the JavaScript the Execute button has two functions associated:_

* _JavaScript-code-before: before the update, but after clicking the button, it runs the function to display the wait icon: “Wait()”_
* _JavaScript-code-after: after updating the data, it runs the Page update function “exec()”_

_The second JAVASCRIPT (#3) occupies a specific position inside the Page page, since a printing function for the current date and time is declared inside it._

Step 2: Viewing in DAC

![](<../../.gitbook/assets/119 (1).png>)

_Viewing in DAC_

_Step 1: the user enters the data in a mask and presses the Add to Order ( Execute button) button)_

_In a completely transparent manner for the user, the system runs the update query showing the wait icon._

_Step 2: At the end of the query the icon disappears and the Page is updated:_

_Note that the report shows an additional row with the last data entered._

_In the top right the current date and time are displayed._

## Social Spaces

The Social spaces Widget correspond to those used in DAC by the administrators of the social spaces.

In the Page Designer, it will be possible to use and configure them based on the properties. The property present in all social spaces widgets is:

* **Spaces-associated**

The categories are as follows:

| ![](<../../.gitbook/assets/120 (2).png>)[Others](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Others)                                                                                                                                                           | ![](<../../.gitbook/assets/121 (2).png>) [Users](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_User)         | ![](<../../.gitbook/assets/122 (2).png>) [Contents](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Content)   | ![](<../../.gitbook/assets/123 (1).png>) [Sub-Spaces](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Sub-Spaces) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| <p><img src="../../.gitbook/assets/124 (1).png" alt=""> <a href="/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Signal">Signals</a></p><p><img src="../../.gitbook/assets/125 (1).png" alt=""> <a href="/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Task_2">Tasks</a></p> | ![](<../../.gitbook/assets/126 (1).png>) [Bookmarks](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Bookmark) | ![](<../../.gitbook/assets/127 (1).png>) [Documents](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Document) |                                                                                                       |

### Content

The _Content List_ is the widget for generic content. All of the other content has properties that have already been assigned a value, so that they can be offered as pre-packaged items in the Web environment.

The specific properties of **Content View** are:

* _**content-association-type**_: criteria that need to have the following items:
  * _MOST-LIKED_, the most voted as liked
  * _MOST\_RECENT_, the most recent
  * _MOST\_VIEWED_, the most viewed
* _**content-types:**_ select the content to be published, selected from the Documents, Blog Posts, and Signals

![](<../../.gitbook/assets/128 (1).png>)

The _Content View_ allows you to view a Document or Blog post in an expanded manner.

The specific properties of **Content View** are:

* _**content-association-type:**_ criteria with which the document or blog post was selected:
  * _MOST-LIKED_, the most voted as liked
  * _MOST\_RECENT_, the most recent
  * _MOST\_VIEWED_, the most viewed
  * _SELECTED, to select a specific document or blog post. This property enables:_
    * _content-selected_: content to be published, selected from a list of all of the documents or blog posts (based on that specified in the successive properties)
* _**content-types:**_ type of content to be published, selected from the Documents and Blog Posts
* _**Template-style**_: publication style, selected from the preview or editing

The other widgets are:

* **List of latest Contents** displays the list of the latest content

Equivalent to a Content List configured with:

*
  * _**content-association-TYPE**_ _MOST\_ RECENT_
* **List of most viewed content** displays the list of the most viewed content

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_VIEWED_
* **List of popular contents**, displays the list of the most popular content

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_

### Document

All the widgets related to documents can be customized b&#x79;_:_

* **List of most popular content** displays the list of the most popular signals

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_
  * _**content-types**_: Document
* **List of latest Contents** displays the list of the latest documents

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ RECENT_
  * _**content-types**_: Document
* **List of most viewed documents** displays the list of the most viewed documents

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_VIEWED_
  * _**content-types**_: Document
* **Most popular documents** displays the most popular document

Equivalent to a _Content List_ configured with:

*   _**content-association-TYPE**_ _MOST\_ LIKED_

    _**content-types**_: Document
* **Latest documents** displays the latest documents

Equivalent to a _Content List_ configured with:

*   _**content-association-TYPE**_ _MOST\_ RECENT_

    _**content-types**_: Document
* **Most viewed documents** displays the most viewed document

Equivalent to a _Content List_ configured with:

*   _**content-association-TYPE**_ _MOST\_VIEWED_

    _**content-types**_: Document
* **DOCUMENT** displays a specific document

Equivalent to a _Content List_ configured with:

* _**content-association-TYPE**_ _SELECTED_
* _**content-types**_: Document

This component has the following properties enabled:

*
  * _**content-selected**_: document to be published
  * _**Template-style**_: publication style, selected from the preview or editing

### Bookmark

The _All Bookmarks_ widget is the generic way of collecting bookmarks sent to the associated spaces; all of the others have a property with a value that has already been assigned in order for the items to be filtered based on the object type.

The properties of the **All bookmarks** are:

* _**object-types:**_ type of objects to which the bookmarks are assigned, including:
  * _AREA\_GROUP_, bookmarks assigned to the social groups
  * _AREA\_INITIATIVE_, bookmarks assigned to the initiatives
  * _AREA\_NORMAL_, bookmarks assigned to the areas
  * _BLOG_, bookmarks assigned to the blog posts
  * _DOCUMENT_, bookmarks assigned to the documents
  * _TASK_, bookmarks assigned to the _tasks_
  * _REPORT_, bookmarks assigned to the _reports_
  * _USER_, bookmarks assigned to the users
  * _DASHBOARD_, bookmarks assigned to the page

The other widgets are:

* **Documents as bookmarks** displays the list of bookmarks assigned to the reports

Equivalent to a _Tasks List_ configured with:

*
  * _**object-types:**_ _DOCUMENT_
* **Documents as bookmarks** displays the list of bookmarks assigned to the pages

Equivalent to a _Tasks List_ configured with:

* _**object-types:**_ _Dashboard)_
* **Spaces as bookmarks** displays the list of bookmarks assigned to the social spaces, for any type

Equivalent to a _Tasks List_ configured with:

*
  * _**object-types:**_ _AREA\_GROUP, AREA\_INITIATIVE, AREA\_NORMAL_
* **Documents as bookmarks** displays the list of bookmarks assigned to the documents

Equivalent to a _Tasks List_ configured with:

* _**object-types:**_ _DOCUMENT_
* **Blog posts as bookmarks** displays the list of bookmarks assigned to the Blog posts

Equivalent to a _Tasks List_ configured with:

* _**object-types:**_ Blog

### Task

The specific properties of the **TASK List** are the following:

* _**statuses**_, task status:
  * _NEW_, newly created tasks
  * _ACCEPTED_, accepted tasks
  * _CLOSED_, closed tasks
* _**group-by**_, type of grouping of the listed tasks, with respect to:
  * _CATEGORY_
  * _ASSIGNEE_
  * _PRIORITY_
  * _STATUS_
  * _AREA,_ social space
  * _SCHEDULE\_DATE_
* _**assignee-type**_, whether or not the assignee has been defined:
  * _ASSIGNEE\_STATUS\_DEFINED_
  * _ASSIGNEE\_STATUS\_NOT\_DEFINED_
  * _ASSIGNEE\_STATUS\_ALL_, all tasks independent of whether or not an assignee has been assigned
* _**additional-info**_, additional information to be entered in the tasks in the list:
  * _CATEGORY_
  * _ASSIGNEE_
  * _STATUS_
  * _Area,_ social space
  * _SCHEDULE\_DATE_, schedule date
  * _DUE\_DATE_, due date

The other widgets are

* **All tasks** displays the list of active tasks, ordered by priority and grouped by schedule date

Equivalent to a _Tasks List_ configured with:

*
  * _statuses NEW, ACCEPTED_
  * _group-by SCHEDULE\_DATE_
  * _order-by PRIORITY_
* **Tasks assigned by category** displays the list of tasks grouped by category

Equivalent to a _Tasks List_ configured with:

*
  * _group-by CATEGORY_
* **Task assigned by person** displays the list of tasks grouped by assignee

Equivalent to a _Tasks List_ configured with:

*
  * _group-by ASSIGNEE_
* **Tasks assigned by category** displays the list of tasks grouped by priority

Equivalent to a _Tasks List_ configured with:

*
  * _group-by PRIORITY_
* **Tasks assigned by schedule date** displays the list of tasks grouped by schedule date

Equivalent to a _Tasks List_ configured with:

*
  * _group-by SCHEDULE\_DATE_
* **Unassigned task** displays the list of tasks without assigning them

Equivalent to a _Tasks List_ configured with:

*
  * _assignee-type ASSIGNEE\_STATUS\_NOT\_DEFINED_

### Signal

All the widgets related to the signals are customized by the following _Content list_:

* **List of most popular Signals** displays the list of the most popular signals

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_
  * _**content-types:**_: Signal
* **List of latest Blog Posts** displays the list of the most recent posts

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ RECENT_
  * _**content-types:**_: Signal
* **List of Most viewed blogs posts** displays the list of the most viewed posts

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_
  * _**content-types:**_: Signal

### User

The widgets for **Associated members** displays the list of associated members There are not any specific properties.

### Sub-Spaces

The other widgets are:

* **The sub-areas** displays the list of the sub-spaces for the area type

Equivalent to a _Tasks List_ configured with:

*
  * _**Sub-Spaces-types:**_ _SOCIAL\_AREA_
* **The sub-areas** displays the list of the sub-spaces for the group type

Equivalent to a _Tasks List_ configured with:

*
  * _**Sub-Spaces-types:**_ _SOCIAL\_GROUP_
* **The sub-areas** displays the list of the sub-spaces for the area type

Equivalent to a _Tasks List_ configured with:

*
  * _**Sub-Spaces-types:**_ _SOCIAL\_INITIATIVES_

### Others

_Activity Streams_ is the widget which displays the list of activities made by the users in the social space.

The specific properties for this component are:

* **Discussion type associated with the** type of discussions that need to be collected in the activity stream

A pop-up list of the available types: signals, documents, blog posts, tasks, and discussions opened directly in the activity stream (standard)

_Selected Page_ is the widget which displays a page in the social space.

The specific properties for this component are:

* **Application**-**selected**:
* **page-selected:** selection of the page to be displayed in the social space
