# Drill-through

A Drill-through can recall an object from a report such as:

* Another report
* A Page
* An App
* A Web Page

The drill-through (in short DS) can be activated both from dimensional levels and from report metrics. You can also associate it with the report for opening a Page, including some forms, from which you can “command” the calling report, i.e., to filter it in real time according to the choices made in the forms (Top-type DS).

It is possible to set more than one DS (up to 25) for the same report, each of which can execute different actions.

During DS there is a [parameter transfer](drill-through.md#parameters-transfer) from the report to the _called_ object: every time the opening parameters are modified, the object will not be taken by the user session cache, but it will have to be _re_-_executed_ by accessing the Data Model, of cache or on the data, according to the settings.

Once activated the user displays a predefined icon (only in DAC). The system allows you, however, to set custom icons.

![](<../../../../.gitbook/assets/0 (8).png>)

A DS is activated by setting the properties of the **Drill-through**, group in the report editing window:

1. in _**drill-groups**_, you can define the number \[_n]_ of DSs that you want to set in the report; for each of them, the properties _activatedrillthrough\[n]_ are repeate&#x64;_;_
2. you can activate one of the DSs set by selecting the corresponding _**activate drillthrough\[n]**_ property, each of which enables the specific properties, needed for configuring:

* the [DS activation mode](drill-through.md#page-opening-mode) (_drill-through_), that tells us whether it is on a specific report level/metric or on the whole report;
* the [DS target object](drill-through.md#ds-destination-object) (_open ActionType_);
* the [page opening mode](drill-through.md#page-opening-mode);
* the setting of an [image and description associated with the DS;](drill-through.md#ds-destination-object)
* the [parameters transfer](drill-through.md#parameters-transfer)

**Note:** _In a graphic display of a report, you can open the DS by clicking on the graphic element (bar, join point on rows or areas). Only one DS is open and it is the first one defined._

## DS Activation Mode

You can activate a DS both from a specific dimensional level or report metric, and directly from the report. This mode also allows you to “command” the calling report. From the property:

* _**drill-through**_, a pop-up opens with the list of levels/metrics or the items relating to the report (_Top mode_).

![](<../../../../.gitbook/assets/1 (8).png>)

The Top modes available are as follows:

* _\<Top>_&#x61;llows you to open the DS and pass the parameters of the _calling_ report to the new page;
* _\<Top (Page filter)>_ the _calling_ report is filtered, in real time, according to the choices made on the _called_ _object._

In DAC this setting activates in the report a menu with the parameter values, chosen in the _called_ object

![](../../../../.gitbook/assets/2.png)

**Note:** _The calling report will include parametric filters, on parameters with names corresponding to those set in the object open in DS. See the following example._

Step 1: drill-through a \<Top (Page Filter)>

![](<../../../../.gitbook/assets/3 (4).png>)

_Dashboard (MainFilter) which includes two form objects (a Select element and a Checklist-type one ) is created with the list of products and clients: these will be later used to filter the calling report. The name given to the components (in the form-name property) is the parameter by which the report is filtered:_

_?skuid? and ?cust?_

Step 2: drill-through a \<Top (Page Filter)>

![](<../../../../.gitbook/assets/4 (6).png>)

_We define a report including also the two levels, product and client, on which we define the two custom filters, of parametric-type: the level field key is connected (operator IN) to the parameter defined in the Page. The parameter will be inserted manually. Remember to use question marks on both sides._

_You can activate the DS on the report (activateDrillThrough1) by setting the following:_

* _in the drill-Through property, choose the item \<Top (Page filter)>_
* _in openActionType choose the item for the opening of a Page (Page Page)_
* _in the Page property, choose the Main Filter Page, created in step 1_
* _in the drillThroughDesc property you can set the “Launch Main Filter” text as the description._

Step 3: drill-through a \<Top (Page Filter)>

![](<../../../../.gitbook/assets/5 (21).png>)

_Accessing the report on DAC, the DS defined in the previous step is placed at the top:_

* _the symbol of the DS is displayed, along with the alternative description and a field with the text \<None selection>._

_Clicking on the DS link opens the associated Page MainFilter_

_The item selection, both from the menu and from the list, begin the update of the calling report, to which the filters for product and client are applied._

_In addition, you can insert a Submit type button in the Page, so that the choices made are applied only after this has been clicked._

Step 4: drill-through a \<Top (Page Filter)>

![](<../../../../.gitbook/assets/6 (4).png>)

_The values taken by the parameters are reported in the text field next to the DS._

## DS Destination Object

The settings for the object open by a DS are chosen with the property _**openActionType**_:

* **REPORT -** _-_ Opens another report.

This item enables the property:

*
  * _**report**_ for the selection, in the catalog, of the report to open (see [example](drill-through.md#example-ds-to-a-report))
* **PAGE** - Opens a Page.

This item enables the property:

*
  * _**Page**_ to select one of the Pages created with Page Designer (see [example](drill-through.md#example-of-passing-parameters-from-pages-to-reports))
* **OPEN URL** - Opens a page or web application, using the report parameters.

This item enables the property:

*
  * _**drill-through-URL**_ where you specify the URL page address (see [example](drill-through.md#example-ds-to-a-url)).

### Example DS to a Report

Step 1:drill-through on a Report

![](<../../../../.gitbook/assets/image (107).png>)

_We associate the drill-through with the level MONTH (drill-through property) and do NOT select the option openNewWindow; the destination report (“01 – Test pageby shared”) will be, then, open in the same page as the initial one._

_NOR do we select the apply-sel-as-filter property, therefore the values, exported through drill-through, will not affect any filter on the destination report data._

Step 2: Drill-through on a Report

![](<../../../../.gitbook/assets/image (183).png>)

_From the DAC, the initial report will display then the drill-through on the values of the level MONTH. If you click to open one of them, the target report will be displayed in the same page as the initial one._

Example - DS to a Page

Step 1: Drill-through to a Page

_We associate the drill-through with one of the report dimensional levels (Project in this case) using, as before, the drill-through property. We ask the system to open, when we click on the drill executed from the Web module, a Page (Project Details) in a new page measuring 650 by 600 pixels._

_Furthermore, we specify that we want to filter the data of the target page (apply-sel-as-filter) with a “view-filter”, using the values exported from the report._

Step 2: Drill-through to a Page

![](<../../../../.gitbook/assets/9 (23).png>)

_We then insert the report in a Page presenting it both as Crosstab element and as graph. You can perform the drill-through to the target Page both from the Crosstab object and from the Graph object, both associated with the initial report. The only difference is that, in the graph, the symbol that indicates the drill-through is not visible, but if you move the mouse to the values of the Project level, you can see the pointer, indicating possibility of connecting to the new Page._

Step 3: Drill-through to a Page

![](<../../../../.gitbook/assets/10 (22).png>)

_Using the drill-through, on one of the values of the Project level (ex. APPLICATION), we will be able to open the linked page with a report that has been correctly filtered by the value of the exported level._

### Example DS to a URL

Step 1: Drill-through to an External Application

![](<../../../../.gitbook/assets/11 (24).png>)

_We have a web application that allows users to analyze the development stages of a software and that is used to display and/or edit the corresponding use cases (UseCase, acronym UC). The application uses the UC\_ID\_Name parameter, the username of the current UC. We want to call this application from a DAC report_.

Step 2: Drill-through to an External Application

![](<../../../../.gitbook/assets/12 (21).png>)

_In the report we insert a level with the UCs of the software._

Step 3: Drill-through to an External Application

![](<../../../../.gitbook/assets/13 (22).png>)

We define a URL-type DS :

* in _openActionType_ we choose the item _Open URL_
* in the _drill-through-URL_ property we insert the application address
* in the _request-param-names_ property we set the name of the parameter UC recognized by the application, different in this example from the name of the level

Step 4: Drill-through to an External Application

![](../../../../.gitbook/assets/14.png)

_Using he drill-through in DAC, the system exports the value you have clicked on (in the example: “4.0.0.0\~FS.KPI.GEK.001”) and the application interprets it correctly by displaying the page for that specific UC._

_Note that the parameter relating to the UC is not the only parameter exported from the drill-through, even if it is the only one actually used._

## Page Opening Mode

The DS can open in a new page, or it can replace the calling page: the opening mode is set in the _**openNewWindow**_ property.

If the DS opens in a new window (_openNewWindow_ enabled), the following properties are enabled:

* _**full-screen**_ to open in full screen mode
* _**window-wiDSh**_ and _**window-height**_ for window dimensions (these are visible if full-screen mode has not been _chosen)_
* _**open-in-same-window and modal-window disabled:**_ _every_ link of the DS opens a new window.
* _**open-in-same-window**_ enabled: allows you to open all DSs in the same window. This way, you do not need to close the window opened in DS to be able to display another one (visible only if modal-window is disabled).
* _**modal-window**_ _enable&#x64;**:**_ allows you to open the window in modal mode. This means that the window remains active until shut down, preventing access to the calling report (visible only if _open-in-same-window is disabled_).
* _**repaint-opener**_ to redraw the calling report when the window close&#x73;**:** the report reads the data in the datamart again.

## Parameters Transfer

When a DS opens a report or a Page, you can transfer the following to these:

* the elements associated with the rows (or column) of the calling report
* the parameters in the Page that includes the calling report

You can customize the parameter management using the drill-through properties, in the calling report.

The properties for the parameter passage depend on the target object selected in _**openActionType**_.

For all the types of _**openActionType**_ the following are available:

* _**change-param-names**_ to modify the name of the levels and metrics transferred through the DS; a window opens in which you can assign the new names.

_**Note:**_ _The change of parameters is particularly useful if you need to distinguish the parameter passed in the new page from the one present in the same page._

_For example, the transfer of the level MONTH to a second dashboard, opened in DS, is necessary as a filter on some objects, while for others it is not: we rename this level in the_ _**change-param-names**_ _property_ _of_ _the calling report and we use this second name in the filters of the destination objects._

* _**total-behavior**_ to set the transfer mode for the values of the levels in page-by, when they are selected in \[Total]. You can choose one of the following:
  * _\<total>_ ignores the level, so that no value is passed
  * _\<page-by-content> all values listed_ in the page-by are instead passed
  * _\<Previous drill-through- value_> the values selected in page-by are passed, not those of the calling report, but those selected in a previous DS:

this property is especially useful when there are at least three DS levels , to transfer the parameters selected in the first page to a third, going through an intermediate level, where it is possible to set the _**total-behavior**_ property to _\<Previous drill-through- value>_.

The target page will only show the parameters chosen in the starting page. The following example illustrates this behavior.

* _**onlyReportParams**_ to transfer to the target page only the parameters of the report.

If this property is not selected, all parameters of the Page that includes the report are passed.

While for all the types, except for Workflow Change State, the following are active:

* _**export-body-**_ _**content**_ allows you, via an ON TOP or _PAG&#x45;**-**&#x42;Y_ drill-through, to send as parameters all the elements in the body of the report. (see [example](/broken/pages/-MjDoXUz10A2eG7ylGjx#_Esempio_Valori_del))
* _**sent-parameters**_ to select the levels that must be passed as parameters to the called object. If no level is selected, the property assumes the \<all-parameters> value and all the levels of the report are passed as parameters.

For openActionType selected on Report and Page the following are available:

* _**apply-sel-as-filter**_, if selected, allows you to automatically filter the target report or Page with the values exported from the starting report. This is allowed when the destination object has the same levels as the starting report. Selecting this property enables
  * _**filter-type**_ where we choose whether the filter _**is**_ _\<custom_> or _\<view>_>
* _**clear-params**_ if we do not want to use the parameters placed in the user session cache.

When a Page or a report is opened in DS, these are kept in the user session cache (see _Presentation Administrator , Cache for the DAC user session_ section), together with the parameters that have been passed from the calling report.

Afterwards, if there are no changes to transferred parameters, the system will always access the user session cache. If we want the object to be executed once more, we must select the property, to reset the parameters, forcing the system to request the object once more.

_**Note:**_ _For Pages opened in DS the_ _**development-mode**_ _and_ _**refresh-page-objects**_ _properties, nonetheless, remain valid. You cannot access the session cache through these, but the components are requested again (see Presentation Administrator_ _,Updating Pages and data section)._

In the following figure, we highlight the list of parameters exported and used by the destination object, which change according to the report element the DS is associated with. In the figure, their numerical values are also reported, for clarity.

![](<../../../../.gitbook/assets/15 (19).png>)

The level placed under the columns C and D is the one labeled “Customer\_Group” (not shown in DAC).

The values of exported parameters refer to the level IDs, even if the report shows the descriptions (for example the description of the level “Customer\_Group” in column returns the FINANCIAL value, _but_ the exported value is the corresponding ID, that is, _G01_).

### Example of Passing Parameters from Pages to Reports

Step 1: Incidence Calculation

![](<../../../../.gitbook/assets/16 (19).png>)

_This example shows the publication of a report that has activated a “drill-through” on the “Product” level. Note how the property “multi-selection” is activated for the “MONTH” level with parameters : “2004 Jan”, “2004 Feb”, “2004 Mar ”._

Step 2: Incidence Calculation

![](<../../../../.gitbook/assets/17 (18).png>)

_By activating the drill-through on the “Product” level from the previous page, we obtain the transfer to the report in the figure. The report shows, for the level “MONTH” in page-by, the element “Total”; If you insert the in the report the “Previous drill-through value” property of the “Total behavior” group on the “MONTH” level, the subsequent report (target report) will contain, for the MONTH” level, the parameters chosen in the initial report._

Step 3: Incidence Calculation

![](../../../../.gitbook/assets/18.png)

_In this figure, we see how all parameters chosen in the initial report are transferred to the destination report : “Jan 2004”, “Feb 2004”, “Mar 2004”, applying then the “ Previous drill-through value” property._

Example of Exporting all the Values of the Report in DS

Step 1: Report Creation

![](<../../../../.gitbook/assets/19 (15).png>)

_The report in the figure has been configured to export values of the body of the report as parameters in DS._

_The Top type DS has been selected from the Drill-Through and the following property has been enabled: export-body-content for exporting the data contained in the report. These will then be passed to the objects in the associated Page._

_In the example, the Liguria region has been selected from page-by. As a result, the report products are filtered for that region._

Step 1: Viewing in DAC

![](<../../../../.gitbook/assets/20 (14).png>)

_After selecting a value in page-by selecting the link selector for activating the DS. Note that the Region page-by displays only the Liguria region, while Product contains all products related to the selected region._

## Image and Description Associated with the DS

You can associate an image and a tooltip to the DS in the properties:

* _**drillThroughImage**_, which will replace the default one, by selecting one of those loaded previously to the _Resource Catalog_ (_Presentation administrator, Resource Catalog_ section). This property enables the following:
  * _**image-wiDSh**_ and _**image-height**_ where we specify the height and wiDSh to assign to the image (default 0, value for which the image is displayed with the original dimensions)
* _**drillThroughDesc**_ the description of the DS is inserted, which will be presented as a tooltip to the DS link and as the title of the window opened by the DS (see example below).

If the description is not entered, this title shows the title of the Page (containing the report) of the DS points to a Page, or does not show any title of the DS points to other types of object.

For Top Type DSs, the [description](/broken/pages/-MjDoXUz10A2eG7ylGjx#_Drill-through_di_tipo) is displayed to the right of the image, in central position; in this case, if we insert HTML text, the description displayed will respect the formatting specified with the HTML code. In the other cases, ONLY the text part is displayed (as a tooltip) while the HTML tags are deleted.

Example: Image and Description for DS

![](<../../../../.gitbook/assets/21 (14).png>)

_The example shows a report where a drillThrough has been defined with an image, on a level of the report._

_The main properties set for the definition of the icon are as follows:_

_drillThroughImage: where the image was selected from the catalog of resources._

_DrillThroughDesc: DrillThroughDesc: where a description has been inserted (DS Product) that is displayed both as a tooltip for the icon, and as the title of the new window in which you open the drill-through._
