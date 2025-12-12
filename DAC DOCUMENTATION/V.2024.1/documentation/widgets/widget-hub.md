# Widget Hub

## Introduction

**Widget Hub** is a central online repository of widgets available in App Composer where developers can find and download widgets to add to their applications.&#x20;

Developers can **browse the hub** to find the widgets they need, or they can use the search feature to look for specific widgets. Once they find the widget they want, they can download it and add it to their application with just a few clicks.

<figure><img src="../../.gitbook/assets/image (661).png" alt=""><figcaption><p><a href="https://widgethub.decisyon.com/">https://widgethub.decisyon.com/</a></p></figcaption></figure>

{% embed url="https://widgethub.decisyon.com/" %}

The Widget Hub also ensures the **compatibility** of widgets with the version of App Composer being used. The API level of DAC determines the compatibility with the widgets to be installed. Widget Hub verifies the API level of DAC before allowing widget to be installed, ensuring that only compatible widgets are added to the application. This helps to prevent compatibility issues and ensures that widgets work as intended.

Developers can also **upgrade** widgets from the Widget Hub. When a new version of a widget is released, developers can download and install the new version from the hub with just a few clicks. When upgrading a widget, developers should pay attention to any compatibility issues that may arise due to changes in the DAC API level, especially in case of version upgrade of DAC.

For each widget it is possible to read the [dedicated documentation](widgets-list.md).

