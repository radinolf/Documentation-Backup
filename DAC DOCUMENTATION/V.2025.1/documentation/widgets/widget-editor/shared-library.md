# Shared library

## Introduction

The **Shared library** contains resources that can be shared across different widgets.

<div data-full-width="false"><figure><img src="../../../.gitbook/assets/image (660).png" alt=""><figcaption></figcaption></figure></div>

Shared libraries are composed of:&#x20;

* Some assets as JavaScript libraries, CSS definitions, template HTML, or images that widget developer wants to reuse on multiple widgets&#x20;
* Resource dependencies settings (JS, CSS)

The specific properties to configure the shared libraries are available in the **Widget Resources** and **Settings** panels of the Widget Editor.

The properties of the **MAIN** group in the **Settings** tab are shared with those of the Generic widget type.

The specific properties are related to the **Widget Resources** panel, where you can set the JS, HTML, CSS, gif, or png type resources.

### Upload Resources in a  shared library

Open a shared library and choose the item **Upload Resources** from the context menu in the Widget Resources panel of the Widget Editor to upload a new shared library.

<figure><img src="../../../.gitbook/assets/image (1660).png" alt=""><figcaption></figcaption></figure>

After uploading the resources, there are different actions in the context menu of the file name, such as download the file locally or, in the case of images, opening a preview.

<figure><img src="../../../.gitbook/assets/image (1773).png" alt=""><figcaption></figcaption></figure>

### Use a Shared library in a widget

The resources loaded inside the shared library are available to all widgets created in the Widget Catalog after it is published.

Select **Add library** item from the **shared folder** of your widget to select a shared library to use. The list of all published libraries can be selected in a dialog.

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1577).png" alt=""><figcaption></figcaption></figure></div>

## How to create a Shared library

The main steps to create a new Shared library in DAC are the following:

### Step 1 - Create the resources  that compose your Shared library

Create the resources that compose your Shared library. This example will use an image and a CSS resource as a dependency.

```css
.small_logo {
    width: 52px;
    height: 90px;
    display: block;
    -webkit-mask-image: radial-gradient(34% 30%, black 99%, transparent 100%);
    -webkit-mask-size: 95%;
    background: url("./logo.png") -20px 2px no-repeat;
    -webkit-mask-position: 6px -26px;
    background-size: 190%;
}

.big_logo {
    background-image: url('./logo.png');
    background-position: center center;
    background-repeat: no-repeat;
    width:730px;
    height:232px;
    margin: 0 auto;
}

.header{
    font-family: Impact, Charcoal, sans-serif ;
    font-size: 24px;
    text-align: left;
    height: 40px;
    background-color: #ccc;
    color: forestgreen;
    padding: 10px 0px 0px 10px;
}

```

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1769).png" alt=""><figcaption></figcaption></figure></div>

### Step 2 - Create your Shared library

Open the Widget Catalog Page from the DAC sidebar:&#x20;

* Select **Widget Designer**
* Click **New Widget**                                                                                                                                                                                                                                                                                                                                                                                                                &#x20;

{% hint style="warning" %}
Only Administrator role can display and open the Widget Editor
{% endhint %}

Fill out the form to insert your widget's information:

* Select the widget type "**Shared library"**&#x20;
* Input a mandatory name for the new widget.
* Select the folder in which you want to locate the Shared library in the catalog.
* Click **Save.**

<figure><img src="../../../.gitbook/assets/image (1107).png" alt=""><figcaption></figcaption></figure>

If your Shared library is successfully created, a confirmation message will be displayed

<figure><img src="../../../.gitbook/assets/image (1852).png" alt="" width="329"><figcaption></figcaption></figure>

Open the newly created Shared library from the folder where it has been saved (DAC Widget Hub): the Widget Editor opens.

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1326).png" alt=""><figcaption></figcaption></figure></div>

### Step 3 - Upload the resources in your Shared library

Upload the resources created in the first step that will compose your Shared library:

* Righ-click the Root of the Widget Resources.
* Select **Upload Resources** option.

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1319).png" alt=""><figcaption></figcaption></figure></div>

### Step 4 - Configure the Dependency resources

Configure the CSS resource as a dependency:

* Select the **Settings** tab
* Select **Main settings** --> **DEPS**
* In the **CSS dependences** property, select the **style.css** resource load in the Shared library&#x20;
* Save

<figure><img src="../../../.gitbook/assets/image (1587).png" alt=""><figcaption></figcaption></figure>

### Step 5 - Publish your Shared library

