# What's New in this page

## Version 2.0

### Comaptibility with **Flex Container**

In version 2.0, the **Basic Chart** widget has been made compatible with **Flex Container** **introduced in DAC** version **2022.2.0**. The **Basic Chart** now supports responsive sizing, this reduces the number of modifications in the UI you need to make and lets you arrange the widget within an application without issues of misalignment and allowing widget's wrapping.

{% hint style="info" %}
Now, when the widget is used in the **Page Designer**:&#x20;

* The values of the  properties **width** and **height**, **min-width** and **max-width**, **min-height**, and **max-height** will be empty;&#x20;
* When the properties **min-width** and **max-width**, **min-height**, and **max-height** are set, they will be applied to the widget;
* When the **width** and **height** properties are not set and the widget **is not in a Flex Container**,the widget will adjust its width and height based on the content;
* When the **width** and **height** properties are not set and the widget **is in a Flex Container**, the width and height will be driven by the Flex property;
* When the **width** and **height** properties are set in **pixels**, the value will be used to assign the width and height to the widget. If the content overflows, horizontal and vertical scrollbars will be rendered;
* When the **width** and **height** properties are set in **%**, the width and height will be driven by the %. If the content overflows, horizontal and vertical scrollbars will be rendered.
{% endhint %}

## Version 1.0

The first widget version has been introduced. See the **Documentation** section to learn more about all the features available.
