# E.1 How to configure a Geographical Map using OSM provider

This example explains configuring a geographical map using only a simple report and setting **OpenStreetMap** as the Map provider. It also shows how to configure custom pins which open a detail window when clicked.

{% hint style="warning" %}
&#x20;It is assumed that the page the pins will open via the Drill-through has already been created.
{% endhint %}

Create the data source report. The report must have the following mandatory fields:

1. **R01\_item**
2. **R01\_latitude**
3. **R01\_longitude**
4. **R01\_active\_flag**

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Enable a Drill-through on this report from the **Report Editor**![](../../../.gitbook/assets/3) and configure the following properties:

* **show-on:** Set **Icon and text** as the drill-through rendering type&#x20;
* **drill-through-position:** Set the column of the report where to associate the drill-through. **ACTIVE\_MAP\_FLAG\_ID** in this example.
* **openActionType:** Select **Page** as the target object type that the drill-through will open.
* **page:** Select a page previously created.&#x20;

<figure><img src="../../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

In the Page Design, create a new page and drag the **Map widget**.

Associate the report created in the first step to the widget.

Map report columns to specific fields in the **fields association** property of the widget:

<div align="left"><figure><img src="../../../.gitbook/assets/image (68).png" alt="" width="563"><figcaption></figcaption></figure></div>

Configure the following specific properties for the **Map** widget:

* **Map Provider:** Set the map source. Maintain the default configuration set on **OSM** option.
* **Default pin icon:** Set the icon for the pins. Go to the [https://material.io/icons/](https://material.io/icons/) to get the name of a different icon shape than the default one (place). In this example "map".
* **Default pin color:** Set a custom color for the active pins. In this example "rgb(255,153,51)"

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Display the **Map** widget on the Web Application.

<figure><img src="../../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

Click an active pin on the map to open detailed data on a new window.

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
