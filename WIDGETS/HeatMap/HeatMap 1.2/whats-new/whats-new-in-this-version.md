# What's New in this version

## Version 1.2

### Comaptibility with **Flex Container**

In version 1.2, the **HeatMap** widget has been made compatible with **Flex Container** **introduced in DAC** version **2022.2.0**. The **HeatMap** now supports responsive sizing, this reduces the number of modifications in the UI you need to make and lets you arrange the widget within an application without issues of misalignment and allowing widget's wrapping.

{% hint style="info" %}
Now, when the widget is used in the **Page Designer**:&#x20;

* The values of the  properties **width** and **height**, **min-width** and **max-width**, **min-height**, and **max-height** will be empty;&#x20;
* When the properties **min-width** and **max-width**, **min-height**, and **max-height** are set, they will be applied to the widget;
* When the **width** and **height** properties are not set and the widget **is not in a Flex Container**, the widget will take all the available space in its container;&#x20;
* When the **width** and **height** properties are not set and the widget **is in a Flex Container**, the width and height will be driven by the Flex property;
* When the **width** and **height** properties are set in **pixels**, the value will be used to assign the width and height to the widget.
* When the **width** and **height** properties are set in **%**, the width and height will be driven by the %.
{% endhint %}

## Version 1.1

The first widget version has been introduced. See the **Documentation** section to learn more about all the features available.
