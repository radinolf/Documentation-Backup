# Generic Widgets

## How to create a Generic Widget

We are going to create the classic **Hello World** in AngularJS.&#x20;

In this simple widget, the user provides input via an input field, and as the user is typing in this input field, the UI gets updated with the latest value retrieved from the input field.

<figure><img src="../../../.gitbook/assets/image (1584).png" alt=""><figcaption></figcaption></figure>

The main steps to create a new Generic widget in DAC are the following:

1. [Create a new widget in the Widget Catalog](generic-widgets.md#step-1-create-a-new-widget-in-the-widget-catalog)
2. [Develop your widget code](generic-widgets.md#step-2-develop-your-widget-code)
3. [Publish your widget](generic-widgets.md#step-3-publish-your-widget)
4. [Set up your page by using your widget in the Page Design](generic-widgets.md#step-4-set-up-your-page-by-using-your-widget-in-the-page-design)
5. [View your page in DAC web application](generic-widgets.md#step-5-view-your-page-in-dac-web-application)

{% hint style="info" %}
This is the process for creating a widget of type **Generic**. For [**Data Presentation**](data-presentation-widgets.md) widgets, after the first step it is necessary also to associate an existing report to get data definition in JSON format.
{% endhint %}

### Step 1 - Create a new Widget in the Widget Catalog

Open the Widget Catalog Page from the Main Menu:&#x20;

* Select **Widget Designer**
* Click **New Widget**                                                                                                                                                                                                                                                                                                                                                                                                                &#x20;

{% hint style="warning" %}
Only Administrator role can display and open the Widget Editor
{% endhint %}

Fill out the form to insert your widget's information:

* Select the widget type "**Generic"** (without report association). This step is mandatory
* Input a mandatory name for the new widget.
* Select the folder in which you want to locate the widget in the catalog.
* Click **Save.**

<figure><img src="../../../.gitbook/assets/image (1369).png" alt="" width="491"><figcaption></figcaption></figure>

If the widget is successfully created, a confirmation message will be displayed

<figure><img src="../../../.gitbook/assets/image (1662).png" alt="" width="329"><figcaption></figcaption></figure>

Open the newly created widget from the folder where it has been saved:

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1372).png" alt=""><figcaption></figcaption></figure></div>

* The Widget Editor opens &#x20;
* Start developing the Hello World widget

### Step 2 - Develop your widget code

Define the widget view in the file `index.html`**.** You can eventually copy the following code.

Set the ng-model directive for the TextBox:

```html
<div class="exampleContainer">
      <p>Write something in the input box.</p>
      <p>Name: <input type="text" ng-model="name" placeholder="Enter name here"></p>
      <h1 ng-show="name">Hello {{name}}!</h1>
      <h1 ng-show="name">Hey <span ng-bind="name"></span>!</h1>
</div>
```

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1365).png" alt=""><figcaption></figcaption></figure></div>

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (766).png" alt=""><figcaption></figcaption></figure></div>

Define the widget style in the file `index.css`**:**

```css
.exampleContainer, .exampleContainer > p, .exampleContainer > h1{
    padding: 10px;
    font-size: 20px;
}
```

### Step 3 - Configure the Settings properties

Configure the CSS resource as a dependency:

* Select the **SETTINGS** tab
* Select **Main settings** --> **DEPS**
* In the **CSS dependences** property, click **Select file** to select the `index.css` resource &#x20;
* Save

View and test your widget in the **Preview** section

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1575).png" alt=""><figcaption></figcaption></figure></div>

### Step 4 - Publish your widget

Publish the widget and make it available in Page Design in Design Studio.&#x20;

1. Select the **Settings** tab. The administrator uses the Settings tab to add widget components that will be shown in the widget's properties panel when it is added to the page.
2. Select the **Main** settings group of properties.
3. Set a new Logical name for the widget.&#x20;
4. Select the **Published** property.

{% hint style="info" %}
The system automatically gives a default logical name when a new widget is created.&#x20;

We advise modifying the widget's default logical name and assigning the widget a meaningful logical name.&#x20;

For further details on the Logical Name of widgets, go to [Widget Settings](widget-settings.md#logical-name).
{% endhint %}

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1649).png" alt=""><figcaption></figcaption></figure></div>

### Step 5 - Set up your page by using your widget in the Page Design

Add the new widget on a page:

* Open the Page Design
* Create a new page&#x20;
* Drag the Hello World widget to the page. It is located inside the same folder that was chosen during its creation

<figure><img src="../../../.gitbook/assets/image (1656).png" alt="" width="489"><figcaption></figcaption></figure>

* Save and publish the page.

### Step  6 - View your page in DAC web application

Open the widget on the Web Application and input some text in the input field

<figure><img src="../../../.gitbook/assets/image (1400).png" alt=""><figcaption></figcaption></figure>
