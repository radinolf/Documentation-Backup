# Page Designer

### Page presentation

The Application can contain one or more **pages** where the business user can analyze data, collaborate with colleagues, perform analysis and take actions. DAC pages are designed using the "Design Studio" and consumed in "DAC". Pages are composed using one or more widgets. Widgets can be entered on the Page, making the applications and data analyses particularly efficient. In addition the layout was designed so that you can have the most complete picture possible on a single page. The page structure and layout are defined in **Decisyon App Composer** and distributed to the final users using the **DAC** module, which is an intuitive interface, even for inexperienced users.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/1.PagePresentation/PagePresentation.mp4" %}

### Page Widget

**Widgets** are the fundamental bricks of a page and provide specific functionalities that you can leverage to build your page. Each widget has its own configuration properties; a page contains one or more widgets and you can also create interactions on them and they can leverage the same data.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/Widget/Widgets.mp4" %}

### Page Creation

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/3.PageCreation/PageCreation.mp4" %}

#### Default Title for a Page

When you create a new page, the Page Design starts a wizard that allows you to set the name for the page (see image below). The title defined in the Page Design Catalog will be associated by default with the page container. This way, you can easily and quickly create new pages and assign the name.

In the group **Title** of the **Container** folder, the property **show-title** is enabled by default and the property **title-text** is set as **%PAGE\_TITLE%.**

When you access **DAC**, the title of the page will be the same as the name defined in the Page Design catalog.

### Page Publishing

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/4.PagePublication/PagePublishing.mp4" %}

**Page Preview**

When designing a Page, it is possible to get a preview by accessing the **View Page** button.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/PageDesigner/001.png)

The system opens the browser and displays the preview of the page selected in the catalog.

To open the preview DAC starts the local DAC, if not yet started and, automatically manages the authentication of the user without having to insert the credentials.

The system will show the preview page even if it’s not published and if it’s not associated with a Group.

### Page Element Container (Page, Section, Components)

All the Page components are entered in a container, identified by a cell in the Page Designer.

Also the Page page and the section are associated with a container.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/PageDesigner/002.png)

Components copied from another cell or from another Page can be pasted into a cell. If it is pasted on a cell ‘taken up’ by another component, the system asks for confirmation and if confirmed, the old component is removed and replaced with a new one.

In the container, define the Container Style positioning and visibility , the  (_**Container Size**_ dimensions), a title and a (_**description**_).

Some elements of the Page are enabled for the configuration of a border and a background (uniform color or images).

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/PageDesigner/003.png)

### Container Style (Positioning)

Positioning the object in the page is set through properties (_Container_ folder, _ContainerStyle group_):

* _**Position**_ for the position, defined a&#x73;_**:**_
  * _Relative_ (default), the object is positioned according to the coordinates selected by the browser and those _set_ for _top_ and _left_ (negative values are also accepted).
  * _Static_, the container is positioned according to the coordinates selected by the browser while ignoring the settings for _top_ and
  * _Absolute,_ the container is positioned on the coordinates set for _top_ and _left_, while ignoring the browser coordinates.

_The coordinates selected by the browser depend on where the object was positioned (in which cell/section)._ See the example below for further detail&#x73;_._

* _**top**_ and _**left**_ for the distance of the container, respectively from the top and from the left (in pixels)

### Container Style (Visibility )

The container may be made invisible or hidden via the properties (_Container_ folder, _ContainerStyle_ group):

* **visibility** type of visibility
* _visible (default),_ visible element
* _hidden_ element not visible, but the space taken up remains reserved
* _none_ element completely hidden, including the space taken up in the Page.

**Note:**

_The visible/hidden setting does not have a hereditary nature on the components entered in it (as a section or a container). If, for example, a table is set to hidden and the components inside it are visible, the components will be displayed._

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/PageDesigner/004.png)

This property is available both for the section and for all the components of the Page, but it is not available at page level.Step1Step 2

**Example of Page Creation with Visibility**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/DesignStudio/PageDesigner/005.png)

_The Page is made up of:_

* _Three Styled Selectors which allow the respective selection of:_
* _Customer_
* _Invoice Number_
* _Product_
* _Two Text Area components to display and change the quantity and description of the product selected._

