# Page Layout

## Introduction

Starting from version 2022.2.0 App Composer adopted the CSS Flexbox module to create responsive and flexible pages adding new set of properties and changing the behaviour of some existing widgets and features.

{% hint style="info" %}
If you are migrating from a DAC version before 2022.2.0 you can read the dedicated chapter about the migration of existing pages.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (482).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1024).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1605).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (490).png" alt=""><figcaption></figcaption></figure>

## What is Flexbox <a href="#what-is-flexbox" id="what-is-flexbox"></a>

**Flexbox**, or Flexible Box Layout, is a CSS module that defines an efficient way to create page layout, align and distribute space among items in a container, even when their size is dynamic or even not defined, “flexible”.

<figure><img src="../../../.gitbook/assets/image (453).png" alt=""><figcaption></figcaption></figure>

With flexbox the children of a flex container can be laid out in any direction (horizontal or vertical), and can "flex" their sizes, either growing to fill unused space or shrinking to avoid overflowing (rendering scrollbars) the parent. Both horizontal and vertical alignment of the children can be easily manipulated.



<figure><img src="../../../.gitbook/assets/image (497).png" alt=""><figcaption></figcaption></figure>



There are some basic concepts of flexbox that are useful to know to be more effective in creating a responsive page with DAC Page Designer.

Flex items in a flex container can be laid out along two axes:&#x20;

* the **main axis** is the axis running in the direction the flex items are laid out. In example, when the main axis is “row” the widgets are laid out from left to right; when the main axis is “column” the widgets are laid out from top to bottom. The start and end of this axis are called the main start and main end.
* the **cross axis** is the axis running perpendicular to the direction the flex items are laid out in. The start and end of this axis are called the cross start and cross end.

<figure><img src="../../../.gitbook/assets/image (572).png" alt=""><figcaption></figcaption></figure>

To create a responsive page, some Flexbox properties are applied on the flex container and some other properties on the flex items.

Here some example of properties set on the **flex container** and used in DAC:

* Main axis direction
* Horizontal alignment
* Vertical alignment
* Wrapping

Here some example of properties set on the **flex items** and used in DAC:

* Flex (shorthand for Flexflow)
* Overflow

These properties are better ex**l**pained in the next chapters.

{% hint style="info" %}
Please note that DAC expose to the user only some of the main properties of the CSS Flexbox module, the ones that make sense to be modified to create responsive pages. Page developer doesn’t need to know in details the CSS properties of Flexbox, but a basic knowledge of the concepts is required to be more effective when creating the page.
{% endhint %}

More references about Flexbox:

