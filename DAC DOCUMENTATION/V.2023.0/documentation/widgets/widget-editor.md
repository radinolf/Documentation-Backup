# Widget Editor

It is a great idea to familiarize yourself with the main components of the Widget Editor, since that is where you will make building applications and rich user interfaces much easier.

Widget Editor has the following features:

* Editing and upload of JS and CSS resources
* Code editor and content assist
* Multiple perspectives
* Preview
* Resource dependencies settings (JS, CSS)
* Ability to use any browser developer tools
* Multiple resources association

## **Opening Widget Editor**

Once you on the Widget Catalog page, double-click on a widget in your Resource Catalog to open the Widget Editor. The next screenshot provides an overview of the Widget Editor.

* Widget Resources Catalog
* Settings
* Perspectives
* Documentation

![](<../../.gitbook/assets/13 (5)>)

You can modify the layout of the screen accordingly to your needs:

![](<../../.gitbook/assets/17 (3)>)

## ​Widget Resources Catalog

Here we will take a look at how the different areas of the Widget Editor can be used.

### **Widget Resources Catalog**

The next screenshot shows the different resources in the Resources Catalog.

* Each widget has special resources that are automatically organized into special folders.
* A special folder can’t be deleted, moved or renamed
* A special resource can’t be deleted, moved or renamed

![](<../../.gitbook/assets/14 (7)>)

* Special resource: `index.html`
  * `index.html` resides at the root level.
  * `index.html` resource is the main view and contains HTML, CSS, and Angular elements.

![](<../../.gitbook/assets/15 (3)>)

* Special resource: `configuration.json`
  * `configuration.json` contains all generic configuration data to load parameters.
  * `configuration.json` will be used to specify the custom properties of the widget.
  * When you specify a new custom property and save the `configuration.json` file, the system automatically adds the property in Settings panel. When editing the widget, this allows you to easily modify the widget's property values.
  * The custom properties defined in the `configuration.json` will be available by using `DECISYON.target.content.ctx` object. The context object can be used in your code and in data binding expressions.
* Special resource: `mockContext.json`
  * `mockContext.json` contains all contextual information of the widget.
  * The context is a list of references to the business data manipulated by the process instance during its execution.
  * `mockContext.json` also contains all custom properties defined in the `configuration.json` and all supported properties.
  * The context data will be automatically assigned to the `$scope` and will be available by using `DECISYON.target.content.ctx` object. The context object can be used in your code and in data binding expressions.
  * `mockData.json` and `mockContext.json` help you to simulate the widget behavior.
* Special resource: `mockData.json`
  * The `mockData.json` contains data for scripts testing.
  * The data will be automatically assigned to the `$scope` and will be available by using `DECISYON.target.content.data` object. You can use it in your code and in data binding expressions.
  * When you associate a report data source in a Data Presentation widget, the system allows to you to automatically generate mock data. For each report associated with the widget, the system generates a specific node in the JSON. The first report has

_**reportProvider**_ as the main node, while the main node for all subsequent reports are named _**reportProvider\_n**_, where n is an unique sequential number starting with 1

* Special Folder: shared
  * The shared folder will contain the individual shared libraries that you want to reuse on multiple widgets.
  * The system will automatically resolve the imported shared libraries as dependencies before resolving the widget dependencies.

## Settings

The next screenshot shows the different options in the Settings panel.

![](<../../.gitbook/assets/image (553).png>)

* Dependencies
  * Describe all scripts and css dependencies for each widget.
  * To do so, upload the resource that you want to use in widget resource catalog and add to your custom widget as an asset.
  * Use dependency properties in the Settings panel to add a resource as a dependency to the widget.
* In the SETTINGS >> MAIN >> ADVANCED tabs you will find all the information relating to the version of the widget and the compatibility of the APIs:
  * Version: Widget Version
  * Minimum API level : Minimum API level supported by the widget
  * Maximum API level: Mazimum API level supported by the widget
  * &#x20;Target API level: Indicates the widget API target
* Page Integration : In this section you can hide the properties not needed by the widget. Once disabled, these properties are not displayed in the Design Studio when configuring the widget on pages.

## Documentation

Documentation contain the API reference materials for DAC.

The documentation is organized into modules which contain the core global API.

The core global API functions are attached to the&#x20;

## **Creating a Custom Widgets**