_The Text Areas will be visible or hidden based on the result of the control queries associated with the Text Field components specified below._

* _Text Field A contains a control query on the Product Family of the selected Product. For all product families with code 10128 it will not be possible to make any change to the description. The Text Field is not visible._
* _Text Field B contains a control query on the product quantity. All the quantities <100 can be changed. The Text Field is not visible._
* _The Submit button sends the changes made to the Database through an update query._

_The control queries on the Text Fields return the two ‘hidden’ and ‘visible’ values. These two values are read by the visibility property of the Text Area objects: the parameter associated with the Text Field is typed on the visibility field._

### Container Size (Dimensioning)

####

The dimensions of the container may be defined in **absolute value** (pixel) or as a **percentage**. By default **auto-expand** is activated with regard to the dimensions of the component, with the possibility of setting a **maximum dimension** allowed; the scrollbars are activated once this is exceeded. If the auto-expand is disabled the dimensions taken are those of the container and, if the object is larger, the scrollbars activate.

The properties for dimensioning the container are (_Container_ folder, _Container Size_ group):

* **wiDSh**: minimum wiDSh taken up by the container of the object.
* **auto-expand:** activates the auto expand of the wiDSh of the container (default). This property enables:
  * **max-wiDSh** maximum wiDSh allowed for the container
* **height:** minimum height taken up by the container of the object.
* **auto-expand:** activates the auto-expand of the height of the container (default). This property enables:
  * **max-height**: maximum height allowed for the container

The following elements are an exception to this behavior:

* Crosstab with column lock activated. In this case the wiDSh of the container must be fixed, and one scroll must appear to scroll through the columns.
* Column Container with “wrap” setting. In this case the wiDSh of the container must be fixed, and the components that exceed the wiDSh must be placed on different rows.

### Container Style ( Background and Image )

&#x20;You can customize some elements:

* the same page of the Page
* the sections of the Page
* the Table, Column and Row Container components
* the Discussion containers &#x20;

The properties for this type of customization are (_ContainerStyle group_):

* _**background-color**_ for the background color.

You can also set the transparent effect by selecting the _**Transparent**_ button, from the color selection window. This is especially useful when the components overlap with the table or section, so that the components are in the foreground.

_The property also admits a parameter of the page, through which it is possible to govern the background color of these objects. The parameter has a format rgb(x,y,z)._

_For example, where x, y and z are the numbers between 0 and 255._

* **background-image** for the image of the background (previously loaded from the resource catalog).

After selecting the image, the following properties are enabled, which will control the arrangement and size of the image.

* **fill-style**: extension style of the image
  * _none –_ **–** none
  * _fill horizontally_ – extension of the image along the horizontal axis of the container
  * _fill all_ – extension of the image over the sizes of the container.
* **position:** position of the background image compared to the container
* **repeat-style**: style of repetition of the image in the container
  * _none_ -no repetition
  * _repeat-x_ -repetition on the horizontal axis
  * _repeat-y_ -repetition on the vertical axis
  * _repeat-all_ – repetition throughout the whole container

Design Container StylePreview Container Style

The figure shows the configuration of a Page, where the following properties were defined:

* _for the container of the page:_
* _a background color (background-color)_
* _height and wiDSh (wiDSh and height) and auto expand disabled_
* _a title (Title Group)_
* _a description (Description Group)_
  * _for the table container:_
* _a background image (background-image)_
  * _Flash graphics were used for which the transparency properties for the background are available (background-graph-effect)_

### Description and Title

A title may be associated with the **container** and displayed as a text box above the object, whose wiDSh coincides with the one of the same container:

* **show-title**(_Container_ folder, _Title_ group) enables the title of the container, which activates
* **title-text: text** of the title
* **titleFontSize:** Specific the size of the font used in the title

Also a **description** may be associated with the container, displayed as an information icon which has the content of the description as tooltip:

* **show-description** (_Container_ folder, _Description_ group) activates the display of the description of the object, which activates
* **description-text:** specifies the text of the description, shown as tooltip

**Note:** _The box of the title is activated by default._

### Passing Parameters in the Page

The widgets of the Page may be made to interact with each other through passing of parameters. The interaction is enhanced by using the form type objects: these objects select or request information (such as drop-down menus, multiple or exclusive lists, or simple data entry fields).

