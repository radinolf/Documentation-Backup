---
description: >-
  This exercise will guide you through the configuration of the PageBy Selector
  widget on a page and use it to dynamically filter data.
---

# E.1 Configuring and Using the PageBy Selector Widget

## Step 1: Create a page on Design Studio

Create a new Page in the Page Design <img src="../../../.gitbook/assets/image (8).png" alt="" data-size="line"> and drag and drop the following widgets:

* **PageBy Selector**
* **Smart Grid**
* **Chart**

## Step 2: Configure the Widget's Properties

### 1. PageBy Selector widget

* `levels-associated:`Choose the dimensions you want to use as selectors (e.g., `YEAR` and `MONTH`). These levels will be used as filters for all widgets on the page that share the same dimensional levels.
* `alias-level:`assign meaningful names to the selected levels. For example, rename `YEAR` to "Select Year" and `MONTH` to "Select Month" to make the interface more intuitive.
* `selection-type:` configure how users can make their selections. For example, set `YEAR` to Single with Search and `MONTH` to Multiple.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### 2. Smart Grid and Chart widgets

* `reportAssociated:` associate a report, previously created, that contains the dimensional levels associated with the PageBy Selector widget.

## Step 3: Test the Widgets in the Web Application

Finally, test the widget to ensure everything is working as expected.

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>
