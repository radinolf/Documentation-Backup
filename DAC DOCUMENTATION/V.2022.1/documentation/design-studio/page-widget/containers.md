# Containers

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

![](<../../../.gitbook/assets/83 (1).png>)

### Container Theme

For the Page, the section and the components for the type of container make it possible to apply a theme which defines a layout style of the page and its components.

The _**theme**_ property in the _**ContainerStyle**_ group will let you choose the theme among those made available by DAC.

If the default style is set at page level all the components will have the _**Default**_ value selected for the _**theme**_ property.

Example: Container theme

Step 1: Theme selection

![](<../../../.gitbook/assets/image (225).png>)

_The figure shows a Page page to which Dark was applied as theme. This will be used in all the Page components, since the respective theme property will not be changed for any themes. Therefore all the components inherit the style of the page, i.e. the Dark theme (default(Dark)) will be applied to the table titles, the Style Selector and the Submit button_

Step 2: Viewing in DAC

![](<../../../.gitbook/assets/85 (4).png>)

_Note how all the components have inherited the Dark style defined in the Page creation phase._

### Column Container and Row Container

The **Column Container** and **Row Container** are objects that, when used in a combined mode, create Pages that re-adapt to the resolution of the screen.

In the _Row Container_ the components contained in them may be hidden (collapsed), to have a cleaner view of the page.

The characteristic of the _Column container_ is that the components contained in it will automatically be wrapped in case the wiDSh is outside the wiDSh of the same container.

For example if you restrict the browser window containing the Page, and the dimensions of the objects of the column container are too big compared to the overall space of the page, these will be wrapped.

![](<../../../.gitbook/assets/86 (3).png>)

The specific properties for the **Column Container** are (_Object_ group):

* **cells-number:** number of container columns
* **wrap-content:** if active, in case the wiDSh of the contained objects is outside the wiDSh of the same container, these will be wrapped.

The specific property for the **Row Container** is (_Object group_):

* **cells-number:** number of container rows

Step 1: Column Container using the wrap-content

![](<../../../.gitbook/assets/87 (2).png>)

_The example shows how the components contained in the Column Container will be repositioned in the page if the window changes wiDSh and height size._

* _Enter the Column Container object_
* _Set the number of cells Cells-number_
* _Enable the property to wrap the components \<wrap-content>_
* _Set the size of the container. In this case it will take up 100% of the page._
* _Enter the reports which will all have a wiDSh equal to 400 pixels._

Step 2: Page - Column Container

![](<../../../.gitbook/assets/88 (2).png>)

_Access DAC. Restrict the wiDSh of the window of the browser (from right to left)_

_The reports are automatically wrapped since their size is too big for the page which contains them._

### Table

The _**Table**_ component is a table, entered in the cell in the Page design area.

For tables, the number of rows and columns can be defined that are required to contain the Page components, which will be entered in the cells of the table.

![](../../../.gitbook/assets/89.png)

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

![](<../../../.gitbook/assets/90 (1).png>)

_In the figure a Column Container with three elements, in the last cell a graph is entered with two active properties: in the first instance it is in closed form, with an arrow which lets you open the graph._

For the components entered in a _Table_ and _Row Container_ the following is available:

* **horizontal-align** (_ContainerStyle_ group, _Container_ folder) for the horizontal alignment, which may be of the _Center, Top and Left type_

![](<../../../.gitbook/assets/91 (2).png>)

For the components entered in a _Table_ it is possible to define the grouping of cells in rows and/or columns and the vertical alignment via the properties (_Table-Cell group,_ _Object_ folder):

* **rowSpan**, **colSpan** number of rows and columns which the object must span
* **vertical-align** vertical alignment of the object compared to the cell it is contained in

Step 1: Aligning objects in a table

![](<../../../.gitbook/assets/92 (3).png>)

_The following example publishes a table near two graphs, where the graphs occupy the same space/height as the crosstab._

_Insert the Table object in the first cell, with_

* _dimensions 2x2: row-number=2, col-number=2_
* _a title_

_Insert a crosstab in the first cell of the table; in the second column insert the two graphs, as indicated in the figure._

_For the crosstab component, access the properties of the Table Cell group and set_

* _rowSpan at 2, so that it occupies 2 rows_

Step 2: Aligning objects in a table

![](<../../../.gitbook/assets/93 (1).png>)

_The Page is published in DAC as shown in the figure. Notice how the crosstab occupies two rows, while the graphics are aligned next to it._

Step 1: Page - Column Container & Row Container

![](<../../../.gitbook/assets/94 (2).png>)

_The figure shows the configuration of a Page where the Row Containers were embedded with the Column Containers. In this Page you can collapse individual components, for each section and for all the sections._

_Also, the wrap of the components was enabled._

Step 2: Page - Column Container & Row Container

![](<../../../.gitbook/assets/95 (2).png>)

_The figure shows the Page viewed in DAC._

_Step 1 and Step2: if you want to hide the filters for the brand and the product, just move to the side arrow. The section will be hidden with a click_

_Step 2 and Step 3: if you want to hide all the filters section, just select the arrow relating to the outside. This will hide the entire area dedicated to the filters, placing the graph and the report to be analyzed in the foreground._

### Tab Control

The _Tab Control_ is a Page container. It is inserted in a main Page and shows various Pages by simply selecting the TABs associated with them.

The parameters of the main Page may be used as a filter in the Pages contained in the Tab Control. Developers may define whether the filters are applied instantly (i.e. when choosing each value) or only when selecting the Pages of the Tab Control so there isn’t a refresh when selecting each parameter, but rather a single refresh requested after the selection of all the parameters of interest.

![](../../../.gitbook/assets/96.png)

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

![](<../../../.gitbook/assets/97 (2).png>)

_Create a new Page containing the Tab Selector and Tab Panel components. For the Tab Panel the following properties are set:_

* _name the name of the panel;_
* _Template-theme the theme of the container_
* _transitionEffect the type of transition for the TAB change_

_For the Tab Selector the following properties are set:_

* _tab-pages select the Page pages to be associated with the TABs_
* _tab-panel the panel name to be associated with the Tab Selector (defined before)._
* _Template-theme theme for the TABs._

Step 2: Page display

![](<../../../.gitbook/assets/98 (2).png>)

_The figure shows the Page Preview. Note that:_

* _for each Page page, a specific TAB was created, which takes the same name._
* _the Page pages can be browsed by simply selecting the desired TAB._

_If the auto-sliding property of the Tab Selector object had been enabled, this would have made the sliding of the Pages automatic._

### Wizard (Deprecated)&#x20;

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

The **Wizard** object builds a succession of pages in order to define an application.

The Wizard object is shown as a container of a defined number of pages referred to as _Steps_. In each individual _Step_ of the Wizard, a Page is associated, containing one or more defined parameters in the appropriate property group. You can explore the wizard by clicking on each individual step or with the “back”, “forward” buttons.

![](<../../../.gitbook/assets/99 (2).png>)

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

### Inner Container (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

**The Inner Container** is an object which shows a box in a Page which points to a specific URL: for example, an application.

The URL may be defined in a dynamic manner by entering the parameters.

The only specific property is the one concerning the entry of the URL:

* _**url**_ (_Main_ group of the _Object_ folder) defines the URL address which will be displayed inside the component.

It is possible to define the URL parametrically: the object will be displayed only when all parameters are valued.