Once the parameter is available in the page and has an assigned value, you can use it:

* to filter data retrieved in the “Time Series Chart” or “Time Series Data Table” widget
* as **a filter on other objects of** the Page with automatic or accurate management
* to filter the SQL record in a “Crosstab” or “Chart” widget
* to dynamically change the value of the widget’s property (only for supported properties)
* to import the parameters in a custom JavaScript function
* to execute a SQL statement using the value of parameters
* to create an alias for a column name
* and more

There are two types of **manners in which the filters are applied**, and they are set in the _**refreshMethod**_ property:

* Synchronized (_Synchronize_), applied to each parameter change
* On request (_OnSubmit_), applied:
  * to the selection of a button: the **Submit component**
  * When the tab of the Page is selected: _**autoSubmit**_ property selected (_Main_ groups of the page)

This property is in the Main _group_ of all data presentation components.

The dimensional levels placed in page-by automatically update all page-bys relating to the same level, present in the components published in the Page. This way, export conditions and level filter in page-by do not require setting.

This behavior can be disabled by deselecting the property relating to the page, _**expand-page-by-selections**_ (_Main_ group), which by default is enabled.

The following can be defined for the parameters of the Page page:

* **mandatory conditions**
* **default values**
* ability to **initialize the page** to the initial values

There is also **a debug** function, which allows displaying the values of the parameters and objects involved in the filters that use them.

DAC has some Java interface classes for developing a custom validation program.

### Contextuality in Pages: Parameters to Link Widget

Most of the widgets available in DAC support both parameter import and export: they can create and assign value to a new parameter or they can import and leverage the value of an existing page parameter.

Some of the widgets automatically create a parameter value while in others you need to configure the export of parameters.

Some of the widgets that automatically create parameters are:

* Form / Styled Selector
* Form / Plain Text
* Form / Text Area
* Button / Execute button

Some of the widgets that you need to configure to export parameters are:

* Data Visualization / Crosstab
* Data Visualization / Chart
* Data Visualization / Map
* Resources / JavaScript

**Example: Widget that Automatically Create a Parameter**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/1.jpg)

_The example shows inserting a widget into the page that automatically creates a parameter. Note: you are required to insert a name for the parameter. The name of the parameter is also visible in the widget’s box in Page Design._

**Example: Widget that you have to configure to export parameters**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/2.jpg)

_The example shows_

_Inserting a widget into the page that you need to configure to export parameters. When you insert this type of widget into the page, in this example the Crosstab widget, you need to check the property activate-params-export. You can export the parameter as a single value or multiple values._

_You can now configure_

1. _Which column of the report will be exported as a parameter._
2. _If the parameter is exported as a single value or multiple value. When using DAC, this changes the behavior of the controller from a single selection to multiple selection (see images)._

**Widget Parameters Menu to Display Exported and Imported Parameters**

The parameters exported and imported by the widgets inserted into the Page Design can be quickly displayed through an intuitive Widget Parameters menu.

https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/1.jpg

To display the Widget Parameters menu, simply right click on a widget of the page to enable the contextual menu, and then choose _**Show In/Out Parameters**_ item.

**Note:** The page must be in Edit mode to enable the contextual men&#x75;**.**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/4.jpg)

### Filter conditions on widgets

The parameters defined in the Page page are used as a filter for the other widgets.

The **automatic** **management** (default) applies a filter condition for each parameter exported on all the objects of the page.

The filter condition applied is:

_“Parameter\_NAME@ID IN(?Parameter\_NAME?)”_

Where _Parameter\_NAME_ is the level exported in a report (logical name) or the parameter defined in a form object.

_Parameter\_NAME_ could also arrive consequently to a Drill-through.

For each object, the filter application mode is subsequently distinguished, in the property:

* _**auto-filter type**_ by selecting one of the following:

–       _only> VIEW filter type._

–       _filters> VIEW filter type if the level is in the report, CUSTOM if the level is not there._

–       _only> CUSTOM type filter._

–       _no_ application of the filter.

The individual widgets, in addition to automatic filters, have the properties to enter other filter conditions:

* _**filter**_ opens a window to enter the condition in two separate modes:

–       property of a **component associated with a report**

–       property of a **selection/entry form component**

