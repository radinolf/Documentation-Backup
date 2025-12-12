# Widget Resources

## Introduction

The **Widget Resources** is the left panel of the **Widget Editor** provides access to multiple resources necessary for the development of the widget.

In the Widget Editor each widget has the following special resources and dependencies resources:

* **index.html**  It is the main view and is used as the entry point for displaying the widget.
* **configuration.json**  It contains all generic configuration data to load a few parameters and it is used to specify the widget properties.
* **mockContext.json**  It contains all contextual information of the widget, the properties defined in the configuration.json, and all supported properties.
* **mockData.json**  It contains data for script testing.
* **index.css** It is a dependency resource. It is used to define the controller and the directive and is optional.
* **index.js** It is a dependency resource. It is used to define the widget style and is optional.&#x20;

The special resources are automatically organized into special folders.

<figure><img src="../../../../.gitbook/assets/image (565).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Special folders and special resources can not  be deleted, moved or renamed
{% endhint %}

The **Widget** **Resources** context menu provides different options that depend on the selected resource:

* **Download:** Allows you to export all the contents of the selected resource as a file.
* **Upload resources:** Allows you to import a folder and all its files in the chosen location of the resources tree.

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (1727).png" alt=""><figcaption></figcaption></figure></div>

## Index.html

The `index.html` lives at the root structure, it is the main view of the widget and contains HTML, CSS, and Angular elements.

```html
<div class="exampleContainer">
      <p>Write something in the input box.</p>
      <p>Name: <input type="text" ng-model="name" placeholder="Enter name here"></p>
      <h1 ng-show="name">Hello {{name}}!</h1>
      <h1 ng-show="name">Hey <span ng-bind="name"></span>!</h1>
</div>
```

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (1507).png" alt=""><figcaption></figcaption></figure></div>

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (908).png" alt=""><figcaption></figcaption></figure></div>



## Configuration.json

The `configuration.json` contains all generic configuration data to load a few parameters.

This special resource will be used to specify the widget's custom properties:

* When you specify a new custom property and save the `configuration.json`, the system automatically adds the property in the **Settings** panel. This allows to modify the widget's property values easily when editing the widget.
* The custom properties defined in the `configuration.json` will be available by using `DECISYON.target.content.ctx` object. The context object can be used in your code and in data-binding expressions.