This section provides an introduction on how to create custom widgets using Widget Designer

### **Hello World Application**

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

* We have set the ng-model directive for the Textbox. We use `ng-model="name"` in the input field to data-bind the input with the model named as "name".
* There are two HTML H1 elements. One is set with a template expression (written with double curly braces and the model name within: \{{name\}}), while other is specified with the ng-bind directive: `ng-bind="name"`.
* We have set the ng-show directive for the two HTML H1 to display the elements based on the given model value.
* As we type in the Textbox, both the HTML H1 elements display the value of the Textbox dynamically.

**Output**

**Use the Widget in Page Designer**

This screenshot shows how to use the widget in Page Designer to create a new page in DAC Runtime.

### **Hello \<current\_user> Application**

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
* the service `dcyService` by injecting them in our controller function arguments
* the filter `dcyTranslate` for translating the greeting
* the method `DECISYON.ng.register.directive` to register a directive in DAC
* the method `DECISYON.ng.register.controller` to register a controller in DAC

**Controller**

* Define a controller to create the User model which can be used in our template. The User information data is already available in `$scope` variable: `$scope.DECISYON.userInfo`.
* Create and register the controller by `DECISYON.ng.register.controller(‘nameController’, ConstructorController)`. The function passed is injected with the services that we need.
* Use the Decisyon service dcyService to translate the label for the greeting in multiple languages.

**Directive**

* Define the directive "helloCurrentUser".
* Create and register the directive using `DECISYON.ng.register.directive(‘nameDirective’, ConstructorDirective)`.
* The function passed returns a directive definition object which contains these following properties:
* restrict: 'E' - this means that the directive will only work as an Element.
* template - this specifies the HTML markup that will be produced when the directive is compiled and linked by Angular. This includes HTML, data binding expressions (\{{ \}}), using the filter dcyTranslate.
* controller - this defines the controller that will be associated with the directive template.
* controllerAs - this defines the controller alias used in the controller code and in the view.
* bindToController: true - this ensure that properties are bound to the controller instead of the scope. In combination with controllerAs, this lets us access the user variable as currUserCtrl.userInfo.fullname within the view.

**View**

* Define the view in `index.html`.
* Use the CSS class defined in index.css (resolved as a widget dependency).
* Use the directive helloCurrentUser as an element

**Output**

**Use the Widget in Page Designer**

This screenshot shows how to use the widget in Page Designer to create a new page in DAC Runtime.

### **Hello World Application using Custom Settings**

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
* Define the custom properties in `configuration.json`
* Define the controller in `index.js`
* Define the widget view in `index.html`
* Define the widget style in `index.css`
* Publish the widget
* In the Page Designer, use the widget in a page

**Custom Settings**

* In `configuration.json`, define two custom properties in the JSON schema shown in the above image.
* Use the prefix $ to refer to a custom group, a custom subgroup, a custom subset or a custom property.
* Define the first custom property named “theme” (`$THEME`) that allows to change the widget content style.
* This property is defined as a dropdown list and has two admissible values:
* orange: rounded border, orange background, white text
* green: border and text green
* Define the second custom property named "center horizontally" (`$H_CENTER_ALIGN`) that allows to center the widget content horizontally.
* This property is defined as a switch and its value accepts a parameter. The field

_allowPageParameter_ indicates that the value refers to a page parameter.

**Controller**

* Define a controller to create the model which can be later used in the template to binding our custom properties.
* The custom properties data is already available in $scope variable: `$scope.DECISYON.target.content.ctx`.
* Use `$scope.DECISYON.target.content.ctx.<property_id>`.value to refer to our two custom properties in the code.
* Use `$watch` to watch any changing in values on the scope `DECISYON.target.content.ctx`.
* To manage a parameter than is not assiged a value related to a custom property, check if that is equal to ‘_PARAM\_VALUE\_NOT\_FOUND_’
* To manage the changes of a parameter related to a custom property, use `$scope.$watch()`

**View**

* Define the view in `index.html`.
* Use the CSS class defined in `index.css` (resolved as a widget dependency).
* Use the `ngClass` directive allows to dynamically/conditionally add CSS classes to the HTML by databinding an expression that represents all classes to be added.
* Write an expression for the `ngClass` directive using array syntax and checking both the scope variable theme and the scope variable `centerClass`.

**Output**

* Remember to reload the `mockContent.json` after the custom property value is changed.

