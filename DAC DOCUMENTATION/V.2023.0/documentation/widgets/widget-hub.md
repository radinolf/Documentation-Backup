# Widget Hub

## Introduction

**Widget Hub** is a central online repository of widgets available in App Composer where developers can find and download widgets to add to their applications.&#x20;

Developers can **browse the hub** to find the widgets they need, or they can use the search feature to look for specific widgets. Once they find the widget they want, they can download it and add it to their application with just a few clicks.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption><p><a href="https://widgethub.decisyon.com/">https://widgethub.decisyon.com/</a></p></figcaption></figure>

The Widget Hub also ensures the **compatibility** of widgets with the version of App Composer being used. The API level of DAC determines the compatibility with the widgets to be installed. Widget Hub verifies the API level of DAC before allowing widget to be installed, ensuring that only compatible widgets are added to the application. This helps to prevent compatibility issues and ensures that widgets work as intended.

Developers can also **upgrade** widgets from the Widget Hub. When a new version of a widget is released, developers can download and install the new version from the hub with just a few clicks. When upgrading a widget, developers should pay attention to any compatibility issues that may arise due to changes in the DAC API level, especially in case of version upgrade of DAC.

For each widget it is possible to read the [dedicated documentation](https://widgets.decisyon.com/widgets/).

![https://widgets.decisyon.com/widgets/](<../../.gitbook/assets/image (1059).png>)

Click on the widget title to view the dedicated documentation .

![](<../../.gitbook/assets/image (264).png>)

At the top left you can sleect the version.

![](<../../.gitbook/assets/image (773).png>)

On the left you can also consult the change log and the document "What’s new" that shows the new feature for the widget.

The documentation of each widget is divided into three sections:

* **Overview**: Overview on using the widget with several sample images .

![](<../../.gitbook/assets/image (1001).png>)

* **Properties:** The properties that are specific for the configuration of the widget.

![](<../../.gitbook/assets/image (409).png>)

**Examples**: A series of examples that will help you understand how to configure the widget

![](<../../.gitbook/assets/image (619).png>)

{% embed url="https://widgets.decisyon.com/dac-widget-hub" %}

## **Widget Hub Folder**

Widget catalog contains a special folder called "**DAC Widget Hub**" in which it's possible to install or import (manually) widgets from the Widget Hub.

The folder can not be deleted, modified or moved and it is always displayed on top of the list.

It is possible to open the Widget Hub to install widgets from the dedicated icon or from the contextual menu of the folder. &#x20;

<figure><img src="../../.gitbook/assets/image (975).png" alt=""><figcaption></figcaption></figure>

The contextual menu of Widget Hub folder shows the Install and Import items.

* **Install:** Opens Widget Hub in a dedicated dialog. In this section there are widgets that can be installed in your application.
* **Import:** manually import widgets downloaded from Widget Hub. Importing a widget not downloaded from Widget Hub will raise an error.

{% hint style="warning" %}
Make sure that the browser from which you are using App Composer is able to reach the external website [https://widgethub.decisyon.com/](https://widgethub.decisyon.com/), otherwise the dialog will display an error message.&#x20;

Connectivity could be blocked by firewall or corporate security rules.
{% endhint %}

## Install widgets

The Install menu item opens the Widget Hub dialog and shows the list of all widgets that can be installed in the Widget Designer. Widgets are grouped into categories, visible on the left. When you select a folder, the table shows a list of all the widgets belonging to that category. The following information are available for each widget:

* **Name**: Widget name
* **Version**: Widget version number
* **Update & changelog:** when the icon ![](<../../.gitbook/assets/image (10).png>) is visible it means that a new version of the Widget is available.

![](<../../.gitbook/assets/image (1072).png>)

Click on the widget name to get and overview and more details about the widget.

![](<../../.gitbook/assets/image (983).png>)

On the right, there is a panel where the following information is listed:

* **Version**: Specify the version of the widget available to install. By default, the latest version of the widget available [and that could be installed in the App Composer instance is selected](#user-content-fn-1)[^1].
* **Type**: Specify the type of widget.
* **Last Update:** The latest date when the widget was modified.
* **Author:** Who created or modified the widget.
* **Manual**: open the documentation page of the selected widget. Here you can find all the information about the widget properties and you can review available examples.
* **What’s New:** you can review the new features that have been introduced with the latest version of the widget.
* **ChangeLog**: The Change Log is a document distributed at the same time as the release of a new version (minor release or patch) of the Widget is generated. In fact, the 'Change Log' list, the changes and improvements made to the widget is distributed only after the widget has been and approved based on the specifications provided by the development team.
*   **Action:** from here it's possible to install, upgrade or downgrade the widget. The button is disabled if no action is expected.&#x20;

    <figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

To install the widget you can just click on the "**Install**" button: if the installation is successfuly, you will see a confirmation message and the button will be modified in "**Widget Installed"**

![](<../../.gitbook/assets/image (509).png>)

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Folders will be automatically created accordingly to the widget category.

<figure><img src="../../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>

Please note that the widgets installed from Widget Hub are automatically published and they will be available in the Page Designer widget catalog.

![](<../../.gitbook/assets/image (301).png>)

{% hint style="danger" %}
The widgets installed from Widge Hub cannot be edited. If you try to export the widget and import it outside the HUB folder App Composer will show an error message.
{% endhint %}

## Upgrade Widget <a href="#upgrade-widget" id="upgrade-widget"></a>

In the Widget Hub, when a new version of a widget is available, the icon ![](<../../.gitbook/assets/image (10).png>)is visible in the "**Update & Changelog**" column. This indicates that a newer versions is available for the widget. When you click on the icon the widget changelog opens.

![](<../../.gitbook/assets/image (285).png>)

When you click on the widget title, the button at the bottom right (Action) indicates that the widget can be upgraded and the current version used in App Composer.

![](<../../.gitbook/assets/image (936).png>)

![](<../../.gitbook/assets/image (265).png>)

Once upgraded, the old widget is updated with the new version.

{% hint style="warning" %}
App Composer keeps only the latest version of widgets download from Widget Hub. The files and resources related to the previous version are deleted. If you need to use a specific widget version, please see how to [downgrade widget](widget-hub.md#downgrade-widget) and how to [install widget](widget-hub.md#install).
{% endhint %}

## **Downgrade Widget** <a href="#downgrade-widget" id="downgrade-widget"></a>

The widget can always be downgraded[^2]. You can select a version earlier than the one already installed in App Composer using the "**Version**" menu.

![](<../../.gitbook/assets/image (168).png>)

&#x20;Note that the button at the bottom is ready to "**DOWNGRADE WIDGET**" the widget and App Composer warns that you are installing a version older than the one already installed.

Downgrading could be necessary if the newer version of the widget is not working properly with the installed version of App Composer. Please always check the changelog to check compatibility.

## Manual Import of widgets

It is possible to manually download the DWP file of the widget from the Widget Hub to later import it in any compatible instance of App Composer, i.e. when the corporate security rules prevent access to [https://widgethub.decisyon.com/](https://widgethub.decisyon.com/).

From the widget page in the website, you can download the file.

<figure><img src="../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

You can now manually import the DWP file in the folder.

<figure><img src="../../.gitbook/assets/image (373).png" alt=""><figcaption></figcaption></figure>

The context menu of the Hub folder, unlike the "standard" folders, shows only the Import action.

{% hint style="info" %}
Only **Widget Hub** widgets can be imported into this folder. Otherwise the system will show an error and will not allow the import. When you access the HUB folder, the list of imported widgets is shown.
{% endhint %}

![](<../../.gitbook/assets/image (707).png>)

[^1]: It means that in the Widget Hub there could be newer version of the widget, but they are not available for installation due to incompatible API Version.

[^2]: It means you can to back to a previous version, in example when you find compatibility issues.