{% hint style="info" %}
To learn more about **DECISYON object: target.content.ctx.** and the detail of all the exposed APIs, refer to the Widget [SDK documentation](https://widgetdev02.decisyon.net/docs/widget_sdk/index.html#/widget_sdk/CustomPropertiesStructure), accessible from the Widget Editor
{% endhint %}

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (1714).png" alt=""><figcaption></figcaption></figure></div>

### Definers configurable in the configuration.json <a href="#definer-in-the-widget" id="definer-in-the-widget"></a>

The file `configuration.json` is configured by the widget developer and contains the properties of the widget that will be exposed to the application developer in Page Design. For each property it is possible to define information such as the name, the description, the position among the other properties and the **definer**, which provide to Page Design the instructions about how the property will be rendered and used by application developers when used in Page Design

It is possible to use the following definers in the widgets:

1. [SELECT](/broken/pages/CKQnTDfKrGPzLiYIwgDa#select)
2. [NUMERIC](/broken/pages/CKQnTDfKrGPzLiYIwgDa#numeric)
3. [SWITCH](/broken/pages/CKQnTDfKrGPzLiYIwgDa#switch)
4. [TEXTFIELD](/broken/pages/CKQnTDfKrGPzLiYIwgDa#textfield)
5. [TEXTAREA](/broken/pages/CKQnTDfKrGPzLiYIwgDa#textarea)
6. [EXECUTE\_BUTTON](/broken/pages/CKQnTDfKrGPzLiYIwgDa#execute-button)
7. [REPORT\_LEVEL](/broken/pages/CKQnTDfKrGPzLiYIwgDa#report-level)

It is possible to configure all these properties in a JSON format that will be parsed and used by the Design Studio to render them in the widget's properties of Page Design.

{% hint style="info" %}
To learn more about **JSON attributes** refer to the [Widget SDK documentation](https://widgetdev02.decisyon.net/docs/widget_sdk/index.html#/widget_sdk/CustomPropertiesStructure), accessible from the Widget Editor
{% endhint %}

## MockContext.json

The `mockContext.json` contains all contextual information accessible at runtime by the widget. This is one of the most important file available to the widget developer because it shows the JSON file that can be used at runtime to access the properties value (previously defined in the `configuration.json`), other widget's properties available from Page Designer (that are not defined in the `configuration.json`) and other contextual information inherited from the page.&#x20;

This is an example of the JSON:

```json
{
  "max-height": {
    "id": "max-height",
    "value": "",
    "dataType": "STRING"
  },
  "contrUID": {
    "id": "contrUID",
    "value": "dshEmbedObject"
  },
  "defaultReferenceName": {
    "id": "defaultReferenceName",
    "value": "",
    "dataType": "STRING"
  },
  "useDataConnector": {
    "id": "useDataConnector",
    "value": "false"
  },
  "preferred-width": {
    "id": "preferred-width",
    "value": "100%",
    "dataType": "STRING"
  },
  "min-height": {
    "id": "min-height",
    "value": "",
    "dataType": "STRING"
  },
  "refObjType": {
    "id": "refObjType",
    "value": "264"
  },
  "importParameters": {
    "id": "importParameters",
    "value": "",
    "dataType": "OBJECT"
  },
  "renderScope": {
    "id": "renderScope",
    "value": "designer"
  },
  "defaultMaxWidth": {
    "id": "defaultMaxWidth",
    "value": "",
    "dataType": "STRING"
  },
  "defaultMaxHeight": {
    "id": "defaultMaxHeight",
    "value": "",
    "dataType": "STRING"
  },
  "exportParameters": {
    "id": "exportParameters",
    "value": "",
    "dataType": "OBJECT"
  },
  "baseName": {
    "id": "baseName",
    "value": "",
    "dataType": "STRING"
  },
  "sharedLibDeps": {
    "id": "sharedLibDeps",
    "values": []
  },
  "owner": {
    "id": "owner",
    "value": ""
  },
  "defaultMinWidth": {
    "id": "defaultMinWidth",
    "value": "100%",
    "dataType": "STRING"
  },
  "visibility": {
    "id": "visibility",
    "value": "inherit",
    "dataType": "OBJECT"
  },
  "defaultMinHeight": {
    "id": "defaultMinHeight",
    "value": "",
    "dataType": "STRING"
  },
  "instanceReference": {
    "id": "instanceReference",
    "value": "335686736911970"
  },
  "supportedApiLevel": {
    "id": "supportedApiLevel",
    "value": "2.1.0"
  },
  "refObjId": {
    "id": "refObjId",
    "value": "0"
  },
  "contAutoExpH": {
    "id": "contAutoExpH",
    "value": "0",
    "dataType": "STRING"
  },
  "useCustomJsCallback": {
    "id": "useCustomJsCallback",
    "value": "false"
  },
  "mshPageId": {
    "id": "mshPageId",
    "value": "-1"
  },
  "max-width": {
    "id": "max-width",
    "value": "",
    "dataType": "STRING"
  },
  "preferred-height": {
    "id": "preferred-height",
    "value": "",
    "dataType": "STRING"
  },
  "contAutoExpW": {
    "id": "contAutoExpW",
    "value": "0",
    "dataType": "STRING"
  },
  "restApiListDefinition": {
    "id": "restApiListDefinition",
    "value": "",
    "dataType": "STRING"
  },
  "min-width": {
    "id": "min-width",
    "value": "",
    "dataType": "STRING"
  }
}
```

It contains all custom properties defined in the `configuration.json` and all supported properties when the widget is used on the page:

The context data will be automatically assigned to the `$scope` and will be available by using `DECISYON.target.content.ctx` object. The context object can be used in the code and in data binding expressions.

{% hint style="info" %}
To learn more about **DECISYON.target.content.data** object and the detail of all the exposed APIs, refer to the Widget [SDK documentation](https://widgetdev02.decisyon.net/docs/widget_sdk/index.html#/widget_sdk/CustomPropertiesStructure), accessible from the Widget&#x20;
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (854).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (1106).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
`mockContext.json` is automatically generated by the system both for **Generic** and **Data Presentation** widgets.
{% endhint %}

## MockData.json

The `mockData.json` contains in JSON format the data available the associated report and that could be retrieved by the widget. In widget designer, the `mockData.json` is useful to "simulate" the data that will be retrieved at runtime from the report's execution when the widget will be loaded.&#x20;

The data will be automatically assigned to the `$scope` and will be available by using `DECISYON.target.content.data` object. Widget developers can use it in the code and in data binding expressions.

{% hint style="info" %}
To learn more about **DECISYON.target.content.data** object and the detail of all the exposed APIs, refer to the Widget [SDK documentation](https://widgetdev02.decisyon.net/docs/widget_sdk/index.html#/widget_sdk/CustomPropertiesStructure), accessible from the Widget&#x20;
{% endhint %}

```json
{
  "reportProvider": {
    "description": "",
    "displayName": "04 - Report visualization table",
    "id": "927488989068154",
    "colMap": {},
    "rows": [
      {
        "rowIdx": -1,
        "cells": [
          {
            "colIdx": 0,
            "viewVal": "A",
            "type": "L",
            "visible": true
          },
          {
            "colIdx": 1,
            "viewVal": "B",
            "type": "L",
            "visible": true
          },
          {
            "colIdx": 2,
            "viewVal": "C",
            "type": "L",
            "visible": true
          }
        ]
      },
      {
        "rowIdx": 0,
        "visible": true,
        "cells": [
          {
            "colIdx": -1,
            "viewVal": "1",
            "type": "N"
          },
          {
            "colIdx": 0,
            "idVal": "ASSET",
            "viewVal": "Asset",
            "type": "H",
            "subType": "He",
            "sortType": "DESC"
          },
          {
            "colIdx": 1,
            "idVal": "COUNT_ALARMS_Sum",
            "viewVal": "# of alerts",
            "type": "C",
            "subType": "F"
          },
          {
            "colIdx": 2,
            "idVal": "tag_value_Sum",
            "viewVal": "Tag Value",
            "type": "C",
            "subType": "F"
          }
        ]
      },
      {
        "rowIdx": 1,
        "visible": true,
        "cells": [
          {
            "colIdx": -1,
            "viewVal": "2",
            "type": "N"
          },
          {
            "colIdx": 0,
            "idVal": "ASSET_1",
            "viewVal": "Turbine 1",
            "type": "R",
            "subType": "D"
          },
          {
            "colIdx": 1,
            "idVal": "10",
            "viewVal": "10",
            "type": "B",
            "subType": "B"
          },
          {
            "colIdx": 2,
            "idVal": "1330.0000000000",
            "viewVal": "1.330",
            "type": "B",
            "subType": "B"
          }
        ]
      },
      {
        "rowIdx": 2,
        "visible": true,
        "cells": [
          {
            "colIdx": -1,
            "viewVal": "3",
            "type": "N"
          },
          {
            "colIdx": 0,
            "idVal": "ASSET_2",
            "viewVal": "Turbine 2",
            "type": "R",
            "subType": "D"
          },
```

When you associate a report data source in a **Data Presentation** widget, the system allows you to automatically generate mock data.&#x20;

<figure><img src="../../../../.gitbook/assets/image (1032).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (956).png" alt=""><figcaption></figcaption></figure>

For each report associated with the widget, the system generates a specific node in the JSON. The first report has `reportProvider` as the main node, while the successive reports have the main node named reportProvider followed by \_n, where n is a unique sequential number starting with 1.

<figure><img src="../../../../.gitbook/assets/image (1691).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The `mockData.json` and `mockContext.json` help you to simulate the widget behaviour.
{% endhint %}

{% hint style="warning" %}
`mockData.json` is automatically generated by the system only for **Data Presentation** widgets.
{% endhint %}