[![](https://developer.mozilla.org/favicon-48x48.cbbd161b.png)CSS Flexible Box Layout - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)

[![](https://developer.mozilla.org/favicon-48x48.cbbd161b.png)Basic concepts of flexbox - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)

[![](https://developer.mozilla.org/favicon-48x48.cbbd161b.png)Flexbox - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

[![](https://www.w3schools.com/favicon.ico)CSS Flexbox (Flexible Box)](https://www.w3schools.com/css/css3_flexbox.asp)

[![](https://i0.wp.com/css-tricks.com/wp-content/uploads/2021/07/star.png?fit=32%2C32\&ssl=1)A Complete Guide to Flexbox | CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

## Flexbox in DAC: containers and widgets <a href="#flexbox-in-dac-containers-and-widgets" id="flexbox-in-dac-containers-and-widgets"></a>

It is possible to create flexible pages in App Composer because Flexbox can be implemented using a dedicated set of properties, widgets and pattern when creating the page.

The widgets **column container** and **row container** can optionally be defined as “**flex containe**r” enabiling the property `flex-container` and they will be rendered using flexbox properties.

<figure><img src="../../../.gitbook/assets/image (823).png" alt=""><figcaption></figcaption></figure>

* when you use the **column container** widget with `flex-container` enabled, the **main axis is “row”** and the widgets are laid out from left to right. The name of widget chande in \<Flex Column Container>
* when you use the **row container** widget with with `flex-container` enabled, the **main axis is “column”** and the widgets are laid out from top to bottom. The name of widget chande in \<Flex Row Container>

As a consequence, any **widget** placed inside the column or row container is considered as “flex items” in Flexbox terminology. When the container is a `flex-container`, the widgets inside have the property `flex` that can be used to properly configure the responsivness and flexibility of the flex widgets in the flex container.&#x20;

<figure><img src="../../../.gitbook/assets/image (673).png" alt=""><figcaption></figcaption></figure>

The property `flex` accepts only integer number (or empty values) and defines the ability of the widget to grow in the container if necessary. It accepts a unitless value that is used as a proportion and it dictates what amount of the available space inside the flex container the widget should take up.

If all the widgets have `flex` set to 1, the remaining space in the flex container will be distributed equally to all the widgets in the container. If one of the widget has a value of 2, that widget would take up twice as much of the space than the others. Negative numbers are invalid.

<br>

<figure><img src="../../../.gitbook/assets/image (1479).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Be careful: the flex value is a proportion that is applied to calculate the width of the widget in respect of the available space in the flex container. It is not the width of the widget, neither in pixel or % values. The relationship between the properties width/height and flex is explained in the dedicated chapter.
{% endhint %}

In example, let’s assume that the flex container will be rendered with 1000 pixel. The space of each widget will be:

<br>

<table data-header-hidden><thead><tr><th width="133"></th><th width="80"></th><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Widget</strong></td><td><strong>Flex</strong></td><td><strong>Proportion</strong></td><td><strong>Flex width available</strong></td><td><strong>Widget width</strong></td></tr><tr><td>Report 1</td><td>1</td><td>1/3 = 33%</td><td>1000 px</td><td>333 px</td></tr><tr><td>Report 2</td><td>1</td><td>1/3 = 33%</td><td>1000 px</td><td>333 px</td></tr><tr><td>Report 3</td><td>1</td><td>1/3 = 33%</td><td>1000 px</td><td>333 px</td></tr></tbody></table>

&#x20;The same example as above can be configured with different values of `flex` in the widgets:

<figure><img src="../../../.gitbook/assets/image (1180).png" alt=""><figcaption></figcaption></figure>

With this configuration, the available container space is splitted in 6 (1+3+2, the sum of the flex properties of the widgets in the container) and each wiget will take up a the spaced accordingly to the flex value.

<br>

<table data-header-hidden><thead><tr><th width="133"></th><th width="72"></th><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Widget</strong></td><td><strong>Flex</strong></td><td><strong>Proportion</strong></td><td><strong>Flex width available</strong></td><td><strong>Widget width</strong></td></tr><tr><td>Report 1</td><td>1</td><td>1/6 = 16%</td><td>1000 px</td><td>166 px</td></tr><tr><td>Report 2</td><td>3</td><td>3/6 = 50%</td><td>1000 px</td><td>500 px</td></tr><tr><td>Report 3</td><td>2</td><td>2/6 = 33%</td><td>1000 px</td><td>333 px</td></tr></tbody></table>

<br>

<figure><img src="../../../.gitbook/assets/image (804).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1181).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1230).png" alt=""><figcaption></figcaption></figure>

The same proprortion is maintained also when the browser is resized:

<br>

<figure><img src="../../../.gitbook/assets/image (1700).png" alt=""><figcaption></figcaption></figure>

The property `flex` is used to calculate the amount of the available space inside the flex container the widget should take up: when we mention “available” it means that the container may also have a widget that is not flexible because, in example, it has a fixed width. In that case, the “available flex space” is calculated on the space that remains in the container after the fixed elements is rendered.

In the example we can see how to configure two widgets with different flex values ​​and a fixed width widget.

<figure><img src="../../../.gitbook/assets/image (1557).png" alt=""><figcaption></figcaption></figure>

In example, let’s assume that the flex container will be rendered with 1000 pixel, but in this scenario report 3 has a fixed width of 100 pixel. The remaining flexible space is 1000 px - 100 px = 900 px, and thus:

<table data-header-hidden><thead><tr><th width="143"></th><th width="97"></th><th width="117"></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Widget</strong></td><td><strong>Flex</strong></td><td><strong>Proportion</strong></td><td><strong>Flex width available</strong></td><td><strong>Widget width</strong></td></tr><tr><td>Report 1</td><td>1</td><td>1/3 = 33%</td><td>900 px</td><td>300 px</td></tr><tr><td>Report 2</td><td>2</td><td>2/3 = 66%</td><td>900 px</td><td>600 px</td></tr><tr><td>Report 3</td><td>-</td><td>-</td><td>-</td><td>100 px</td></tr></tbody></table>

<br>

<figure><img src="../../../.gitbook/assets/image (1617).png" alt=""><figcaption></figcaption></figure>



Starting from version 2022.2.0 it is strongly reccomended to build pages using flex properties.

&#x20;

There are few important rules that you must follow in order to build effective responsive pages:

* make sure the properties `width` and `height` of the **page** are set to 100%.
* make sure the properties `width` and `height` of the **section** are set to 100%.
* use only one main flex **row container** or flex **column container** widget and develop all the layout in this container. Nested flex containers are supported.
* work only with widgets with the property `position = relative`. The position `absolute` is maintened only for retro-compatibility but it creates unexpected results when used in a flexible layout.

{% hint style="info" %}
If you are creating a new page since 2022.2.0, by default on a new page the `width` and `height` of both the page and the section are set to 100%.

If you are modifying pages built before 2022.2.0 and you want to make them flexible, make sure to set the `width` and `height` of both the page and the section to 100%..
{% endhint %}

{% hint style="danger" %}
Having two or more flex containers in different cells of the page designer may cause unexpected behaviour when rendering the page.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1036).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1448).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1182).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1136).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (654).png" alt=""><figcaption></figcaption></figure>

### Example: build the first flex page <a href="#example-build-the-first-flex-page" id="example-build-the-first-flex-page"></a>

In the following example we show you how to build a page using the widgets in the row and column containers, using the Flex property that allows to create a flexible layout.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/Whitewater/RowAndColContainer/ResizeDef.gif" %}

In the image below, you can see the page layout and the expected behaviors of each widget when the browser is resized.

<figure><img src="../../../.gitbook/assets/image (1764).png" alt=""><figcaption></figcaption></figure>



The page is designed to have to main areas: the header and the content.

* Header: you find the logo, a search box and a validation button. When the browser is resized they must stay in the same position.
* Content: there are 2 chart widgets and 1 crosstab widget. Those widgets will be adjusted on browser resize, and will wraps when there is not enough width available

**Step 0 - Set page and section properties**

<figure><img src="../../../.gitbook/assets/image (1778).png" alt=""><figcaption></figcaption></figure>



* Set the width and height of the **page** to 100%
* Set the width and height of the **section** to 100%

**Step 1 - Containers' Definition**

**1. Row Container**

<figure><img src="../../../.gitbook/assets/image (509).png" alt=""><figcaption></figcaption></figure>

Insert a Row Container with 2 rows( Cells-number=2) and make sure that flex-container is enabled

**2. Column Container**

In order to build the header add 1 column container in the first row.

<figure><img src="../../../.gitbook/assets/image (835).png" alt=""><figcaption></figcaption></figure>

Set flex = 1 in the column container, so that it will take all the available space within the row container, and make sure that flex-container is enabled.

**2.1 Column Container - Add Widgets**

Now we add the widgets in the Column Container, maintaining the default values for width and height.

<figure><img src="../../../.gitbook/assets/image (1241).png" alt=""><figcaption></figcaption></figure>

In the image below you can see the RunTime result. As you can notice, the widgets are positioned on the left and the image widget image is not properly spaced from the previous one. It also shows the scroll bar in the image widget because the default size are too small to be displayed in the image.

<figure><img src="../../../.gitbook/assets/image (1767).png" alt=""><figcaption></figcaption></figure>

**2.3 Column Container- Activate Flex Property**

Now let’s see how to use the Flex property on the image widget. The widget should adapt automatically at the container creating a proper space from the second widget.

<figure><img src="../../../.gitbook/assets/image (860).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (601).png" alt=""><figcaption></figcaption></figure>



* **Widget Image :** Flex=1
* **Widget Textfield** : width:150px
* **Widget Execute Button:** width:150px

It means that the column container will have the second and third widget with a fixed width and aligned on the right since the widget logo, on the left, will take all the available space.

This dimension value will remain the same even when the browser will be resized. Below the final result.

<figure><img src="../../../.gitbook/assets/image (909).png" alt=""><figcaption></figcaption></figure>

**3. Column Container**

The last step is to create the second row of widget&#x73;**.**

<figure><img src="../../../.gitbook/assets/image (1690).png" alt=""><figcaption></figcaption></figure>

Add in the second cell in the row container a new column containe&#x72;**.**

<figure><img src="../../../.gitbook/assets/image (926).png" alt=""><figcaption></figcaption></figure>

**Second column container** property:

* **Flex-container**: is active. All the widgets in this container will be considered as flex items.
* **Wrap Content:** is active: Widget will automatically go to a new line if the browser is resized and there is not enough space to render all in the same space.

In the new column container there are 2 chart widgets and 1 Crosstab widget. Let’s configure the most relevant properties:

1. **Widget1 - Chart**
   1. **min-width**: 300. It means that when browser is resized the widget should not be smaller than 300 pixel.
   2. **Flex**: 1
2. **Widget2 - Chart**
   1. **min-width**: 300.
   2. **Flex** : 1
3. **Widget3 - Crosstab**
   1. **min-width**: 300
   2. **Flex** : 2. This widget will be twice the width of the two chart widgets.

&#x20;

The sum of the `flex` property for the widgets is 4: the available width of the column container will be divided in 4: the two chart widgets will take up 25% of the container’s width each (1/4 = 2**5**%), while the crosstab will take up 50% of the container’s width (2/4 = 50%).

<br>

<figure><img src="../../../.gitbook/assets/image (668).png" alt=""><figcaption></figcaption></figure>

Let’s see how the page is rendered in the browser.

When there is enough width in the browser window, all the widgets aligned on the same row respecting the predefined Flex properties.

<figure><img src="../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>



When the browser is resized and there is not enough width, the widget will be rendered accordingly to the flex rules defined:

* The image in the header is smaller
* The button in the header will have a fixed width
* The crosstab wrapped on a new line, taking up all the available width in the second line
* The charts re-adjusted their width to take up the available width in the first line.



<figure><img src="../../../.gitbook/assets/image (1165).png" alt=""><figcaption></figcaption></figure>

When you reduce again the browser size, also the chart widgets wraps, adjusting their width to the available space.

<figure><img src="../../../.gitbook/assets/image (1433).png" alt=""><figcaption></figcaption></figure>

## Size and Wrap

It is possible to define for each widget (and also for the page and the sections in the page) 3 properties about the width and 3 properties about the height:

<table data-header-hidden><thead><tr><th width="278"></th><th></th></tr></thead><tbody><tr><td>width</td><td>height</td></tr><tr><td>min-width</td><td>min-height</td></tr><tr><td>max-width</td><td>max-height</td></tr></tbody></table>

Each one of this property accepts pixel, percentage or even empty values.

## Width

width sets the width of the widget and accepts value in pixels, percentage or even empty value.

When a value is **not set**, the width of the widget depends on the type of widget: it could be driven by its content (i.e. the “execute button” widget) or it could take up all the available space (i.e. the “crosstab” widget).

When a value in **pixel** is set, the width of the widget is assigned in pixel. If the content of the widget is bigger than the width, scrollbar are displayed. Using values in pixel, it’s not possible to set properties min-width and max-width

When a value in **percentage (%)** is set, the width of the widget is calculated as the percentage of the width of its container. If the content of the widget is bigger than the width, scrollbar are displayed

{% hint style="info" %}
When the widget is used in a column container with flex-container enabled and the widget has a flex value, the property width is ignored because the width will be calculated automatically by Flexbox.
{% endhint %}



#### Example 1: width not set

In a page we can use a column container with one column and use an execute button widget with some text. Do not set any value for the width on the widget. The width of the button depends on the length of the text:

<figure><img src="../../../.gitbook/assets/image (656).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1740).png" alt=""><figcaption></figcaption></figure>

When the text is longer, also the width of the widget is higher.

<figure><img src="../../../.gitbook/assets/image (966).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1811).png" alt=""><figcaption></figcaption></figure>

#### Example 2: width in pixel

Starting from the previous example, let's now define a fixed width of 250px for the widget. As visible, with a fixed width it's not possibile to define min-width or max-width.

<figure><img src="../../../.gitbook/assets/image (1216).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (523).png" alt=""><figcaption></figcaption></figure>

When the content is bigger, in this case the widget width **is not** automatically adjusted based on the conten&#x74;**.**

<figure><img src="../../../.gitbook/assets/image (1040).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1273).png" alt=""><figcaption></figcaption></figure>

#### Example 3: width in percentage

Starting from the example 1, let's now define 75% as width for the widget. The width of the widget will 75% of the width of the column container. In this case the column container has 100% as width of the section and the section is 100% width in respect of the page. This means that the button is 75% of the entire page.

<figure><img src="../../../.gitbook/assets/image (427).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (747).png" alt=""><figcaption></figcaption></figure>

When the window is resized, since we used % values also the button is automatically resized:

<figure><img src="../../../.gitbook/assets/image (1646).png" alt=""><figcaption></figcaption></figure>

### Min-width and Max-width

The property min-width sets the minimum width of a widget and it prevents the used value of the width property from becoming smaller than the value specified for min-width. It is a pixel value or a percentage value and it can be configured **only** when the property width is a percentage or is not set.

The property max-width sets the maximum width of a widget and it prevents the used value of the width property from becoming bigger than the value specified for max-width. It is a pixel value or a percentage value and it can be configured **only** when the property width is a percentage.

#### Example **1**: using min-width:

Configure an execute button with width = 100% in a container that has width =100%: the button has the same width of the viewport, 1015px in this example:

<figure><img src="../../../.gitbook/assets/image (1762).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1750).png" alt=""><figcaption></figcaption></figure>

Now set a min-width= 800px.

<figure><img src="../../../.gitbook/assets/image (1087).png" alt=""><figcaption></figcaption></figure>

When the viewport is more than 800pixel, the button takes up all the available width; when the viewport is below 800 pixel, scrollbars in the widget are rendered.

<figure><img src="../../../.gitbook/assets/image (691).png" alt=""><figcaption></figcaption></figure>

#### Example 2: using max-width

Configure an execute button with width = 100% in a container that has width =100%: the button has the same width of the viewport, 1015px in this example:

<figure><img src="../../../.gitbook/assets/image (1732).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1178).png" alt=""><figcaption></figcaption></figure>

Now set a max-width= 700px. Even if there is enough space, the widget will not exeed 700px as width.

<figure><img src="../../../.gitbook/assets/image (1327).png" alt=""><figcaption></figcaption></figure>

## Height

Height sets the height of the widget and accepts value in pixels, percentage or even empty value.

When a value is **not set**, the height of the widget is driven by its content.

When a value in **pixel** is set, the height of the widget is assigned in pixel. If the content of the widget is higher than the height, scrollbar is displayed. Using values in pixel, it’s not possible to set properties min-height and max-height.

When a value in **percentage (%)** is set, the height of the widget is calculated as the percentage of the height of its container. If the content of the widget is higher than the height, scrollbar is displayed.

{% hint style="info" %}
When the widget is used in a row container with flex-container enabled and the widget has a flex value, the property height is ignored because the height will be calculated automatically by flexbox.
{% endhint %}

If the property title of the widget is enabled, the spaces reserverd for the title is included in the height set for the widget.

#### Example 1: height not set

In a page we can use a row container with one row and use an execute button widget. Do not set any value for the heighton the widget.

The height of the button is defined by the widget in this case:

<figure><img src="../../../.gitbook/assets/image (1063).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1770).png" alt=""><figcaption></figcaption></figure>

#### Example 2: height in pixel

Starting from the previous example, let's now define a fixed height of 250px for the widget. As visible, with a fixed height it's not possibile to define min-height or max-height.

<figure><img src="../../../.gitbook/assets/image (1463).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1568).png" alt=""><figcaption></figcaption></figure>

#### Example 3: height in percentage

Starting from the previous examples, let's now define 75% as height for the widget. The height of the widget will 75% of the height of the row container. In this case the row container has 100% as height of the section and the section is 100% height in respect of the page. This means that the button is 75% of the entire page.

<figure><img src="../../../.gitbook/assets/image (1475).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (637).png" alt=""><figcaption></figcaption></figure>

It’s possible to configure the percentage height of each such in a way that they sum up to 100%:

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (921).png" alt=""><figcaption></figcaption></figure>

#### Example 4: title enabled

Starting from the previous example with height = 250, let’s now enable the title on the widget.

<figure><img src="../../../.gitbook/assets/image (1623).png" alt=""><figcaption></figcaption></figure>

As you can see from the picture, the overall height of the widget is still 250 pixel, but part of this height is now used to render the title.

<figure><img src="../../../.gitbook/assets/image (1293).png" alt=""><figcaption></figcaption></figure>

### Min-height and Max-height

The property min-heightsets the minimum height of a widget and it prevents the used value of the heightproperty from becoming smaller than the value specified for min-height. It is a **pixel** value or a **percentage** value and it can be configured **only** when the property height is a percentage.

The property max-height sets the maximum width of a widget and it prevents the used value of the height property from becoming bigger than the value specified for max-height. It is a pixel value or a percentage value and it can be configured **only** when the property height is a percentage.

#### Example 1: using min-height

To better understand how min-height works, let’s use a widget that could change its height depending on the content, i.e a crosstab widget. Let’s also use a second widget below the crosstab.

You can configure tha page in the following way and do not set any height for the crosstab widget

<figure><img src="../../../.gitbook/assets/image (1521).png" alt=""><figcaption></figcaption></figure>

Make sure the crosstab has very few data and open runtime. As you see, the height of the crosstab depends on its content:

<figure><img src="../../../.gitbook/assets/image (734).png" alt=""><figcaption></figcaption></figure>

Now set on the crosstab min-height = 300 px. As you can see, even if the content is smaller the crosstab gets 300px as height, leaving some blank space before the button:

<figure><img src="../../../.gitbook/assets/image (576).png" alt=""><figcaption></figcaption></figure>

#### Example 2: using max-height

Starting from the previous example, now configure the crosstab widget to have max-height = 300 (pixel).

<figure><img src="../../../.gitbook/assets/image (493).png" alt=""><figcaption></figcaption></figure>

Since the content of the crosstab is much higher than 300px, the widget height was set to 300px and scrollbars shows up:

<figure><img src="../../../.gitbook/assets/image (571).png" alt=""><figcaption></figcaption></figure>

## Managing overflow

The property overflow-auto is used to manage the [overflow](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Overflowing_content) when the content of a flexible widgets grows vertically (i.e. crosstab widget when the number of rows changes based on the volume of data or discussion widget when the number of messages increase) but you want to be sure that the scrollbars are rendered only where needed.

You may need to enable this property starting for the desired widget and up to the container widgets where it is placed.

<figure><img src="../../../.gitbook/assets/image (1396).png" alt=""><figcaption></figcaption></figure>

When the content of the widget grows vertically and is higher than it’s flex container, scrollbars will be used. When the property overflow-auto is used in combination with flex, the height of the container will be fixed even if the content is higher and the scrollbar will be used only in the widget.

<figure><img src="../../../.gitbook/assets/image (743).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (520).png" alt=""><figcaption></figcaption></figure>

In the above example let’s see the same page when the property overflow-auto is applied on the crosstab widget.

On the left, the crosstab widget has so many rows that its height is higher than the container is which it is located and the crosstab “expands” itself taking up some height allocated for the “File Manager” widget. Moreover, the entire page is equipped with a vertical scrollbar.

On the right, in the same page the property overflow-auto is applied on the crosstab widget. Even if the content is higher than the container, the scrollbar is used only on the widget, not in the entire page. The height of the container is fixed even if the content is higher.

In the following chapter there are several example to understand how to use the overflow-auto effectively.

### Overflow on the widget

In this example we can use a widget that may have a content higher that the vertical space allocated for him, i.e. the crosstab widget.

The widget is not inside other row container with flex enabled. In this case, the overflow-auto can be enabled on the crosstab widget itself.

<figure><img src="../../../.gitbook/assets/image (882).png" alt=""><figcaption></figcaption></figure>

Configure the page and widgets as follows:

<figure><img src="../../../.gitbook/assets/image (1154).png" alt=""><figcaption></figcaption></figure>

**Step 1 - Create the page**

<figure><img src="../../../.gitbook/assets/image (513).png" alt=""><figcaption></figcaption></figure>

Insert in the page a **Row Container** with the following properties

* cells-number = 2
* flex-container = enabled
* width and height = 100%

Insert in the first cell of the row Container a **File Manager** widget with the following properties

* width = 100%
* height = 250px. In this case we set a fixed height on this widget.

Insert in the second cell of the row Container a **Crosstab** widget (make sure it has many rows) with the following properties

* flex=1
* overflow-auto= enabled
* width and height = 100%

&#x20;

**Step 2 - View on web**

Please note that even if the content of the crosstab is higher, only the crosstab is equipped with a vertical scrollbar.

<figure><img src="../../../.gitbook/assets/image (1052).png" alt=""><figcaption></figcaption></figure>

If the overflow-auto would not have been activated, the scrollbar was used on the entire page and the crosstab widget would have taken up some of the vertical space of the file manager widget.

<figure><img src="../../../.gitbook/assets/image (687).png" alt=""><figcaption></figcaption></figure>

### Overflow on container

In this example, the widget that grows vertically is used in a flexible row container. In this case the property overflow-auto must be enabled on both widgets.

<figure><img src="../../../.gitbook/assets/image (1412).png" alt=""><figcaption></figcaption></figure>

Configure the page and widgets as follows:

<figure><img src="../../../.gitbook/assets/image (1628).png" alt=""><figcaption></figcaption></figure>

**Step 1 - Create the page**

<figure><img src="../../../.gitbook/assets/image (1636).png" alt=""><figcaption></figcaption></figure>

**Row Container N°1**

* cells-number = 2
* flex-container= active
* width and height= 100%

**Widget N°2 - File Manager**

* width= 100%
* height= 250

**Row Container N°3**

* cells-number = 1
* flex-container =active
* flex=1
* overflow-auto= enabled
* width and height = 100%

**Widget N°4**

* flex=1
* overflow-auto= active
* width and height 100%

**Step 2 - View on WEB**

When the content of the crosstab is higher than the container, scrollbars are rendered. Without the overflow-auto, the scrollbar would have been used on the entire page.

<figure><img src="../../../.gitbook/assets/image (1234).png" alt=""><figcaption></figcaption></figure>

### Overflow with nested containers

This is a more complex example where the widget that grows vertically is part of a series of nested containers.

In this scenario, the overflow-auto must be applied inside to outside to widget and all the containers.

<figure><img src="../../../.gitbook/assets/image (1635).png" alt=""><figcaption></figcaption></figure>

Configure the page and widgets as follows:



<figure><img src="../../../.gitbook/assets/image (1642).png" alt=""><figcaption></figcaption></figure>

**Step 1 - Create the page**

<figure><img src="../../../.gitbook/assets/image (931).png" alt=""><figcaption></figcaption></figure>

**Row Container n°1**

* cells-number = 2
* Columns-container = 1
* Flex-container= enabled
* width and height 100%

**Row Container N°2**

* cells-number=2
* overflow-auto= enabled
* columns-container = 1
* Flex-container= enabled
* width and height = 100%

**Column Container N°3**

* overflow-auto= enabled
* flex=1
* Flex-container=enabled
* wrap-content= enabled

**Row Container N°4**

* flex=1
* min-width= 480 px
* height= 100%
* Flex-container= enabled

**Row Container N°5**

* flex=1
* Flex-container=enabled
* min-width= 480 px
* height = 100%

**Column Container N°6**

* flex-container= enabled
* horizontal-align= right
* vertical-align= center
* width =100%
* height= 54px

&#x20;

**Step 2 : View on web**

Please note that when the browser windows is resized, the scrollbars are displayed only within the crosstab widget.

<figure><img src="../../../.gitbook/assets/image (1217).png" alt=""><figcaption></figcaption></figure>

## Wrap

Column container widgets has the property wrap-content that could be enable to wrap the widgets when the viewport width is not enough to render all of the in the same line.

Row container widget doesn’t have this property.

<figure><img src="../../../.gitbook/assets/image (636).png" alt=""><figcaption></figcaption></figure>

**Example 1: wrapping widgets in a non-flex container**

In this example we see the behavior of the wrap-content in a colum container with and without flex enabled.

The example shows how the widgets in a column container will be repositioned in the page if the browser is resized.

<figure><img src="../../../.gitbook/assets/image (492).png" alt=""><figcaption></figcaption></figure>

* Add a column container widget in the page with 3 columns (cells-number = 3)
* Enable the property wrap-content in the container
* Set the container’s size width=100%
* Add 3 widgets in the column container. All of them must have height=200px .

Open the page in the browser to see the result. Not having set the fixed height to the container, but only the heights of the widgets contained, so the window resizes these scale and the container adjusts in height.

<figure><img src="../../../.gitbook/assets/image (1593).png" alt=""><figcaption></figcaption></figure>

Now resize the browser window, from right to left. When the window shrinks and the space occupied by one of the widgets is less the widget is wrapped. Please note that the widgets wrap and maintain a fixed height of 200 px.

<figure><img src="../../../.gitbook/assets/image (1020).png" alt=""><figcaption></figcaption></figure>

**Example 2: wrapping widgets in a flex container**

Now let’s setup the same example but using flex containers.

<figure><img src="../../../.gitbook/assets/image (1306).png" alt=""><figcaption></figcaption></figure>



* Enable the property wrap-content and flex-container in the column container
* For each widget in the container set flex = 1 and min-width = 30&#x30;**.**

{% hint style="info" %}
In this case we can ignore the property width for each widget in the container because when the widgets are in the flex-container the width applied is automatically calculated accordingly to the property flex and applied depending on the viewport of the browser..
{% endhint %}

Open the page in the browser to see the result: each widget takes up 33% of the available width.

<figure><img src="../../../.gitbook/assets/image (623).png" alt=""><figcaption></figcaption></figure>

Now resize the browser window, from right to left. When the window shrinks and the space available for the widgets is less than 300 px the widget is wrapped.

Please note that in a flex container the widget that wraps is now able to take all the spaces available in the new line, and the widgets that were not wrapped were able to recalculate their width in order to take all the space available.

<figure><img src="../../../.gitbook/assets/image (1771).png" alt=""><figcaption></figcaption></figure>

## Alignment

The alignment of a widget in a container depends if the container is a flex container or not.

When the container is set as flex-container (both row container and column container) the following properties can be configured:

* **horizontal-align**: set the horizontal alignment of the widget in the flex container. Possible values: left, center, right, space around , space between, space evenly or empty. When empty, the “left” alignment is applied.
* **vertical-align**: set the vertical alignment of thw widget in the flex container. Possible values: top, center, bottom, space between, space evenly or empty. When empty, the “top” vertical alignment is applied.
* **flex-grap**: set a space, in px, between the widgets inserted in the container.

**horizontal-align options in Flex Column Container**

{% tabs %}
{% tab title="Left" %}
<figure><img src="../../../.gitbook/assets/image (599).png" alt=""><figcaption></figcaption></figure>

The widget is aligned to the left of the container
{% endtab %}

{% tab title="Center" %}
<figure><img src="../../../.gitbook/assets/image (778).png" alt=""><figcaption></figcaption></figure>

The widget is aligned to the center of the container
{% endtab %}

{% tab title="Right" %}
<figure><img src="../../../.gitbook/assets/image (1591).png" alt=""><figcaption></figcaption></figure>

The widget is aligned to the right of the container
{% endtab %}

{% tab title="space-around	 " %}
<figure><img src="../../../.gitbook/assets/image (1067).png" alt=""><figcaption></figcaption></figure>

Widgets are evenly distributed in the Flex Column Container with equal space around them.
{% endtab %}

{% tab title="space-evenly	 " %}
<figure><img src="../../../.gitbook/assets/image (794).png" alt=""><figcaption></figcaption></figure>

Widgets are distributed so that the spacing between any two adjacent alignment subjects, before the first alignment widget, and after the last alignment widget is the same.
{% endtab %}

{% tab title="space-between	 " %}
<figure><img src="../../../.gitbook/assets/image (1268).png" alt=""><figcaption></figcaption></figure>

Widgets are evenly distributed in the Flex Column Container ; first widget is on the start of container, last widget on the end of container.
{% endtab %}
{% endtabs %}



**Vertial lign options in Flex Row Container**

{% tabs %}
{% tab title="Top" %}
<figure><img src="../../../.gitbook/assets/image (1242).png" alt=""><figcaption></figcaption></figure>

The widget is aligned on top of the container
{% endtab %}

{% tab title="Center" %}
<figure><img src="../../../.gitbook/assets/image (447).png" alt=""><figcaption></figcaption></figure>

The widget is aligned in the center of the container
{% endtab %}

{% tab title="Bottom" %}
<figure><img src="../../../.gitbook/assets/image (779).png" alt=""><figcaption></figcaption></figure>

The widget is aligned at the bottom of the container
{% endtab %}

{% tab title="space-around" %}
<figure><img src="../../../.gitbook/assets/image (1196).png" alt=""><figcaption></figcaption></figure>

Widgets are evenly distributed in the Flex Row Container with equal space around them.
{% endtab %}

{% tab title="space-evenly" %}
<figure><img src="../../../.gitbook/assets/image (1815).png" alt=""><figcaption></figcaption></figure>

Widgets are distributed so that the spacing between any two adjacent alignment subjects, before the first alignment widget, and after the last alignment widget is the same.
{% endtab %}

{% tab title="space-between" %}
<figure><img src="../../../.gitbook/assets/image (1446).png" alt=""><figcaption></figcaption></figure>

Widgets are evenly distributed in the Row Column Container ; first widget is on the start of container, last widget on the end of container.
{% endtab %}
{% endtabs %}

When the widget **Column Container** is not configured to be flex, it is not possible to use the alignment property.

When the widget **Row Container** is not configured to be flex, the horizontal align property must be configured for each widget in the container.

<figure><img src="../../../.gitbook/assets/image (1383).png" alt=""><figcaption></figcaption></figure>

The **flex-gap** property allows you to insert space between widgets in a flex container.

In the image below we can see what the result is after applying a gap between the widgets, of 20 px present in a Flex container.

<figure><img src="../../../.gitbook/assets/image (1222).png" alt=""><figcaption></figcaption></figure>

## Margins

The margin property allows you to define the margins of the widget.

\
The values ​​will be assigned respectively to the top, right, bottom and left separated by commas. Only values in pixels are accepted.

<figure><img src="../../../.gitbook/assets/image (1264).png" alt=""><figcaption></figcaption></figure>

Some examples:



<table data-header-hidden><thead><tr><th width="161"></th><th width="95"></th><th></th><th width="140"></th><th></th></tr></thead><tbody><tr><td><strong>Margin Value</strong></td><td><strong>Top</strong></td><td><strong>Right</strong></td><td><strong>Bottom</strong></td><td><strong>Left</strong></td></tr><tr><td>8,0,0,0</td><td>8px</td><td>0px</td><td>0px</td><td>0px</td></tr><tr><td>8,4,0,0</td><td>8px</td><td>4px</td><td>0px</td><td>0px</td></tr><tr><td>2,4, 6, 8</td><td>2px</td><td>4px</td><td>6px</td><td>8px</td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (1025).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1704).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (592).png" alt=""><figcaption></figcaption></figure>
