# Widget Catalog

To open Widget Catalog and Widget Editor select in the vertical toolbar menu item **Widget Designer**

<figure><img src="../../.gitbook/assets/image (1357).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Only administrator users are able to open Widget Designer.
{% endhint %}

The main components of the Widget Catalog are described here and this is where you will manage all your standard and custom widgets.

As you open Widget Designer, the Catalog page is displayed. The next screenshot provides an overview of the Widget Designer Catalog.

​

<figure><img src="../../.gitbook/assets/image (856).png" alt=""><figcaption></figcaption></figure>

We will take a look at how the following areas of the Widget Catalog can be used.

* Widget and Folders catalog
* [Import Resources](widget-catalog.md#import-widget-or-resource)
* [Create Folder](widget-catalog.md#create-new-folder)
* [Create Widget](widget-catalog.md#create-new-widget)
* [DAC Widegt Hub (folder)](widget-catalog.md#hub-folder)
* [DAC Widget Hub (button)](widget-catalog.md#install)

## Widget and Folders catalog

The widget catalog shows the list of folders and widgets created in the application.

&#x20;By default the table shows the following information for each widget.

<figure><img src="../../.gitbook/assets/image (638).png" alt=""><figcaption></figcaption></figure>

**Name**: Widget name assigned when it was created.

**Version**: The widget version allows you to define if there is a new widget to update or if the installed version is the same as the version published in the widget repository.

**Logical Name:** it is the name used by the page when referring to the page. It's possible to have multiple widget with he same logical, but it's possible to have only one widget published with the same logical name at a time.

**Published:** Whether the widget is published or not. When published it shows the icon ![](<../../.gitbook/assets/3 (10)>)

[**API Version**](widget-catalog.md#widget-editor)**:** Each version of the DAC has a version of the API. For each widget, the MINIMUM and MAXIMUM API version supported by the widget is shown in the API version column. Therefore, if the version of the widget API is not compatible with the DAC version, the widget cannot be used.



{% hint style="info" %}
Remember!  To use a widget on the Page Designer it must be[ PUBLISHED](widget-catalog.md#widget).
{% endhint %}

## Contextual Menu

All the objects in the catalog on the left an icon with three dots.

<figure><img src="../../.gitbook/assets/image (1073).png" alt=""><figcaption></figcaption></figure>

Depending on the type of object [Widget ](widget-catalog.md#widget)or [Folder ](widget-catalog.md#folders)this allows you to display a menu with actions applicable to that type of component.

### Folders Contextual Menu

For Folder type objects, a menu is enabled that allows you to:

![](<../../.gitbook/assets/image (1464).png>)

o   **Move**: move the folder to another catalog folder&#x20;

![](<../../.gitbook/assets/image (1434).png>)

o   **Import**: import files or widgets directly into the folder

o   **Rename**: Rename the folder

o   **Delete**: Delete the folder and all its contents.



<figure><img src="../../.gitbook/assets/image (657).png" alt=""><figcaption></figcaption></figure>

* **Open:** Opens the widget editing interface
* **Publish or Unpublish** If the widget is published or not , the Publish or Unpublished button will be visible, otherwise if the widget is published Unpublish
* **Clone: Create a copy of the selected widget.**
  * Define the name and select a folder to save it to.

![](<../../.gitbook/assets/7 (1)>)

#### Widgets Contextual Menu

The contextual menu on widgets allows to:

<figure><img src="../../.gitbook/assets/image (370).png" alt=""><figcaption></figcaption></figure>

* **Open:** Opens the widget editing interface
* **Publish/Unpublish:** If the widget is not published, the Publish button will be visible, otherwise if the widget is published Unpublish.
* **Move:** move the widget to another catalog folder.
* **Clone:** Create a copy of the selected widget.
  * Define the name and select a folder to save it to.
  * ![](<../../.gitbook/assets/image (731).png>)
* **Export:** exports the widget in .dwp format.
* **Rename:** rename the widget
* **Delete:** Permanently delete the widget from the catalog.
* **Show dependencies:** Show the dependencies of the widget to the other component
* **Show Info:**&#x20;

&#x20;        ![](<../../.gitbook/assets/image (371).png>)

The Info panel displays information about the selected widget:

* **ID**: Identification code of the widget. This code can be used, for example, in APIs like `/api/rest/widgets/<widget-id>`.
* **Owner**: Application
* **Type**: Widget type
* **Type ID**: Identification code of the widget type. Useful for debugging.
* **Created by:** Name of the user who created the widget.
* **Created:** Date and time when the widget was created in UTC.
* Edited by : User who edited the widget.
* Edited: Date and time of the widget's last modification.

## Search Widget

In addition to the information listed above, you can view additional information for widgets. At the top right there is a button that allows you to select other columns to the table to view more information:

![](<../../.gitbook/assets/8 (6)>)

* **Created by :** shows the name of the user that created the widget
* **Created:** Shows the Widget creation date and time
* **Edited by:** Shows the name of the user that edited the widget
* **Edited:** Shows the date and time of edited of the widget

If you want to search for a widget or a folder in the catalog, just enter the name or part of the name in the "Search" field. You can also apply advanced filters to the search. The filter menu is enabled by the arrow icon on the left.

![](<../../.gitbook/assets/9 (3)>)

The search field can be narrowed to:

* **Status**: The status in the widget
* **Platform compatibility**: You can filter all the widgets that are compatible or not with the version of the DAC installed
* **Logical Name:** Logical name of the widget
* **Created by:** Name of the person who created the widget
* **Edited by:** Name of which who modified it.

## Import Widget

From the Widget catalog is possible import widgets using the DWP files. Any widgets can be exported in DWP file to be later imported in another instance of App Composer.&#x20;

To import a widget or resource into the widget catalog, select the icon on the top left and upload (or drag\&drop) the .DWP file. When the file is successfully imported, two green flags icons appear next to the progress bar.

![DWP file of the wigdet "Button"](../../.gitbook/assets/20)

![](../../.gitbook/assets/21)

​

By default, imported widget are **not published**: you need to publish it first before using it in Design Studio.

![](../../.gitbook/assets/22)

## Widget dependencies

To know the dependencies of the widget within your application, select Show dependences from the menu.

<figure><img src="../../.gitbook/assets/image (1083).png" alt=""><figcaption></figcaption></figure>

A window opens in which both the application and the page where the widget is used are indicate&#x64;**.**

<figure><img src="../../.gitbook/assets/image (1177).png" alt=""><figcaption></figcaption></figure>

## Create New Folder

To create a new folder, select the icon at the top left.

The panel allows you to enter a name for the new folder using the Name field, by default the folder is created on the root of the catalog, but it is always possible to change location by choosing a folder from those already present.

![](<../../.gitbook/assets/11 (3)>)

## Create New Widget

You can create folders to group and organize widgets in the widget catalog.

To create a new widget, select the third button at the top left.

![](<../../.gitbook/assets/12 (2)>)

The panel allows you to set the following information:

* **Type**: The following types of widgets can be created:
  * **Generic widget:** Widget that has any type of user interface
  * **Data presentation widget:** Widget data source consists of one or more Reports
  * **Data Connector:** Data connector widget allows pushing data to a generic visualization widget
  * **Shared library:** Shared libraries are composed of:
    * JavaScript libraries, CSS definitions, template HTML, and/or images that you want to reuse on multiple widgets.
    * Resource dependency settings (JS, CSS)
* **Name**: Give the widget a name
* **Folder**: Folders can be created to group and organize widgets in the Widget Catalog.

