---
description: >-
  On this page you will find the list of components that have an impact on
  migration.
---

# Migration notes

The introduction of CSS Flexbox module is an important technological upgrade for the App Composer but it brings some changes that must be considered when migrating from a version lower than 2022.2.0 because some properties are now deprecated or removed and some other are automatically migrated to the new settings.

App Composer tried to ensure as much as possible the retro-compatibility, but some manual migrations tasks are required to make pages works.&#x20;

## Properties Top and Left

When creating a new page or adding a new widget to an existing page, properties `top` and `left` are no longer available.

On existing widgets and pages, when the properties top or left were set to 0, they are automatically removed and the new property `margin` is displayed.&#x20;

Please see the [specific documentation](../../../documentation/design-studio/page-designer/page-properties/#margin-container-style) for additional information.

On existing widgets and pages, when the property top or left were set to any value different from zero, they are not automatically removed and they are still used in order to prevent layout issues on existing page, but it is **STRONGLY** reccomended to manually set them to 0 and use the `property` margin.

When top and left are set to 0 in Page Designer, they automatically disappear from the widget's properties and they can no longer be used.

When the new property `margin` is set and top and left had a value different from 0, the properties `top` and `left` will be removed from the widget.

The new property `margin` can be use in the scenario for which the properties `top` and `left` were used to create some "spacing" around widget.

## Property auto-expand

The properties width autoexpand and height autoexpand are now completely removed in favor of the new properties min-width and min-height.

In this case the migration is managed by App Composer as follow. The migration works both is the property was in pixel or in % values.

When autoexpand was **disabled**

* the property width keeps its original value
* the property width autoexpand is removed from the widget/section/page
* the new property min-width is set to null
* the property max-width is now visible and set to null
* the property heightkeeps its original value
* the property height autoexpand is removed from the widget/section/page
* the new property min-heightis set to null
* the property max-height is now visible and set to null



<table data-header-hidden><thead><tr><th width="353"></th><th></th></tr></thead><tbody><tr><td><strong>Before</strong></td><td><strong>After</strong></td></tr><tr><td><ul><li><p><strong>width</strong>: 200</p><ul><li><strong>auto-expand:</strong> disabled</li></ul></li><li><p><strong>height:</strong> 300</p><ul><li><strong>auto-expand:</strong> disabled</li></ul></li></ul></td><td><ul><li><p><strong>width</strong>: 200</p><ul><li><strong>min-width:</strong></li><li><strong>max-width:</strong></li></ul></li><li><p><strong>height:</strong> 300</p><ul><li><strong>min-height:</strong></li><li><strong>max-height</strong>:</li></ul></li></ul></td></tr></tbody></table>



When autoexpand was **enabled**

* the property width is set to null and its value is now copied in the property min-width
* the property width autoexpand is removed from the widget/section/page
* the new property min-width has now the value of the property width
* the property max-width keeps its original value
* the property heightis set to null and its value is now copied in the property min-height
* the property height autoexpand is removed from the widget/section/page
* the new property min-height has now the value of the property height
* the property max-height keeps its original value



<table data-header-hidden><thead><tr><th width="356"></th><th></th></tr></thead><tbody><tr><td><strong>Before</strong></td><td><strong>After</strong></td></tr><tr><td><ul><li><p><strong>width</strong>: 200</p><ul><li><strong>auto-expand:</strong> active</li><li><strong>max-width:</strong> 400</li></ul></li><li><p><strong>height:</strong> 300</p><ul><li><strong>auto-expand:</strong> active</li><li><strong>max-height</strong>: 500</li></ul></li></ul></td><td><ul><li><p><strong>width</strong>:</p><ul><li><strong>min-width:</strong> 200</li><li><strong>max-width:</strong> 400</li></ul></li><li><p><strong>height:</strong></p><ul><li><strong>min-width:</strong> 300</li><li><strong>max-height</strong>: 500</li></ul></li></ul></td></tr></tbody></table>

Please see the [specific documentation](../../../documentation/design-studio/page-designer/page-layout/#size-and-wrap) for additional information about sizing a widget.

## Property horizontal-align

The property `horizontal-align` visible when a widget was used in a row container will no longer be visible when the new property “`Flex-container`” is activated on the same container.\
Once the `Flex-container` is activated, the new alignment functionality will be selectable at the row-container level and will affect all the widgets used in the container.

In order to reduce the regression impact, when the property `flex-container` is disabled, the alignment of the widgets in the container will follow the legacy management.

Please see the [specific documentation](../../../documentation/design-studio/page-designer/page-layout/#alignment) for additional information.

## Property graphHeight&#x20;

The property `graphHeight`of widget "Chart" been removed and the height of the chart is now driven by the property `height` set in the widget.

## Widget Tab Panel&#x20;

Due to the introduction of flexbox, the widget “Tab Panel” has now a different behaviour and must be manually modified to restore back the original behaviour.

Before the migration, the widget could be configured to have an `height` in pixel and the property `autoexpand` enabled, resulting in the widget to take all the required height in case the content of the widget was higher than the value set in the `height` property.

<figure><img src="../../../.gitbook/assets/image (812).png" alt=""><figcaption></figcaption></figure>

After the upgrade, the `height` + `autoexpand` is migrated in the new property `min-height` but because it is not possible to automatically calculate the height of the content of the page associated to the widget, a value of 150px is assigned as max-height, resulting in the tab panel to be “cutted” at 150px and with the internal scroller enabled.

To fix this issue it is necessary to migrate the page and the widget to use the flexbox capabilities:

* Page `height=100%`
* Section `height=100%`
* Main container `height=100%` and `flex` enabled
* Tab panel: `flex=1` or `height=100%` (depending if used in a row container or column container widget).

<figure><img src="../../../.gitbook/assets/image (800).png" alt=""><figcaption></figcaption></figure>

## Widget’s title height

Before version 2022.2.0, when the property `title` was enabled in the widget, the height of the title (28 pixels) was added to the height configured for the widget.

In example, if you set the height of a widget to 200px and the title was enabled, the total height was 200 px + 28 px = 228 pixels.

Starting from 2022.2.0, the height of the title is included in the height of the widget. This change in the behaviour could cause impact in the page that must be manually evaluated and fixed page by page.

<figure><img src="../../../.gitbook/assets/image (446).png" alt=""><figcaption></figcaption></figure>

## New default for width and height

Starting from version 2022.2.0, the default value of width of some items has bee modified when a page is created from scratch:

<table><thead><tr><th width="132">Item</th><th width="122">property</th><th width="219">Before 2022.2.0</th><th>After 2022.0.0</th></tr></thead><tbody><tr><td>Page</td><td>width</td><td>98%</td><td>100%</td></tr><tr><td>Page</td><td>height</td><td>50</td><td>100%</td></tr><tr><td>Sections</td><td>width</td><td>98%</td><td>100%</td></tr><tr><td>Sections</td><td>height</td><td>50</td><td>not set</td></tr><tr><td>Widgets</td><td>width</td><td>98%</td><td>depends on the widget</td></tr><tr><td>Widgets</td><td>height</td><td>50</td><td>depends on the widget</td></tr></tbody></table>

&#x20;

Properties of pages already created before 2022.2.0 **will not be modified** during the upgrade.

Please see the [specific documentation](../../../documentation/design-studio/page-designer/page-layout/#size-and-wrap) for additional information.

## Custom Widgets: properties removed from the context in Widget Designer

{% hint style="info" %}
This regression could affects only custom widgets created with Widget Designer before the upgrade to 2022.2.0 and just in case one of the belowe property has been used to develop the widget.
{% endhint %}

There are a set of properties passed in the context of widgets in widget designer that will have migration impacts due to the introduction of Flexbox.

The following properties will be forced to the value **0 (false)**.

```json
{
  "contAutoExpH": {
    "id": "contAutoExpH",
    "value": "0",
    "dataType": "STRING"
  },
  "contAutoExpW": {
    "id": "contAutoExpW",
    "value": "0",
    "dataType": "STRING"
  },
  "defaultAutoExpandHeight": {
    "id": "defaultAutoExpandHeight",
    "value": "0",
    "dataType": "STRING"
  },
  "defaultAutoExpandWidth ": {
    "id": "defaultAutoExpandWidth ",
    "value": "0",
    "dataType": "STRING"
  }
}
```

The following properties are now deprecated and will be removed in a later version. If a custom widget is using one of these properties, it must be refactored avoiding to use them.

```json
{
  "contAutoExpH": {
    "id": "contAutoExpH",
    "value": "0",
    "dataType": "STRING"
  },
  "contAutoExpW": {
    "id": "contAutoExpW",
    "value": "0",
    "dataType": "STRING"
  },
  "defaultMaxHeight": {
    "id": "defaultMaxHeight",
    "value": "",
    "dataType": "STRING"
  },
  "defaultMaxWidth": {
    "id": "defaultMaxWidth",
    "value": "",
    "dataType": "STRING"
  },
  "defaultMinHeight": {
    "id": "defaultMinHeight",
    "value": "50",
    "dataType": "STRING"
  },
  "defaultMinWidth": {
    "id": "defaultMinWidth",
    "value": "100%",
    "dataType": "STRING"
  },
  "preferred-height": {
    "id": "preferred-height",
    "value": "",
    "dataType": "STRING"
  },
  "preferred-width": {
    "id": "preferred-width",
    "value": "100%",
    "dataType": "STRING"
  }
}
```

These changes may cause regression bugs on custom-built widgets that must be fixed by the widget’s owner. Please contact Decisyon support if you need help to migrate.

Widgets built and distributed by Decisyon’s INC are not affected by this regression.

## Custom CSS

If you defined custom CSS in the page that affect the layout of the page or the widgets, Decisyon Inc can not ensure that they will work again after the migration to version 2022.2.0

Custom CSS must be manually evaluated and modified to make them work after the migration.

## API Version

With the release of the 2022.2.0 version, the supported API version is 2.0.0

After migration access the Widget Designer.

Widgets not compatible with API version 2.0.0 will display in the widget catalog with a red icon.

<figure><img src="../../../.gitbook/assets/image (683).png" alt=""><figcaption></figcaption></figure>

The icons means that the compatibility of the widget with the current DAC version is not ensured and you should verify the compatibility with the API versions.

If the widget was **download from Decisyon Widget Hub**, you can just upgrade the widget version. Widget's distributed by Decisyon always ensure the comptibility with the proper API level.

If the widget is a **custom widget** built with Widget Designer, you need to verify if the API used in the widget are still supported in the current API version and then you can change the API level in the widget designer to remove the alert. If the widget is using an API no longer supported in the current API version, a refactoring of the widget is required.



To modify the API level of custom widget:

1. Open Widget Designer
2. Edit the widget
3. Open the properties "Settings --> Advanced"
4. Modify the property `Maximum API Level` and select version "`2.*`"

<img src="../../../.gitbook/assets/image (732).png" alt="" data-size="original">

Once you change the Maximum version of the API level you will need to verify that the widget is working properly.&#x20;

To know which APIs have been deleted, deprecated, and which ones have been introduced please see the [API Level changelog](https://dac-documentation-1.gitbook.io/dac-api/).
