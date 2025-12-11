# Page Designer

This section describes the functions to **develop Pages**. The table lists the main subjects, with a short description and the link to the sub section, where they are described.

**Note**: For each component entered in the page, you must configure the mandatory properties. If one of them has not been configured while saving the properties, the properties will be highlighted and a warning message will be shown.

| Function/object                          | Description                                                                                                                                                                                                                                                             | Section                                                                                                               |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Page presentation and creation           | Creating a Page, presenting the components and all the available configurations and functions, with links to the part of the manual which describes them.                                                                                                               | [Page introduction and creation](page-designer.md#introduction-to-pages)                                              |
| Page publication                         | Page publication and creation of the catalog using the Organize Page Autorun page. Choosing the catalog theme and style, associating images with the Pages published on DAC.                                                                                            | [Page publication](page-designer.md#page-publication)                                                                 |
| Configuring Containers                   | Configuring element containers of the Page, such as the page, the sections and the individual components: choosing the theme, positioning, visibility, dimensions (Container Size), setting the title and description, choosing the background on the enabled elements. | [Page element container (page, section, components)](page-designer.md#page-element-container-page-section-components) |
| Configuring a Page page                  | Configuring the properties and enabling the functions, for the Page page: Action bar, default styles, updating, page-by sharing, JavaScript and CSS, etc.                                                                                                               | [Configuring a Page page](page-designer.md#elements-enabled-at-the-background-and-border-container-style)             |
| Page export                              | Enabling and configuring the exporting of PDF and Excel files of the Page. Defining the exporting of Excel files with or without a template, using Tags and dynamic templates.                                                                                          | [Page export](page-designer.md#page-export)                                                                           |
| Passing parameters among different Pages | <p>Setting the passage of parameters among several Pages:</p><ul><li>defining global parameters</li><li>selecting shared levels (shared page-by)</li></ul><p>configuring drill-through among calling Pages and called Pages</p>                                         | [Passing parameters among several Pages](page-designer.md#passing-parameters-in-the-page)                             |
| Opening Pages from external systems      | Activating the links to be used to recall the Pages from external systems, directly or by opening DAC on the pre-chosen Page.                                                                                                                                           | [Accessing Page from external systems](page-designer.md#accessing-page-from-external-systems)                         |
| Predefined JavaScript functions          | Using predefined JavaScript functions for the components which accept JavaScript code.                                                                                                                                                                                  | [Predefined JavaScript functions](page-designer.md#js-function-associated-with-updating-components)                   |

## Introduction to Pages

The Application can contain one or more **pages** where the business user can analyze data, collaborate with colleagues, perform analysis and take actions. DAC pages are designed using the "Design Studio" and consumed in "DAC". Pages are composed using one or more widgets.

Widgets can be entered on the Page, making the applications and data analyses particularly efficient. In addition the layout was designed so that you can have the most complete picture possible on a single page.

The page structure and layout are defined in **Decisyon App Composer** and distributed to the final users using the **DAC** module, which is an intuitive interface, even for inexperienced users.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/1.PagePresentation/PagePresentation.mp4" %}



To access the Page management window, select **Application >> Page Designer** from the menu bar.

![](<../../.gitbook/assets/0 (6).png>)

The _**Group**_ folder (bottom left) lists the user groups or users with Page display privileges, which is a prerogative of Page publishing. By default the page is associated with the “everyone” group.

The module consists of an area for designing the Page (_Design_ folder on the right) and a preview (_Preview_ folder on the right).

The **design area** consists of a series of cells, grouped by row, where the components (_Components_ folder, on the left) available on DAC are inserted, which are grouped by type:

* data visualization, relating to publication of reports in the modes supported by DAC, such as tables (_Crosstab_), chart, indicators, and maps provided by Google Maps (_Map_).
* _FORM_ type components, used to:
  * the selection of data by the user, such as drop-down menus, lists or text fields
  * execute actions, both towards external systems (_Execute button_), and within the same page (_Submit_ and Params Cleaner)
* components for Collaboration
* **containers**, such as tables, used for alignment
* generic components, to customize your Page:
  * An image
  * Some text, to enter free format text and especially useful to **enter HTML code** in the Page page, other than the one managed by the system
  * An object dedicated to JavaScript code to be used in the page

Customizing the Page page can be enhanced by importing JavaScript or CSS style files to be assigned to the same page.

The page default background color is light gray.

Components are published on the Page by simply dragging them into one of the cells available.

They can then be customized by accessing the object-specific properties from the _**Properties**_ folder (bottom left). The _**Properties**_ are divided into three main groups:

* _**Object**_ contains all the properties for the elements of the Page
* _**Container**_ contains all the properties for the element “containers” of the Page
* _**Advanced**_ contains all the properties of the most advanced level.

This is the method used to customize any Page element, whether it is a component inserted in a cell, or a page or row of cells (section): each time one of these elements is selected in the design area, the properties are enabled in the _Properties_ folder.

The properties of a component/element are divided into groups, some of which are common to all objects, such as the title, description and border.

When multiple objects are entered, they require alignment in the modes available in the module.

Container components can be customized to background (by associating a uniform color or an image, or making them transparent).

A pop-up menu (right button of the mouse) is enabled on the components, where the following operations can be performed:

* _**copy, paste, and delete the selected element**;_
* _**copy and paste individual groups of properties**_ or all properties of the element; this function is particularly useful because after having defined a graphic aspect for a component, such as the title, the properties of the title can be copied and pasted on the other components.

The specific properties of the page allow the user to configure the behavior and enable export Excel formats.

Also available is a shared management of the datamarts for the Page data presentation objects, in a way that optimizes the number of temporary tables necessary for the Page.

DAC allows you to execute Page connections from other systems.

**Preview: allows you to visualize** the preview of the Page

## Page Creation

To create a new Page press the **New** button. From the **Insert page name** property, assign the name to the page you are creating, while in the **Select** **Template Style** section the system displays a gallery of templates that may be used as a starting structure for the creation of a new page.

![](<../../.gitbook/assets/1 (12).png>)

Selecting the **Empty** template lets you create a page without the row and column structure already predefined in the page.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/3.PageCreation/PageCreation.mp4" %}





Example: Creating a New Page Via Template

Step 1: Example of creating a new page via template.

![](<../../.gitbook/assets/2 (10).png>)

_Access Page Designer_

_1. Select the Not-published folder._

_2. Press the New button_

_3. In the template selection window, enter the name of the new page._

_4. Select the template to use as base structure. In the example, template 3 box 1 Row has been chosen._

Step 2: Template Structure Visualization

![](<../../.gitbook/assets/3 (9).png>)

_Selecting template “3 box 1 Row” will have the structure shown in the figure, to which additional row containers and column containers can be added._

### Default Title for a Page

When you create a new page, the Page Design starts a wizard that allows you to set the name for the page (see image below). The title defined in the Page Design Catalog will be associated by default with the page container. This way, you can easily and quickly create new pages and assign the name.

In the group **Title** of the **Container** folder, the property **show-title** is enabled by default and the property **title-text** is set as **%PAGE\_TITLE%.**

When you access **DAC**, the title of the page will be the same as the name defined in the Page Design catalog.

![](<../../.gitbook/assets/4 (5).png>)

## Page Publication

Page publication and creation of the catalog using the Organize Page Autorun page. Choosing the catalog theme and style, associating images with the Pages published on DAC.

See a brief presentation of how to publish a page.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/4.PagePublication/PagePublishing.mp4" %}



To publish a Page, first set the _**display privileges**_.

In the Groups **section** of _the Page_ select:

* user groups ( button) ![](<../../.gitbook/assets/5 (9).png>)

![](<../../.gitbook/assets/6 (4).png>)

By default the page is associated with the _**Everyone**_ group. This Group is created by the system, includes all users on the system, and includes the permissions to access the application and display all objects of the application.

In the next step, the pages you want to publish in DAC are moved to the **Published** folder.

The **Published** folder catalogs the Pages that are made available to the end users, respecting the privileges assigned. The catalog defined in this way is published on DAC in the **Application section.**

The first Page in the list will be the Page, visible to the connected user, run automatically when accessing DAC.

The Catalog can be customized by applying one of the **themes and styles available for the application**.

![](<../../.gitbook/assets/7 (6).png>)

Images may be associated with the mashboard catalog, both in the home page of the models and in the detail. Additionally, you can select the mashboards to present in the home page of the models.

Images can be associated with the Page catalog, both in the home page of the applications and in the detail.

Additionally, you can select the Pages to present in the home page of the applications (see _Properties on the Pages_ section).

![](<../../.gitbook/assets/8 (6).png>)

**Page Preview**

When designing a Page, it is possible to get a preview by accessing the **View Page** button.

![](<../../.gitbook/assets/9 (4).png>)

The system opens the browser and displays the preview of the page selected in the catalog.

To open the preview DAC starts the local DAC, if not yet started and, automatically manages the authentication of the user without having to insert the credentials.

The system will show the preview page even if it's not published and if it's not associated with a Group.

## Associating Images with the Page

Associating Page images may be defined:

* &#x20;from the home page of the models
* from the Page section of the model

The insertion of the image from the home page is activated by enabling the menu using the right button on the specific Page.

Two _Edit_ or _Remove_ items are displayed, which let you remove or change the image associated with the Page, respectively.

Selecting the edit item enables the panel for the choice of the image.

![](<../../.gitbook/assets/10 (4).png>)

From the Page of the Application, the association of the image occurs by selecting the administration button placed on the bar of the Page list.

### Autorun

The _Autorun_ group is a predefined group: the Pages associated with this group are shown when accessing DAC-DS for the first time.

![](<../../.gitbook/assets/11 (4).png>)

If no Pages are entered in **Autorun** the user must select the one he wants from the catalog (see figure below).

![](<../../.gitbook/assets/12 (7).png>)

**Autorun** may be hidden in the left section of the catalog, even if the associated Pages are shown each time the user accesses DAC-DS for the first time.

The property which activates this behavior is configurable on the application (see _Hide Autorun group from the Page menu_ section).

### Associating Images with the Page Catalog

Associating images with the Page catalog is performed in DAC, directly in the Page section of the application.

The first button to the left opens the window to associate the images with the catalog. The button is enabled for administrators only.

![](<../../.gitbook/assets/13 (8).png>)

The ![](<../../.gitbook/assets/14 (5).png>) button (placed to the side of the folders and Pages) opens a menu:

* to load images (Image) to be associated both to the folders and Pages and shown as icons in the menu to the left of the Pages.

The icons associated with the Pages are only visible for the menu styles and themes that include the display of images (see _Properties of Pages, Theme and style of the Page catalog_ section).

* the preview images to be displayed in the main home page in DAC

A wizard described in the _User manual for DAC, Appendix I – Loading images,_ loads the images.

The figure below shows how the images loaded from this image setting window are applied.![](<../../.gitbook/assets/15 (4).png>)![](<../../.gitbook/assets/16 (6).png>)

Associated **Preview** images

Associated **catalog** images

Again in the image setting window, the top right button lists the catalog of the Pages published in the Organize Pages or the Page Designer catalog, thus letting you associate images and previews with Pages that are not published yet.

![](<../../.gitbook/assets/17 (4).png>)

## Page Element Container (Page, Section, Components)

All the Page components are entered in a container, identified by a cell in the Page Designer.

Also the Page page and the section are associated with a container.

![](<../../.gitbook/assets/18 (4).png>)

Components copied from another cell or from another Page can be pasted into a cell. If it is pasted on a cell ‘taken up’ by another component, the system asks for confirmation and if confirmed, the old component is removed and replaced with a new one.

In the container, define the Container Style positioning and visibility , the (_**Container Size**_ dimensions), a title and a (_**description**_).

Some elements of the Page are enabled for the configuration of a border and a background (uniform color or images).

![](<../../.gitbook/assets/19 (5).png>)

### Positioning (Container Style)

Positioning the object in the page is set through properties (_Container_ folder, _ContainerStyle group_):

* _**Position**_ for the position, defined a&#x73;_**:**_
  * _Relative_ (default), the object is positioned according to the coordinates selected by the browser and those _set_ for _top_ and _left_ (negative values are also accepted).
  * _Static_, the container is positioned according to the coordinates selected by the browser while ignoring the settings for _top_ and _left._
  * _Absolute,_ the container is positioned on the coordinates set for _top_ and _left_, while ignoring the browser coordinates.

_The coordinates selected by the browser depend on where the object was positioned (in which cell/section)._ See the example below for further detail&#x73;_._

* _**top**_ and _**left**_ for the distance of the container, respectively from the top and from the left (in pixels)

Step 1: Relative/Static Positioning

![](<../../.gitbook/assets/20 (5).png>)

_There are 3 components entered in the Page: a check list, a crosstab and a graph_

_The checklist component is shifted down by 70 pixels, leaving the relative positioning:_

* _relative position_
* _top at 70_

_Note that in DAC, the browser coordinates were assigned to the component, in addition to those set in the top property._

_If the position is set to static, the top property is ignored, and the checklist returns to the top (as in step 2)._

Step2: Positioning Absolute

![](<../../.gitbook/assets/21 (5).png>)

_The checklist component is positioned in absolute mode, under the graph: absolute position; top at 280; left at 100_

_Note that in DAC, a component with absolute positioning is ignored in the Page Designer arrangement, and the cell is considered empty: in fact the graph, which is in the next cell, is considered as though it were in the first position._

_However, the checklist component, which is configured in absolute position, has been assigned the coordinates set in the top and left properties._

### Visibility (Container Style)

The container may be made invisible or hidden via the properties (_Container_ folder, _ContainerStyle_ group):

* **visibility** type of visibility
* _visible (default),_ visible element
* _hidden_ element not visible, but the space taken up remains reserved
* _none_ element completely hidden, including the space taken up in the Page.

**Note:**

_The visible/hidden setting does not have a hereditary nature on the components entered in it (as a section or a container). If, for example, a table is set to hidden and the components inside it are visible, the components will be displayed._

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered.

.

![](<../../.gitbook/assets/22 (4).png>)

This property is available both for the section and for all the components of the Page, but it is not available at page level.

Example Visibility

Step 1: Example of Page Creation with Visibility

![](<../../.gitbook/assets/23 (5).png>)

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

Step 2: Viewing in DAC

![](<../../.gitbook/assets/24 (5).png>)

_The three cases of value viewing in DAC are shown at the top._

_Note how the quantity or description can be changed or not, based on the product selected. The box is not visible if its value cannot be changed._

### Dimensioning (Container Size)

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

Example: Container Size

![](<../../.gitbook/assets/25 (4).png>)

_The Crosstab container has a 20% wiDSh (wiDSh) and auto expand activated (auto-expand activated). The height is fixed at 200 px. The report consists of 7 columns and 100 rows. In this case the space of 20% it is not sufficient to show the entire report. Rather than a horizontal scroll appearing, due to the auto-expand, the container widens until the report shows all the columns. On the contrary, a vertical scrollbar activates for the height, since a fixed value was set._

### Description and Title

A title may be associated with the **container** and displayed as a text box above the object, whose wiDSh coincides with the one of the same container:

* **show-title**(_Container_ folder, _Title_ group) enables the title of the container, which activates
  * **title-text: text** of the title
  * **title-effect:** effect to be associated with the title; _\<page default>_ inherits the effect set at page level.

Also a **description** may be associated with the container, displayed as an information icon which has the content of the description as tooltip:

* **show-description** (_Container_ folder, _Description_ group) activates the display of the description of the object, which activates
  * **description-text:** specifies the text of the description, shown as tooltip

![](<../../.gitbook/assets/26 (4).png>)

**Note:** _The box of the title is activated by default._

### Elements Enabled at the Background and Border (Container Style)

You can customize some elements:

* the same page of the Page
* the sections of the Page
* the Table, Column and Row Container components
* the Discussion containers

The properties for this type of customization are (_ContainerStyle group_):

* _**background-color**_ for the background color.

You can also set the transparent effect by selecting the _**Transparent**_ button, from the color selection window. This is especially useful when the components overlap with the table or section, so that the components are in the foreground.

The property also admits a parameter of the page, through which it is possible to govern the background color of these objects. The parameter has a format rgb(x,y,z).

_For example, where x, y and z are the numbers between 0 and 255_.

* **background-image** for the image of the background (previously loaded from the resource catalog).

After selecting the image, the following properties are enabled, which will control the arrangement and size of the image.

* **fill-style**: extension style of the image
  * _none -_ **-** none
  * _fill horizontally_ - extension of the image along the horizontal axis of the container
  * _fill all_ - extension of the image over the sizes of the container.
* **position:** position of the background image compared to the container
* **repeat-style**: style of repetition of the image in the container
  * _none_ -no repetition
  * _repeat-x_ -repetition on the horizontal axis
  * _repeat-y_ -repetition on the vertical axis
  * _repeat-all_ - repetition throughout the whole container
* **background-effect:** effect applied to the background color.

**Note:**

_In order to have a uniform background on the web page which displays a Page, the background effects are applied to all of the page and NOT to its container; as a result, if a container of the page has a wiDSh of 50px set (regardless of auto-expand) and a red background, this color will be applied to the entire web page displaying the Page._

* **border-effect:** effect applied to the border of the container.
  * _thin_: the border is defined with a thin line
  * _rounded_: the border is defined with a thin line and rounded corners
  * _shadow_: border with shadow
  * _rounded and with shado&#x77;**:**_ border with rounded corners and shadow.

![](<../../.gitbook/assets/27 (3).png>)

An illustrative example is below.

Example: Container Style

Step 1: Design Container Style

![](<../../.gitbook/assets/28 (3).png>)

The figure shows the configuration of a Page, where the following properties were defined:

*
  *
    *
      * _for the container of the page:_
* _a background color (background-color)_
* _height and wiDSh (wiDSh and height) and auto expand disabled_
* _a title (Title Group)_
* _a description (Description Group)_
  *
    *
      * &#x20;_for the table container:_
* _a background image (background-image)_
  *
    *
      * _Flash graphics were used for which the transparency properties for the background are available (background-graph-effect)_

Step 2: Preview Container Style

![](<../../.gitbook/assets/29 (5).png>)

_In the Preview figure of the Page_

_If you select the icon placed near the title, a pop-up opens to show the description._

_Please note that the page has a gray background while the table has an image as a background._

_The image remains as the background also for the graphs since these were made transparent._

Example - fill-style: Image Extension Style

Step 1:- fill-style: image extension style

![](<../../.gitbook/assets/30 (5).png>)

_The Page publishes an indicator entered in a TABLE component which a background image is associated with as shown in the figure. In the example the extension style is shown of the image on the TABLE applied with the FILL-STYLE property:_

* _FILL HORIZONTALLY the background image extends along the horizontal axis of the container._
* _FILL ALL the background image extends until entirely filling the space of the container._

Step 2. Position: position of the image compared to the container

![](<../../.gitbook/assets/31 (5).png>)

_This Page publishes the same TABLE component of the previous example. In this case, the positionings available via the POSITION property are applied: the figure indicates the value selected on each container._

Step 3: Repeat Style

![](<../../.gitbook/assets/32 (4).png>)

_This Page publishes the TABLE component where the repetition styles are applied via the REPEAT STYLE property: the figure indicates the value selected on each container._

**Configuring a Page**

The Page may be customized in relation to:

* the Action Bar
* the default style of the page
* updating Pages and data
* Drill synchronization (_**Sync drill-down**_)
* sharing of the page-by (_**Shared page-by**_)
* Applying styles and controls via CSS and JavaScript
* recalling a JavaScript function after a Page object in Web environment was refreshed

### Action Bar

The Action Bar (see _DAC Manual, Action Bar_ section) lets you have information of a social type relating to the Page, in addition to containing the exporting commands.

![](<../../.gitbook/assets/33 (4).png>)

The type of information to be made visible is defined through the properties of the Action Bar group, _relating_ to the page

* **excel-export**: enables the exporting Excel configuration properties and the command on the Action Bar.
* **show-connected-users:** activates the display of the number of users connected to the Page.
* **show-Social-functions**: activates the display of the social elements (follows, likes, signals and bookmarks, direct links to the Page).
* **Refresh-page**: activates the display of the item relating to the refreshing of the Page data.
* **Initialize-page**: activates the item relating to initializing the Page.
* **Collapsed: defines** whether the bar must appear collapsed, alternatively the bar will appear directly expanded when first displayed.
* **show-in-overlay:** the Action Bar will be shown as overlapping the content of the Page page (if deactivated, it will be shown statically).

### Default Style of the Page

The container of the page lets you define other styles, compared to those of the other components (_Container_ folder, _Page Default Styles_ group):

* **background-effect:** effect applied to the background color.
* **border-effect:** effect applied to the border of the container.
  * _thin_: the border is defined with a thin line
  * _round and_: the border is defined with a thin line and rounded corners
  * _shadow_: border with shadow
  * _rounded and with shado&#x77;**:**_ border with rounded corners and shadow.
* **title-effect** effect to be associated by default with the titles of the components of the page.
* _**font-family**_ font to be associated with the Page page.

The _\<Tools default>_ value indicates that the page will inherit the font set at Tools level

* _**textfield-effect**_ effect to be applied by default to Text Field or Text Area type components in the page, selected among the following:
* _(none):_ no style
* _shadow_: shading
* _rounded:_ rounding effect
* _gradient:_ gradient effect

### Updating Pages and data

Updating the changes to the Page and the data published can take place automatically, by simply clicking on the (TAB) folder of the Page in DAC, or when the Page is opened through drill-through.

The properties are as follows:

* _**development-mode**_ (_Main_ group) automatic updating to the changes of the Page, preserving the parameters valued according to the user's selections.
* _**initialize-page**_ (_On Enter_ group) automatic updating to the changes of the Page, as if accessing with a new login (therefore the parameters will be reset)

We advise using these properties only in the Page building phase.

Instead, after creating the Page, these are disabled, in order to be able to use the user session cache (see _Cache Management, Cache for the DAC user session section_).

* _**refresh-page-objects**_ (_On Enter_) group automatic updating the data published on the Page. The components a report is associated with are re-executed, together with those a population query was assigned to (Form components).

Refreshing may also be configured at individual object level, through the _**refresh-page-objects**_ in both the components which have a report associated with them, and in the selection and entry components (FORM type).

*
  * _**evaluate-cache**_ enables the use of the cache of the reports of the Page, following the refresh-page-objects operation (see example below).

### Drill Synchronization (_Sync drill-down_)

Drill-down operations among the page components can be synchronized. When a drill-down is performed on a level in one of the reports on the page, the same operation will be performed automatically on any other report on the page, when they have the same level and the same hierarchy.

This behavior is enabled using the Sync _**drill-down property**_ (_Main_ group).

### Page-by Sharing

The page-level properties on Page-by are defined in the _**Shared**_ _**page-by**_ group. In this section, two properties can be set that are always enabled by default:

*
  *
    * _**apply-shared-page-by**_: this property lets you apply the sharing of the page-bys among more Page pages. Once the parameters of one page-by level have been selected, they will be shared by the other pages.
    * _**modify-shared-page-by**_: this property changes the parameters of the page-by level and sends the change to the other Page pages. Changes made this way can be shared.

Below is an example showing the behavior of both properties.

![](<../../.gitbook/assets/34 (4).png>)

_In the example mentioned above there are three Pages._

* _Page "A": the apply-shared-page-by and modify-shared-page-by properties are set._
* _Page "B": the apply-shared-page-by property is set._
* _Page "C": the modify-shared-page-by property is set._

_If you select a parameter from Page "A", it will only be displayed in Page "B" because the apply-shared-page-by property is enabled._

_It will not be displayed in Page "C" because the modify-shared-page-by property is enabled. If changes are made to Page page "C", they will affect Page pages "A" and "B" because the apply-shared-page-by property is enabled._

In order for parameters to be shared between Pages, you must define the global page-bys at the application level. (see Properties on the Pages, page-by sharing section).

### JavaScript and CSS of the Page

The combination of JavaScript and CSS is perfect to make a Page even more attractive and interactive.

CSSs are used to manage the page layouts and it is possible, for example, to edit the formatting of the text.

**JavaScript** is the most used language to create dynamic events, such as one that changes the content of a page depending on the actions of the end user.

JavaScript and CSS in the Pages

![](<../../.gitbook/assets/35 (4).png>)

To use customized CSS and/or JavaScript it is necessary to load them previously through the Resource Catalog module (_Presentation Administrator_, _Resource Catalog_ section) and subsequently associate them to the Page page.

For the selection of the application default files, see _JavaScript and CSS_ _Selection_ section.

CSS and JavaScript settings are configured on the Page page. By selecting the area of the page, in the properties of the folder _**Object**_ there are:

* _**css**_ (_CSS grou&#x70;**)**_

for the selection of the CSS type resources, previously created

* _**import-css-from-model**_ (_CSS grou&#x70;**)**_

to use the CSSs defined at application level

* _**import-order**_ (_CSS grou&#x70;**)**_

to establish the CSS order among those of the application and those of the page:

*
  * _AFTER_ CSS of the application AFTER those of the Page
  * _BEFORE_ CSS of the application BEFORE those of the Page
* _**javascript**_ (JavaScript _grou&#x70;**)**_

for the selection of the JAVASCRIPT type resources, previously created

* _**import-JS-from-model**_ (_JavaScript grou&#x70;**)**_

to use JAVASCRIPT defined at application level

* _**import-order**_ (_JavaScript group_)

to establish the CSS order among those of the application and those of the page:

*
  * _AFTER_ CSS of the application AFTER those of the Page
  * _BEFORE_ CSS of the application BEFORE those of the Page

Three different modes can be defined through these properties for CSS and/or JavaScript application:

* CSS or JavaScript exclusively used of the Page.

Example only for CSSs:

_**import-css-from-model disabled**_ and CSS resources selected in the _**css property**_

* CSS or JavaScript imported exclusively from the model.

Example only for CSSs:

_**import-css-from-model enabled**_ and CSS resources loaded only from the properties of the application

* CSS or JavaScript of the model and the Page.

Example only for CSSs:

_**import-css-from-model**_ enabled and CSS resources selected in the _**css**_ property; in _**import-order**_ to establish the order among those imported from the application and those selected in the css of the Page.

Below is an example of using Javascript and CSS defined at application level (second case).

Step 1: Creating CSS and JavaScript Resources with the Resource Catalog

![](<../../.gitbook/assets/36 (4).png>)

_The first step is to load the css and JavaScript files._

_Access the Resource Catalog module and select the CSS and Javascript files that will be used inside the Page._

Step 2: Associating Resources with the Application

![](<../../.gitbook/assets/37 (4).png>)

_The second step is to associate the resources with the properties of the application: in the Page section, associate the CSS and the Javascript in the related properties (also shown in the figure)._

Step 3: Defining Pages

![](<../../.gitbook/assets/38 (4).png>)

_In the Page page the import-css-from-model and import-Js-from-model properties are enabled for the CSS and JavaScript group, indicating that the Page will use the css and JavaScript imported in the application. Enter a Text component where the html code that will give the structure to your page is defined._

Step 4: JavaScript and CSS in Pages

![](<../../.gitbook/assets/39 (4).png>)

_The figure shows the end result of the Page._

_The CSS file was used for the creation of the page layout while the Javascript controls that you correctly enter the data inside the form._

_If the text entered respects the parameters set inside the Javascript file, the system considers the entry as correct and shows a green check to the side of each row. Otherwise the system returns a message in red where the correct format is specified._

### JS function associated with updating components

When Page components are updated, a Javascript function that performs custom operations can be run.

_Take for example a Crosstab object: by performing any navigation operation (e.g. page-by, drill-down), this function is recalled following the updated view of the report._ The Javascript function to be customized is:

* _**customDshObjectReloaded(PageID,objectID)**_ in the _customizations/jsLib_ folder

where the Page (_**PageID**_) that contains the component (_**objectID**_) is indicated

## Passing Parameters in the Page

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

### Contextuality in Pages: Parameters to Link Widget

Most of the widgets available in DAC support both parameter import and export: they can create and assign value to a new parameter or they can import and leverage the value of an existing page parameter.

Some of the widgets automatically create a parameter value while in others you need to configure the export of parameters.

Some of the widgets that automatically create parameters are:

* Asset Model
* &#x20;Dropdown
* &#x20;Slider
* Range Picker
* Datetime Picker
* Datetime Range Panel
* Typehead
* Form / Styled Selector
* Form / Plain Text
* Form / Text Area
* Button / Execute button

Some of the widgets that you need to configure to export parameters are:

* Data Visualization / Crosstab
* Data Visualization / Chart
* Data Visualization / Map
* Resources / JavaScript

Example: Widget that Automatically Create a Parameter

![](<../../.gitbook/assets/40 (4).png>)

_The example shows inserting a widget into the page that automatically creates a parameter. Note: you are required to insert a name for the parameter. The name of the parameter is also visible in the widget’s box in Page Design._

Example: Widget that you have to configure to export parameters

![](<../../.gitbook/assets/41 (4).png>)

_The example shows_

_Inserting a widget into the page that you need to configure to export parameters. When you insert this type of widget into the page, in this example the Crosstab widget, you need to check the property activate-params-export. You can export the parameter as a single value or multiple values._

_You can now configure_

1. _Which column of the report will be exported as a parameter._
2. _If the parameter is exported as a single value or multiple value. When using DAC, this changes the behavior of the controller from a single selection to multiple selection (see images)._

#### Widget Parameters Menu to Display Exported and Imported Parameters

The parameters exported and imported by the widgets inserted into the Page Design can be quickly displayed through an intuitive Widget Parameters menu.

![](<../../.gitbook/assets/42 (4).png>)

To display the Widget Parameters menu, simply right click on a widget of the page to enable the contextual menu, and then choose _**Show In/Out Parameters**_ item.

**Note:** The page must be in Edit mode to enable the contextual men&#x75;**.**

![](<../../.gitbook/assets/43 (4).png>)

### Filter conditions on widgets

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

#### Content Assist filter Conditions

When defining the filter conditions for the Page components (_**filter**_ property), _content assist_ is active that suggests possible commands, such as dimension levels list, entering some operations, the DAC tags or user variables.

With an **initial mouse** **click** on the formula definition area, you activate a menu with the dimensional levels of the application (in alphabetical order).

![](<../../.gitbook/assets/44 (4).png>)

By selecting the level you enable _content_ _assist_ for the selection of some special operations:

* **IN()** for the manual entry of a list of values.

If the dimensional level is descriptive, the system enters the commas inside the brackets, otherwise the values will be inserted without any commas.![](<../../.gitbook/assets/45 (4).png>)

* **IN (…)** if you have selected it, the system displays the list of values for the selected level in a new window in multi selection.
* ![](<../../.gitbook/assets/46 (4).png>)
* **IN(\[?**_NAME\_LEVEL?]_**)** for the level chosen a filter condition is proposed on the same level, indicated as a parameter.

This way, as soon as you export the selected level (e.g. YEAR) to an object of the Page, the report will be filtered by it.

![](<../../.gitbook/assets/47 (4).png>)

* **IN(\[?**_NAME\_PARAMETER?])_ **)** for each Page parameter, the corresponding filter condition on it is proposed.

![](<../../.gitbook/assets/48 (4).png>)

### Exporting Dimensional Levels

The **activateExpParams** property enables the export of parameters relating to the report levels.

The **exp-levels** property opens a window where the levels are specified of the report associated with the object (_**reportAssociated**_) to be exported as parameters.

Each level can be selected and used as an import parameter.

When the export of parameters is enabled for a report, a checkbox is displayed on the levels displayed that is a single-selection box. To display a multiple-selection box, the **multiple-export** property must be set to true.

Displaying a report in DAC, which has parameter export enabled, is shown in the figure.

![](<../../.gitbook/assets/49 (4).png>)

If the exported level has a parent dimensional level, and grouping is also enabled, selecting one of the exported levels has the effect of enabling shading on the parent level checkbox.![](<../../.gitbook/assets/50 (4).png>)

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

* _**settings**_

opens a window where it is possible to select the mandatory parameters of the component, among those defined in the Page. If at least one parameter is chosen, enable:

* _**custom-message**_ defines the message to be displayed in case the mandatory parameters are not valued.

### Parameter Default Values

Default values, applied to the parameter when it is not valued, may be applied in two different ways and defined in _**apply-type**_:

* <_\<initial-value>_&#x74;he default is applied only to the first access to the Page
* <_\<default-_&#x76;alue>the default value is applied to each access

Default values are not applied if the parameters are already valued (e.g. originating from another page) when the Page is accessed.

Default values are set in the pre-selectio&#x6E;_**-values property**_ which opens a window with the list of parameters defined in the page, where for each of them it is possible to enter a default value as a constant, variable, or the result of a query.

![](<../../.gitbook/assets/51 (4).png>)

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

![](<../../.gitbook/assets/52 (4).png>)

_The example shows the application of the “Pre-Selection-Values property”. Note the publication of a Page with a "Text Field" object and a "Checklist" object. The “Text Field” object will have the param base name: year while the “Check List” object will have the param base name: month._

_The pre-selection-values property defines a constant for the year parameter; in this example 2007 was defined. For the month parameter, a selection query is entered of the months but filtered for the year exported from the text field (2007)._

_Note how only the months of the year entered in the "Text Field" are checked._

_By changing the value in the "Text Field", the corresponding items in the "Checklist" are updated._

#### Example of Default Value with a System Parameter (VARIABLE type)

The following is an example using a VARIABLE parameter.

DAC will display the information relating to the logged-on user. These will be used in a data entry mask: this way, the user who loaded the data can be tracked. The information will be stored in a specific table using the _Execute Query component_.

Step 1: Page

![](<../../.gitbook/assets/53 (4).png>)

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

Step 2: Page

![](<../../.gitbook/assets/54 (3).png>)

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

Step 3: Page DAC

![](<../../.gitbook/assets/55 (3).png>)

_After logging on, access the Page._

_The system initializes form parameters as set in params-default-value, by valuing the user variables with the data of the user who accesses the Page._

_Select the material from the drop-down menu and enter the quantity. The update is executed using the UPDATE button on the table of materials. The report will be updated with the data just entered._

### Page Initialization

Restore the initial values of the parameters at the page level can also be enabled, rather than from the Params Cleaner component.

By enabling the **autoCleanParams** property (_Advanced_ group) of the Page page, the following behavior is obtained on DAC.

By selecting the page folder, the parameters return to the initial value and the filtered objects are also restored to the initial situation, i.e. when the filters had not yet been applied. This procedure also takes place when the Page is opened in drill-through.

### Enabling Debug Mode (_Debug-_&#x6D;ode)

The debug function of the Page is enabled with the Debu&#x67;_**-mode property**_ (_Main_ group), which displays the parameters of the page, with the respective values:

* on a section within the Page, where the parameters relating to the FORM objects are listed, to the levels exported from the reports and those placed in page-by.
* This icon displays messages that are useful for understanding the status of the parameters in the page; in particular, when a parameter value is modified on the page, the system displays the parameter objects that will be updated following the change.

The items **actual parameters/submit parameters** lists all the values for that step, used respectively for synchronized updates or on command (with the _Submit component_).

![](<../../.gitbook/assets/56 (4).png>)

## Page Export

The export of a Page is available in Excel formats

* **Microsoft Excel**, such that the reports associated with the components are exported, in a simple manner (one for each worksheet). Moreover, it is possible to repeat the export in different worksheets, each with one of the level values.

### Excel Export

DAC lets you export Pages in Excel format. The indicators and reports associated with the Page components are exported: Crosstabs, Images, and Map.

The system provides two types of export for Pages:

* _simple:_ where all the components of the Page associated with a report (such as graphs, crosstabs, indicators etc.) are exported exclusively in table format.
* _with template:_ defined beforehand, where you set in detail what to export, from the data to the elements constituting the reports, to the graphs, indicators or the parameters of the user, using suitable TAGs.

Exporting the report can be subdivided into several Excel spreadsheets. The subdivision depends on the occurrences of a dimensional level.

Exporting the Page is activated from the properties of the page, activating the Excel- _**export property**_ (_Action Bar_ group). Once the property is activated, the configurations are visible and valued, and can be associated with the export (_Excel Export_ group).

The **individual components** can be exported (Crosstab, Graph, Map, Flash Map), through the properties (_Page Excel Export_ group):

* _**export-on-excel**_ are enabled on export (default)
* _**export-titles**_ enables the exporting of the report name
* _**export-description:**_ if enabled, all the components of the Page which have a report associated with the excel-description property with a value will be exported with this description.

**Note: (template with images)**

_The template cannot contain images. The presence of images in the template could cause the image to be canceled or even make it impossible to open the exported Excel document. The exported Excel document needs to be saved again with Excel if static images are exported._

_Excel has its own way of managing images. If a spreadsheet of the exported document contains 2 or more images, any change in the spreadsheet could cause the images to be distorted. To solve this issue, just open the exported document with Excel, save it with the same name, close the document and then reopen it._

**Note: (crosstab and graph on the same report)**

_By exporting a Page containing a crosstab and a graph linked to the same report, the system reports the setting given to the graph of the_ _**col-number**_ _and_ _**row-number**_ _properties also on the crosstab, not allowing a differentiation in terms of number of rows and columns in the resulting Excel file._

_The problem may be bypassed with a copy of the report or by setting a fictitious filter in the crosstab (for example: 1=1). This way, the report is managed as a different instance and will be possible to set a different number of rows and columns for the crosstab and the graph._

#### Level exporting to several Excel spreadsheets

You can set the subdivision of a report export into multiple Excel spreadsheets in the following properties:

* _**Repeated-export**_ to enable the export of the events of a specific page-by level, contained in one of the reports in the Page: each event of the in page-by level is exported on a separate Excel spreadsheet, if there is the \[Total] item, a spreadsheet will be generated also for the aggregated data, this property enables the following:
  * _**repeated-export-**_**report** and _**repeated-export-level**_, where the report and page-by level can be respectively selected to export the values.

**Note:** All occurrences of a page-by level can only be exported if the default _expandPageSelection_ property (_Main_ group) is enabled.

#### Exporting without a template

Simple exporting, without a template, is set through the following properties:

* _**export-with-template**_ disabled (default) which activates the following:
* _**separate-sheets**_ for exporting each object to separate Excel spreadsheets
* _**export-page-title**_ for exporting the Page title (on the first spreadsheet)
* _**export page-description for**_ exporting the description of the Page (on the first spreadsheet).

Below is an example.

Step 1: Report creation

![](<../../.gitbook/assets/76 (3).png>)

_The Page page to be exported contains two objects: a Crosstab and a Graph, both associated with the same report._

_To enable Excel export, select the area of the page (shown in the figure) and select the excel-exportable property. Then enable:_

* _export-with-template left deactivated_
* _export-page-title to show the title of the Page_
* _export page-description to show the description of the Page._

Step 2: Enabling individual components for Excel export

![](<../../.gitbook/assets/77 (2).png>)

_In the second step, ensure the individual components Crosstab and Graph, were enabled for Excel export._

_Select the component, and the following properties are enabled in the Page Excel Export group:_

* _export-on-excel, to enable export_
* _export-titles to show the name of the report associated with the component_

Step 3: Viewing Page

![](<../../.gitbook/assets/78 (2).png>)

_From DAC the Page will be presented as shown in the figure: an Excel button will be shown to request the export (top left). Clicking on the button opens the window for selecting the path and setting the name of the Excel file (the one proposed by the Page)._

Step 4: Exporting Page

![](<../../.gitbook/assets/79 (2).png>)

_Excel spreadsheet that contains the Page page appears as shown in the figure above._

_Notice that the system kept the color formatting and in the case of the graph, presented the report in table format. The reports are shown below each other and the title is shown for each of them, as set in the export-titles property of the Crosstab and Graph component._

_The title and description of the Page are shown at the top, as requested using the export-title and export-page-description properties._

_Had the separate-sheets property also been set, the two tables would have been positioned on two separate sheets, with the title and description of the Page on the first sheet._

#### Exporting With Template

Exporting a Page through a template requires the existence of an Excel file to be used as a template (xlsx format), built and saved in DAC-DS.

You can set the export with template via the following properties:

* _**export-with-template enables**_ the export through a template (by default the property is disabled)
  * _**template**_ lets you select the template _**from**_ the window of the resource catalog. The file containing the template must be previously loaded in the suitable catalog.
  * _**auto-adjust-col-wiDSh enables**_ the automatic dimensioning of the columns and rows to the larger content (default). If disabled, the columns and rows have the dimension set in the template.

The template may be made up of one or more Excel spreadsheets. The cells may have any formatting.

A set of specific TAGs will allow you to customize the export. Therefore, the export operation will replace each TAG with the object indicated.

If the template contains TAGs that are incorrect or are associated with non-existent objects, the resulting report will contain some cells in red, signaling the error in question.

The two examples show the construction of a template both in the case of exporting static Pages, i.e. whose tables do not change their number of rows depending on the choices made in the report, and dynamic Pages.

**Excel export TAG**

The exporting TAGs of the Page refer to the same Page and the reports contained in them.

Those relating to the mashboard are:

* _**\<PAGE\_TITLE/>**_

Title of the Page, corresponding to the value of the _**title-text**_ property of the Page (_Container_ folder, _ContainerStyle_ group).

* _**\<PAGE\_TITLE/>**_

Description of the Page, corresponding to the value of the _**description-text**_ property of the Page (_Container_ folder, _ContainerStyle_ group).

* _**\<Parameter? KEY:?Parameter?/>**_

Exporting values of the Page parameters (parameter name of the parameter)

| **Subject**                                     | **TAGS**                                                                                | **TYPE**                                      | **Excel cell occupation**                                                       |
| ----------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------------------------- |
| **Crosstabs**                                   | _\<OBJECT\_BODY ID: id\_num />_                                                         | Table form of the report                      | 1 Cell                                                                          |
| **Graph**                                       | _\<OBJECT\_BODY ID: id\_num \[type:val]/>\<OBJECT\_BODY ID: id\_num \[type:val\|img]/>_ | Table form of the report                      | Number of cells equal to the number of row by the number of columns of the body |
| _\<OBJECT\_BODY ID: id\_num \[type:val\|img]/>_ | Graphic form of the report                                                              | Cell number on which the image is overlapped. |                                                                                 |
| **Flag Setup**                                  | _\<OBJECT\_BODY ID: id\_num \[type:val]/>_                                              | Table form of the report                      | Number of cells equal to the number of row by the number of columns of the body |
| _\<OBJECT\_BODY ID: id\_num \[type:val\|img]/>_ | Graphic form of the report                                                              | Cell number on which the image is overlapped. |                                                                                 |
| **Map**                                         | _\<OBJECT\_BODY ID: id\_num/>_                                                          | Table form of the report                      | Number of cells equal to the number of row by the number of columns of the body |
| **Textfield**                                   | _\<OBJECT\_BODY ID: id\_num/>_                                                          | Selected item                                 | 1 Cell                                                                          |
| **Textarea**                                    | _\<OBJECT\_BODY ID: id\_num/>_                                                          | Selected item                                 | 1 Cell                                                                          |
| **Image**                                       | _\<OBJECT\_BODY ID: id\_num/>_                                                          | image                                         | Cell number on which the image is overlapped.                                   |
| **Text**                                        | _\<object\_body ID: id\_num/>_                                                          | Text of the element                           |                                                                                 |

The TAGs relating to the reports of the Page to be exported are a subset of those defined for the Excel exporting of the reports (see _Report Administrator, TAG exporting reports in Excel section_) and namely:

* _\<MODEL/>_
* _\<OBJECT\_TITLE ID:id\_num/>_
* _\<OBJECT\_DESCRIPTION ID: id\_num/>_
* _\<OBJECT\_BODY ID: id\_num \[type:val|img]/>_
* _\<METADATA ID: id\_num/>_
* _\<METRICS ID: id\_num/>_
* _\<LEVELS ID: id\_num/>_
* _<\<FILTERS/> ID: id\_num/>_
* _\<LEVELS ID: id\_num/>_
* _<\<RANGE\_FILTERS/> ID: id\_num/>_
* _<\<CUSTOM\_FILTERS/> ID: id\_num/>_

For each TAG referring to a component of the report, the ID of the same report must be indicated:

_for example \<METADATA ID: id\_num/>, where id\_num is the ID number of the object you want to export;_

When exporting reports the \<OBJECT\_BODY/> TAG is used to export the body of the report in table form. For Pages, this tag is used to move the body of the report both in table and graph format, regardless of the object it is associated with.

The syntax is as follows:

**\<OBJECT\_BODY ID: id\_num \[type:val|img]/>**

In the event that the id\_num refers to an image object, the type is indicated if the table or image part is exported, as described in the following table.

**An Example of Using Static Template Files**

The static template may be used if you are sure that the rows and columns of the reports do not incur any change in height and wiDSh. The static templates are configured without the help of the NEW\_COL and NEW ROW tags. In the Excel file each object must have as many rows and columns available as there are in the associated report. Below is an example.

Step 1: Page Designer

![](<../../.gitbook/assets/80 (2).png>)

_The example above shows the Page page to be exported. Starting from the other, the following objects were entered:_

Step 2: Template Configuration

![](<../../.gitbook/assets/81 (2).png>)

_The template to export to Excel shows the same objects of the Page though arranged in the following way:_

1. _in the initial part of the page, a banner containing:_

* _Company logo and address_
* _The user who performed the analysis_
* _Date and time when the printing was carried out._

1. _in the lower part of the banner:_

* _left:_
* _year of analysis_
* _type of product brand_
* _right:_
* _Direct Unit Cost and Unit Cost of Sales report_

1. _next row:_

* _left:_

_the Year report will be used as the header of the columns, a drop-down menu will show the Unit Sales, Unit, price, Sales reports._

* _right_

_The Marketing Expense Budget report and the Annual expense Budget graph. These objects will be aligned to the center compared to the left reports. Below we will enter the Actual vs Year report in line with the Marketing Expense Budget report._

1. _In the lower part of the Excel spreadsheet, we will enter a section, Notes and signatures for approval, which will be compiled after printing._

_The image at the top shows the Excel file configured as previously described. For each object entered within, the rows and columns which will be occupied were left blank._

Step 3: Template Configuration

![](<../../.gitbook/assets/82 (2).png>)

_For example we know that the Unit Sales report occupies exactly 4 rows and 13 columns. Thus, in the Excel spreadsheet, this object was reserved as many rows as the columns required for the correct display. The same method was also used for the other elements which make up the Page._

Step 4: Export with Template

![](<../../.gitbook/assets/83 (2).png>)

_After the configuration of the template, the Page Designer is accessed again where the export property_

_activateExcExport will be activated._

_Choose the export with template from the export-mode property, while in the template-file-name property the name of the file created previously is entered._

_The figure shows the results of the export. Note that each object respects the position given inside the template._

Exporting With Dynamic Template

Exporting is defined with a dynamic template since the components of the Page do not always maintain the same dimensions, and the number of rows and columns of the reports change depending on the choices made on the Page.

Step 1: Page Designer

![](<../../.gitbook/assets/84 (2).png>)

_The example above shows the Page page to be exported. Starting from the other, the following objects were entered:_

* _images to display the logo_
* _five text fields populated by the parameters transferred to the page_
* _four reports_
* _An indicator_

Step 2: Template Configuration

![](<../../.gitbook/assets/85 (2).png>)

The template must contain the same objects of the Page but with different arrangements:

1. a banner in the initial part containing the information relating to: User, access date, year, brand, status and Logo.
2. On the next row, you want to display the indicator and the values relating to the associated metrics.
3. A drop-down menu will subsequently show the reports.
4. In the lower part of the spreadsheet a section, Note _and signatures for approval_, will be entered which may be compiled after printing.

The image at the top shows the Excel file configured as described previously.

Note that in the page, the tags NEW\_ROW and New\_Col were entered. The system automatically calculates the dimension the object occupies in the page by occupying for each one as many cells as are necessary for the correct display.

Step 3: Export with Dynamic Template

![](<../../.gitbook/assets/86 (2).png>)

After the configuration of the template, the Page Designer is accessed again where the export property

_activateExcExport_ will be activated.

Choose the export with template from the expor&#x74;_-mode property_ while in the _template-file-name property_ enter the name of the template file.

The figure shows the results of the export with Dynamic Template. Note how each object respects the position given inside the template and how the system automatically calculates how much space is required by each element.

## Activities Task

DAC offers a solution to manage activities and to assign tasks to users.

You can manage tasks in DAC through reports or Page components enabled for this purpose. In fact, it is possible to assign tasks:

* on the report cells
* on some Page components (Graph, Indicator, Table)

Recipients can be notified of tasks through e-mails which give direct access to the task. Therefore, in order to access the task, the mail server and DAC server must be configured (see _System Administrator,_ _System properties on e-mail management_ section).

### Enabling Tasks on Page Components

The Page components used during the task assignment process are:

* Tables
* Crosstabs
* Graphs
* Indicators

You can activate components for the assignment of tasks by enabling the _**activate-Task**_ property in the **Title** group.

Example: Displaying Tasks on a component: GRAPH

![](<../../.gitbook/assets/image (27).png>)

_From Page Designer, we enter the graph-type component and in the TITLE section we enable the property activate-task. The graph in DAC will display the task button next to the title_![](<../../.gitbook/assets/88 (2).png>)_. Clicking the button opens the window for inserting the new task._

### Shared Datamarts for Report Presentation Components

The system allows you to associate report presentation Page components (such as crosstabs, indicators, graphs, ...), so they use the same datamart, generated by a master component.

The other components dependent on it (slave) will NOT be executed. That is, the respective private datamart will NOT be created. The datamart for the master component will be generated before the other components, so that the dependent reports can access it. After the datamart has been changed, the reports associated with it will be upgraded to show any modified values.

This function minimizes the space required by the reports for each Page.

Components can use the datamart of a master object if the master object contains the levels of the dependent report. The following conditions must also be met:

* first-level and advanced metrics of the slave reports are to be contained in the master. The metrics required by the slave report can also be component metrics of a composite metric of the master report
* composite metrics that use the metric function (including the respective dependent metrics) of the slave reports are to be contained in the master. The metrics required by the slave report can also be component metrics of a composite metric of the master report
* the direct filters of the slave reports are to be contained in the master
* the range filters of the slave reports are to be contained in the master
* the custom filters of the slave reports must have a counterpart in the master, that is, a filter must exist in the master (direct, range or custom) such that its formula is equal to that of the custom filter of the dependent reports
* the master component cannot be defined as slave of another report

Compatibility between master and slave components is executed whenever the DAC user makes a change on the Page, using the report navigation. If they are not compatible, navigation is interrupted and an error message is shown. An error message is also received in cases where reports are changed by DAC.

Dependency is only valid in the Page where it is defined.

To define a report presentation component as slave, simply select the master report in the _**share-datamart**_ property:

* this property lists all reports that are used by the components of the Page (name and ID).

If an incompatible master report is selected, an error message will block the procedure, and indicate the reason

* the default item is \<repor&#x74;_-datamart>, which_ indicates the use of a private datamart, rather than a shared one

### Access to the Report Associated with the Component

You can access the report for the components which have an associated report. This behavior can be customized using the _**launch-report**_ property _**(ObjectStyle**_ group); if it is enabled, it lets you open, in the catalog, the report associated with the object (crosstab, graph, indicator, map) used for data display by double-clicking on the object or by clicking on the title of the object.

This property enables _**instance-type**_ which allows the user to decide, once the report associated with the object is launched, if the changes made to the report should have an impact on the starting object (_same instance_) or if the launched report is to be considered a separate instance (_clone instance_).

If you access the report associated with a crosstab (“launch report” property enabled), and perform operations on it (e.g. pivoting, operations on the page-bys, adding metrics or levels) and then use the “reload report” button, the report will return to the initial situation while maintaining the settings it had in the Page when the catalog was launched.

#### Passing Parameters among Several Pages

It is particularly useful to make Pages interact with each other, in order to transmit the analyses from one to another, reporting the choices of the filters on all the pages of interest.

There are different interaction modes among the Pages:

* shared parameters and page-bys
* Page open in DS

**Shared Parameters and Page-bys**

It is possible “to share” the parameters defined in a Page, to all the other Pages of the application, so that the choices made in Pages can affect all those which use the same parameter.

Also for page-bys you can activate sharing, so that the user has the same choices repeated on every Page. For example if a particular year is chosen in a Page, all the Pages will show the same year in the page-by levels.

The sharing of parameters and page-bys is applied at application property level (see _Parameters shared among several Pages_ section).

It is possible to "update" the page-bys with respect to the selections made in a "SELECT" or "CHECKLIST" object. By enabling the property of the **align-page-by-to-params Page** pag&#x65;**,** the following type of behavior is obtained:

* a "SELECT" or "CHECKLIST" object defined at a specific level and named with the same name as the corresponding dimensional level
* a "CROSSTAB" object, which has the same dimensional level defined in "SELECT", placed in page-by

&#x20;by selecting a level value in "SELECT", the same will be automatically displayed in the report of the same Page page.

Property of Page (align-page-by-to-params)

![](<../../.gitbook/assets/89 (2).png>)

_One "Select" object and one "Crosstab" object are on the following Page. Note how by selecting any value in the "Select" object (in the above example "2004"), the same will be displayed in the report of the same Page page. The align-page-by-to-params property then allows aligning the parameters of a "Select" or "Checklist" object, to the page-bys (with the same name) of the reports on the same page._

**Passing Parameters Through Page Open in DS**

In the case of Drill-through towards another Page page, the parameters on the latter can be used both of the calling report and of the Page containing the report (it therefore becomes the calling Page).

Using the property:

* _**apply-DS-auto-filters**_ (_Filter_ group)

The automatic filters are applied originating from the drill-through in which the "apply-sel-a&#x73;_**-filter" option is enabled**_”.

#### Accessing Page from External Systems

Pages defined in DAC can be recalled: the system provides for the **automatic generation of a link**, including the desired parameters.

This makes it possible to dynamically link DAC Pages to external (web-type) applications, for example, by requesting the Page filtered by the parameters of the source application.

![](<../../.gitbook/assets/90 (2).png>)

You can display the links:

* To open DAC directly on a specific Page page,
* To open the Page only, to then be entered in an application; this method is embedded.

The operations are the following:

* Enables any command of the Action Bar of the mashboard
* From the Page, open the settings menu from the button and select **Share** (only visible to administrators)

![](<../../.gitbook/assets/91 (2).png>)

* From _Share_ a pop-up opens with two links, shown in the figure.

![](<../../.gitbook/assets/92 (2).png>)

the following is the syntax of the two URLs:

_**http://\<HOST>:\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE ID**>/_**\[view** or **embedView]**

where:

_**\<HOST> -**_ Host name or IP of the Application Server

_**\<PORT>**_ _**-**_ port of the Application Server

_**\<CONTEXT**_> _**-**_ name of the Web Application DAC

_**\<OWNER>**_ _**-**_ ID of the application

<_**Page**_ ID

**view** _**-**_&#x66;or direct opening

**embed view** _**-**_&#x66;or embed opening

for access to the Page already authenticated, enter the part shown below in the previous link:

_http://\<HOST>:\<PORT>/\<CONTEXT>/content/Page/\<OWNER>\_\<PAGE\_ID>/_\[view or embedView]_?**csUsrn=\<USER ID>\&csPass=\<PASSWORD>\[\&crypted=1]**_

where:

* **csUsrn:** user id
* **csPass:**&#x70;assword of the user clear or encrypted
* **crypted:** if the value 1 is set the password is encrypted. If you do not want to enter an encrypted password, the variable is not entered in the link.

The encrypted password for a specific user can be retrieved by the system administrator inside the SUBJECT table of the db. In this case the _CsPass_ variable will have the encrypted password associated

In the case where you want to enter the preselected parameters add the following syntax to the link:

_http://\<HOST>:\<PORT>/\<CONTEXT>/ content/Page/\<OWNER>\_\<PAGE ID>/_\[view or embedView]_?_ _**pNames=\<PARAMETER>\&pValues=\<VALUES>**_

where:

* _**\<PARAMETER>**_ is the list of the parameters

The parameters are listed separately from %23\_%23\_%23, so _n_ parameters have the following syntax:

_Param&#x31;**%23\_%23\_%23**Param&#x32;**%23\_%23\_%23**…Paramn_

* _**\<VALUE>**_ the corresponding values to be assigned to the parameters. The values of each parameter are always separated by the same separator _**%23\_%23\_%23**_.

So if _Param1_ has the value _Val1, Param2_ has the value _Val2, Paramn_ has the value _Valn_ the correct syntax is the following:

_Val&#x31;**%23\_%23\_%23**Val&#x32;**%23\_%23\_%23**…Valn_

In case one or more parameters must be assigned more values, the separator between the multivalue is _**%23%23%23%23%23**_

So if _Param1_ assumes three values _Val11, Val12 and Val13_ the syntax becomes:

_Val1&#x31;**%23%23%23%23%23**Val1&#x32;**%23%23%23%23%23**Val1&#x33;**%23\_%23\_%23**Val&#x32;**%23\_%23\_%23**…Valn_

&#x20;**Note:** _for operation on browsers IE8/IE10, often cleaning the cache is not sufficient to correctly use the direct access links, rather you must perform the following operations:_

1. _enable the “Always update from server” option, which is in “Development tools (F12)” -> Cache;_
2. _system “logout”;_
3. _access the system with one of the direct access links;_
4. _system “logout”;_
5. _disable the “Always update the server” option;_
6. _access with one of the direct access links._

Example of a Link to a Page

Step 1: Page link

![](<../../.gitbook/assets/93 (2).png>)

_Access a dashboard page in debug mode. Select the parameters, for example the following were selected:_

* _Area -> CENTER_
* _Region -> Lazio_
* _Business Unit -> Business Unit 01._

_Reload the page (click on the Sales Analysis tab). The parameters set are displayed in the debug window, page parameter value section._

Step 2: Page link

![](<../../.gitbook/assets/94 (2).png>)

_From the Action Bar select the button shown in the figure and choose the Share menu item._

_A window opens with two links_

* _Direct Link to the Page. Provides direct access to the Page page. Authentication is automatic and any page parameters are set automatically._
* _Direct link to DAC. To access DAC, placing it directly on the Page. The authentication mode is automatic._
* _The link with the passage of the parameters is as follows:_

_http://192.168.2.102:8080/Decisyon450MANUAL/content/Page/RTQDANB\_216381316292328/view?pNames=AREA\&pValues=2\&pNames=Region\&pValues=714\&pNames=Business\_Unit\&pValues=0_

_Note that in pName and pValue, the parameters exported from Page found in the debug window have been entered_

#### Predefined JavaScript Functions

DAC provides some Javascript functions accessible from the properties of the components which use this code, such as the JavaScript, Image or Execute button component.

The Javascript code entry window is a real Javascript text _Editor_ and the code commands are shown in a different color.

The code entered does not require the opening and closing _commands "<_&#x73;cript>\</script>" since the system enters them automatically during execution. If these were entered, they will be ignored.

JavaScript functions can also be used where it is possible to enter free text, such as in text objects of the Page or in the custom functions for the reports (_Presentation Administrator,_ _Custom functions for reports section_).

The **f(x)** button (top right) opens a window where you can select one of the _JavaScript functions_ shown by DAC that are directly applicable to Pages and Reports.

This window also shows other particularly useful functions.

![](<../../.gitbook/assets/95 (2).png>)

**Page Management Functions**

In the _Page_ folder functions are gathered which may be applied to the Pages.

The reference to the Page is defined in _**object-id**_ property (_**metadataInfo**_, property _Advanced_ folder, _Advanced_ group).

![](<../../.gitbook/assets/96 (2).png>)

Below are the functions to be applied to the Pages:

* **extDshExportToExcel(**_**id**_**)** and **extDshExportToPdf(**_**id**_**)**

the functions export a specific Page in Excel and PDF format (_**id**_:_object-id_ id of the Page)

* **extSendParamChanged(**_**pName**_**,&#x20;**_**pValue**_**)**

Value a pName _**parameter**_ in the current Page, with the value specified in _**pValue**_

* **extSendCheckListParamChanged(**_**pName**_**,&#x20;**_**pValue**_**,&#x20;**_**type**_**,&#x20;**_**checked**_**)**

the value of a checklist is changed in the current Page, identified with _**pName parameter**_::

the value specified in _**pValue**_ is selected or not depending on whether _**0**_ or 1 is checked.

The _**type**_ indicates whether the value is numeric (_type: 0_) or a string (_type: 1_).

* **extReLaunchCurrentPage()**

Run the current Page (by possibly updating data and objects, regardless of the configuration of the update properties)

* **extRedirectToDsh(id) and extRedirectToDsh(id,params)**

It redirects the page to a specific Page (_**id**_:_object-id_ id of the Page). In the function the parameters may be indicated, to be used as filters for the specific Page.

* **extOpenDshDialog, extOpenDshModalDialog and extOpenDshModalDialogParam**

similar to the previous group, only that in this case a Page is opened.

![](<../../.gitbook/assets/97 (2).png>)

* _**extExecuteButton**_**&#x20;(**_**custom-js-id**_ **)**

carries out the action associated with an _Execute button_ and includes, as a single parameter in input, the one defined in the _custom-js-id_ property of the Execute button.

* _**extRefreshObject (custom-js-id**_ _**)**_

The function runs the update of a specific component with a report, a graph or any form type report associated with it. The only parameter provided as input is the one defined in the _custom-js-id_ property of the component.

* _**extRefreshPagePage**_

The function allows for updates to be carried out for a specific component that has an associated report, or for those types of forms (i.e. under the file form in the Page Designer section).

**extRedirectToDsh with or without parameters**

It redirects the page to a specific Page (_**id**_:_object-id_ id of the Page). In the function the parameters may be indicated, to be used as filters for the specific Page.

The execution of the Page is preceded by an initial repost on a loading page, in which the repost to the desired Page page is subsequently carried out.

The function includes as parameters in input the ID of the Page page and possibly the list of the parameters to be sent, defined in the following format:

_\[{"name": "parameter\_name1", "value": ?parameter1?}, { "name": "parameter\_name2", "value ?parameter1?}, { "name": "parameter\_nameN", "Value ?parameterN?}]._

where "parameter\_name1", "parameter\_name2" and “parameter\_nameN” are the names of the parameters expected and imported in the called page.

**In the example below create Page “A” for the selection of parameters, which will then be passed to Page “B”**, using the _extRedirectToDsh_ function, entered in the code of a JavaScript object.

Step 1: Page with a Redirect ExtRedirectToDsh

![](<../../.gitbook/assets/98 (2).png>)

_In the Page called “A” a Text Field object named Year, a Text Field object named User, a multiselection type Styled Selector object (e.g. Checkbox) associated with the MONTH level, an Execute button and finally a JavaScript type object with the code shown in the figure are entered. In the code indicate that the redirection function is active upon clicking execute button._

Step 2: Page with a Redirect ExtRedirectToDsh

![](<../../.gitbook/assets/99 (2).png>)

_In the Page called “B”, with id '684350310331296' ("metadataInfo" property), a Crosstab associated with a report with the Year and Month levels is entered and with the following filters: MONTH@ID IN ('?\_month?') and YEAR@ID = '?\_year?'._

_By selecting and valuing the parameters Year, User and MONTH in Page A, the system updates the JavaScript object containing the parameters to be sent._

_By selecting the Execute button, the system will redirect to Page '684350310331296', passing all the parameters correctly._

**extOpenDshDialog, extOpenDshModalDialog and extOpenDshModalDialogParam**

The functions _**extOpenDshDialog**_ and _**extOpenDshModalDialog**_ open a window containing a particular Page.

The function _**extOpenDshDialog**_ opens a NON MODAL type window; access to the other windows is therefore permitted.

For the function _**extOpenDshModalDialog,**_ the opening of the window is of the MODAL type: i.e., access is blocked to the other windows until the modal one is not closed.

The function _**extOpenDshModalDialogParam**_ has the same behavior as the previous one, with the possibility of sending a list of the parameters to the Page.

The parameters of the functions are as follows:

* **dshID**: Id of the Page (mandatory)
* **title**: Title of the window (by default no title)
* **wiDSh**: wiDSh of the window in pixels or percentage (default 800)
* **height**: height of the window in pixels or percentage (default 600)
* **resizable**: flag to resize, maximize and iconize the window (default true)
* **top**: position from the top margin of the dialog (default center)
* **left**: position from the left margin of the dialog (default center)
* **idDialog**: ID of the window (random value by default)

![](<../../.gitbook/assets/100 (2).png>)

For the function _**extOpenDshModalDialogParam**_ the parameters to be sent to the Page are defined in the following format:

_\[{"name": "parameter\_name1", "value": ?parameter1?}, { "name": "parameter\_name2", "value ?parameter1?}, { "name": "parameter\_nameN", "Value ?parameterN?}]._

**Example of a Page with an extOpenDshDialog type pop-up**

Step 1: Page with pop-up type extOpenDshDialog

![](<../../.gitbook/assets/101 (2).png>)

_Enter the text type object in the Page. Enter the Javascript code from the test property main section._

_The following code is entered:_

_\<script>_

_extOpenDshDialog('479348149187281', 'PAGE', '50%', '50%', false, 0, 0, 'idWinMod')_

_\<script>_

_In detail:_

* _'479348149187281'-> Page ID_
* _'PAGE'-> Window title_
* _‘50%’-> WiDSh of the pop-up_
* _‘50%’->Height of the pop-up_
* _‘False’-> redimensioning of the pop-up_
* _0-> position from the upper margin of the dialog_
* _0 -> position from the left margin of the dialog_
* _idWinMod-> Id of the dialog_

Step 2: Page with Pop-up Type extOpenDshDialog

![](<../../.gitbook/assets/102 (2).png>)

_Access DAC. When first accessed, a window is shown containing a page defined in the link, which will be opened in modal mode. The window is non-modal; this allows navigation to the page below, even if the popup is closed._

**Example of a Page with an extOpenDshModalDialog tType Pop-up**

Step 1: Creating Page

![](<../../.gitbook/assets/103 (2).png>)

_Enter the text type object in the Page. Enter the Javascript code from the test property main section._

_The following code is entered:_

_\<script>_

_extOpenDshModalDialog('479348149187281', 'PAGE', '50%', '50%', false, 0, 0, 'idWinMod')_

_\<script>_

_In detail:_

* _'479348149187281'-> Page ID_
* _'PAGE'-> Window title_
* _‘50%’-> WiDSh of the pop-up_
* _‘50%’->Height of the pop-up_
* _‘False’-> redimensioning_ of _the pop-up_
* _0-> position from the upper margin of the dialog_
* _0 -> position from the left margin of the dialog_
* _idWinMod-> Id of the dialog_

Step 2: Visualization on DAC

&#x20;_Access DAC. When first accessed, a window is shown containing a page defined in the Page page, which will be opened in modal mode And browsing the underlying page will be locked until the window is closed by the user._

![](<../../.gitbook/assets/104 (2).png>)

**Report Management Functions**

In _the Report_ folder, functions are grouped that can be applied to a report as listed below:

* **extExportToExcel(id)**

Run the Excel export of a specific report (_**id**_:_object_-id of the crosstab containing the report to be exported)

* **extShowCSVExportSettings(**_**id**_**)**

Run the PDF export of a specific report (_**id**object_-id of the crosstab containing the report to be exported)

* **extShowCSVExportSettings(**_**id**_**)**

Run the CSV export of a specific report (_**id**_ _object_-id of the crosstab containing the report to be exported)

* **extPrintReport(**_**id**_**)**

Print a specific report (_**id**_ _object_-id of the crosstab containing the report to be printed)

* **extRefreshReport(**_**id**_**)**

Update a specific report (_**id**_ _bject_-id of the crosstab containing the report to be updated)

* **extExecuteReport(**_**id**_**)**

Run a specific report (_**id**_ _object_-id of the crosstab containing the report to be run)

* **extLaunchReport(**_**id**_**)**

Open a specific report (_**id**_ _object-id_ of the crosstab containing the report to be launched) displaying it in the report section

* **extReinitPageBy(id)**

Restores the value of the page bys of a report. (_**id**_ _object-id_ ID of the crosstab object).

**Other Functions Available**

In the _Other_ folder some functions are listed which do not pertain to the management of reports or Pages, but are useful for the development of a Page.

* **extStartLoading()**

It shows a transparent image in front of the Page, stopping the changes in the underlying page. Useful during asynchronous operations.

* **extStopLoading()**

Remove the transparent image created through the _extStartLoading() function._

* **extShowWait()**

A please wait operation in progress image is shown.

* **extHideWaits()**

Remove the image shown by the _extShowWait() function._

* **extCloseDialog(idDialog)**

Closes a dialog previously opened, allows the id of the dialog to be closed as single mandatory parameter.

* &#x20;**extCloseCurrentDialog()**

The current window closes.

* extDialog and **extConfirmDialog**

To open a pop-up containing a text message and an icon for the type of message.

In the second function, separate actions can be associated both for confirmation and cancellation. Both pop-ups are modal.

![](<../../.gitbook/assets/105 (2).png>)

* **extOpenDialog, extOpenModalDialog and extOpenModalDialogParam**

To open a web page, by simply indicating the address; also in this case the functions support one of the two types of opening, modal and non-modal. In addition a function allows the passing of parameters.

![](../../.gitbook/assets/106.jpeg)

* **extGetDialogWindowOpener:**

This is applied to a window open in Drill-Through and returns the **reference to the calling window** (Page or report). Once the _calling_ reference is obtained, from the _calling window_ the system functions may be performed on the _calling_ window.

**Example**

_You want to update a report on a Page, starting from a window open in drill-through. In the calling window, enter an Execute button and in the javascript-code-after property of the object, enter the following code:_

_//report code to be updated, in the calling Page_

_var_ _**reportId:**_ _= '394336474062156';_

_//reference to the calling window_

_var_ _fwin =_ _**extGetDialogWindowOpener();**_

_//check the existence of the_ _**fwin**_ _calling window and the report updating function_

_**If**_ _(fwin&& fwin!=null && fwin.extRefreshReport)_

_{_

_//updates the report in the calling window_

_fwin.extRefreshReport(**reportId:**);_

_}_

* **extShowNotification(Notification**_**:, icon, notificationMessage, autoClose, cssClassName**_**)**

Function which displays a notification message

* _**Notification**_: Notification Title (default: "Execution completed")
* _**icon**_**:** (numeric) type of icon:

0 (blank, default); 1 (info); 2 (notification); 2 (Error)

* _**notificationMessage**_**:** detail message of the notification (default is blank)
* _**autoClose**_**:** automatic closure of the notification window (default: true)
* _**cssClassName**_**:**&#x41;ssociated CSS Class (default: none)
* **extDialog**

The **extDialog** function opens a pop-up with a simple text message.

![](<../../.gitbook/assets/107 (2).png>)

This type of window is modal: to access the calling page you must first close the pop-up.

It **is possible** to graphically customize the window, **by changing the default of the following parameters:**

* **message**: text message or html displayed in the pop-up (mandatory);
* **title**: title of the pop-up;
* **icon**: icon for the type of message:
  * 0: No icon _(default)_,
  * 1: Info
  * 2: Warning
  * 3: Error
  * 4: Question

In case of entering an incorrect value the default is set automatically;

* **wiDSh**: wiDSh in pixels or percentage _(default 300)_
* **height**: height in pixels or percentage _(default null)_
* **idDialog**: ID of the pop-up _(default casual value)_

![](<../../.gitbook/assets/108 (2).png>)

Below are some examples for each type of message. For each window the related creation code is shown.

**Default Window**

![](<../../.gitbook/assets/109 (2).png>)

_\<script>_

_extDialog ('Message Text')_

_\<script>_

**Window configured for an information message**

![](<../../.gitbook/assets/110 (2).png>)

_\<script>_

_extDialog ('Message Text',Info,1,200,110,'MyDialog' )_

_\<script>_

**Window configured for an alert message**

![](<../../.gitbook/assets/111 (2).png>)

_\<script>_

_extDialog ('Message Text','Warning',2,200,110,'MyDialog' )_

_\<script>_

**Window with error message**

![](<../../.gitbook/assets/112 (2).png>)

_\<script>_

_extDialog ('Message Text','Error',3,200,110,'MyDialog' )_

_\<script>_

**Window with question type message**

![](<../../.gitbook/assets/113 (2).png>)

_\<script>_

_extDialog ('Message Text',Question,4,200,110,'MyDialog' )_

_\<script>_

Example of Page with extDialog pop-up

Step 1: Page configuration with pop-up extDialog

![](<../../.gitbook/assets/114 (2).png>)

_This example configures a Page that, when opened, shows an information pop-up (modal)._

_For the creation, a text object is entered inside the Page. In the text property enter the JavaScript function:_

_\<script>_

_extDialog ('Select year and month to filter the graph and report','Info',1,300,150,'MyDialog' )_

_\<script>_

_The parameters set are in detail :_

* &#x20;_‘Select year and month to filter the graph and report’ Text of the message_
* _'Info' Title of the pop-up_
* _1 Information icon type_
* _800,600-> WiDSh and height of the pop-up._
* _'MyDialog'->Id of the Pop-up._

Step 2: Page configuration with pop-up extDialog

![](<../../.gitbook/assets/115 (2).png>)

_Open the preview. The underlying page is obscured and browsing remains blocked until the user presses the pop-up confirmation button._

**extConfirmDialog**

The "extConfirmDialog" **function** opens a window with a confirmation message (non-modal).

![](<../../.gitbook/assets/116 (2).png>)

This function lets you define an action after clicking the confirmation or cancellation button.

It **is possible** to graphically customize the window, **by changing the default of the following parameters:**

* **message**: text message or html shown in the window (mandatory);
* **title**: title of the pop-up (mandatory);
* **onConfirm**: action to be performed when clicking on the confirmation button (mandatory)
* **onCancel**: action to be performed when clicking on the cancellation button
* **icon**: icon for the type of message:
  * 0: No icon,
  * Info _(default)_
  * 2: Warning
  * 3: Error
  * 4: Question

In case an incorrect value is entered, the default is set automatically;

* **labelYes**: label of the confirmation button _(default YES)_
* **labelNo**: label of the cancellation button _(default NO)_
* **wiDSh**: wiDSh of the dialog in pixels or percentage _(default 300)_
* **height**: height of the dialog in pixels or percentage _(default null)_
* **idDialog**: id of the dialog _(default casual value)_

![](<../../.gitbook/assets/117 (2).png>)

Below are some examples of a customized window, with its code.

**Default window**

![](<../../.gitbook/assets/118 (2).png>)

_\<script>extConfirmDialog('Text Message',Info,'alert(“Message on Yes button”)')\</script>_

**Window with information message and confirm and cancel buttons**

![](<../../.gitbook/assets/119 (2).png>)

_\<script>_

_extConfirmDialog('Text Message',Info, 'alert(“Message on YES button”)', 'alert(“Message on NO button”)', '1', 'OK','CANCEL','300',110,'MyDialog' )_

_\<script>_

**Window with information message and confirm and cancel buttons**

![](<../../.gitbook/assets/120 (2).png>)

_\<script>_

_extConfirmDialog('Text Message',Warning,'alert(1)','alert("2")','2','OK','CANCEL','300',110,'MyDialog' )_

_\</_**\<script>**

**Window with error message and confirm and cancel buttons.**

![](<../../.gitbook/assets/121 (2).png>)

_\<script>_

_extConfirmDialog('Text Message',Error,'alert(1)','alert("2")','3','OK','CANCEL','300',110,'MyDialog' )_

_\<script>_

**Window with question type message with confirm and cancel buttons**

_\<script>_

_extConfirmDialog('Text Message',Question,'alert(1)','alert("2")','4','OK','CANCEL','300',110,'MyDialog' )_

_\<script>_

![](<../../.gitbook/assets/122 (2).png>)

Step 1: Page with pop-up type ExtConfirmDialog

![](<../../.gitbook/assets/123 (2).png>)

_In this example, you want to open a warning pop-up when opening a Page. The pop-up will be of the modal type, with confirm or cancel keys. For the creation, a text object is entered inside the Page. In the text property enter the Javascript function:_

_\<script>_

_extConfirmDialog ('You are about to save this item. It cannot be restored at a later time continue?', 'Warning','alert("Data have been saved")','alert("Reselect date")','2','OK','CANCEL','300',null,'MyDialog' )_

_\<script>_

_In detail:_

* _extConfirmDialog Function for the pop-up_
* _‘You are about to save this item…’ Text of the message_
* _'Warning' Title of the pop-up_
* _'alert("Data have been saved")' Action associated with the confirm key_
* _'alert("Reselect date")' Action associated with the cancel key_
* _2 Warning icon type_
* &#x20;_‘OK’ Confirm key_
* _‘CANCEL’- Cancel key_
* _300,null- WiDSh and height of the pop-up_
* _'MyDialog'->Id of the Pop-up._

Step 2: Page with pop-up type ExtConfirmDialog

![](<../../.gitbook/assets/124 (2).png>)

_Access DAC. The underlying page is obscured and browsing remains locked as long as the user does not press one of the two buttons._

_If you select the confirm button the alert associated with it is displayed. The same thing for the cancel key._

**extOpenDialog, extOpenModalDialog and extOpenModalDialogParam**

The **extOpenDialog** type function opens a NON MODAL window, containing a page of a specific URL.

The **extOpenModalDialog** type function also opens a window with the content of a URL, though the opening is of the MODAL type. Thus browsing the underlying page will be locked until the window is closed by the user.

The **extOpenModalDialogParam** function has the same behavior as the previous function (therefore MODAL), but includes the possibility of sending a list of parameters.

![](<../../.gitbook/assets/125 (2).png>)

The parameters of the three functions are:

* **src**: URL (mandatory)
* **title**: Title of the window (by default no title)
* **wiDSh**: wiDSh of the window in pixels or percentage (default 800)
* **height**: height of the window in pixels or percentage (default 600)
* **resizable**: flag to resize, maximize and iconize the window (default true)
* **top**: position from the top margin of the dialog (default center)
* **left**: position from the left margin of the dialog (default center)
* **idDialog**: ID of the window (random value by default)

For the function **extOpenModalDialogParam** the parameters to be sent to the URL are defined in the following format:

_\[{"name": "parameter\_name1", "value": ?parameter1?}, { "name": "parameter\_name2", "value ?parameter1?}, { "name": "parameter\_nameN", "Value ?parameterN?}]._

**Example of a Page with an extOpenDialog Type Pop-up**

Step 1: Page with Pop-up Type extOpenDialog

![](<../../.gitbook/assets/126 (2).png>)

_Enter the text type object in the Page. Enter the Javascript code from the test property main section._

_The following code is entered:_

_\<script>_

_extOpenDialog('http://www.decisyon.com','Decisyon','800','600','true','center','center','MyDialog')_

_\<script>_

_In detail:_

* _‘‘http://www.decisyon.com’ -> Real link to the Web page._
* _'Decisyon'-> Title of the pop.up._
* _800,600-> WiDSh and height of the pop-up._
* _' true '-> Automatic resize popup._
* _' center ', ' center '-> position compared to the top and left margin._
* _'MyDialog'->Id of the Pop-up._

Step 2: Page with pop-up type extOpenDialog

![](<../../.gitbook/assets/127 (2).png>)

_Access DAC. When accessing for the first time, the pop-up is shown which displays the web page specified in the code. The window is non-modal; this lets you browse the underlying page, even if the pop-up is not closed._

**Example of a Page with an extOpenModalDialog type pop-up**

Step 1: Page with pop-up type extOpenModalDialog

![](<../../.gitbook/assets/128 (2).png>)

_Enter the text type object in the Page. Enter the Javascript code from the test property main section._

_The following code is entered:_

_\<script>_

_extOpenModalDialog('http://www.decisyon.com','Decisyon','800','600','true','center','center','MyDialog')_

_\<script>_

_In detail:_

* _‘_[_‘_](http://www.decisyon.com/)[_http://www.decisyon.com_](http://www.decisyon.com/)_’ -> Real link to the Web page._
* _'Decisyon'-> Title of the pop.up._
* _800,600-> WiDSh and height of the pop-up._
* _' true '-> Automatic resize popup._
* _' center ', ' center '-> position compared to the top and left margin._
* _'MyDialog'->Id of the Pop-up._

Step 2: Page with pop-up type extOpenModalDialog

![](<../../.gitbook/assets/129 (2).png>)

_Access DAC. When first accessed, a window is shown containing a page defined in the link, which will be opened in modal mode. In this case browsing the underlying page will be locked until the window is closed by the user._

#### Notification Designer

The notification service is a complete contact management system which lets companies optimally manage their communication with user groups or single users. A management system allows users to create, review and send notification messages, without requiring users to always be connected to the application.

The type of notification is:

* Mai&#x6C;**,** where the notification is sent by e-mail;

From the **Application>> Notification Designer** menu, open the window that manages the notification service.

![](<../../.gitbook/assets/130 (2).png>)

In the Mail notification we define the send mode, the recipients and the message with the title.

**Notification Transmission**

Notifications can be sent instantly, by clicking the ![](<../../.gitbook/assets/131 (2).png>) button.

During execution, the system displays the dialog window _Execution log_ which displays the different steps, detailing the instructions which are carried out.

The steps are highlighted in red if there are errors such as missing privileges, reports not found, etc. The figure shows an example where a user does not have the license to receive notifications.

![](<../../.gitbook/assets/132 (2).png>)

Notifications can be also sent through:

* a schedule defined with the _Scheduler_ modul&#x65;_._
* via a command in a Page . In this case, the recipients can be set dynamically: we can select recipients on the Page, in addition to those set in the notification itself.
* SQL commands, when a JOB is created .

**Notification Recipients**

You can select **Notification recipients** in the **Groups** section; you can choose them by groups or individually. To send the notification, DAC takes the information from user configuration, shown in the figure, which indicates the data used for each type of notification.

![](<../../.gitbook/assets/133 (2).png>)

### **Notification Message**

Notification messages are composed of a title and the actual message. In the message it is possible to enter custom parameters, such as the username:

selecting the ![](<../../.gitbook/assets/134 (2).png>) button will enter the keyword %SUBJECT%; this will be replaced by the corresponding recipient username, when the notification is sent.

![](<../../.gitbook/assets/135 (2).png>)

For e-mail notifications, there are functions for the formatting of reports in text \[form].

**E-mail Notifications**

With e-mail notifications, you can send reports and/or Pages in different formats, including DAC format.

The message can contain information about one or more reports formatted through Pattern.

For sending notification e-mails, the **mail server** must be defined in the _Server Designer_ module (see _Server connections_ section, parag. _SMTP server_) and then associated in the system properties _**associated–SMTP-server**_ ( _Tools properties_, _E-mail_ section, _System E-mails_ group)_._

To create this type of notification, select the **Create Mail notification** item from the pop-up menu on the _Root._

The sender of the email server may be defined, differently from the system-wide one (through the Server Designer) in the properties (_Main_ group):

* _**the default email-notification-sender**_ is identified, in parentheses, as the sender defined in the _email-sender_ property in the _Server designer_; this may be edited, entering a different email address to be used as the sender.
* _**the default email-sender-name**_ indicates, in parentheses, the name to be associated with the sender defined in the _email-sender-name_ property in the _Server designer_; this may be edited, entering a different name to be used as the sender.

You can associate one or more user groups to an e-mail notification, which must be CC'ed in the e-mail, using the property:

* _**CC**_ opens a window for selecting DAC groups and/or users to be added to the mailing list as CC. These users must also have a _Notification_ license. Users associated with multiple groups will receive only one copy of the email.

**Report and Page Attachments**

You can choose the reports and Pages to attach to the e-mail using the appropriate buttons, as shown in the figure (_**Attachments**_ panel): the reports/Pages attached are placed in the bottom table. A menu is enabled for each one that allows you to select an export format.

The formats available for the **report** are:

* _PDF_ or _Excel_
* text (_TEXT_) or _CSV_
* or by directly accessing the report in DAC (WEB).

While a **Page** can be sent in the formats:

* PDF or Excel (configured beforehand)
* by directly accessing the Page in DAC (WEB).

the prior configuration of a Page must be completed in the Page Designer module

![](<../../.gitbook/assets/136 (2).png>)

**WEB Format**

The **WEB** format sends you a link that will allow you to directly access the report or the Page, without having to be authenticated.

![](<../../.gitbook/assets/137 (2).png>)

To use this type of format, you must set the address of DAC for the connection in the system properties:

* _**decisyonWebURL**_ (_Tools properties_, _Web section,_ _Connection_ group) enter the DAC link.

**Report Pattern (formatting report in the message)**

The e-mail notification message can contain information from one or more reports, which are formatted according to patterns specified by the user instead of being sent in the usual tabular form.

For example, you can list products sold to a certain customer, in a text form such as: _Product X’ was sold to 'Client Y’ with sales for ‘sales value', where the_ product, the client and the sales value are given a value in the report.

The pattern is set in the _**pattern{n}**_ property (_Report Pattern_ group), enabled from the _**patterns-number**_ property (by default set to 0), which indicates the number of patterns you intend to define.

![](<../../.gitbook/assets/138 (2).png>)

You can open a window from the _**pattern{n}**_ property, shown in the figure above, where you can select the report with the information to be formatted.

After choosing the report, _Column_ lists the references to the columns of the report itself: with the + **+**&#x62;utton (on the right) we input the references in the text area below, under _Pattern_, together with the desired textual form (an example is given by default).

The section to be used for the text (in HTML format) is enclosed between quotation marks and is linked to the report columns with the + command. **+**.

The preview button (shown in the picture) displays the text formatted according to the pattern input in the text area.

_Excel-like functions_ are also supported, selected with the button shown in the figure. The functions to format metric values are particularly useful.

After defining one or more patterns, you can input them in the message title or body, simply by indicating the reference to the chosen pattern: this enables a list for selecting the pattern, which you can input in the message by clicking the + Button.

![](<../../.gitbook/assets/139 (2).png>)

An example of the application of the _Report Pattern_ method is shown below, where a text string is defined for the list of sales of each product and detail for the customer groups the product was sold to.

Example : Report Pattern

Step 1: Report Pattern

![](<../../.gitbook/assets/140 (1).png>)

_We define an e-mail notification. In patterns-number we set the value 2: we enable the corresponding pattern{1} and pattern{2} properties._

_You define the e-mail message for the list of products sold with reference to the pattern{1}, and the detail list with reference to the pattern {2}._

Step 2: Report Pattern

![](<../../.gitbook/assets/141 (1).png>)

_We define the report for the list of products sold: the report has the Product level and the metric Sales Val._

_In the pattern{1}, the window opens for defining the first pattern: the text shown in the figure is inserted._

_You can see the text form in the preview, where references to the corresponding report columns are shown._

Step 3: Report Pattern

![](<../../.gitbook/assets/142 (1).png>)

_We define the report for the detail list (product sales and corresponding customer groups): the report will contain the Product and Customer Group, with the metric Sales Val._

_The window opens in pattern{2} for defining the second pattern, where we insert the text shown in the figure._

_You can see the text form in the preview, where references to the corresponding report columns are shown_**.**

Step 4: Report Pattern

![](<../../.gitbook/assets/143 (1).png>)

_In the picture we see the e-mail message received by the user associated with the notification. The two parts of the message, corresponding to the patterns defined in the notification, are pointed out._

### Resource Catalog

Resources that refer to files, images and CSS, that can be used by other DAC modules, can be “loaded” into the application. In addition to individual files, the system can load entire folders and subfolders.

With the **Resource catalogue** module (_**Application**_ menu item), a real catalog of the resources is created, which may be used as:

* Images loaded into a Page
* Images loaded on TAG @IMG for levels and metrics
* JavaScript or CSS associated with Page pages
* Logos for PDF exports

Use the **New** button to open a window with access to the local folders. This is where you can select the file and generate a resource.

![](<../../.gitbook/assets/144 (1).png>)

Once the resource is selected, a window opens, where confirmation to perform the loading is requested. Once the operation is confirmed, a progress bar is displayed.

Once loading has finished, the resource is added to the document repository:

* For the resource to be generated, you have to configure this repository beforehand.

You cannot rename loaded resources since the name of the resource must coincide with the name of the loaded file.

Mass deletion of several resources is allowed by selecting them and choosing delete (right button of the mouse). Once the resource is selected, a window opens, where confirmation to perform the deletion is requested. Once the operation is confirmed, a progress bar will be displayed.

In case a mass resource deletion is interrupted, the system deletes up to the current resource and interrupts the flow. Likewise, to interrupt a mass import, the system loads up to the current resource and interrupts the flow.

Once the file is uploaded, you can enter the resource information in detail:

* The _Browse_ button (_Update_ pane) opens the loading page of the resources to make the updates.
* In the _Resource details_ pane, all the information on the resource is detailed: the file name, its creation date, the user who created it, the date of the last change, the type and measurements of the file.
* The _Preview_ pane shows a preview of the file if possible
* The _Download_ button (_Download file_ pane), saves the resource in the local folder.

![](<../../.gitbook/assets/145 (1).png>)

**Loading Talend Jobs**

For the Talend Job to be correctly recognized within DAC, it must be generated through the export of a **.zip** file, containing folders and files, as described below:

* **lib**
  * _\[JOB Name]_
    * _\[PROJECT Name]_
      * ….
* **jobInfo.properties**

If the file of the Talend Job has this structure when it is loaded as a resource in the catalog, it is recognized as a **Job Talend** type resource, as shown in the figure below.

In the summary information, the type and the name of the Job's main class are specifie&#x64;**.**

![](<../../.gitbook/assets/146 (1).png>)

The Talend Job loaded using this method will be available to be associated with:

* A Talend Integration schedule

An **Execute button**, of a TALEND\_INTEGRATION type

**Note:** _The_ _Talend version supported is 5.5.1._

### Schedules Designer

A schedule consists of preparing, managing and monitoring a plan for performing the activities foreseen on a time calendar (daily, weekly, monthly). A schedule of this type is created through the **Schedules Designer** module, which is opened from the _Application_ menu item.

![](<../../.gitbook/assets/147 (1).png>)

To create a schedule, set:

* _**Start scheduling**_ _–_
  * _**Date**_ and _**Time zone**_ _**-**_ The start date and time zone the times refer to
* _**Schedule Interval**_ - Scheduling time with regular time intervals, for which you set:
* _**Start time**_, _**Stop time**_ and _**Interval**_.

_**Note:**_ _In the stop scheduling time, the minutes are set to 59, therefore, if 16 is specified as_ _**Stop**_ _**time**, the end will be at 16:59._

* _**Schedule Time**_ - Scheduling time defined with single times. It is an alternative to the scheduling interval. Set the time (_**Hours**_) and (_**Minutes**_) for each schedule to start.
* _**Month Day**_ - Day of the month when the schedule starts. To set more single days, separate with a comma. The intervals are defined with start and stop day separated by “-“.
* _**Week day**_ - Days of the week when the schedule starts.

#### Scheduler (Task Schedule)

Use the **Scheduler** module to plan the updating and executing of certain logical objects based on a schedule, which was previously defined with the Schedules Designer module.

Open _Scheduler_ from the _Application_ menu item.

![](<../../.gitbook/assets/148 (1).png>)

The planning of a task, or updating rule, takes place by selecting the objects to be performed and by associating a schedule in the _**schedule**_ property: at the top right the date and time of the next execution is indicated.

The _**execution of the refresh rule**_ will be launched by DAC according to the definitions in the time schedule (e.g. every morning at 11:36).

The refresh rules may be also be performed through SQL commands, through the creation of a JOB, with the _**activateRefresh**_ property which enables (as default) or disables the planned execution of the refresh activity. Objects affected by a Refresh Rule are described in the image below.

![](<../../.gitbook/assets/149 (1).png>)

A Refresh Rule can be defined for the following objects:

* Absolute cache reports
* Alarms
* Notifications
* Dsearch Server update
* DLR execution
* Job Talend execution

The objects selected are indicated automatically in the middle pane with the object name, date and time of the last execution (_**Execution date**_), (_**Execution time**_) and (_**Average time**_), the number of executions performed (_**En**_), the number of executions completed with errors (_**Er**_) and the **total** for each field in the bottom row. The objects are sorted inside the list by using drag & drop.

![](<../../.gitbook/assets/150 (1).png>)

If the execution ends successfully, a green check is displayed, otherwise a red X is displayed.

In case of error the schedule does not block: select the row of the object performed with error to view the date and the details of the error in the bottom section.

**Talend Integration Scheduling**

The Talend Integration type allows you to start a Talend Job through scheduling.

The Job created on Talend should be loaded as a resource in the Resource Catalog, which will recognize it as a Talend Job type resource.

If the associated resource contains more jobs, the one associated with the Main Class, recognized by DAC (contained in the bat file), will be executed. If the associated resource contains a job with multiple child jobs, the parent job will be performed first and, in sequence, the child jobs.

Selecting the **TALEND\_INTEGRATION** key will open a pop-up for the selection of the job to execute. The window lists all Talend Job type resources loaded in the Resource Catalog.

#### Validating DAC objects

Validation is an automatic process which makes it possible to verify that the metadata underlying the application loaded and used for report definition are correct, and to ensure that tables and links exist.

After accessing the **Application>>Utilities>>Validate** menu, it is possible to:

* validate all application objects (**Validate All…**)
* validate individual objects categories (**Validate cubes, Validate dimensions, Validate metrics, Validate** filters)
* verify the SQL syntax underlying the application reports (Test **model reports**)
* execute the report using the cache or not (**Execute reports (cache)** or **Execute reports (full**_)_

During the execution of the validation processes, the system shows a window which lists the objects being validated (with a green check for those successfully validated and a red cross for the invalid ones)

![](<../../.gitbook/assets/151 (1).png>)

If an error occurs, the reason for the failures is registered and displayed by the _**log**_ folder, while the validation process continues on the remaining objects. In addition, you can interrupt the execution of the validation (_**Abort**_ button) and export the log of the validations up to that point (_**Export**_ button).

A progress bar shows the process execution in real time.

### Task

DAC offers a solution to manage activities and to assign tasks to users.

You can manage tasks in DAC through reports or Page components enabled for this purpose. You can assign tasks:

* on the report cells
* on some Page components (Graph, Indicator, Table)

Tasks can be notified to recipients through e-mails which give direct access to the task. Therefore, in order to access the task, the mail server and DAC server must be configured (see next paragraph).

**Configuring Task Notifications for E-mail**

The mail server for sending notification e-mails must be defined in the _Server Designer_ module and then associated in the system properties _**associated–SMTP-server**_ (_Tools preference_, _E-mail_ sectio&#x6E;_, System Emails_ group)_._

The e-mails contain a link for directly accessing the assigned Tasks; the reference to DAC must therefore be defined in the system properties:

_**decisyonWebURL**_ (_Tools properties_, _Web section,_ _Connection group_) enter the DAC link.

**Enabling Task on the Report**

You will need to set the properties in the _Body_ section for reports that have to be used in the task assignment process:

_**activateCellsTask**_ allows you to enable the insertion of the new task on the report cells

![](<../../.gitbook/assets/152 (1).png>)

_**viewCellinfoTask**_ to display, on the metric cells, information about the percentage deviation between the metric and set target

![](<../../.gitbook/assets/153 (1).png>)

**Enabling Tasks on Page Components**

The Page components used during the task assignment process are:

* Tables
* Crosstabs
* Graphs
* Indicators

You can enable components for the assignment of tasks in the following way:

* enable the component title with the _**show-Title**_ property of the **Title** group
* enable the _**activate-Task**_ property, always in the **Title** group.

Example: Displaying Tasks on a Component - GRAPH

![](<../../.gitbook/assets/image (22).png>)

_From Page Designer, we enter the graph-type component and in the TITLE section we enable the property activate-task. The graph in DAC will display the task button_ ![](<../../.gitbook/assets/155 (1).png>) _next to the title. Clicking the button opens the window for inserting the new task._





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