1. In the **Main settings**, select-->**MAIN**
2. Set the **Logical name** for the Shared library
3. Select the **Published** property

<figure><img src="../../../.gitbook/assets/image (1836).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
It is very important to assign a self-explanatory and unique logical name, because:

* In the presence of multiple shared libraries with the same name, only one can be published.
* A self-explanatory logical name helps you access and use the Decisyon API to manage the widget information in your code.
{% endhint %}

Now you can use your Shared library in multiple widgets.

## How to use a Shared library in multiple Widgets

This explanation will show how to use a Shared library in two different Widgets:

### Step 1 - Create the widgets

Create two **Generic** widgets. Go to [How to create the Widgets](./#how-to-create-the-widgets) for more the details on creating widgets:

Develop the first widget (**WIDGET A**): define the widget view of the **WIDGET A** in the file **index.html.** You can eventually copy the following code:

```html
<div class="header">WIDGET A</div>
<div class="contentCenter">
    <div class="big_logo"></div>
</div>
```

Define the widget style in the file **index.css:**

```css
.contentCenter {
    -webkit-box-shadow: 0px 7px 0px 0px rgba(51,68,97,1);
    -moz-box-shadow: 0px 7px 0px 0px rgba(51,68,97,1);
    box-shadow: 0px 7px 0px 0px rgba(51,68,97,1);
    width: 100%;
}
```

Configure the **index.css** as a dependency:

* Select the **Settings** tab
* Select **Main settings** --> **DEPS**
* In the **CSS dependences** property, select the **index.css** resource&#x20;
* Save

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (810).png" alt=""><figcaption></figcaption></figure></div>

Develop the second widget (**WIDGET B**): define the widget view of the **WIDGET B** in the file **index.html.** You can eventually copy the following code:&#x20;

```html
<div class="container">
    <table>
        <tr><th colspan="2" class="header">WIDGET B</th></tr>
        <tr>
            <td>
                <div class="small_logo">
                </div>
            </td>
            <td>
                <table>
                    <tr>
                        <td>Company name:</td>
                        <td>Companyname</td>
                    </tr>
                    <tr>
                        <td>Address:</td>
                        <td>Street Avenue</td>
                    </tr>
                    <tr>
                        <td>Telephone:</td>
                        <td>111-9872</td>
                    </tr>
                    <tr>
                        <td>Fax:</td>
                        <td>111-9823</td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</div>
```

Define the widget style in the file **index.css:**

```css
.container {
    width: 1000px;
    border:1px #ccc solid;
    margin-top:100px;
}
.container table {
    width: 100%;
    font-size: 18px;
}
```

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1156).png" alt=""><figcaption></figcaption></figure></div>

Configure the **index.css** as a dependency:

* Select the **Settings** tab
* Select **Main settings** --> **DEPS**
* In the **CSS dependences** property, select the **index.css** resource&#x20;
* Save

### Step 2 - Use the same Shared library in the Widgets

Use a published Shared library in both the widgets created in the first step. Go to [How to create a Shared library](shared-library.md#how-to-create-a-shared-library) for more details on creating the Shared libraries. You can eventually create the same Shared library of this explanation:

Include the **Shared Library** in **WIDGET A**

* Open the Widget Editor of the **WIDGET A**&#x20;
* Right-click the **shared folder** in the **Widget Resources**&#x20;
* Select the **Add library** item from the context menu

<figure><img src="../../../.gitbook/assets/image (681).png" alt=""><figcaption></figcaption></figure>

* Select your Shared Library from the list of all published libraries that will appear in a window
* Click OK

<figure><img src="../../../.gitbook/assets/image (670).png" alt=""><figcaption></figcaption></figure>

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (767).png" alt=""><figcaption></figcaption></figure></div>

Include the same **Shared Library** in **WIDGET B.**  Use the same procedure as WIDGET A.

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (676).png" alt=""><figcaption></figcaption></figure></div>

### Step 3 - Publish the Widgets

Publish both the **WIDGET A** and the **WIDGET B**:

* Select  **Main settings** -->**MAIN**&#x20;
* Set the **Logical name** for the widget
* Select the **Published** property

### Step 4 - Use the Widgets on a page

Add the WIDGET A and the WIDGET B  on a page:

* Open the Page Design
* Create a new page&#x20;
* Drag the widgets to the page. They are located inside the same folder that was chosen during them creation
* View your page in DAC web application

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1744).png" alt=""><figcaption></figcaption></figure></div>
