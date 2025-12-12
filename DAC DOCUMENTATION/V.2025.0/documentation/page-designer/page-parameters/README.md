# Page Parameters

## Introduction

The widgets of the Page may be made to interact with each other through passing of parameters. The interaction is enhanced by using the form type objects: these objects select or request information (such as drop-down menus, multiple or exclusive lists, or simple data entry fields).

Once the parameter is available in the page and has an assigned value, you can use it:

* to filter data retrieved in the “Time Series Chart” or “Time Series Data Table” widget
* as a filter on other objects of the Page with automatic or accurate management
* to filter the SQL record in a “Crosstab” or “Chart” widget
* to dynamically change the value of the widget's property (only for supported properties)
* to import the parameters in a custom JavaScript function
* to execute a SQL statement using the value of parameters
* to create an alias for a column name
* and more

There are two types of **manners in which the filters are applied**, and they are set in the _**refreshMethod**_ property:

* Synchronized (_Synchronize_), applied to each parameter change
* On request (_OnSubmit_), applied:
* to the selection of a button: the Submit component
* When the tab of the Page is selected: _**autoSubmit**_ property selected (_Main_ groups of the page)

This property is in the Main _group_ of all data presentation components.

The dimensional levels placed in page-by automatically update all page-bys relating to the same level, present in the components published in the Page. This way, export conditions and level filter in page-by do not require setting.

This behavior can be disabled by deselecting the property relating to the page, _**expand-page-by-selections**_ (_Main_ group), which by default is enabled.

The following can be defined for the parameters of the Page page:

* mandatory conditions
* default values
* ability to initialize the page to the initial values

There is also a debug function, which allows displaying the values of the parameters and objects involved in the filters that use them.

DAC has some Java interface classes for developing a custom validation program.

## Contextuality in Pages: Parameters to Link Widget

Most of the widgets available in DAC support both parameter import and export: they can create and assign value to a new parameter or they can import and leverage the value of an existing page parameter.

Some of the widgets automatically create a parameter value while in others you need to configure the export of parameters.

Some of the widgets that automatically create parameters are:

* Form / Plain Text
* Form / Text Area
* Button / Execute button

Some of the widgets that you need to configure to export parameters are:

* Data Visualization / Crosstab
* Data Visualization / Chart
* Resources / JavaScript

**Example: Widget that Automatically Create a Parameter**

![](<../../../.gitbook/assets/40 (9).png>)

The example shows inserting a widget into the page that automatically creates a parameter. Note: you are required to insert a name for the parameter. The name of the parameter is also visible in the widget’s box in Page Design.

**Example: Widget that you have to configure to export parameters**

![](<../../../.gitbook/assets/41 (4).png>)

The example shows

Inserting a widget into the page that you need to configure to export parameters. When you insert this type of widget into the page, in this example the Crosstab widget, you need to check the property activate-params-export. You can export the parameter as a single value or multiple values.

You can now configure

1. Which column of the report will be exported as a parameter.
2. If the parameter is exported as a single value or multiple value. When using DAC, this changes the behavior of the controller from a single selection to multiple selection (see images).

### Widget Parameters Menu to Display Exported and Imported Parameters

The parameters exported and imported by the widgets inserted into the Page Design can be quickly displayed through an intuitive Widget Parameters menu.

![](<../../../.gitbook/assets/42 (8).png>)

To display the Widget Parameters menu, simply right click on a widget of the page to enable the contextual menu, and then choose _**Show In/Out Parameters**_ item.

**Note:** The page must be in Edit mode to enable the contextual men&#x75;**.**

![](<../../../.gitbook/assets/43 (7).png>)

## Filter conditions on widgets

The parameters defined in the Page page are used as a filter for the other widgets.

The **automatic** **management** (default) applies a filter condition for each parameter exported on all the objects of the page.

The filter condition applied is:

_"Parameter\_NAME@ID IN(?Parameter\_NAME?)"_

Where _Parameter\_NAME_ is the level exported in a report (logical name) or the parameter defined in a form object.

_Parameter\_NAME_ could also arrive consequently to a Drill-through.

For each object, the filter application mode is subsequently distinguished, in the property:

* _**auto-filter type**_ by selecting one of the following:
  * _\<View filters_ only> VIEW filter type.
  * _\<Views custom_ filters> VIEW filter type if the level is in the report, CUSTOM if the level is not there.
  * _\<Custom filters_ only> CUSTOM type filter.
  * _\<None> no_ application of the filter.

The individual widgets, in addition to automatic filters, have the properties to enter other filter conditions:

* _**filter**_ opens a window to enter the condition in two separate modes:
  * property of a component associated with a report
  * property of a selection/entry form component

For the filter conditions, a content assist is active to facilitate the writing of the condition (See next paragraph).

### Content Assist filter Conditions