![https://widgets.decisyon.com/widgets/](<../../.gitbook/assets/image (517).png>)

Click on the widget title to view the dedicated documentation .

![](<../../.gitbook/assets/image (1096).png>)

At the top left you can sleect the version.

![](<../../.gitbook/assets/image (811).png>)

On the left you can also consult the change log and the document "What’s new" that shows the new feature for the widget.

The documentation of each widget is divided into three sections:

* **Overview**: Overview on using the widget with several sample images .

![](<../../.gitbook/assets/image (1026).png>)

* **Properties:** The properties that are specific for the configuration of the widget.

![](<../../.gitbook/assets/image (1338).png>)

**Examples**: A series of examples that will help you understand how to configure the widget

![](<../../.gitbook/assets/image (1324).png>)

## **Widget Hub Folder**

Widget catalog contains a special folder called "**DAC Widget Hub**" in which it's possible to install or import (manually) widgets from the Widget Hub.

The folder can not be deleted, modified or moved and it is always displayed on top of the list.

It is possible to open the Widget Hub to install widgets from the dedicated icon or from the contextual menu of the folder. &#x20;

<figure><img src="../../.gitbook/assets/image (542).png" alt=""><figcaption></figcaption></figure>

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
* **Version**: Widget version number available
* **Installed version:** The version of the widget installed in the environment
* **Install & Change Log:** This section has shortcut buttons that provides different information and the following operations available for each widget:

<figure><img src="https://lh3.googleusercontent.com/E-6cwAk8zhIjXa0npmv6uAcQpmEYwMdmD85L_Oz7fPPqKOXrUwNj42oprGzi1l-EbeG3tXyGCJzB0pPdcDbhn23Gz9ARqv7NhWPq4eTRO6jnHj4-PLvhgjASvPS7l8uc8E2Nb-GiyDH7Q2pXQKa6xgOQqw=nw" alt="" width="563"><figcaption></figcaption></figure>

The **Upgrade** button![](<../../.gitbook/assets/image (786).png>) indicates that a new version of the Widget is available. In this case, the special folder **UPGRADES** will appear on the left, showing all the widgets that may be upgraded.

* **Category:** Specifies the category the widget belongs to
* **Last Update:** Indicates the last update performed

<figure><img src="../../.gitbook/assets/image (1220).png" alt=""><figcaption></figcaption></figure>

Click on the widget name to get and overview and more details about the widget. In this section, the same operations of the shortcut buttons are available.

<figure><img src="../../.gitbook/assets/image (435).png" alt=""><figcaption></figcaption></figure>

On the right, there is a panel where the following information is listed:

* **Version**: Specify the version of the widget available to install. By default, the latest version of the widget available [and that could be installed in the App Composer instance is selected](#user-content-fn-1)[^1].
* **Type**: Specify the type of widget.
* **Last Update:** The latest date when the widget was modified.
* **Author:** Who created or modified the widget.
* **Manual**: Open the documentation page of the selected widget. Here you can find all the information about the widget properties and you can review available examples.
* **What’s New:** You can review the new features that have been introduced with the latest version of the widget.
* **ChangeLog**: The Change Log is a document distributed at the same time as the release of a new version (minor release or patch) of the Widget is generated. In fact, the 'Change Log' list, the changes and improvements made to the widget is distributed only after the widget has been and approved based on the specifications provided by the development team.
*   **Action:** From here it's possible to install, upgrade or downgrade the widget. The button is disabled if no action is expected.&#x20;

    <figure><img src="../../.gitbook/assets/image (1319).png" alt=""><figcaption></figcaption></figure>

To install the widget you can just click on the **Install** button: if the installation is successfuly, you will see a confirmation message and the button will be modified in "**Widget Installed"**

<figure><img src="../../.gitbook/assets/image (1200).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (590).png" alt=""><figcaption></figcaption></figure>

Folders will be automatically created accordingly to the widget category.

<figure><img src="../../.gitbook/assets/image (583).png" alt=""><figcaption></figcaption></figure>

Please note that the widgets installed from Widget Hub are automatically published and they will be available in the Page Designer widget catalog.

![](<../../.gitbook/assets/image (828).png>)

{% hint style="danger" %}
The widgets installed from Widge Hub cannot be edited. If you try to export the widget and import it outside the HUB folder App Composer will show an error message.
{% endhint %}

## Upgrade Widget <a href="#upgrade-widget" id="upgrade-widget"></a>

In the **Widget Hub**, when a new version of a widget is released:

* The **Upgrade** button ![](<../../.gitbook/assets/image (1634).png>)  is visible in the **Install & Change Log** column. This means that a newer version is available for the widget. When you click this shortcut button,  you will be able to install the updated version immediately. The **Chage Log** button ![](<../../.gitbook/assets/image (1209).png>)opens the widget's Chage Log, allowing you to see the changes and improvements made with the latest version.
* The **UPGRADES**  folder appears on the left. This special folder contains the list of all the widgets that may be upgraded.

<figure><img src="../../.gitbook/assets/image (603).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (783).png" alt=""><figcaption></figcaption></figure>

* When you click on the widget title, the button at the bottom right (Action) indicates that the widget can be upgraded and the current version used in App Composer.

<figure><img src="../../.gitbook/assets/image (1266).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1066).png" alt=""><figcaption></figcaption></figure>

Once upgraded, the old widget is updated with the new version.

{% hint style="warning" %}
App Composer keeps only the latest version of widgets download from Widget Hub. The files and resources related to the previous version are deleted. If you need to use a specific widget version, please see how to [downgrade widget](widget-hub.md#downgrade-widget) and how to [install widget](widget-hub.md#install).
{% endhint %}

## **Downgrade Widget** <a href="#downgrade-widget" id="downgrade-widget"></a>

The widget can always be downgraded. You can select an earlier version than the one that is already installed in App Composer by referencing the **Version** column.

Downgrading could be necessary if the newer version of the widget is not working properly with the installed version of App Composer. Please always check the Change Log to ensure compatibility.

It is possible to downgrade a widget:

* By clicking the **Downgrade** shortcut button![](<../../.gitbook/assets/image (1204).png>)available in the **Install & Change Log** column.&#x20;

<figure><img src="../../.gitbook/assets/image (1381).png" alt=""><figcaption></figcaption></figure>

* By clicking the widget title and selecting the button at the bottom right (Action) that indicates that the widget can be downgraded.&#x20;

<figure><img src="../../.gitbook/assets/image (1201).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note that the downgrade button is ready to downgrade the widget, and App Composer warns that you are installing a version older than the one already installed.
{% endhint %}

## Manual Import of widgets

It is possible to manually download the DWP file of the widget from the Widget Hub to later import it in any compatible instance of App Composer, i.e. when the corporate security rules prevent access to [https://widgethub.decisyon.com/](https://widgethub.decisyon.com/).

From the widget page in the website, you can download the file.

<figure><img src="../../.gitbook/assets/image (1311).png" alt=""><figcaption></figcaption></figure>

You can now manually import the DWP file in the folder.

<figure><img src="../../.gitbook/assets/image (1519).png" alt=""><figcaption></figcaption></figure>

The context menu of the Hub folder, unlike the "standard" folders, shows only the Import action.

{% hint style="info" %}
Only **Widget Hub** widgets can be imported into this folder. Otherwise the system will show an error and will not allow the import. When you access the HUB folder, the list of imported widgets is shown.
{% endhint %}

![](<../../.gitbook/assets/image (1030).png>)

[^1]: It means that in the Widget Hub there could be newer version of the widget, but they are not available for installation due to incompatible API Version.