For the filter conditions, a content assist is active to facilitate the writing of the condition (See next paragraph).

**Content Assist filter Conditions**

When defining the filter conditions for the Page components (_**filter**_ property), _content assist_ is active that suggests possible commands, such as dimension levels list, entering some operations, the DAC tags or user variables.

With an **initial mouse** **click** on the formula definition area, you activate a menu with the dimensional levels of the application (in alphabetical order).

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/5.jpg)

By selecting the level you enable _content_ _assist_ for the selection of some special operations:

* **IN()** for the manual entry of a list of values.

If the dimensional level is descriptive, the system enters the commas inside the brackets, otherwise the values will be inserted without any commas.

* **IN (…)** if you have selected it, the system displays the list of values for the selected level in a new window in multi selection.
* **IN(\[?**_NAME\_LEVEL?]_**)** for the level chosen a filter condition is proposed on the same level, indicated as a parameter.

This way, as soon as you export the selected level (e.g. YEAR) to an object of the Page, the report will be filtered by it.

* **IN(\[?**_NAME\_PARAMETER?])_ **)** for each Page parameter, the corresponding filter condition on it is proposed.

### Exporting Dimensional Levels

The **activateExpParams** property enables the export of parameters relating to the report levels.

The **exp-levels** property opens a window where the levels are specified of the report associated with the object (_**reportAssociated**_) to be exported as parameters.

Each level can be selected and used as an import parameter.

When the export of parameters is enabled for a report, a checkbox is displayed on the levels displayed that is a single-selection box. To display a multiple-selection box, the **multiple-export** property must be set to true.

Displaying a report in DAC, which has parameter export enabled, is shown in the figure.

If the exported level has a parent dimensional level, and grouping is also enabled, selecting one of the exported levels has the effect of enabling shading on the parent level checkbox.

This indicates that child levels were exported for that level.

The adjacent example exports the DAY level, for a report that also has a WEEK parent level. When the end user selects one or more days in a specific week, a shading is automatically enabled in its checkbox.

### Mandatory Parameters

The mandatory parameters are _initially defined at global level_, i.e. applied to all the components of the Page:

1. select the _page_
2. in the **params-mandatory** property (_Parameters_ group) select the mandatory parameters, among those in the Page.
3. the components which use these parameters in the filter conditions, are replaced with a text box, where the mandatory parameters are specified;

the components will be displayed only when all parameters are value&#x64;_**.**_

The global setting may be _customized subsequently on each individual component:_

1. select the _component_
2. in the **params-mandatory-type** property (_Parameters_ group) select:

* _\<page-default>_

where all the parameters selected in the _params-mandatory_ property of the page are all considered mandator&#x79;_**.**_

* _\<custom>_

to set the specific mandatory parameters of the component; the selection of this item enables the following:

−      _**settings**_

opens a window where it is possible to select the mandatory parameters of the component, among those defined in the Page. If at least one parameter is chosen, enable:

* _**custom-message**_ defines the message to be displayed in case the mandatory parameters are not valued.

### Parameter Default Values

Default values, applied to the parameter when it is not valued, may be applied in two different ways and defined in _**apply-type**_:

* <_\<initial-value>_&#x74;he default is applied only to the first access to the Page
* <_\<default-_&#x76;alue>the default value is applied to each access

Default values are not applied if the parameters are already valued (e.g. originating from another page) when the Page is accessed.

Default values are set in the pre-selectio&#x6E;_**-values property**_ which opens a window with the list of parameters defined in the page, where for each of them it is possible to enter a default value as a constant, variable, or the result of a query.

The type of value is set in _**Type:**_

* _UNDEFINE **,**_ when a default value is not assigned
* _CONSTAN&#x54;**,**_ to define a constant value. In the case of a parameter with multiple values, the syntax permitted is as follows:

_#####value\_1#####value\_2##### ……… ##### value\_n_

* _QUERY,_ to define the default values as the result of a query. The query is inserted in the _**Value section**._

If the query result is multiple, it can only be shown for components that support multiple selection (such as multiple checklists or page-bys, or exports of levels in multiple mode). In the other cases, only the last one on the list in the query result will be selected as default value.

The query can also be defined **parametrically**. The parameter can originate from another Page page or be defined in the page itself. In the latter case, the value of the parameter is applied whenever a new value is taken on (see example below).

