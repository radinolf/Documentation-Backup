# Page Element Container (Page, Section, Components)

All the Page components are entered in a container, identified by a cell in the Page Designer.

Also the Page page and the section are associated with a container.

![](<../../../.gitbook/assets/18 (10).png>)

Components copied from another cell or from another Page can be pasted into a cell. If it is pasted on a cell ‘taken up’ by another component, the system asks for confirmation and if confirmed, the old component is removed and replaced with a new one.

In the container, define the Container Style positioning and visibility , the (_**Container Size**_ dimensions), a title and a (_**description**_).

Some elements of the Page are enabled for the configuration of a border and a background (uniform color or images).

![](<../../../.gitbook/assets/19 (10).png>)

### Positioning (Container Style)

Positioning the object in the page is set through properties (_Container_ folder, _ContainerStyle group_):

* _**Position**_ for the position, defined a&#x73;_**:**_
  * _Relative_ (default), the object is positioned according to the coordinates selected by the browser and those _set_ for _top_ and _left_ (negative values are also accepted).
  * _Static_, the container is positioned according to the coordinates selected by the browser while ignoring the settings for _top_ and _left._
  * _Absolute,_ the container is positioned on the coordinates set for _top_ and _left_, while ignoring the browser coordinates.

_The coordinates selected by the browser depend on where the object was positioned (in which cell/section)._ See the example below for further detail&#x73;_._

* _**top**_ and _**left**_ for the distance of the container, respectively from the top and from the left (in pixels)

Step 1: Relative/Static Positioning

![](<../../../.gitbook/assets/20 (10).png>)

_There are 3 components entered in the Page: a check list, a crosstab and a graph_

_The checklist component is shifted down by 70 pixels, leaving the relative positioning:_

* _relative position_
* _top at 70_

_Note that in DAC, the browser coordinates were assigned to the component, in addition to those set in the top property._

_If the position is set to static, the top property is ignored, and the checklist returns to the top (as in step 2)._

Step2: Positioning Absolute

![](<../../../.gitbook/assets/21 (10).png>)

_The checklist component is positioned in absolute mode, under the graph: absolute position; top at 280; left at 100_

_Note that in DAC, a component with absolute positioning is ignored in the Page Designer arrangement, and the cell is considered empty: in fact the graph, which is in the next cell, is considered as though it were in the first position._

_However, the checklist component, which is configured in absolute position, has been assigned the coordinates set in the top and left properties._

### Class-name (Container Style)

Allows to define css class to apply on the component. Class names must be separated by a space. It will therefore be possible to manage the customization of CSS of the widget.

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

![](<../../../.gitbook/assets/25 (6).png>)

_The Crosstab container has a 20% wiDSh (wiDSh) and auto expand activated (auto-expand activated). The height is fixed at 200 px. The report consists of 7 columns and 100 rows. In this case the space of 20% it is not sufficient to show the entire report. Rather than a horizontal scroll appearing, due to the auto-expand, the container widens until the report shows all the columns. On the contrary, a vertical scrollbar activates for the height, since a fixed value was set._

### Description and Title

A title may be associated with the **container** and displayed as a text box above the object, whose wiDSh coincides with the one of the same container:

* **show-title**(_Container_ folder, _Title_ group) enables the title of the container, which activates
  * **title-text: text** of the title
  * **title-effect:** effect to be associated with the title; _\<page default>_ inherits the effect set at page level.

Also a **description** may be associated with the container, displayed as an information icon which has the content of the description as tooltip:

* **show-description** (_Container_ folder, _Description_ group) activates the display of the description of the object, which activates
  * **description-text:** specifies the text of the description, shown as tooltip

![](<../../../.gitbook/assets/26 (6).png>)

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

![](<../../../.gitbook/assets/27 (5).png>)

An illustrative example is below.

Example: Container Style

Step 1: Design Container Style

![](<../../../.gitbook/assets/28 (5).png>)

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

![](<../../../.gitbook/assets/29 (5).png>)

_In the Preview figure of the Page_

_If you select the icon placed near the title, a pop-up opens to show the description._

_Please note that the page has a gray background while the table has an image as a background._

_The image remains as the background also for the graphs since these were made transparent._

Example - fill-style: Image Extension Style

Step 1:- fill-style: image extension style

![](<../../../.gitbook/assets/30 (5).png>)

_The Page publishes an indicator entered in a TABLE component which a background image is associated with as shown in the figure. In the example the extension style is shown of the image on the TABLE applied with the FILL-STYLE property:_

* _FILL HORIZONTALLY the background image extends along the horizontal axis of the container._
* _FILL ALL the background image extends until entirely filling the space of the container._

Step 2. Position: position of the image compared to the container

![](<../../../.gitbook/assets/31 (5).png>)

_This Page publishes the same TABLE component of the previous example. In this case, the positionings available via the POSITION property are applied: the figure indicates the value selected on each container._

Step 3: Repeat Style

![](<../../../.gitbook/assets/32 (5).png>)

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

![](<../../../.gitbook/assets/33 (5).png>)

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

![](<../../../.gitbook/assets/34 (5).png>)

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

![](<../../../.gitbook/assets/35 (5).png>)

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

![](<../../../.gitbook/assets/36 (5).png>)

_The first step is to load the css and JavaScript files._

_Access the Resource Catalog module and select the CSS and Javascript files that will be used inside the Page._

Step 2: Associating Resources with the Application

![](<../../../.gitbook/assets/37 (5).png>)

_The second step is to associate the resources with the properties of the application: in the Page section, associate the CSS and the Javascript in the related properties (also shown in the figure)._

Step 3: Defining Pages

![](<../../../.gitbook/assets/38 (5).png>)

_In the Page page the import-css-from-model and import-Js-from-model properties are enabled for the CSS and JavaScript group, indicating that the Page will use the css and JavaScript imported in the application. Enter a Text component where the html code that will give the structure to your page is defined._

Step 4: JavaScript and CSS in Pages

![](<../../../.gitbook/assets/39 (4).png>)

_The figure shows the end result of the Page._

_The CSS file was used for the creation of the page layout while the Javascript controls that you correctly enter the data inside the form._

_If the text entered respects the parameters set inside the Javascript file, the system considers the entry as correct and shows a green check to the side of each row. Otherwise the system returns a message in red where the correct format is specified._
