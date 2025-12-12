# Page Properties



All the Page widgets are entered in a container, identified by a cell in the Page Designer.

Also the Page page and the section are associated with a container.

![](<../../../.gitbook/assets/18 (1).png>)

Widgets copied from another cell or from another Page can be pasted into a cell. If it is pasted on a cell ‘taken up’ by another component, the system asks for confirmation and if confirmed, the old component is removed and replaced with a new one.

In the container, define the Container Style positioning and visibility , the (_**Container Size**_ dimensions), a title and a description.

Some elements of the Page are enabled for the configuration of a border and a background (uniform color or images).

![](<../../../.gitbook/assets/image (1271).png>)

###

## **Configuring a Page**

The property to customize the page are grouped by

* [**Object** ](./#object): in this folder are grouped all the property to configure parameters and sharing the page-by or configure the Action Bar or activate the debug modality
* [**Container**](./#main): In the folder Container you can find all the property to customize the page container.
* [**Advanced**](./#advanced): In the folder Advance you can find the property to customize the page using Css , Javascript and others

### Object

In this folder are grouped all the property to configure:

* [**Main** ](./#main): to manage the Page-By in the page and activate the page in Debug Mode
* [**On enter**](./#on-enter)**:** properties to Initialize and Refresh Page
* [**Parameters**](./#parameters): properties to manage the parameter in the page.
* [**Action Bar**](./#action-bar)**:** list of property to customize the Action Bar.
* [**Shere Page-by**](share-parameters-and-pageby.md)**:** property for sharing the page through the widgets of the page or other pages of the application

### Main

* **development-mode** automatic updating to the changes of the Page, preserving the parameters valued according to the user's selections.
* **debug-mode** Enables visualization of information useful to debug the objects contained in the page. **(see** [**Passing Parameters in the Page**](../page-parameters/)**)**

![](<../../../.gitbook/assets/image (1709).png>)



* **expand-page-by-selections** : when activated, a filter in Page-by performed on an object will be applied to all objects on the page containing the same level in Page-by
* **align-page-by-to-params:** Aligns page-by selections of the page, to the parameter value
* **auto-filter reports** : Enable the automatic filter applied to all objects linked to the report on the page. If enabled, when a parameter associated with a dimension (e.g. Month) receives a value, the system will automatically apply an ‘in values’ filter to every object associated with a report on the page and having a relatiohip with that dimension
* **page-description:** To define the description associated with the page

#### On Enter

In this group of properties you can find the properties to initialize and refresh the page.

* **initialize-page:** Enables the full page reset. Any browsing information will be rejected and all the page objects will be presented as if initially accessed.
* **refresh-page:** if enabled, at avery access to the page all the object will be updated. The objects associated to the report will be updated querying the releated data source.

#### **Parameters**

In this group of properties you can find the properties to manage the parameter in the page.

* **pre-selection-values** opens a window with the list of parameters defined in the page, where for each of them it is possible to enter a default value as a constant, variable, or the result of a query. see [Passing Parameters in the page ](../page-parameters/)
* **params-mandatory :** Allows you to set the list of mandatory parameters among those defined on the page. see [Mandatory Parameters](../page-parameters/#mandatory-parameters)
* **activate-global-params :** enable the sharing of parameters exported from the page with the others page of references application. Whenever the value of these parameters changes, this will apply to all pabe that contain them and that have parameter sharing enabled

#### Action Bar

The Action Bar lets you have information of a social type relating to the Page, in addition to containing the exporting commands.

<figure><img src="../../../.gitbook/assets/image (1680).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1887).png" alt=""><figcaption></figcaption></figure>

The type of information to be made visible is defined through the properties of the Action Bar group, _relating_ to the page

* **excel-export**: enables the exporting Excel configuration properties and the command on the Action Bar.
* **Refresh-page**: In the menu the advanced functions it displays the update function for the object in the page.
* **Initialize-page**: activates the item relating to initializing the Page.
* **show-connected-users:** activates the display of the number of users connected to the Page.
* **show-Social-functions**: activates the display of the social elements&#x20;
* **show-in-overlay:** the Action Bar will be shown as overlapping the content of the Page page (if deactivated, it will be shown statically).

## Container

In the folder Container you can find all the property to customize the page container.

The property to customize the page is present in the Container Tab and are grouped by the tipology:

* **Container Style**
* **Container size**
* **Title**
* **Description**
* **Others**

### Class-name (Container Style)

Allows to define css class to apply on the component. Class names must be separated by a space. It will therefore be possible to manage the customization of CSS of the widget.

See the example in the example graph

### :no\_entry: Positioning (Container Style)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

Positioning the object in the page is set through properties (_Container_ folder, _ContainerStyle group_):

* _**Position**_ for the position, defined a&#x73;_**:**_
  * **Relative** (default), the object is positioned according to the coordinates selected by the browser and those _set_ for _top_ and _left_ (negative values are also accepted).
  * **Static**, the container is positioned according to the coordinates selected by the browser while ignoring the settings for _top_ and _left._
  * **Absolute**_,_ the container is positioned on the coordinates set for _top_ and _left_, while ignoring the browser coordinates.

_The coordinates selected by the browser depend on where the object was positioned (in which cell/section)._ See the example below for further detail&#x73;_._

### Visibility (Container Style)

The container may be made invisible or hidden via the properties (Container folder, ContainerStyle group):

* **Visibility:** Set the visibility of the element
  * **hinerit**: inherits the visibility of the container
  * **visible**: (default), visible element
  * **hidden**: element not visible, but the space taken up remains reserved
  * **none**: element completely hidden, including the space taken up in the page.

**Note:** The visible/hidden setting does not have a hereditary nature on the widgets entered in it (as a section or a container). If, for example, a table is set to hidden and the widgets inside it are visible, the latter will be displayed. Instead ‘none’ is inherited.

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered.

This property is available both for the section and for all the widgets of the page, but it is not available at page level.

![](<../../../.gitbook/assets/image (1063).png>)

**STEP1: Example of Page Creation with Visibility**

![](<../../../.gitbook/assets/image (734).png>)

The page comprises:

* Three Styled Selectors which allow the respective selection of:
  * Customer
  * Invoice Number
  * Product
* Two Text Area widgets to display and change the quantity and description of the product selected.
* The Text Areas will be visible or hidden based on the result of the control queries associated to the
* Text Field widgets specified below.
  * Text Field A contains a control query on the Product Family of the selected Product. For all product families with code 10128 it will not be possible to make any change to the description. The Text Field is not visible.
  * Text Field B contains a control query on the product quantity. All the quantities <100 can be changed. The Text Field is not visible.
  * The Submit button sends the changes made to the Database through an update query.

The control queries on the Text Fields return the two ‘hidden’ and ‘visible’ values. These two values are read by the visibility property of the Text Area objects: the parameter associated to the Text Field is typed on the visibility field.

**STEP2: Viewing in Decisyon Web**

![](<../../../.gitbook/assets/image (915).png>)

The three cases of value viewing in Decisyon Web are shown at the top.

Note how the quantity or description can be changed or not, based on the product selected. The box is not visible if its value cannot be changed.

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

{% hint style="info" %}
_In order to have a uniform background on the web page which displays a Page, the background effects are applied to all of the page and NOT to its container; as a result, if a container of the page has a width of 50px set (regardless of auto-expand) and a red background, this color will be applied to the entire web page displaying the Page._
{% endhint %}

### Margin (Container Style)

The margin property allows you to define the margins of the container.\
The values ​​will be assigned respectively to the top, right, bottom and left (example: 2px top, 4px right, 6px bottom, 8px left) separated by commas. Only values in pixels are accepted

Some Examples

![](<../../../.gitbook/assets/image (792).png>)

![](<../../../.gitbook/assets/image (1800).png>)

![](<../../../.gitbook/assets/image (713).png>)

![](<../../../.gitbook/assets/image (955).png>)

### Flex (Container Style)

The propeirtà Flex is activated when the widget is inserted in a Row or Column container that has the Flex property enabled .

This property can take a numeric value. This number defines the space occupied by that widget inside the container.

Example:

To create the spacing between the first widget and the penultimate one, simply configure the Flex property of each widget in the following way:

![](<../../../.gitbook/assets/image (1006).png>)

* **Widget 1 :** Felx=5
* **Widget 2** : Flex=2
* **Widget 3:** Flex = 1

This means that the container column will be divided into 8 parts (the sum of the values entered in the Flex property) and each widget will be reserved a space equal to the value entered in the property. (See img below)&#x20;

{% hint style="info" %}
This value is always retained even when the window is resized.
{% endhint %}

![](<../../../.gitbook/assets/image (1682).png>)



## Container Size

### Dimensioning (Container Size)

The dimensions of the container may be defined in **absolute value** (pixel) or as a **percentage**.

The properties for dimensioning the container are (_Container_ folder, _Container Size_ group):

* **width** : set the width taken up by the container of the object. If insert a percentage value then you can use this properties:
  * **min-width** : set the minimum width of the container in percentage value. The scrollbar will appear in case the width of the object exceeds the minimum width.
  * **max-width:** Set the maximum width of the container in absolute or percentage value. The scrollbar will appear in case the width of the object exceeds the maximum width.
* **height**: Ser the height taken up by the container of the object.If insert a percentage value then you can use this properties:
  * **min-height:** set the minimum height of the container in percentage value. The scrollbar will appear in case the heidht of the object exceeds the minimum height.
  * **max-height:** Set the maximum height of the container in absolute or percentage value. The scrollbar will appear in case the height of the object exceeds the maximum height .

{% hint style="info" %}
The property accept the empty values. In this case, from web, the Widgets it will have a sufficient size to be able to see itself correctly. See the example below
{% endhint %}

{% hint style="warning" %}
**Exception:** the Row Container can have a % as height (height, min-height, max-height) only if the container has the flex property enabled
{% endhint %}

### Description

A title may be associated with the **container** and displayed as a text box above the object, whose width coincides with the one of the same container:

* **show-title**(_Container_ folder, _Title_ group) enables the title of the container, which activates
  * **title-text:** text of the title
  * **titleFontSize:** set the size of the font using in the title

### Title

Also a **description** may be associated with the container, displayed as an information icon which has the content of the description as tooltip:

* **show-description** (_Container_ folder, _Description_ group) activates the display of the description of the object, which activates
  * **description-text:** specifies the text of the description, shown as tooltip

![](<../../../.gitbook/assets/image (1609).png>)

## Advanced

In the folder Advance you can find the property to customize the page using Css , Javascript and others

* **metadataInfo**: The reference to the page is defined in  **object-id**  property (**metadataInfo**,  property Advanced folder, Advanced group)
* **sync drill-down:** Drill-down operations among the page widgets can be synchronized. When a drill-down is performed on a level in one of the reports on the page, the same operation will be performed automatically on any other report on the page, when they have the same level and the same hierarchy.

**Note:** If the page has a crosstab associated with the same report, enabling the property has no effect.

* **autoSubmit:** Enables, when accessing the page, the auto submit of the modified parameters
* **autoCleanParams:** Enables, when accessing the page, the re-initialization of the page parameters

### JavaScript and CSS

The combination of JavaScript and CSS is perfect to make a Page even more attractive and interactive.

CSSs are used to manage the page layouts and it is possible, for example, to edit the formatting of the text.

**JavaScript** is the most used language to create dynamic events, such as one that changes the content of a page depending on the actions of the end user.

JavaScript and CSS in the Pages

![](<../../../.gitbook/assets/image (1114).png>)



To use customized CSS and/or JavaScript it is necessary to load them previously through the Resource Catalog module (_Presentation Administrator_, _Resource Catalog_ section) and subsequently associate them to the Page page.

For the selection of the application default files, see _JavaScript and CSS_ _Selection_ section.

CSS and JavaScript settings are configured on the Page page. By selecting the area of the page, in the properties of the folder _**Object**_ there are:

* **css** (CSS grou&#x70;**)**&#x66;or the selection of the CSS type resources, previously created
* _**i**_**mport-css-from-model** (CSS grou&#x70;**)** to use the CSSs defined at application level
* **import-order** (CSS grou&#x70;**)**&#x74;o establish the CSS order among those of the application and those of the page:
  * AFTER CSS of the application AFTER those of the Page
  * BEFORE CSS of the application BEFORE those of the Page
* **javascript** (JavaScript _grou&#x70;**)**_ for the selection of the JAVASCRIPT type resources, previously created
* **import-JS-from-model** (JavaScript grou&#x70;**)** to use JAVASCRIPT defined at application level
* **import-order** (JavaScript group) to establish the CSS order among those of the application and those of the page:
* _AFTER_ CSS of the application AFTER those of the Page
  * BEFORE CSS of the application BEFORE those of the Page

Three different modes can be defined through these properties for CSS and/or JavaScript application:

* CSS or JavaScript exclusively used of the Page.

**Example only for CSSs:**

_**import-css-from-model disabled**_ and CSS resources selected in the _**css property**_

* CSS or JavaScript imported exclusively from the model.

**Example only for CSSs:**

_**import-css-from-model enabled**_ and CSS resources loaded only from the properties of the application

* CSS or JavaScript of the model and the Page.

**Example only for CSSs:**

_**import-css-from-model**_ enabled and CSS resources selected in the _**css**_ property; in _**import-order**_ to establish the order among those imported from the application and those selected in the css of the Page.

## Example

### **Example - fill-style: Image Extension Style**

**Step 1:- fill-style: image extension style**



The Page publishes an indicator entered in a TABLE component which a background image is associated with as shown in the figure. In the example the extension style is shown of the image on the TABLE applied with the FILL-STYLE property:

* FILL HORIZONTALLY the background image extends along the horizontal axis of the container.
* FILL ALL the background image extends until entirely filling the space of the container.

**Step 2. Position: position of the image compared to the container**

![](<../../../.gitbook/assets/image (803).png>)

This Page publishes the same TABLE component of the previous example. In this case, the positionings available via the POSITION property are applied: the figure indicates the value selected on each container.

**Step 3: Repeat Style**

![](<../../../.gitbook/assets/image (1345).png>)

This Page publishes the TABLE component where the repetition styles are applied via the REPEAT STYLE property: the figure indicates the value selected on each container.

### Example- How to use the Class-name property

In this example we will see how to customize the border of a container using a custom CSS.

Below we can see the final result. The top of the container is decorated with a green line and the border with a raised effect.

![](<../../../.gitbook/assets/image (1338).png>)

#### Step 1 - Define the CSS

Below we can see the code of the CSS file, used to customize the container.

```
.container-decoration > .dshObjBody{
	background: #ffffff;
	height: calc(100% - 37px) !important;
	margin: 8px;
	padding: 8px;
	border-top: 5px solid #009530 !important;
	box-shadow:0 1px 3px 0 rgba(0,0,0,.2),0 1px 1px 0 rgba(0,0,0,.14),0 2px 1px -1px rgba(0,0,0,.12);
}
```

**Step 2 - Import the CSS**

![](<../../../.gitbook/assets/image (590).png>)

Access the Resource Catalog module and select the CSS files that will be used inside the Page.

{% hint style="info" %}
The CSS File must be imported as a Resource via the [Resource Catalo](../../app-functionality/resource-catalog/)
{% endhint %}

#### Step 3 - How to Configure the page

![](<../../../.gitbook/assets/image (595).png>)

The page is made up of a Row Container and a Column Container into which a Chart widget has been inserted.

In the **Class-name property** of the Column Container, insert the name of class define in the CSS. In this example the name is container-decoration

The system will apply the decoration to the selected containe&#x72;**.**

![](<../../../.gitbook/assets/image (471).png>)

**Insights: Associating Resources with the Application**

It’s possible to associate the resources with the properties of the application: in the Page section, associate the CSS and the Javascript in the related properties (also shown in the figure). In this case all the pages created in the application will be applied the Style define in the css.

![](<../../../.gitbook/assets/image (478).png>)

## **Example - How to define the dimensions of the object**

Below we will illustrate how to configure the size of objects.

* **WITHOUT SPECIFYING HEIGHT and / or WIDTH**

The widget takes up the space it needs when you insert it on the page, maintaining the default values for height and width.

![](<../../../.gitbook/assets/image (1396).png>)

The chart adapts in width taking up all the available space.

* **SPECIFY MINIMUM SIZE (MIN-WIDTH and / or MIN-HEIGHT)**

The widget takes up the necessary space respecting the minimum dimensions set. The scroll bar will appear in case the object width exceeds the minimum width.

In this example the min-width= 900px and the min-height= 500

![](<../../../.gitbook/assets/image (1642).png>)

![](<../../../.gitbook/assets/image (1233).png>)

When the window is resized and the minimum height and width is lower than the one set, the scrollbars appear.

* **SPECIFY DIMENSION (WIDTH and / or HEIGHT)**

The widget must take the size you set, although it does not need to expand to fill the container area.

![](<../../../.gitbook/assets/image (1452).png>)



* **SPECIFY MAXIMUM SIZE (MAX-WIDTH and / or MAX-HEIGHT)**

The widget occupies the necessary space within the limits set by the maximum size.

If the size of the content is larger than the container, then the scrollbars will appear on the container.

![](<../../../.gitbook/assets/image (1716).png>)



* **BLANK VALUE FOR ALL PROPERTIES**

if you HAVE a Widgets and I set all the values to empty, from the web the Widgets will have a sufficient size to be able to see itself correctly.

![](<../../../.gitbook/assets/image (954).png>)

![](<../../../.gitbook/assets/image (815).png>)