* _VARIABLE,_ when one of the system variables is to be applied as a value.

The variables are listed in the _**Values**_ section and correspond to the parameters of the user and group to which it belongs.

**Example: Assigning Default Value (pre-selection-values)**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/27.jpg)

_The example shows the application of the “Pre-Selection-Values property”. Note the publication of a Page with a “Text Field” object and a “Checklist” object. The “Text Field” object will have the param base name: year while the “Check List” object will have the param base name: month._

_The pre-selection-values property defines a constant for the year parameter; in this example 2007 was defined. For the month parameter, a selection query is entered of the months but filtered for the year exported from the text field (2007)._

_Note how only the months of the year entered in the “Text Field” are checked._

_By changing the value in the “Text Field”, the corresponding items in the “Checklist” are updated._

**Example of Default Value with a System Parameter (VARIABLE type)**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/28.jpg)

The following is an example using a VARIABLE parameter.

DAC will display the information relating to the logged-on user. These will be used in a data entry mask: this way, the user who loaded the data can be tracked. The information will be stored in a specific table using the _Execute Query component_.

Step 1: Page

_The figure shows the Form Material Page for entering data._

_By passing the default parameters of the page, the system will be able to initialize the data relating to the logged-on user when the Page is opened, in particular for this example:_

* _SUBJECT NAME: the full name of the logged-on user_
* _USERNAME: user login_
* _ROLE: role associated with the user_
* _ACCESS DATE: login date of the user (valued using a query)_

_The logged-on user must set:_

* _MATERIAL DESCRIPTION: configured as a selection menu with the list of materials for which quantities require entering._
* _MATERIAL QUANTITY blank field to enter the quantity of material._

_The UPDATE button updates the DB._

_The Report Material Quantity shows the quantity entered and the operator who loaded it._

**Step 2: Page**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/29.jpg)

&#x20;_The Page was created as shown in the figure. The components used are:_

* _Text Field (SubjectName) to display the complete name of the user_
* _Text Field (Username) to display the username_
* _Text Field (Role) of the role associated with the user_
* _Text Field (Date) to enter the date_
* _Select (Material\_Ds) drop-down menu valued using a query_
* _Text Field (Material\_qty) to enter the quantity of material_
* _Execute button updates the table concerning the materials_

_In this Page, user variables will be used as default values of the parameters. These variables are set using the pre-selection-values property of the page._

_The Username, SubjectName and Role parameters are associated with the Variable Type and the corresponding variable is selected in Value._

**Step 3: Page DAC**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/30.jpg)

_After logging on, access the Page._

_The system initializes form parameters as set in params-default-value, by valuing the user variables with the data of the user who accesses the Page._

_Select the material from the drop-down menu and enter the quantity. The update is executed using the UPDATE button on the table of materials. The report will be updated with the data just entered._

### Page Initialization

Restore the initial values of the parameters at the page level can also be enabled, rather than from the Params Cleaner component.

By enabling the **autoCleanParams** property (_Advanced_ group) of the Page page, the following behavior is obtained on DAC.

By selecting the page folder, the parameters return to the initial value and the filtered objects are also restored to the initial situation, i.e. when the filters had not yet been applied. This procedure also takes place when the Page is opened in drill-through.

#### Enabling Debug Mode (_Debug-_&#x6D;ode)

The debug function of the Page is enabled with the Debu&#x67;_**-mode property**_ (_Main_ group), which displays the parameters of the page, with the respective values:

* on a section within the Page, where the parameters relating to the FORM objects are listed, to the levels exported from the reports and those placed in page-by.
* This icon displays messages that are useful for understanding the status of the parameters in the page; in particular, when a parameter value is modified on the page, the system displays the parameter objects that will be updated following the change.

The items **actual parameters/submit parameters** lists all the values for that step, used respectively for synchronized updates or on command (with the _Submit component_).

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/31.jpg)

## Examples -Interaction between components of a Page

The following are examples of interaction between components of a Page:

* Dependence between two Styled Selector widgets
* Checklist component filtered by Styled Selector widget
* Crosstab component filtered by Checklist and Styled Selector widget
* Indicator components filtered by Styled Selector widget
* Graph component filtered by Crosstab widget
* Crosstab component filtered by a date range
* What if analysis

