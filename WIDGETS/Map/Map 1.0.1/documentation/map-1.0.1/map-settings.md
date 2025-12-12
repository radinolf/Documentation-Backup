# Map Settings

In the **Map settings** group are included all the options that allow for interaction with the Map:

### **Zooming**

The **Zooming** feature is used to zoom in and out of Maps to show in-depth information. It is controlled by the properties **Zoomable**, **Initial zoom**, and **Max zoom.**

<div align="left"><figure><img src="../../.gitbook/assets/image (42).png" alt="" width="563"><figcaption></figcaption></figure></div>

### Dragging

The **Dragging** property lets you move the Map up and down and left to right. Press and hold the mouse button and drag the Map to the desired position so that you may centre it on areas of interest.

### Center Longitude and Latitude

The **Center longitude** and **Center** **latitude** properties allow you to set the initial focal latitude and longitude position of the map layer. These properties accept input parameters. For example, if you select a country from a dropdown list, you may open a geographical map exactly in the selected country.

### Horizontal repeat

The **Horizontal repeat** property repeats the Map horizontally when you zoom out or drag it.

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

### Export coordinates on click

The **Export coordinates on click** property is useful when custom maps are used.&#x20;

When enabled, this feature exports the numeric value of the Longitude and Latitude coordinates of any selected point on the map so that you may retrieve the coordinates for placing your pins.

The exported coordinates may be used as parameters on the page so that you could eventually save them in the database (using the widget [Execute Button](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/WkKZCKo2sFH6DZRxWlwU/)) or execute other operations.

The widget will show a blinking marker at the point where the user clicked.

<figure><img src="../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
**Export coordinates on click** property will disable the drill-through and the dialog box (enabled by the **Show pin dialog** property) opening for a better selection.
{% endhint %}

{% hint style="success" %}
Go to the [**Widget Parameters**](../../#_toc63261619) section for more details about these parameters exported by the widget when **Export coordinates on click** property is enabled.
{% endhint %}
