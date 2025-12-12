# Base Pattern

{% hint style="info" %}
With version 2022.3 the **Flex** and **Overflow-auto** properties have been moved under the **ContainerSize** property group
{% endhint %}

The base pattern are:

* [**Strech middle**](base-pattern.md#stretch-middle) it is a pattern with a central flexible widget and a side widget with fixed width.
* [**Stretch and Item fixed:**](base-pattern.md#stretch-and-item-fixed) it’s a combination of a flexible widgets and one or more widgets that are just after the flexible one.
* [Fixed widget on a side: ](base-pattern.md#fixed-widget-on-a-side)In this pattern there are one or more widget with fixed width that must be always rendered on the side of the page (right or left) and the remaining widget is flexible.
* [**Footer Fixed**](base-pattern.md#footer-fixed) it’s a pattern used to have a fixed footer at the bottom of the page.
* [**Grid**](base-pattern.md#grid) **:** it’s used to defined the layout of many widgets in the page, one more than one rows.
* [**Sidebar** ](base-pattern.md#sidebar)**:** it’s used to define a fixed sidebar on the left (usually).
* [**3 Columns with wrap:**](base-pattern.md#columns-with-wrap) it’s a pattern used to create a 3 column layout with flexible width and with wrapping enabled.

## Stretch middle&#x20;

In this pattern you have two widgets on the left and the right of the page that are fixed and must remain in their position (left and right) when the page is resized and you have a central section that is “flexible” and change its width accordingly to the viewport.

This pattern is frequently used to create **headers** of page, with a logo on the left, another widget on the right and the central space that must be properly resized.&#x20;

In the following example there is an “image” widget on the left, a “textfield” widget in the middle and an “execute button” widget on the right.

To build such kind of header the main propertis to configure are the following:

<figure><img src="../../../../.gitbook/assets/image (768).png" alt=""><figcaption></figcaption></figure>

To build such kind of header the main propertis to configure are the following:

<br>

<figure><img src="../../../../.gitbook/assets/image (494).png" alt=""><figcaption></figcaption></figure>

* The three widgets are in a column container widget with the property `flex-container` enabled.
* The widgets on the left and right have fixed width in pixel and the widget in the middle use the property `flex` =1 to adjust its width accordingly to the remaining space in the container.

**Step 0 - Set page and section properties**

* Set the `width` and `height` of the **page** to 100%
* Set the `width` and `height` of the **section** to 100%

**Step 1 : Insert Column Container**

<figure><img src="../../../../.gitbook/assets/image (1816).png" alt=""><figcaption></figcaption></figure>

Add to the page a **Column Container** widget and enable the following properties:

* `Flex-container`: enabled. The container will be “flexible”.
  * `vertical-align`: center
* `Wrap-content:` enabled. When the width of all widgets is higher that the available container’s width, the widgets will wrap
* `Width:` 100%. The container will take up all the availble space horizontally.

**Step 2 : Insert widgets in the container**

<figure><img src="../../../../.gitbook/assets/image (982).png" alt=""><figcaption></figcaption></figure>

Add in the page the “**Image**” widget and set the following properties:

* `width`: 200px. Fixed width in pixel.

Add in the page the “**Textfield**” widget and set the following properties:

* `flex`:1 It will take up all the flex space available, which is the space left after the fixed width element are rendered.

Add in the page the “**Execute Button**” widget and set the following properties:

* `width`: 150px. Fixed width in pixel.

**Step 3 : View on RunTime**

Publish the page and open it in the browser. The textfield in the middle takes up all the available space and the two widgets on the left and right have fixed width.

When you resize the browser’s window (you can also use the responsive toolf of the browser’s developer tools) the widgets on the left and right will not change but the textfield’s width will be adjusted accordingly to the new viewport.

<figure><img src="../../../../.gitbook/assets/image (742).png" alt=""><figcaption></figcaption></figure>

## Stretch and item fixed

In this pattern there is the first widget that is flexible and two (or more) fixed width widgets. It is used for example to create the footer of an insertion form. Usually fixed widgets, are the buttons to save or delete the data entered in the form and are always aligned to the right, while the flex widget serves to reserve space when the window is resized.&#x20;

&#x20;

<figure><img src="../../../../.gitbook/assets/image (838).png" alt=""><figcaption></figcaption></figure>

To create the pattern as shown above, widgets are configured as follows:

<figure><img src="../../../../.gitbook/assets/image (944).png" alt=""><figcaption></figcaption></figure>

* &#x20;The three widgets are placed in a Column Container with the flex-container property enabled to make it flexible.
* **Flex**: We set the value to 1 . It indicates that it will take up all the available space left by the non flexible elements. The second and third widgets will have a fixed width, the top and bottom margins set and are two buttons.

#### How to…

**Step 1 : Insert Column Container**

<figure><img src="../../../../.gitbook/assets/image (764).png" alt=""><figcaption></figcaption></figure>

Insert in the page a **Column Container** widget and enable the properties:

* **Flex-container** to make the container flexible.
* **horizontal-align:** the horizontal alignment of widgets in the Row Container is left
* **certical-align:** vertical alignment of conentui widgets in the Row Container is at the bottom
* **width**: the widgets must occupy in width the maximum available space 100%.
* **height** :the widget will have a fixed height of 60 px.

&#x20;

&#x20;**Step 2 : Insert Widgets**

<figure><img src="../../../../.gitbook/assets/image (1169).png" alt=""><figcaption></figcaption></figure>

&#x20;

Enter the **Plain Text** widget configures the following properties:

* **width**: the width of the widget must occupy the maximum available space 100%.
* **height :** the height of the widget must occupy the maximum available space 100%.
* **min-height:** the minimum height will be 50px.

This widget enabled as Flex, will help us to manage the spacing between the left edge of the page and the first button widget. Alternatively, you can also use a Textfield widget or an empty container.

Enter the **Execute Button** widget and configure the following properties:

* **width**: 150 px fixed width

Enter the **Execute Button** widget and configure the following properties:

* &#x20;**width**: 150 px fixed width

&#x20;

**Step 3 : View on RunTim**

When the page resizes the widgets buttons remain fixed maintaining the size set, while the widget (not visible) reserves a space when the window is resized thus avoiding the displacement of the side widgets.

<figure><img src="../../../../.gitbook/assets/image (843).png" alt=""><figcaption></figcaption></figure>

## Fixed widget on a side

In this pattern there are one or more widget with fixed width that must be always rendered on the side of the page (right or left) and the remaining widget is flexible.

It is frequently used when you want to have buttons (or other widgets) that are always rendered on the right (or on the left) of the page, in example for the “save” or “cancel” button in an input form. Buttons usuall have fixed width, while the widget that is used to configure flex ajdust its width accordingly to the device viewport.

<figure><img src="../../../../.gitbook/assets/image (1753).png" alt=""><figcaption></figcaption></figure>

To build such kind of pattern the main properties to configure are the following:

<figure><img src="../../../../.gitbook/assets/image (1096).png" alt=""><figcaption></figcaption></figure>

* The widgets are in a “**Column Container”** widget with flex-container property enabled
* The first widget has property flex:1 and thus it will take up all the space remaining after the two other widgets in the container are rendere.
* The second and the third widget has fixed width in pixel.

**Step 0 - Set page and section properties**

* Set the width and height of the **page** to 100%
* Set the width and height of the **section** to 100%

**Step 1 : Insert Column Container**

<figure><img src="../../../../.gitbook/assets/image (1328).png" alt=""><figcaption></figcaption></figure>

Add in the page the “**Column Container**” widget and set the following properties:

* Flex-container: enabled
* horizontal-align: right. By default the horizontal-align is left, but in this case it will set on the right.
* vertical-align:center
* width:100% The column container is rendered using all the available width. Make sure that also the section and the page are set to width:100%
* height : 60px The height of the container is fixed.

&#x20;**Step 2 : Insert Widgets**

<figure><img src="../../../../.gitbook/assets/image (480).png" alt=""><figcaption></figcaption></figure>

Add in the page the “**Plain text**” widget and set the following properties:

* flex: 1
* height : 100%

This widget ensure that the two buttons are always “pushed” to the right because, being flexible, its width is adjusted accordingly to the availabel space.

Add in the page two “**Execute button**” widgets and set for each of them the following properties:

* width: 150 px This widget is not flexible

**Step 3 : View on RunTime**

When the browser is resized, the buttons are always rendered on the right of the page, while the flexible “Plaint Text” widget adjust its width accordingly to the viewport and always “pushing” the two buttons on the left of the page.

<figure><img src="../../../../.gitbook/assets/image (531).png" alt=""><figcaption></figcaption></figure>

## Footer fixed

In this pattern there is a widget or a group of widgets that must be always rendered at the bottom of the page.

It is used when you need to create a “footer” that is always displayed at the bottom of the page, regardless the height of the content that is preceding the footer. When the content’s height increase and is bigger that the viewport, the footer will be anyway displayed in the bottom of the page.

<figure><img src="../../../../.gitbook/assets/image (1719).png" alt=""><figcaption></figcaption></figure>

To build such kind of pattern the main properties to configure are the following:

<figure><img src="../../../../.gitbook/assets/image (1618).png" alt=""><figcaption></figcaption></figure>

**Step 0 - Set page and section properties**

* Set the width and height of the page to 100%
* Set the width and height of the section to 100%

**Step 1: Set the dimensions of page, section and row container**

<figure><img src="../../../../.gitbook/assets/image (771).png" alt=""><figcaption></figcaption></figure>



* Select both the page and the section and set
  * width: 100%
  * height: 100%
*   Add in the page the **Row Container** widget and set the following properties:

    * cells: 2
    * flex-container: enabled
    * horizontal-alig&#x6E;**:** left
    * Vertical-alig&#x6E;**:** bottom
    * width:100%
    * height:100%





**Step 2 - Widget Crosstab- Widget Stepper**

<figure><img src="../../../../.gitbook/assets/image (1404).png" alt=""><figcaption></figcaption></figure>

Add a **Crosstab** widget (or another widget) in the first cell of the row container and set

* flex: 1
* width:100%

Add a **Stepper** widget (or another widget) in the **second cell** of the row container and set the following properties:

* width:100%

**Step 2 : View on RunTime**

Open the page in the web application. The stepper widget is always displayed at the bottom of the page, even when the number of records in the crosstab can not be displayed in the viewport.

<figure><img src="../../../../.gitbook/assets/image (889).png" alt=""><figcaption></figcaption></figure>

## Sidebar

In this pattern there is a column of fixed width and 100% height on the left (or on the right) and the remaining widgets in the page are in a second column that is flexible. It is used when you want to create a “Sidebar” that contains a set of button that bring additional featues in the page. The fixed-width column is done using the properties min-width and max-width.

<figure><img src="../../../../.gitbook/assets/image (1825).png" alt=""><figcaption></figcaption></figure>

To build such kind of pattern the main propertis to configure are the following:

<figure><img src="../../../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

**Step 0 - Set page and section properties**

* Set the width and height of the page to 100%
* Set the width and height of the section to 100%

**Step 1 : Add the containers in the page**

<figure><img src="../../../../.gitbook/assets/image (1832).png" alt=""><figcaption></figcaption></figure>

**Column Container N°1**

Add in the page a **Column Container** widget and set the following properties:

* cells-number:2. This is the “external” container
* flex-container: enabled
* width:100%
* height:100%

**Row Container N°2**

Add in the **first cell** of the column container a **Row Container** widget and set the following properties:

* cells-number: 5. This is the container where all the buttons will be positioned
* flex-container: enabled
* horizontal-alignment: left
* width: 60
* height: 100%

**Row Container N°3**

Add in the **second cell** of the column container a **Row Container** widget and set the following properties:

* cells-number: 2. This is the container where the flexible widgets will be rendered
* flex: 1. It will take all the available space of the column container in which it is positioned.
* horizontal-alignment: left
* overflow-auto: enabled
* height:100%

**Column Container N°4**

Add in the **second cell** of the row container a **Column Container** widget and set the following properties:

* cells-number: 2.
* flex: 1. It will take all the available space of the row container in which it is positioned.
* width:100%
* Wrap-Content: enabled. When the width of all widgets is higher that the available container's width, the widgets will wrap

**Step 2 Add the buttons in the sidebar**

<figure><img src="../../../../.gitbook/assets/image (479).png" alt=""><figcaption></figcaption></figure>



For each cells of the row container, add a **Button** widget and set the property

* width: 100%. The button will be flexible, but the entire sidebar has a width of 60 pixel

**Step 3 Add the widgets in the other container**

<figure><img src="../../../../.gitbook/assets/image (1706).png" alt=""><figcaption></figcaption></figure>



* **Row Container N°2**: add a **Chart** widget with width:100% and height:100%.
* **Column Container N°4:** in each cell add a **Crosstab** widget with min-width: 500. flex: 1. It will take all the available space of the row container in which it is positioned.

**Step 3 : View on RunTime**

Open the page in runtime. The sidebar is always displayed on the left of the page. When the browser is resized, the widgets in the second column of the column container are adjusted and wrapped without affecting the sidebar.

<figure><img src="../../../../.gitbook/assets/image (1462).png" alt=""><figcaption></figcaption></figure>

#### Columns with wrap

This pattern is used when you can split the page in three column where the central column contains the main information and is widget that the two lateral columns, tha contains less relevant information or actions.

All columns are “flexible” and their size is adjusted accordingly to the viewport; when the viewport is small, columns are wrapped.

<figure><img src="../../../../.gitbook/assets/image (990).png" alt=""><figcaption></figcaption></figure>

To build such kind of pattern the main properties to configure are the following:

<figure><img src="../../../../.gitbook/assets/image (1140).png" alt=""><figcaption></figcaption></figure>

**Step 0 - Set page and section properties**

* Set the width and height of the page to 100%
* Set the width and height of the section to 100%

**Step 1 - Define the structure of the page**

<figure><img src="../../../../.gitbook/assets/image (1307).png" alt=""><figcaption></figcaption></figure>



Add in the page the outer “**Column Container N°1”** that is the one used to split the page in three columns. Set the following properties:

* cells-number: 3
* flex-container: enabled
* wrap-content: enabled
* width: 100%
* height 100%

**Row ContainerN°2.**

* flex: 3. This container will be 3 times width that the previous container.

**Step 2 - Add widgets in the containers**

<figure><img src="../../../../.gitbook/assets/image (1310).png" alt=""><figcaption></figcaption></figure>

**Widget N°1 :** in this example a “**Key Value Set**” widget was used. Set the following properties:

* flex: 1
* min-width: 350

**Widget N°2:** in this example a “**Chart**” widget was used. Set the following properties:

* flex: 2
* width & height: 100%

**Widget N°3:** in this example a “**Crosstab**” widget was used. Set the following properties:

* flex: 1
* width & height:: 100%

**Widget N°4:** in this example a “**Discussion**” widget was used. Set the following properties:

* flex: 1
* overflow-auto: enabled
* min-width: 350

**Step 3 : View on RunTime**

Open the page in runtime. The central column is widest than the other two column, since the flex properties is 3 times the value of the other columns. When the browser is resized, the widgets are re-adjusted keeping the same proportion.

Please note that also the “Key value set” widget automatically re-adjusted its layout accordingly to the available space.

<figure><img src="../../../../.gitbook/assets/image (547).png" alt=""><figcaption></figcaption></figure>

## Grid

The “**Grid**” pattern is very common and it is used when you need to have several widgets in the page and the page itself requires responsivness. It is very used to build forms. When the viewport changes, widgets wrap.

<figure><img src="../../../../.gitbook/assets/image (1349).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (1677).png" alt=""><figcaption></figcaption></figure>

To build such kind of pattern the main properties to configure are the following:

<figure><img src="../../../../.gitbook/assets/image (1664).png" alt=""><figcaption></figcaption></figure>

**Step 1 - Define the structure of the page**

Add in the page the outer "**Row Container**" widget and set the following properties:

<figure><img src="../../../../.gitbook/assets/image (1672).png" alt=""><figcaption></figcaption></figure>

* cells-number: 3
* flex-container: enabled
* width: 100%
* height: 100%

In each cell of the row container, insert a “**Column Container**” and set for each of the following properties

* flex: 1. The three column containers will have the same height, calculated accordingly to the viewport.
* flex-container: enabled
* wrap-conten&#x74;**:** enabled. Widgets wraps when the viewport is small.

**Step 2 - Insert the widgets in the first column container**

<figure><img src="../../../../.gitbook/assets/image (774).png" alt=""><figcaption></figcaption></figure>

**Widget Chart**

* flex: 2.
* min-width: 300px

**Widget Key Value**

* flex: 1.
* min-width: 300

Let’s now create the small input form in the central cell of the first column container.

<figure><img src="../../../../.gitbook/assets/image (476).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (1797).png" alt=""><figcaption></figcaption></figure>



Add in the cell a "**Row Container**" widget and set the following properties:

* cell-number: 3
* margin: (16,16,16,16)
* flex-containe&#x72;**:** enabled
* items-alignement: left. Widgets in this container will be rendered on the left.
* width: 100%
* min-width: 300px. When the viewport is smaller than 300px, the form wraps.

Add in the **first** and **second** cell of the row container a **Textfield** and **Dropdown** widget with the following properties:

* width: 100%

Add in the **third** cell of the row container a **Column Container** widget and set the following properties:

* cells-number: 2
* flex-container: enabled

In the two cells of the column container, add two **Button** widgets and set for both the following properties:

* width and height: not defined. Their width depends on the content of the widget.

**Step 2 - Add widgets in the second column container**

<figure><img src="../../../../.gitbook/assets/image (751).png" alt=""><figcaption></figcaption></figure>



* Flex: 1
* min-width: 300px

In the **second** cell of the second column container, insert a **Stepper** widget and set the following properties:

* Flex: 2. This widget will have twice the width of the crosstab widget.

**Step 3 Add widgets in the third column container**

<figure><img src="../../../../.gitbook/assets/image (604).png" alt=""><figcaption></figcaption></figure>



In the **first** cell of the third column container, insert a **Crosstab** widget and set the following properties:

* Flex: 1
* min-width: 300px

In the **second** cell of the third column container, insert a **File Manager** widget and set the following properties:

* Flex: 1.
* min-width: 300. Widget will never be less than 300px width.
* min-height: 250. Widget will never be less than 250px height.

In the **third** cell of the third column container, insert a **Discussion** widget and set the following properties:

* Flex: 1.
* min-width: 300. Widget will never be less than 300px width.



**Step 3 - View on RunTime**

Open the page in runtime. When the browser is resized, the widgets are laid out accordingly to the properties you set in the container.

<figure><img src="../../../../.gitbook/assets/image (1254).png" alt=""><figcaption></figcaption></figure>
