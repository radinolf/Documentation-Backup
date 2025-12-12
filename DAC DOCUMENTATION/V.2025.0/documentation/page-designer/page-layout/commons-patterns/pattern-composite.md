# Pattern Composite



{% hint style="info" %}
With version 2022.3 the **Flex** and **Overflow-auto** properties have been moved under the **ContainerSize** property group
{% endhint %}

The “composite” patterns are patterns used to build more complex pages using one or more than one basic pattern explained in the previous chapter.

The composite pattern used more frequently are “[**Form**](pattern-composite.md#form)**”** and “[**Line Board**](pattern-composite.md#line-board)**”.**

## Form <a href="#form" id="form"></a>

This pattern is a composition of the “**Grid**” and “**Footer fixed**” pattern. It is very used to build a page with an input form where you need a footer fixed at the bottom that contains the “save” and “cancel button” and you need that the widgets of the form wraps in order to be used also on smaller devices like tablets or smartphones.

<figure><img src="../../../../.gitbook/assets/image (1368).png" alt=""><figcaption></figcaption></figure>

In this example you will create a page like in the following printscreen:

<figure><img src="../../../../.gitbook/assets/image (1036).png" alt=""><figcaption></figcaption></figure>

The page can be splitted in three main areas:

<figure><img src="../../../../.gitbook/assets/image (1191).png" alt=""><figcaption></figcaption></figure>

* On the left there are the form widgets, like dropdown, textfield etc. Thi section is expected to be visible at the top of the page when the viewport is small.
* On the right there are widgets that provide additional context in the form, like a “file manager” widget and “discussion” widget.
* On the bottom of the page the “save” and “cancel” button, with a right alignment. This section is expected to be always visible also on smaller viewports.

The following picture shows how the widgets are configured:

<br>

<figure><img src="../../../../.gitbook/assets/image (942).png" alt=""><figcaption></figcaption></figure>

In the following picture you can see how the structure of the page is used in the final rendering of the page:

<br>

<figure><img src="../../../../.gitbook/assets/image (1481).png" alt=""><figcaption></figcaption></figure>

In the following pictures you can see that the positioning of the widget in the page designer is exactly the same that will be rendered in the browser.

\
\
<br>

<figure><img src="../../../../.gitbook/assets/image (1187).png" alt=""><figcaption></figcaption></figure>

**Step 0 - Set page and section properties**

* Set the width and height of the page to 100%
* Set the width and height of the section to 100%

**Step 1 - Create the structure of the page**

<figure><img src="../../../../.gitbook/assets/image (1614).png" alt=""><figcaption></figcaption></figure>



Add in the page the first outer “**Row Container**” widget that will contains all the other widgets in the page. Set the following properties:

* flex-containe&#x72;**:** enabled
* width: 100%
* height: 100%

**Step 2 - Create the structure of the main section of the page**

<figure><img src="../../../../.gitbook/assets/image (530).png" alt=""><figcaption></figcaption></figure>



* Flex-containe&#x72;**:** enabled
* Flex: 1
* overflow-aut&#x6F;**:** enabled
* wrap-conten&#x74;**:** enabled

**Step 3 - Create the structure of the two main columns**

<figure><img src="../../../../.gitbook/assets/image (1773).png" alt=""><figcaption></figcaption></figure>



In each cells of the column container add a “**Row Container**” widget.

* The **Row Container N°1** contains the widgets with a basic pattern
  * flex-container: enabled
  * flex: 1
  * margin: (16,16,16,16)
  * min-widt&#x68;**:** 500
  * height: 100%
* **The Row Container N ° 2** contains the same widgets as the example for the [**grid pattern**](base-pattern.md#grid)
  * flex-container: enabled
  * flex: 2
  * margin: (16,16,16,16)
  * height:100%

**Step 4 - Define the structure of the grid**

<figure><img src="../../../../.gitbook/assets/image (1144).png" alt=""><figcaption></figcaption></figure>



In the first cell of the row container add a **Column Container** widget, that will be used to have two textfields side by side. Set the following properties:

* flex-container: enabled
* horizontal-align **:** left
* wrap-content: enabled
* width: 100%

**Step 5 - Define the structure of the fixed footer**

<figure><img src="../../../../.gitbook/assets/image (604).png" alt=""><figcaption></figcaption></figure>



In the second cell of the column container add another **Column Container** that will contains the widget of the footer.

* cells: 3
* flex-containe&#x72;**:** enabled
* horizontal-align : right
* vertical- align **:** center
* width **:** 100%
* heigh&#x74;**:** 54 px

**Step 6 - Add all the form widgets**

<figure><img src="../../../../.gitbook/assets/image (1717).png" alt=""><figcaption></figcaption></figure>

Add all the widgets in the page and set the properties like in the picture.

**Setp 7 - Add some CSS to customize the page**

{% hint style="info" %}
In the DAC version 2023.1.0, the Card style can be applied directly from the property "**preconfigured-style"** of container.
{% endhint %}

To create a “card” style, you can apply a custom CSS class to the container widgets in the page.

<figure><img src="../../../../.gitbook/assets/image (760).png" alt=""><figcaption></figcaption></figure>

The custom CSS class is applied on the highlighted container, in the property class-css.

<figure><img src="../../../../.gitbook/assets/image (642).png" alt=""><figcaption></figcaption></figure>



The CSS used in this example is the following:

```
.box-border{
     border:2px solid #32AD3C;
     height: calc(100% - 5px) !important;
     box-shadow: 10px 10px 5px #dedede;
}
```

## Line Board

The **Line Board** pattern is used to create complex pages like bord to monitor production lines, that requires to have many information and could be also consumed on smaller devices like tablets.

<figure><img src="../../../../.gitbook/assets/image (1197).png" alt=""><figcaption></figcaption></figure>

The page can be splitter in the main components: the main column in the middle that takes most of the space and contains information to be quickly monitored. The two column on the left and right are smaller but contains information or action that needs to be available at a glance, even if less relevant than the information available in the main column.

<figure><img src="../../../../.gitbook/assets/image (1418).png" alt=""><figcaption></figcaption></figure>

In the following pictures you can see the structure of the page and how it is built in Design Studio:

<figure><img src="../../../../.gitbook/assets/image (1474).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (1795).png" alt=""><figcaption></figcaption></figure>

**Step 0 - Set page and section properties**

* Set the width and height of the page to 100%
* Set the width and height of the section to 100%

**Step 1 - Define the outer structure of the page**

<figure><img src="../../../../.gitbook/assets/image (1691).png" alt=""><figcaption></figcaption></figure>

Add in the page a "**Column Container**" widget and set the following properties:

* cells-number: 3
* flex-container: enabled
* wrap-content : enabled
* width: 100%
* heght: 100%

**Step 2 - Define the structure of each column**

<figure><img src="../../../../.gitbook/assets/image (653).png" alt=""><figcaption></figcaption></figure>

In the **first** cells of the outer column container add a “**Row Container N°1**” and set the following properties:

* Cells-number **:** 2
* Flex: 1
* flex-container: enabled
* horizontal-alig&#x6E;**:** left
* min-widt&#x68;**:** 360 px
* height: 100%

In the **second** cells of the outer column container add a “**Row Container N°2**” and set the following properties:

* Cells-number **:** 3
* Flex: 3. This section will be 3 times wider than the later columns
* flex-container: enabled
* horizontal-alig&#x6E;**:** center
* height: 100%

In the **third** cells of the outer column container add a “**Row Container N°3**” and set the following properties:

* Cells-number **:** 2
* Flex: 1
* flex-container: enabled
* horizontal-alig&#x6E;**:** left
* min-widt&#x68;**:** 360 px
* height: 100%

**Step 3 - Define the inner structure of the three columns**

<figure><img src="../../../../.gitbook/assets/image (991).png" alt=""><figcaption></figcaption></figure>

Add to the page the “**Row Container**” widgets like in the above picture and set the following properties

**Row Container N° 1**

* Cells-number **:** 3
* Fle&#x78;**:** 2
* flex-container: enabled
* horizontal-alig&#x6E;**:** left
* Width and heigh&#x74;**:** not defined. Widgets will take the space they need.

**Row Container N° 2**

* Cells-number **:** 1
* overflow-aut&#x6F;**:** enabled
* flex-container: enabled
* horizontal-alig&#x6E;**:** left
* widt&#x68;**:** 100 %
* height: 155

**Row Container N° 3**

* Cells-numbe&#x72;**:** 1
* Flex:1
* flex-container: enabled
* horizontal-alig&#x6E;**:** left
* Width : 100%.

**Column Container N° 4**

* Cells-number **:** 2
* overflow-aut&#x6F;**:** enabled. This will allow the scroll only in the widget, and not in the entire page.
* Flex:1
* flex-container: enabled
* Widt&#x68;**:** 100%

**Row Container N° 5**

* Cells-number **:** 1
* Flex : 2
* overflow-aut&#x6F;**:** enabled
* flex-container: enabled
* horizontal-alig&#x6E;**:** left
* height: 100%

**Step 3 - Define the structure of the this row in the central column**

<figure><img src="../../../../.gitbook/assets/image (475).png" alt=""><figcaption></figcaption></figure>

Add in the column container two **Row Container** and set the following properties on both:

* flex **:** 1
* min-widt&#x68;**:** 480 px
* heigh&#x74;**:** 100%

**Step 4 - Add all the widgets in the containers**

<figure><img src="../../../../.gitbook/assets/image (1607).png" alt=""><figcaption></figcaption></figure>

Add all the widgets in the page and set the properties like in the above picture.

**Setp 5 - Add some CSS to customize the page**

To create a “card” style, you can apply a custom CSS class to the container widgets in the page.

{% hint style="info" %}
In the DAC version 2023.1.0, the Card style can be applied directly from the property "**preconfigured-style"** of container.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (1741).png" alt=""><figcaption></figcaption></figure>

The custom CSS class is applied on the highlighted container, in the property class-css.

<figure><img src="../../../../.gitbook/assets/image (1372).png" alt=""><figcaption></figcaption></figure>

The CSS used in this example is the following:



```
.box-border{
     border:2px solid #674ea7;
}
 .box-card > .dshObjBody{
     border-radius: 2px !important;
     box-shadow: 0 1px 3px 0 rgb(0 0 0 / 40%) !important;
     border-width: 0px !important;
     margin:8px;
     padding: 8px;
}
 .custom-title{
     font-size: 20px;
     font-weight: bold;
     color: #666;
}
 .custom-box > .dshObjBody{
     background: #ffffff;
     height: calc(100% - 32px) !important;
     margin: 8px;
     padding: 8px;
     box-shadow:0 1px 3px 0 rgba(0,0,0,.2),0 1px 1px 0 rgba(0,0,0,.14),0 2px 1px -1px rgba(0,0,0,.12);
}
 .custom-box.secondary >.dshObjBody{
     border-top: 5px solid #59b5e6 !important;
}
 .custom-box.warning >.dshObjBody{
     border-top: 5px solid #f30100 !important;
}
```