**Use the Widget in Page Designer**

This screenshot shows how to use the widget in Page Designer to create a new page in DAC Runtime.

* In a new page in Page Designer, add two instances of the widget that was created in this example.
  * For the first widget, set the theme property to orange value.
  * For the second widget, set the theme property to green value.

## Definer in the widget <a href="#definer-in-the-widget" id="definer-in-the-widget"></a>

List of configurable definers in the `configuration.json` of widgets

#### Definer to selected an Execute Button in the containing page <a href="#definer-to-selected-an-execute-button-in-the-containing-page" id="definer-to-selected-an-execute-button-in-the-containing-page"></a>

In the `configuration.json` of widget, it's possible to use a definer to selected an Execute Button in the containing page.

Example:&#x20;

```json
{
  "$variable1": {
    "name": "<variable1>",
    "desc": "A variable that can be to select a execute button in the page",
    "definer": "EXECUTE_BUTTON",
    "definerOptions": {
      "dataType": "STRING"
    },
    "value": "",
    "allowPageParameter": false,
    "preferredPosition": 1
  }
}
```

### Definer for selecting an Execute button.&#x20;

In this example we will define, in the `configuration.json`, the definer for selecting an Execute button.

**Step 1 Widget Designer**

Access the Widget Designer and select the _`configuration.json`_ from the _metadata >> configuration_ folder Resource of widget. Insert the code in the `configuration.json` widow.

<figure><img src="../../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

Below the code that we are going to insert in the `configuration.json` of the widger.

```json
{
  "additionalSettings": {
    "groups": {
      "$LAYOUT": {
        "name": "Widget properties",
        "desc": "Contain widget properties",
        "subGroups": {
          "$STYLE": {
            "name": "task",
            "subSets": {
              "$CONTENT": {
                "name": "MyWIDGET",
                "properties": {
                  "$EXECUTE": {
                    "name": "Execute object",
                    "desc": "Allows to to select an execute object in the page",
                    "definer": "EXECUTE_BUTTON"
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

**Step 2 - Open Page Designer**

Access the Page Designer and insert in the page the widget you created in step 1 and a widget Execute Button. The new property is present in the folder Object .

When you select the execute object property a window will open, showing the list of Execute button widgets on the page, and you will have the option to select one.

<figure><img src="../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

### Definer to select a report's level in Widget Designer

In the `configuration.json` of widget, it's possible to use the REPORT\_LEVEL definer, which allow the selection of one or more levels of one of the reports associated to the widget. Is it possible to define the index of the report to take into consideration with the optional property "reportIndex" . If the property is not specified, the report at index 1 is considered.

Example:

```json
{
  "$variable2": {
    "name": "<variable2>",
    "desc": "description",
    "definer": "REPORT_LEVEL",
    "definerOptions": {
      "dataType": "LIST",
      "reportIndex": 1
    },
    "preferredPosition": 1
  }
}                        

```

**Example**

In this example we will define, in the configuration.json, the definer for selecting a levels of one of the reports associated to the widget.

**Step 1 Widget Designer**

Access the Widget Designer and select the _configuration.json_ from the _metadata >> configuration_ folder Resource of widget. Insert the code in the configuration.json widow.

```json
{
  "additionalSettings": {
    "groups": {
      "$LAYOUT": {
        "name": "Widget properties",
        "desc": "Contain widget properties",
        "subGroups": {
          "$STYLE": {
            "name": "ReportLevel",
            "subSets": {
              "$REPORT_LEVEL": {
                "name": "Report Level",
                "desc": "Select Report Level",
                "properties": {
                  "$Repor_Level": {
                    "name": "Select Level",
                    "desc": "Select Report Level",
                    "definer": "REPORT_LEVEL",
                    "definerOptions": {
                      "dataType": "LIST",
                      "reportIndex": 1
                    },
                    "value": "",
                    "preferredPosition": 1
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

**Step 2 - Open Page Designer**

Access the Page Designer and insert the widget that you created in step 1 on the page. Associate one or more reports with the widget. In the example we have inserted in the property "reportIndex": 1 this means that the levels of report number 1 will be taken into consideration.

The new property is present in the Object folder.

When you select the “select Level” property, the window for selecting one or more levels opens.

<figure><img src="../../.gitbook/assets/image (804).png" alt=""><figcaption></figcaption></figure>
