# Widget Designer

## **Introduction**

Widget Designer is a powerful online development environment that provides a feature-rich toolset to build complex applications with rich user interfaces. The development environment is based on AngularJS and can be extended with any third party services and front-end libraries.&#x20;

The widgets in Widget Designer are divided into three categories:

* [**Custom Widget:** ](widget-designer.md#how-to-create-a-custom-widgets)with complex workflows that meet your requirements. Once created and published, your custom widgets will be available in the palette for designing pages using Page Designer
  * any desired user interface to make widget setup more user-friendly using client technologies such as HTML, JavaScript and AngularJS
  * shared libraries that can be reused on multiple widgets
* In alternative it's possible to[ **import your widget** ](widget-designer.md#how-to-import-widget)and with the Widget Desigere you can customize them.
* [**Widget HUB:** ](widget-designer.md#hub-folder)The DAC Widget Hub provides a wide range of widgets that you can use on your pages in addition to the existing widgets of the Page designer.

Click below to consult the full DAC Widgets documentation:

{% embed url="https://widgets.decisyon.com/dac-widget-hub" %}





### **Widget Catalog**

To access Widget Designer, you must be an administrator. Only with this type of license you will be enabled the item on the side toolbar.

The main components of the Widget Catalog are described here and this is where you will manage all your standard and custom widgets.

As you open Widget Designer, the Catalog page is displayed. The next screenshot provides an overview of the Widget Designer Catalog.

![](<../../.gitbook/assets/0 (5)>)

​

We will take a look at how the following areas of the Widget Catalog can be used.

* Widget and Folders catalog
* [Import Resources](widget-designer.md#import-widget-or-resource)
* [Create Folder](widget-designer.md#create-new-folder)
* [Create Widget](widget-designer.md#create-new-widget)

The widget catalog shows the list of folders and widgets created in the application.

&#x20;By default the table shows the following information for each widget.

![](<../../.gitbook/assets/2 (2)>)

**Name**: Widget name assigned when it was created.

**Version**: The widget version allows you to define if there is a new widget to update or if the installed version is the same as the version published in the widget repository.**Logical Name:** Nome logico del widget

**Published:** Whether the widget is published or not. When published it shows the icon ![](<../../.gitbook/assets/3 (7)>)

[**API Version**](widget-designer.md#widget-editor)**:** Each version of the DAC has a version of the API. For each widget, the MINIMUM and MAXIMUM API version supported by the widget is shown in the API version column. Therefore, if the version of the widget API is not compatible with the DAC version, the widget cannot be used.





{% hint style="info" %}
Remember!  To use a widget on the Page Designer it must be[ PUBLISHED](widget-designer.md#widget).
{% endhint %}

### Contextual Menu

All the objects in the catalog on the left an icon with three dots.

![](<../../.gitbook/assets/image (370).png>)

Depending on the type of object [Widget ](widget-designer.md#widget)or [Folder ](widget-designer.md#folders)this allows you to display a menu with actions applicable to that type of component.

#### Folders Contextual Menu

For Folder type objects, a menu is enabled that allows you to:

![](<../../.gitbook/assets/image (285).png>)

o   **Move**: move the folder to another catalog folder&#x20;

![](<../../.gitbook/assets/image (42).png>)

o   **Import**: import files or widgets into the folder

o   **Rename**: Rename the folder

o   **Delete**: Delete the folder and all its contents.





![](<../../.gitbook/assets/6 (4)>)

* **Open:** Opens the widget editing interface
* **Publish:** If the widget is not published, the Publish button will be visible, otherwise if the widget is published Unpublish
* **Clone: Create a copy of the selected widget.**
  * Define the name and select a folder to save it to.

![](<../../.gitbook/assets/7 (2)>)

#### Widgets Contextual Menu

For Widget type objects, a menu is enabled that allows you to:

![](<../../.gitbook/assets/image (355).png>)

* **Open:** Opens the widget editing interface
* **Publish:** If the widget is not published, the Publish button will be visible, otherwise if the widget is published Unpublish
* **Clone:** Create a copy of the selected widget.
  * Define the name and select a folder to save it to.
  * ![](<../../.gitbook/assets/image (62).png>)
  * **Move:** move the widget to another catalog folder.
  * **Export:** exports the widget in .dwp format.
  * **Delete:** Permanently delete the widget from the catalog.

### Search Widget or Folder

In addition to the information listed above, you can view additional information for widgets. At the top right there is a button that allows you to select other columns to the table to view more information:

![](<../../.gitbook/assets/8 (6)>)

**Created by :** shows the name of who created the widget

**Created:** Shows the Widget creation date and time

**Edited by:** Shows the name of whoever edited the widget

**Edited:** Shows the date and time of edited of the widget

If you want to search for a widget or a folder in the catalog, just enter the name or part of the name in the "Search" field. You can also apply filters to the search. The filter menu is enabled by the arrow on the left.

![](<../../.gitbook/assets/9 (4)>)

The search field can be narrowed to:

* **Status**: The status in the widget
* **Platform compatibility**: You can filter all the widgets that are compatible or not with the version of the DAC installed
* **Logical Name:** Logical name of the widget
* **Created by:** Name of the person who created the widget
* **Edited by:** Name of which who modified it.

### Import Widget or Resource

To import a widget or resource into the widget catalog, select the icon on the top left. The window for importing a fight is enabled. When the resource is successfully imported, two green flags appear next to the progress bar.

![](<../../.gitbook/assets/10 (5)>)

### Create New Folder

To create a new folder, select the icon at the top left.

The panel allows you to enter a name for the new folder using the Name field, by default the folder is created on the root of the catalog, but it is always possible to change location by choosing a folder from those already present.

![](<../../.gitbook/assets/11 (2)>)

### Create New Widget

You can create folders to group and organize widgets in the widget catalog.

To create a new widget, select the third button at the top left.

![](<../../.gitbook/assets/12 (4)>)

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

## **HUB Folder**

Once you have started to use the Widget Hub, only the widgets that have been already downloaded from the DAC Widget Hub are imported or installed into the HUB folder.

![](<../../.gitbook/assets/image (73).png>)

The contextual menu of the Hub Folder shows the Install and Import items.

* **Install:** From the menu is possible to access the DAC widget catalog. In this section there are widgets that can be installed in your application.
* **Import:** The import item allows you to import a new widget / folder into the folder

{% hint style="info" %}
In the HUB folder it is not possible to import any file or widget from other systems
{% endhint %}

### Import Widget <a href="#import-widget" id="import-widget"></a>

To import a resource (widget, folder or file) into the HUB folder, select the Import menu item from the side menu.

{% hint style="danger" %}
Only **DAC Hub widgets** can be imported into this folder. Otherwise the system will show an error and will not allow the importing. When you access the HUB folder, the list of imported widgets is displayed.


{% endhint %}

&#x20;

1. Select the import item from the menu on the left

![](<../../.gitbook/assets/image (348).png>)

&#x20;

2\. Select your file or folder

![](<../../.gitbook/assets/image (331).png>)

3\. After you have imported the widget, from the contextual menu, available on the right of each widget, ayou can:

* **Open:** Opens the [Widget Editor](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2344255492/Widget+Hub)
* **Publish:** Publish the widget to make it available in the Page Designer Widgets
* **Export:** Export the Widget
* **Delete:** Permanently delete the widget from the folder

![](<../../.gitbook/assets/image (65).png>)

### **Install** <a href="#install" id="install"></a>

The Install menu item, opens the Widget Hub window and shows the list of all DAC widgets that can be installed in the Widget Designer. On the left, under the Widget categories item, there are all the folders containing widgets, grouped by category. When you select a folder, the table shows a list of all the widgets belonging to that category. The following information are available for each widget.

**Name**: Widget name

**Version**: Widget version number

**Update & changelog:** When an icon, like the one below, shows up it means that a new version of the Widget is available.

&#x20;

![](<../../.gitbook/assets/image (72).png>)

![](<../../.gitbook/assets/image (311).png>)

For more information about the look and feel and how to use it, just select the desired widget to view a brief overview.

![](<../../.gitbook/assets/image (342).png>)

The slider shows some graphical examples of the widget, while below there is a short description.

On the right, there is a panel where the following information is listed:

**About widget**

* **Version**: Specify the version of the widget. This change every time a new widget version is released.
* **Type**: Specify the type of widget.
* **Last Update:** The latest date when the widget was modified.
* **Author:** Who edited the widget.

**Widget Documentation:**

* **Manual**: it is possible to consult the complete documentation of the chosen widget. Here you can find all the information about the widget properties and you can consult usage examples.
* **What’s New:** you can review the new features that have been introduced with the latest version of the widget.
* **ChangeLog**: The ChangeLog is a document distributed at the same time as the release of a new version (minor release or patch) of the Widget is generated. In fact, the 'Change Log' list, the changes and improvements made to the widget is distributed only after the widget has been and approved based on the specifications provided by the development team.

**Action:**

**Widget Installed:** The button installs the widget. If the widget is already installed then the button will be disabled.

![](<../../.gitbook/assets/image (27).png>)

#### How to install a widget from the Widget Hub catalog. <a href="#how-to-install-a-widget-from-the-widget-hub-catalog." id="how-to-install-a-widget-from-the-widget-hub-catalog."></a>

The steps to install are the following:

**Step 1**: Access the HUB folder

**Step 2**: Select the INSTALL item from the side menu

![](<../../.gitbook/assets/image (309).png>)

**Step 3:** From the widget catalog select the widget and press the INSTALL WIDGET button.

![](<../../.gitbook/assets/image (286).png>)

**Step 4:** At the end of the installation the button is disabled and will indicate that the widget has been already installed.

![](<../../.gitbook/assets/image (277).png>)



**Step 5**: If you don't want to install any more widgets, close the window and go to the HUB folder.

![](<../../.gitbook/assets/image (376).png>)

The widget that has been installed in this example belongs to the MULTIMEDIA category. If it is the first widget of this category to be installed, the system automatically creates the folder as well.

**Step 6:** Go to the folder to view the widget.

![](<../../.gitbook/assets/image (57).png>)

Please note that the widget is automatically published and will then be available in the Page Designer widget catalog.

{% hint style="danger" %}
The widgets present in the widget HUB cannot be edited. If you try to export the widget and import it outside the HUB folder the system will show an error message.
{% endhint %}



### Upgrade Widget <a href="#upgrade-widget" id="upgrade-widget"></a>

In the Widget Hub, when a new version of a widget is available, the icon shown in the figure is visible in the Update & changelog column. This indicates that new versions are available for the widget. If you select, you can access the changelog.

![](<../../.gitbook/assets/image (284).png>)

After selecting the widget, the button at the bottom right (Action) indicates that the widget can be upgraded and the version of the widget currently in use in the application is indicated.

![](<../../.gitbook/assets/image (29).png>)

![](<../../.gitbook/assets/image (360).png>)



Once upgraded, the old widget is updated with the new version.

&#x20;

### **Downgrade Widget** <a href="#downgrade-widget" id="downgrade-widget"></a>

The widget can always be downgraded. Select a version earlier than the one already installed from the Version menu.

![](<../../.gitbook/assets/image (115).png>)

&#x20;

Note that the button at the bottom is ready to DOWNGRADE the widget, but the system warns you, that you are installing a version older than the one already installed.

Upgrading a widget may cause it to not work properly with the version of the DAC installed. Please always check the changelog to check compatibility.

&#x20;





Only the widgets downloaded from the DAC Widget Hub are imported into the HUB folder.

![](<../../.gitbook/assets/image (59).png>)

The context menu of the Hub folder unlike the standard folders shows only the Import item.

![](<../../.gitbook/assets/image (269).png>)

{% hint style="info" %}
Only **DAC Hub widgets** can be imported into this folder. Otherwise the system will show an error and will not allow the import. When you access the HUB folder, the list of imported widgets is shown.
{% endhint %}

![](<../../.gitbook/assets/image (280).png>)

The context menu available to the right of each widget allows you to:

* **Open:** Opens the [Widget Editor](widget-designer.md#widget-editor)
* **Publish:** Publish the widget and it will be available in the Page Designer Widgets
* **Export:** Export the Widget&#x20;
* **Delete:** Permanently delete the widget from the folder



### Dependence Widget

To know the dependencies of the widget within your application, select Show dependences from the menu.

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

A window opens in which both the application and the page where the widget is used are indicate&#x64;**.**

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>



### **Widget Editor**

It is a great idea to familiarize yourself with the main components of the Widget Editor, since that is where you will make building applications and rich user interfaces much easier.

Widget Editor has the following features:

* Editing and upload of JS and CSS resources
* Code editor and content assist
* Multiple perspectives
* Preview
* Resource dependencies settings (JS, CSS)
* Ability to use any browser developer tools
* Multiple resources association

### **Getting Ready**

Once you on the Widget Catalog page, double-click on a widget in your Resource Catalog to open the Widget Editor. The next screenshot provides an overview of the Widget Editor.

* Widget Resources Catalog
* Settings
* Perspectives
* Documentation

![](../../.gitbook/assets/13)

### ​ Widget Resources Catalog

Here we will take a look at how the different areas of the Widget Editor can be used.

**Widget Resources Catalog**

The next screenshot shows the different resources in the Resources Catalog.

* Each widget has special resources that are automatically organized into special folders.
* A special folder can’t be deleted, moved or renamed
* A special resource can’t be deleted, moved or renamed

![https://gblobscdn.gitbook.com/assets%2Fpothole%2F-Me4UcB3LybUNCnFdfgt%2F-Me4W9R50g3LjxjNzGPU%2F6.png?alt=media](<../../.gitbook/assets/14 (1)>)

* Special resource: index.html
  * index.html resides at the root level.
  * index.html resource is the main view and contains HTML, CSS, and Angular elements.

![https://gblobscdn.gitbook.com/assets%2Fpothole%2F-Me4UcB3LybUNCnFdfgt%2F-Me4W9R6Zyo\_PWsTYtV5%2F7.jpeg?alt=media](<../../.gitbook/assets/15 (1)>)

* Special resource: configuration.json
  * configuration.json contains all generic configuration data to load parameters.
  * configuration.json will be used to specify the custom properties of the widget.
  * When you specify a new custom property and save the configuration.json file, the system automatically adds the property in Settings panel. When editing the widget, this allows you to easily modify the widget's property values.
  * The custom properties defined in the configuration.json will be available by using DECISYON.target.content.ctx object. The context object can be used in your code and in data binding expressions.
* Special resource: mockContext.json
  * mockContext.json contains all contextual information of the widget.
  * The context is a list of references to the business data manipulated by the process instance during its execution.
  * mockContext.json also contains all custom properties defined in the configuration.json and all supported properties.
  * The context data will be automatically assigned to the $scope and will be available by using DECISYON.target.content.ctx object. The context object can be used in your code and in data binding expressions.
  * mockData.json and mockContext.json help you to simulate the widget behavior.
* Special resource: mockData.json
  * The mockData.json contains data for scripts testing.
  * The data will be automatically assigned to the $scope and will be available by using DECISYON.target.content.data object. You can use it in your code and in data binding expressions.
  * When you associate a report data source in a Data Presentation widget, the system allows to you to automatically generate mock data. For each report associated with the widget, the system generates a specific node in the JSON. The first report has

_**reportProvider**_ as the main node, while the main node for all subsequent reports are named _**reportProvider\_n**_, where n is an unique sequential number starting with 1

* Special Folder: shared
  * The shared folder will contain the individual shared libraries that you want to reuse on multiple widgets.
  * The system will automatically resolve the imported shared libraries as dependencies before resolving the widget dependencies.

#### Settings

The next screenshot shows the different options in the Settings panel.

![https://gblobscdn.gitbook.com/assets%2Fpothole%2F-Me4UcB3LybUNCnFdfgt%2F-Me4W9R7owVWMnm7SCS1%2F8.png?alt=media](../../.gitbook/assets/16)

* Dependencies
  * Describe all scripts and css dependencies for each widget.
  * To do so, upload the resource that you want to use in widget resource catalog and add to your custom widget as an asset.
  * Use dependency properties in the Settings panel to add a resource as a dependency to the widget.
* In the SETTINGS >> MAIN >> ADVANCED tabs you will find all the information relating to the version of the widget and the compatibility of the APIs:
  * Version: Widget Version
  * Minimum API level : Minimum API level supported by the widget
  * Maximum API level: Mazimum API level supported by the widget
  * &#x20;Target API level: Indicates the widget API target

#### Perspectives

The next screenshot shows the different perspectives available in the Widget Editor.

​

![](../../.gitbook/assets/17)

#### Documentation

Documentation contain the API reference materials for DAC.

The documentation is organized into modules which contain the core global API.

The core global API functions are attached to the DECISYON object. These core functions are useful for low level JavaScript operations within your application.

![](<../../.gitbook/assets/18 (1)>)

​

## **How to import widget**

The DAC in addition to offering the possibility to create Custom Widgets allows the import of pre-configured and ready-to-use widgets. In the following example we see how to import a widget into our application.

**Step 1 Choose the widget to import**&#x20;

Let's say we want to import the Button widget

![](<../../.gitbook/assets/19 (1)>)

First you need to be in possession of the film.

![](<../../.gitbook/assets/20 (2)>)

**Step 2. Set the widget in the widget designer**&#x20;

Select the icon at the top left to import the widget and select the file in the import window.

![](../../.gitbook/assets/21)

**Step 3 Publish widget**

The widget is now present in the Widget Catalog. Now to be able to use it on a page in the Page Designer you need to publish it.

![](../../.gitbook/assets/22)

The imported widget now is available in the Page designer's widget catalog.

## **How to create a Custom Widgets**

This section provides an introduction on how to create custom widgets using Widget Designer

**Hello World Application**

Let’s build a variation of the classic Hello World application using Widget Designer.

**Getting Ready**

All you will need for this recipe is the Widget Designer IDE and a basic understanding of AngularJS. Our Hello World application needs the following functionality:

1. Ability for the user to provide text input via an input field
2. When the user is typing in this input field, the UI should be updated automatically with the latest value from input field.

**How to do it…**

Here we will take a look at how to create the application using the Widget Catalog and Editor.

* In the Widget Catalog, create a new Generic widget
* Assign a unique logical name, for example “exHelloWorld”
* Double-click and open the widget in Widget Editor
* Define the widget view in index.html
* Define the widget style in index.css
* Publish the widget
* In the Page Designer, use the widget in a page

To publish or unpublish the widgets are available in the contextual menu of the widget.

**Widget Structure**

* We have set the ng-model directive for the Textbox. We use ng-model="name" in the input field to data-bind the input with the model named as "name".
* There are two HTML H1 elements. One is set with a template expression (written with double curly braces and the model name within: \{{name\}}), while other is specified with the ng-bind directive: ng-bind="name".
* We have set the ng-show directive for the two HTML H1 to display the elements based on the given model value.
* As we type in the Textbox, both the HTML H1 elements display the value of the Textbox dynamically.

**Output**

**Use the Widget in Page Designer**

This screenshot shows how to use the widget in Page Designer to create a new page in DAC Runtime.

**Hello \<current\_user> Application**

Let’s build an application to display “_Hello current\_user_” using Widget Designer.

**Getting Ready**

All you will need for this recipe is the Widget Designer IDE and a basic understanding of AngularJS. Our Hello World application needs the following functionality:

1. Display “Hello current\_user!” for the current user
2. Translate the greeting based on the language defined in the user profile

**How to do it…**

Here we will take a look at how to create the application using the Widget Catalog and Editor.

* In the Widget Catalog, create a new Generic widget
* Assign a unique logical name, for example “exHelloCurrentUser”
* Double-click and open the widget in Widget Editor
* Define the controller and the directive named “helloCurrentUser” in index.js
* Define the widget view in index.html
* Define the widget style in index.css
* Publish the widget
* In the Page Designer, use the widget in a page

**Widget Structure**

* Create a directive named “helloCurrentUser”, a controller to create the User model which can be used in our template.
* We will use the following DAC APIs:
* the service dcyService by injecting them in our controller function arguments
* the filter dcyTranslate for translating the greeting
* the method DECISYON.ng.register.directive to register a directive in DAC
* the method DECISYON.ng.register.controller to register a controller in DAC

**Controller**

* Define a controller to create the User model which can be used in our template. The User information data is already available in $scope variable: $scope.DECISYON.userInfo.
* Create and register the controller by DECISYON.ng.register.controller(‘nameController’, ConstructorController). The function passed is injected with the services that we need.
* Use the Decisyon service dcyService to translate the label for the greeting in multiple languages.

**Directive**

* Define the directive "helloCurrentUser".
* Create and register the directive using DECISYON.ng.register.directive(‘nameDirective’, ConstructorDirective).
* The function passed returns a directive definition object which contains these following properties:
* restrict: 'E' - this means that the directive will only work as an Element.
* template - this specifies the HTML markup that will be produced when the directive is compiled and linked by Angular. This includes HTML, data binding expressions (\{{ \}}), using the filter dcyTranslate.
* controller - this defines the controller that will be associated with the directive template.
* controllerAs - this defines the controller alias used in the controller code and in the view.
* bindToController: true - this ensure that properties are bound to the controller instead of the scope. In combination with controllerAs, this lets us access the user variable as currUserCtrl.userInfo.fullname within the view.

**View**

* Define the view in index.html.
* Use the CSS class defined in index.css (resolved as a widget dependency).
* Use the directive helloCurrentUser as an element

**Output**

**Use the Widget in Page Designer**

This screenshot shows how to use the widget in Page Designer to create a new page in DAC Runtime.

**Hello World Application using Custom Settings**

Let’s build a variation of the first Hello World application (in Section 2.1) using custom properties and parameters.

**Getting Ready**

All you will need for this recipe is the Widget Designer IDE and a basic understanding of AngularJS. Our Hello World application needs the following functionality:

1. 1.Ability for the user to provide text input via an input field
2. 2.When the user is typing in this input field, the UI should be updated automatically with the latest value from input field.
3. 3.Ability to control the border, background and text color using custom settings

**How to do it…**

Here we will take a look at how to create the application using the Widget Catalog and Editor.

* In the Widget Catalog, create a new Generic widget
* Assign a unique logical name, for example “exHelloWorldWithCustomSettings”
* Double-click and open the widget in Widget Editor
* Define the custom properties in configuration.json
* Define the controller in index.js
* Define the widget view in index.html
* Define the widget style in index.css
* Publish the widget
* In the Page Designer, use the widget in a page

**Custom Settings**

* In configuration.json, define two custom properties in the JSON schema shown in the above image.
* Use the prefix $ to refer to a custom group, a custom subgroup, a custom subset or a custom property.
* Define the first custom property named “theme” ($THEME) that allows to change the widget content style.
* This property is defined as a dropdown list and has two admissible values:
* orange: rounded border, orange background, white text
* green: border and text green
* Define the second custom property named "center horizontally" ($H\_CENTER\_ALIGN) that allows to center the widget content horizontally.
* This property is defined as a switch and its value accepts a parameter. The field

_allowPageParameter_ indicates that the value refers to a page parameter.

**Controller**

* Define a controller to create the model which can be later used in the template to binding our custom properties.
* The custom properties data is already available in $scope variable:

$scope.DECISYON.target.content.ctx.

* Use $scope.DECISYON.target.content.ctx.\<property\_id>.value to refer to our two custom properties in the code.
* Use $watch to watch any changing in values on the scope DECISYON.target.content.ctx.
* To manage a parameter than is not assiged a value related to a custom property, check if that is equal to ‘PARAM\_VALUE\_NOT\_FOUND’
* To manage the changes of a parameter related to a custom property, use $scope.$watch()

**View**

* Define the view in index.html.
* Use the CSS class defined in index.css (resolved as a widget dependency).
* Use the ngClass directive allows to dynamically/conditionally add CSS classes to the HTML by databinding an expression that represents all classes to be added.
* Write an expression for the ngClass directive using array syntax and checking both the scope variable theme and the scope variable centerClass.

**Output**

* Remember to reload the mockContent.json after the custom property value is changed.

**Use the Widget in Page Designer**

This screenshot shows how to use the widget in Page Designer to create a new page in DAC Runtime.

* In a new page in Page Designer, add two instances of the widget that was created in this example.
  * For the first widget, set the theme property to orange value.
  * For the second widget, set the theme property to green value.