When defining the filter conditions for the Page components (_**filter**_ property), _content assist_ is active that suggests possible commands, such as dimension levels list, entering some operations, the DAC tags or user variables.

With an **initial mouse** **click** on the formula definition area, you activate a menu with the dimensional levels of the application (in alphabetical order).

![](<../../../.gitbook/assets/44 (1).png>)

By selecting the level you enable _content_ _assist_ for the selection of some special operations:

* **IN()** for the manual entry of a list of values.

If the dimensional level is descriptive, the system enters the commas inside the brackets, otherwise the values will be inserted without any commas.![](../../../.gitbook/assets/45.png)

* **IN (…)** if you have selected it, the system displays the list of values for the selected level in a new window in multi selection.
*
* **IN(\[?**_NAME\_LEVEL?]_**)** for the level chosen a filter condition is proposed on the same level, indicated as a parameter.

![](<../../../.gitbook/assets/46 (2).png>)

This way, as soon as you export the selected level (e.g. YEAR) to an object of the Page, the report will be filtered by it.

![](<../../../.gitbook/assets/47 (5).png>)

* **IN(\[?**_NAME\_PARAMETER?])_ **)** for each Page parameter, the corresponding filter condition on it is proposed.

![](<../../../.gitbook/assets/48 (5).png>)

## Exporting Dimensional Levels

The **activateExpParams** property enables the export of parameters relating to the report levels.

The **exp-levels** property opens a window where the levels are specified of the report associated with the object (_**reportAssociated**_) to be exported as parameters.

Each level can be selected and used as an import parameter.

When the export of parameters is enabled for a report, a checkbox is displayed on the levels displayed that is a single-selection box. To display a multiple-selection box, the **multiple-export** property must be set to true.

Displaying a report in DAC, which has parameter export enabled, is shown in the figure.

![](<../../../.gitbook/assets/49 (1).png>)

If the exported level has a parent dimensional level, and grouping is also enabled, selecting one of the exported levels has the effect of enabling shading on the parent level checkbox.![](<../../../.gitbook/assets/50 (8).png>)

This indicates that child levels were exported for that level.

The adjacent example exports the DAY level, for a report that also has a WEEK parent level. When the end user selects one or more days in a specific week, a shading is automatically enabled in its checkbox.

## Mandatory Parameters

The mandatory parameters are _initially defined at global level_, i.e. applied to all the components of the Page:

1. select the _page_
2. in the **params-mandatory** property (_Parameters_ group) select the mandatory parameters, among those in the Page.
3. the components which use these parameters in the filter conditions, are replaced with a text box, where the mandatory parameters are specified;

the components will be displayed only when all parameters are value&#x64;_**.**_

The global setting may be _customized subsequently on each individual component:_

1. select the _component_
2. in the **params-mandatory-type** property (_Parameters_ group) select:
   1. _**\<page-default>**_ where all the parameters selected in the _params-mandatory_ property of the page are all considered mandator&#x79;_**.**_
   2. _**\<custom>**_ to set the specific mandatory parameters of the component; the selection of this item enables the following:
      1. _**settings**_ opens a window where it is possible to select the mandatory parameters of the component, among those defined in the Page. If at least one parameter is chosen, enable:
      2. _**custom-message**_ defines the message to be displayed in case the mandatory parameters are not valued.

{% hint style="info" %}
Any parameter associated as mandatory , both used and not used in the widget, are evaluated.
{% endhint %}

## Parameter Default Values

Default values, applied to the parameter when it is not valued, may be applied in two different ways and defined in _**apply-type**_:

* <_\<initial-value>_&#x74;he default is applied only to the first access to the Page
* <_\<default-_&#x76;alue>the default value is applied to each access

Default values are not applied if the parameters are already valued (e.g. originating from another page) when the Page is accessed.

Default values are set in the pre-selectio&#x6E;_**-values property**_ which opens a window with the list of parameters defined in the page, where for each of them it is possible to enter a default value as a constant, variable, or the result of a query.

![](<../../../.gitbook/assets/51 (5).png>)

The type of value is set in _**Type:**_

* _UNDEFINE_ _**,**_ when a default value is not assigned
* _CONSTAN&#x54;**,**_ to define a constant value. In the case of a parameter with multiple values, the syntax permitted is as follows:

_#####value\_1#####value\_2##### ……… ##### value\_n_

* _QUERY,_ to define the default values as the result of a query. The query is inserted in the _**Value section**._

If the query result is multiple, it can only be shown for components that support multiple selection (such as multiple checklists or page-bys, or exports of levels in multiple mode). In the other cases, only the last one on the list in the query result will be selected as default value.

The query can also be defined **parametrically**. The parameter can originate from another Page page or be defined in the page itself. In the latter case, the value of the parameter is applied whenever a new value is taken on (see example below).

