---
description: >-
  On this page you will find the list of everything that has been removed from
  the DAC in the released version. To know what are the impacts of migration
  please consult the migration notes.
---

# Removals

## Page Designer&#x20;

The introduction of CSS Flexbox module is an important technological upgrade for the App Composer but it brings some changes that must be considered when migrating from a version lower than 2022.2.0 because some properties are now deprecated and some other are automatically migrated to the new settings, in order to minimize the changes required to the pages built with previous versions.

### Top and left

When creating a new page or adding a new widget to an existing page, properties top and left are no longer available.

&#x20;(Please seethe paragraph [Top and left](migration-notes.md#top-and-left) in Migration notes)

### graphHeight property in widget Chart

In the widget “Chart” the property graphHeight has been removed and the height of the chart will be driven by the height properties set in the containerStyle.

(Please see the paragraph [graphHeight property in widget Chart](migration-notes.md#graphheight-property-in-widget-chart) in Migration notes)

## Properties removal in the Page and in the Widget

With the improvements made to the page designer, some properties will no longer be present in the page and widget . Below the properties that have been impacted:

### Auto-expand property

The properties width autoexpand and height autoexpand are now completely removed in favor of the new properties min-width and min-height.&#x20;

(Please see the paragraph [Auto-expand property](migration-notes.md#auto-expand-property) in Migration notes)

### &#x20;TOP an LEFT property on all objects.

\
The Top and Left properties will no longer be available from version 2022.2.0 onwards.&#x20;

(Please see  the paragraph [TOP an LEFT property on all objects](migration-notes.md#top-an-left-property-on-all-objects.) in Migration notes)

### Horizontal-align property

\
The horizontal-align property visible when a widget was used in a row container will no longer be visible when the new property “Flex-container” is activated on the same container.\
Once the Flex-container is activated, the new alignment functionality will be selectable at the row-container level and will affect all the widgets used in the container.

&#x20;(Please see the paragraph [Horizontal-align property](migration-notes.md#horizontal-align-property) in Migration notes)



## Indicator Designer and widget Indicator

The Indicator Designer and the Indicator widget have been removed.

## Data source XML

The Dasta Socurce XML has been removed

## Widget Wizard

The widget Wizard has been removed

## Web Events

The WebEvents property Tools>>Preferences>>web has been removed

## Javascript Funtion

* Is no longer to possible use the javascript function to e export the page in PDF DECISYON.page.exportToPdf
* The function DECISYON.utils.createTask(saveCallback, params) is updated
* It was introduced a new Javascript Function : DECISYON.utils.editTask(saveCallback, taskId, application)
* For more details please see the APi Change Log

## Report

With the development of new Action Lists the group property Custom-Action of the Report has been removed.

## API Version is changed

With the release of the 2022.2.0 version, the supported API version is 2.0.0

(Please see the paragraph [API Version is changed](migration-notes.md#api-version-is-changed) in Migration notes)