### **Dependence between Two Styled Selector Widgets**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/33.jpg)

The following example shows how to “condition” the list of values of a Select object from the selection made for another Select object. The figure shows two Select objects inserted in a Page.

Example: **Dependency of a Select object by an object Select**

https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/32.jpg

_For the first Select object, which selects the geographical area, the following properties are involved:_

* _the formName property specifies the name that identifies the component in the parameter selection windows (Area);_
* _the sql-formula property specifies the query (select LK\_AREA.ID \_ AREA, LK\_AREA.DS\_AREA from DEMO\_BI.LK\_AREA) to run to populate the component itself;_

_For the second Select object, which selects the regions, the following properties are involved:_

* _the formName property specifies the name that identifies the component in the parameter selection windows (REGION);_
* _the sql-formula property specifies the query (select LK\_REGION.ID\_REGION, LK\_REGION.DS\_REGION from DEMO\_BI.LK\_AREA) to run to populate the component itself; To “condition” the list of regions based on the area selected, the parameter ?AREA? is used in the filter as a where condition. Note that AREA is the name given to the formName property of the first Select object and that to identify it as a parameter, it is put between two question marks “?”._
* _The figure also shows the above Page page displayed in DAC before and after the filters are applied._
* _Note how in the second Select object, only the regions belonging to the geographical area of the first Select object can be displayed and selected_

### **Checklist Component Filtered by Select**

The following example shows how to “condition” the list of values of a Checklist object from the selection made for a Select object. In the Page page defined in the previous example, a Checklist type object is added in which the provinces belonging to the region selected by the Select object can be viewed and selected.

**Example: Dependence of an Object from an Object Select Checklist**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/34.jpg)

_For the Checklist object, which allows days to be selected, the properties involved are the same as those indicated for the Select components in the preceding example._

_So the name PROVINCE was specified for the formName property._

_Particular attention should be paid to the setting of the sql-formula property: in fact, to “condition” the list of the provinces to the selection made for the region, in the query (select LK\_PROVINCE.ID\_PROVINCE,LK\_PROVINCE.DS\_PROVINCE from DEMO\_BI.LK\_PROVINCE where LK\_PROVINCE.ID\_REGION=?REGION?) the ?REGION? parameter is used in WHERE condition. Note that REGION is the name given to the formName property of the second Select object and that to identify it as a parameter, it is put between two question marks “?”._

_The geographical area is selected in DAC. The system filters the regions belonging to the area just selected; a region is selected (Lazio)._

_The PROVINCE section allows selecting only the provinces in the selected region._

### **Crosstab Component Filtered by Checklist and Select**

The following example shows how to “condition” a report from the selection made both for a Select object and for a Checklist object. In the Page page defined in the previous examples, a report is added whose data is filtered by the selection of the area and region parameters defined respectively by the Select object and Checklist object.

Example

**Step 1: Dependence of a Report from an Object Select an Object and Checklist**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/35.jpg)

&#x20;_The figure shows the Page page structure in DAC. Note that the components used to apply filters and described in the previous examples were placed at the top, while a Crosstab type report was inserted at the bottom._

_For the Crosstab component, the property involved to allow the application of filters based on the selections of the Select and Checklist objects, is the filter property._

_In the example, the report is filtered by Area, Region and Province. Note that AREA, PROVINCE and REGION are the names assigned to the formName property of the objects and that to identify them as parameters, they are placed between two question marks “?”._

**Step 2:** Page in DAC

_The figure shows the above Page page displayed in DAC. Note how the report data is filtered based on the selection of the parameters AREA, REGION and PROVINCE defined in the Select and Checklist objects._

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/36.jpg)

### **Indicator Components Filtered by Select**

The following example shows how to “condition” an indicator from the selection made for a Select object. In the Page page defined in the previous examples, an indicator is added whose data are filtered by the selection of the Region and Province parameters defined in the Select and Checklist object.

**Step1: Dependency of indicators from an object Select**

_The figure shows the Page page structure in DAC._

_Note that the components used to apply filters and described in the previous examples, including the Crosstab type report, were placed at the top; an indicator was inserted._

**Step 2: Dependency of indicators from an object Select**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/37.jpg)

