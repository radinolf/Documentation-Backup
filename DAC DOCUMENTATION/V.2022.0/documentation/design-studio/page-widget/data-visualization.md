# Data Visualization



Data presentation widget to display the reports created in the application using:

* a table, with the [Crosstab component](/broken/pages/-MgnwoeR4rnLcH21DIFw#crosstabs)
* a [Chart](/broken/pages/-MgnwoeR4rnLcH21DIFw#chart)
* an [**Indicator**](/broken/pages/-MgnwoeR4rnLcH21DIFw#indicator-component)
* a [Map](/broken/pages/-MgnwoeR4rnLcH21DIFw#map-google-maps)
* a Tag [Cloud](/broken/pages/-MgnwoeR4rnLcH21DIFw#cloud-type)

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

![](<../../../.gitbook/assets/0 (29).png>)

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

![](<../../../.gitbook/assets/1 (31).png>)

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

![](<../../../.gitbook/assets/2 (30).png>)

The properties of the **drill-through** group are similar to those of the report, except for the property which enables the opening of the drill-through in the same page (**open-in-same-window**).

The page defined for the drill-through is displayed in a new window, opened from the _**Detail>>**_ (in the information window associated with the marker).![](<../../../.gitbook/assets/3 (30).png>)![](<../../../.gitbook/assets/4 (30).png>)

### Indicator Component

An indicator is published using the Indicator component, which is always in the Presentation _group._ Indicators are defined in advance with the **Indicator Designer module.** Also the indicator may share the datamart of the report presentation components and configure the access to the associated report. In the Form group, the _**form-object-ID**_ property which specifies the identification of the component.

Publishing an indicator specifically involves selecting the graphic display.

DAC has **STATIC** and **FLASH** TYPE graphic **forms.**

The _**static type**_ styles are those reported in the following figure.

![](<../../../.gitbook/assets/5 (29).png>)

![](<../../../.gitbook/assets/6 (16).png>)

Interesting characteristics, for the graphic choice, are those concerning the presence or absence of threshold values and the position of the metric value compared to them:

* the values of all the thresholds (on details and on zone shifts) and the position of the KPI metric value (such as analog types)
* only the thresholds of the details and the position of the KPI metric value (such as the circle type)
* only the thresholds of thresholds without a position of the KPI metric value, but only belonging to one of the three zones (such as shape types)
* thresholds are not valued, but the position of the KPI metric is present (such as for arrow types)
* no values are present for the thresholds or the KPI metric position, but only the pertinence to a zone (such as the led and stop light types)

While the styles of the _**Flash type indicators**_ are much more versatile than the static ones and allow a greater customization.

The styles available are as follows:

* [Angular Gauge](/broken/pages/-MgnwoeR4rnLcH21DIFw#angular-gauge-indicator)
* [Bulb Gauge](/broken/pages/-MgnwoeR4rnLcH21DIFw#bulb-gauge-indicator)
* [Bullet Horizontal Gauge and Bullet Vertical Gauge](/broken/pages/-MgjDmy7ZG1x9SPLST_g#bullet-horizontal-gauge-and-bullet-vertical-gauge-indicators)
* [Cylinder Gauge](/broken/pages/-MgjDmy7ZG1x9SPLST_g#led-horizontal-gauge-and-led-vertical-gauge-indicators)
* [Led Horizontal Gauge and Led Vertical Gauge](/broken/pages/-MgnwoeR4rnLcH21DIFw#led-horizontal-gauge-and-led-vertical-gauge-indicators)
* [Linear gauge](/broken/pages/-MgnwoeR4rnLcH21DIFw#linear-gauge-indicator)
* [Thermometer Gauge](/broken/pages/-MgnwoeR4rnLcH21DIFw#thermometer-gauge-indicator)

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

![](<../../../.gitbook/assets/image (245).png>)

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

![](<../../../.gitbook/assets/8 (16).png>)

_The following properties were set in the indicator in the figure:_

* _Display indicator scale (show-tick-marks):) :_
* _Display scale values (show-tick-values)_
* _A suffix (Sales) to the values of the scale (number-suffix)_
* _Division of level 1 (large ticks) set to 10 (major-tm-number)_
* _Division of level 2 (small ticks) set to 10 (minor-tm-number)._

#### Example: ChartTickMarks Properties

![](<../../../.gitbook/assets/9 (16).png>)

_By setting the tick-value-step to 2, the values of the division of level 1 are shown every 2 ticks. However, by setting the tick-value-distance to 20, the values are offset from the indicator by 20 pixels._

#### Angular Gauge Indicator

This indicator type shows the values in angular mode, on circles, semi-circles, donuts, etc.

Customization is therefore applied to the angle, the radius and the display of the values within or outside the scale.

Angles can have the following properties (_ChartLayout group_):

* _**gauge-start-angle**_ start angle, where the beginning of the indicator scale starts (start value). The permitted values are from 0 to 360.
* _**gauge-end-angle**_ end angle, for the maximum value of the indicator scale (end value). The permitted values are from 0 to 360.

#### Example: Gauge-Start-Angle and Gauge-End-Angle![](<../../../.gitbook/assets/10 (17).png>)![](<../../../.gitbook/assets/11 (17).png>)![](<../../../.gitbook/assets/12 (14).png>)![](<../../../.gitbook/assets/13 (15).png>)

_In the example above, some ways of displaying the indicator are shown. The dotted surrounding circle only serves to graphically show how the degrees set by the gauge-start-angle and gauge-end-angle properties were calculated on the plane._

_For the first indicator, 270° was set as the start angle (gauge-start-angle) and the end angle (gauge-end-angle) was set to 0°._

_For the second indicator, 130° was set as the start angle and the end angle was set to 20°._

_The third has a start angle of 360° and an end angle of 0°. This way the indicator is round._

_The fourth indicator has a start angle of 90° and an end angle of 0°._

The properties for the radius are (_ChartLayout group_):

* _**gauge-inner-radius and**_ gaug&#x65;**-outer-radius inner and** outer radius, conditioned by the property relative to the size of the indicator

#### Step 2: Inner and outer radius

![](<../../../.gitbook/assets/14 (12).png>)

_A donut indicator is shown in the figure. This representation is given by setting the gauge-inner-radius and gauge-outer-radius properties._

Other properties for the scale and color of the indicator are:

* **place-values-**&#x69;nside (_ChartTickMarks_ group) positioning of values within indicator

**Note:** Values are positioned along the inner radius (gaug&#x65;**-**_**inner-radius)**_ and also depend on the distance from the scale (_**tick-mark-distance**_).

* **gauge-fill-**&#x72;atio (_ChartLayout_ group) glass color effect

#### Step 3: Gauge-fill-ratio

![](<../../../.gitbook/assets/15 (12).png>)

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

![](<../../../.gitbook/assets/16 (12).png>)

_The figure shows two indicators; in the first, 3D property is disabled, so the indicator is flat. 3D property is enabled for the second, so there is a three-dimensional effect._

#### Bullet Horizontal Gauge and Bullet Vertical Gauge Indicators

_Bullet_ type indicators show the value using a bar or dot inside the indicator, which is rectangular horizontal or rectangular vertical.

![](<../../../.gitbook/assets/17 (13).png>)

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

![](<../../../.gitbook/assets/18 (13).png>)

_The indicator was customized as follows:_

*
  * _plot-as-dot property enabled for the left indicator and disabled for the right one_
  * _dot/bar fill color purple (plot-fill-color)._
  * _border of dot/bar (show-plot-border) in a light purple color (border-color)_
  * _border of the three ranges in blue (border-color) with thickness equal to 2 (border-thickness)_

#### Cylinder Gauge Indicators

A **Cylinder Gauge** indicator shows a cylinder, whose fill level is the value of the indicator.

![](<../../../.gitbook/assets/19 (11).png>)

The specific properties are (ChartSpecifics _group_):

* _**cyl-radius radius**_ of the cylinder
* _**cyl-height height**_ of the cylinder
* _**automatic-fill-color**_ enables the automatic setting of the cylinder fill color, with the one for the metric. If the property is disabled, the following is enabled:
* **cyl-fill-color** for the fill color of the cylinder

Example: Automatic-fill-color

![](<../../../.gitbook/assets/20 (12).png>)

_The cylinder fill color in this example was customized by setting the following properties:_

_the automatic-fill-color property was disabled and the system automatically enables the sub-property_

_cyl-fill-color from which the desired color can be selected._

#### LED Horizontal Gauge and LED Vertical Gauge Indicators

LED horizontal and vertical indicators represent the value of the indicator by colored fluorescent bars (LED) from the start of the scale, up to the value to be reached.

![](<../../../.gitbook/assets/21 (11).png>)

The specific properties are (_ChartSpecifics group_):

* **led-size:** size of each LED bar
* **led-gap** distance between two LED bars
* **gauge-fill-**&#x63;olor background fill color of the indicator
* **use-same-fill-bgcolor** all non-active LED blocks use the same background color.

Example: Chart Specifics

![](<../../../.gitbook/assets/22 (9).png>)

_The indicator in the figure was customized by setting the properties:_

* _led-size wiDSh of LED,_
* _led-gap: distance between the LEDs_
* _gauge-fill-color: background of the indicator._

#### Linear Gauge indicator

This type of indicator represents the values using a pointer that can be customized.

![](<../../../.gitbook/assets/23 (9).png>)

* _**pointer-on-top**_ (_ChartSpecifics_ group) pointer on top
* _**pointer-radius**_ and _**pointer-sides:**_ (ChartSpecifics group) radius and number of angles of the pointer
* _**pointer-show-border (**_&#x43;hartSpecifics group) enables the display of the pointer border, by setting
* _**pointer-border-color, pointer-border-thickness**_ and pointe&#x72;_**-border-alpha color**_ , thickness and transparency of the border
* _**round-radius**_ (_ChartLayout_ group) the rounding of the angles (in pixels) of the indicator
* **gauge-fill-ratio** (_ChartLayout_ group) _glass_ color effect

Example: Chart Specifics

![](<../../../.gitbook/assets/24 (9).png>)

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

![](<../../../.gitbook/assets/25 (9).png>)

### Tag Cloud

The **Tag Cloud** is a visual representation of the values in a report.

This list is generally presented either alphabetically or randomly, with the special feature of presenting the most important words in a bigger font size. Therefore, we are talking about a weighted list.

The weight of the labels (or TAGs) depends on the frequency of use of the data you are reading. The larger the font, the higher the frequency of the key word.

![](<../../../.gitbook/assets/26 (7).png>)

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

![](<../../../.gitbook/assets/27 (6).png>)

_Create a new Page containing the Styled Selector and Tag Cloud components._

* _Styled Selector publishes a selector of the project phases (in level-associated select the Ds\_Project level)_
* _Tag Cloud presents the activities of each project phase_
* _reportAssociated: associate a report with the Style Selector level in page-by (Ds\_Project) and the activities associated with each phase in rows. The metric calculates the number of tasks for each activity._

_In the report a DS is activated towards a detail Page on the distribution of the resources of the tasks relating to the selected activity._

* _keywordReportitem: as key word for the Cloud, select the description of the activity (Ds\_activity level)_
* _occurrencesReportItem: to calculate the frequency, select the metric which calculates the number of the Tasks_
* _descriptionsReportItem: the same metric is chosen to show the value associated with the key word_

Step 2: Page Preview

![](<../../../.gitbook/assets/image (250).png>)

_The figure shows the Page preview._

_In the upper part, the Styled Selector is shown where a different project phase is specified for each TAB. Selecting one of these will let you filter the respective activities._

_Note how the different activities, based on the number of tasks, assume a different size. It is possible to check the data by consulting the associated report (on the right)._

Step 3: Viewing Page with DS

![](<../../../.gitbook/assets/29 (8).png>)

_This step shows the DS associated with the report:_

* _Select a project (CONCEPTUAL SCHEME)_
* _Select an activity Verify ER Quality. This activity has a number of Tasks equal to 24._
* _Access the detailed Page through DS._
* _The data inside the Page are filtered by the selected activity. Note that the total of the tasks in the report corresponds to those displayed in the Cloud._
