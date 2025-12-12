# New Features

## Widget's Show Info

In the list of widgets in the Widget Designer, it's now possible to display widget information using the "Show Info" dialog.

<figure><img src="../../../.gitbook/assets/image (369).png" alt=""><figcaption></figcaption></figure>

Please refer to the[ Widget Catalog](../../../documentation/widgets/widget-catalog.md#widgets-contextual-menu) for more details.

## New REST API

New REST APIs have been exposed

* API Rest to download a widget by id : **`GET /api/rest/widgets/{widget-id}`**
* API Rest to import a new widget: **`POST /api/rest/widgets`**
* API Rest to update an existing widget by id :**`PUT /api/rest/widgets/{widget-id}`**
* API Rest to delete a widget by id: **`DELETE /api/rest/widgets/{widget-id}`**

## Increase DAC’s Level API

DAC's version 2023.2.2 increased the API level number. The API level supported in this version is 2.2.0.

Please refer to the [API Documentation.](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/aoMTAlAWuBZ0jxWY5320/)

## New Widget File Upload&#x20;

A new "File Upload" widget has been introduced, selectable from the "Execute Button" widget when configured as  Excel Integration. This allows you to leverage Excel integration features even with the new "File Upload" widget.

{% hint style="danger" %}
Attention! There is no automatic migration from the old widget to the new one. Please refer to the [Migration Notes](migration-notes.md) for more details.
{% endhint %}

For more information please see the widget [documentation](https://widgets.decisyon.com/file-upload-1.0/documentation/file-upload-1.0).

## Report Properties New Data Type for Column-definition

From the "Column Definition" property of the Report properties, it is now possible to select the "HTML" data type. Widgets will interpret any HTML, JavaScript or CSS code included in the column; as a result, the data type "String/Text" will not be able anymore to show HTML,JavaScript or CSS.

<figure><img src="../../../.gitbook/assets/image (364).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
The introduction of the data type "HTML" has migration impacts on the widget side, since custom code are no longer interpreted by default. Please refer to the [Migration Notes](migration-notes.md) for more details.
{% endhint %}

## Serve Side Validation

### Server side file validation on File Upload widget

In the Widget File upload has been introduce the validation of the file loaded from  widget.&#x20;

### Server side file validation on User Profile

In the User Profile page, validation has been introduced for the loaded file when selecting the image for the profile picture.