* _VARIABLE,_ when one of the system variables is to be applied as a value.

The variables are listed in the _**Values**_ section and correspond to the parameters of the user and group to which it belongs.

Example: Assigning Default Value (pre-selection-values)

![](<../../../.gitbook/assets/52 (5).png>)

_The example shows the application of the “Pre-Selection-Values property”. Note the publication of a Page with a "Text Field" object and a "Checklist" object. The “Text Field” object will have the param base name: year while the “Check List” object will have the param base name: month._

_The pre-selection-values property defines a constant for the year parameter; in this example 2007 was defined. For the month parameter, a selection query is entered of the months but filtered for the year exported from the text field (2007)._

_Note how only the months of the year entered in the "Text Field" are checked._

_By changing the value in the "Text Field", the corresponding items in the "Checklist" are updated._

### Example of Default Value with a System Parameter (VARIABLE type)

The following is an example using a VARIABLE parameter.

DAC will display the information relating to the logged-on user. These will be used in a data entry mask: this way, the user who loaded the data can be tracked. The information will be stored in a specific table using the _Execute Query component_.

**Step 1: Page**

![](<../../../.gitbook/assets/53 (2).png>)

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

![](<../../../.gitbook/assets/54 (5).png>)

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

![](<../../../.gitbook/assets/55 (3).png>)

_After logging on, access the Page._

_The system initializes form parameters as set in params-default-value, by valuing the user variables with the data of the user who accesses the Page._

_Select the material from the drop-down menu and enter the quantity. The update is executed using the UPDATE button on the table of materials. The report will be updated with the data just entered._

## Page Initialization

Restore the initial values of the parameters at the page level can also be enabled, rather than from the Params Cleaner component.

By enabling the **autoCleanParams** property (_Advanced_ group) of the Page page, the following behavior is obtained on DAC.

By selecting the page folder, the parameters return to the initial value and the filtered objects are also restored to the initial situation, i.e. when the filters had not yet been applied. This procedure also takes place when the Page is opened in drill-through.

### **Shared Parameters and Page-bys**

It is possible “to share” the parameters defined in a Page, to all the other Pages of the application, so that the choices made in Pages can affect all those which use the same parameter.

Also for page-bys you can activate sharing, so that the user has the same choices repeated on every Page. For example if a particular year is chosen in a Page, all the Pages will show the same year in the page-by levels.

The sharing of parameters and page-bys is applied at application property level (see _Parameters shared among several Pages_ section).

It is possible to "update" the page-bys with respect to the selections made in a "SELECT" or "CHECKLIST" object. By enabling the property of the **align-page-by-to-params Page** pag&#x65;**,** the following type of behavior is obtained:

* a "SELECT" or "CHECKLIST" object defined at a specific level and named with the same name as the corresponding dimensional level
* a "CROSSTAB" object, which has the same dimensional level defined in "SELECT", placed in page-by

&#x20;by selecting a level value in "SELECT", the same will be automatically displayed in the report of the same Page page.

Property of Page (align-page-by-to-params)

![](<../../../.gitbook/assets/89 (1).png>)

_One "Select" object and one "Crosstab" object are on the following Page. Note how by selecting any value in the "Select" object (in the above example "2004"), the same will be displayed in the report of the same Page page. The align-page-by-to-params property then allows aligning the parameters of a "Select" or "Checklist" object, to the page-bys (with the same name) of the reports on the same page._

### **Passing Parameters Through Page Open in DT**

In the case of Drill-through towards another Page page, the parameters on the latter can be used both of the calling report and of the Page containing the report (it therefore becomes the calling Page).

Using the property:

* _**apply-DS-auto-filters**_ (_Filter_ group)

The automatic filters are applied originating from the drill-through in which the "apply-sel-a&#x73;_**-filter" option is enabled**_”.

## Enabling Debug Mode (_Debug-_&#x6D;ode)

The Page debug function is enabled with the Debug-mode property (main group) which displays the page parameters with their respective jobs.

![](<../../../.gitbook/assets/image (592).png>)

### Page parameter values

The first parameter group 'Page parameters values' shows the list of page parameters. In the image we can see that the value selected at the top right (Tenant) is passed into the page as a parameter and the underlying report is automatically filtered for this value.

![](<../../../.gitbook/assets/image (721).png>)

### Shared page-by for active: true/false

When shared page-by active is true it means that at the application level (see Application >> Page> Page-by >> shared page-by properties) the sharing of page-by values among the reports on the page is active. When the page receives these values in this section the list is shown.

### Shared params active: true/false

Shared params active: true / false When Shared params active is true it means that at the application level (see Application property >> Page> Parameters >> activate-dsh-global-params) the sharing of the exported parameters among the pages belonging to the application. When the page receives these values in this section the list is shown.