_For the Indicator component, the property involved to allow the application of filters based on the selections of the Select object is the filter property (as for the Crosstab component). Filters can be copied from the crosstab object and pasted to the Indicator, as shown in the figure._

**Step 3: Dependency of indicators from an object Select**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/38.jpg)

_The figure shows the above Page page displayed in DAC before and after the filters are applied. Note how the indicator is modified according to the selection of the parameters Area, Region and Province defined in the Select components._

### **Graph Component Filtered by Crosstab**

The following example shows how to “condition” a graph from the selection made on a level in a report.

Step 1: **Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/39.jpg)

_The figure shows the Page page structure in DAC._

_Note that the components used to apply filters and described in the previous examples, including the Crosstab type report and the indicator, were placed at the top._

_Insert a new graph component. Copy the filters from the crosstab component and paste them on the Graph component as shown in the previous exercise._

**Step 2: Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/40.jpg)

_The fundamental properties for allowing the component of the Crosstab type to export its levels as parameters belong to the Main group and are: activateExpParams and exp-levels._

_The activateExpParams property enables exporting parameters relating to the levels of the associated report. However, the exp-levels property specifies the levels of associated report to be exported as parameters and used as filters for other objects on the page. Then the Business Unit level is exported._

**Step 3: Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/41.jpg)

&#x20;_For the second Graph component, the property involved to allow the application of filters based on the selections of the levels of the first report is the filter property, as shown on the left._

_Note that Business\_Unit is the name of the layer exported and shown in the exp-levels property of the first report which is put between two question marks “?” to identify it as a parameter._

**Step 4: Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/42.jpg)

_The figure shows how the selection of the Business Unit level on the report “conditions” the graph._

### **Crosstab Component Filtered by a Date Range**

The following example shows how to “condition” a report from the selection made for a range of dates using two calendar type TextField objects.

**Step 1: Dependency of a Report by Two TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/43.jpg)

_As shown in the figure, TextField type objects and a Crosstab type report were inserted in a Page page._

**Step 2: Dependency Between Report and TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/44.jpg)

_The first TextField was assigned the name From, and the second To._

_For both TextField objects, the objectInputType property was set to DATE, so the date can be selected from a calendar._

_Therefore the two TextField objects allow a start and end date to be selected to define a time interval based on which the data in the report are to be filtered._

**Step 3: Dependency Between Report and TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/45.jpg)

_For the Crosstab component, the property involved to allow the application of filters based on the selections of the dates is the filter property, as shown in the figure._

_Note that From and To are the names assigned to the param base name property of the TextField objects and that to identify them as parameters, they are put between two question marks “?”._

**Step 4: Dependency between report and TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/46.jpg)

_In the figure, the report is filtered by the range that runs from February 1, 2007 to February 8, 2007_

## Example - How to use the editable report into the Smart Grid Widget

To use a report in editable mode (see Property [Report](application/report-management/report.md#introduction-to-reports)) it is necessary to use the Smart Grid Widget.

(view the Smart Grid Widget Documentation).

The specific properties of the Smart Grid Widget are:

**Object** group:

**Editing**

* **enable-editing** Enable widget data
  * **edit-mode**: select the editing mode (in-line, dialog, batch)
  * **enable import via Excel:** enable data setting via excel file
    * **import operation type:** select the type of operation that will be performed after importing the excel file (Update, Insert, Update/insert, Delete/Insert)
* **Data CRUD (Grid/Configuration)**\
  **Use report CRUD:** Use the CRUD method configured inside the report before\
  **Add button:** set the name of ADD button. Trigger to insert the item\
  **Update button:** Set the name of update button. Trigger to update the excel file\
  **Delete button:** Set the name of delete button. Trigger to delete the item

### Example - How to configure the report editable.

In this example you can understand how to configure the editable report and how to associate the report to the Smart Grid Widget.

**Prerequisites:** The Smart Grid Widget was previously imported via Widget Designer.

See Tutorial:

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/DataGrid/DataGrid2.mp4" %}



### Example - How to import the recod using the Excel files.

\
When you enable the "enable import via Excel" property present in the property group of the page designer for the Smart Grid Widget, you have the possibility to import the data through an excel file.

See Tutorial:

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/DataGrid/DownloadUpload.mp4" %}



