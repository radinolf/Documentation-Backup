---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/h9Knuj2BfqZwIB5BI7sj/whats-new/whats-new-in-this-version
---

# What's New in this version

## Version 3.0

### **New Version Graphical Style**&#x20;

Upgrading the Button widget to version 3.0 introduced significant style changes to align with the latest Angular Material Design standards. These updates enhance the visual consistency and modernize the appearance of the application:

**Updated Styles**

* **Flat Style Renamed to Basic:** The previous Flat style (default) has been redesigned as Basic to better reflect its updated design.

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

* **Consistent Visuals**: All buttons (Raised, FAB, Icon) have been updated to the latest Angular Material standards without any style changes.&#x20;

**New Button Styles**:

* **Stroked Button**: A new style featuring a thin border, providing a lightweight and distinctive look.

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

* **Mini Fab**: An additional style for Floating Action Buttons, offering a smaller variant for more compact design requirements.

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

### Compatibility with **Flex Container**

In version 3.0, the **Button** widget has been made compatible with **Flex Container** **introduced in DAC** version **2022.2.0**. The **Button** now supports responsive sizing, this reduces the number of modifications in the UI you need to make and lets you arrange the widget within an application without issues of misalignment and allowing the widget's wrapping.

{% hint style="info" %}
Now, when the widget is used in the **Page Designer**:&#x20;

* The values of the **width** and **height** properties will be empty;&#x20;
* When the properties **min-width** and **max-width** are set, they will be applied to the widget;
* When the **width** property is not set and the widget **is not in a Flex Container**, the widget will take the required space in its container;&#x20;
* When the **width** property is not set and the widget **is in a Flex Container**, the width will be driven by the Flex property;
* When the **width** property is set in **pixels**, the value will be used to assign the width to the widget.
* When the **width** property is set in **%**, the width will be driven by the %.
* The **height** property is only applicable to DAC containers. The Button height meets the Material Design height guideline.
{% endhint %}

## Version 2.0

The first widget version has been introduced. See the **Documentation** section to learn more about all the features available.
