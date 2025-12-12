# Switch 2.4

## Overview <a href="#toc68171604" id="toc68171604"></a>

Use the **Switch** widget to perform a toggle (false/true) action between selected and unselected states and export the action's value as parameters on the page in different Boolean formats.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/WidgetHub/Switch/Switch.mp4" %}

![](.gitbook/assets/0)

The picture shows the **Switch** button created with minimal configuration via the widget's configuration properties. You can select and unselect the widget and export their values as parameters on the page in different Boolean formats.

The **Switch** is a two-status widget that allows users to select between two options. The widget exports the selected status that could be applied as filters for other widgets on the page.

By default, the **Switch** widget import and exports the value of the selected status (**\<basename>** parameter) using the **false/true Boolean format**:

<div align="left"><img src=".gitbook/assets/1" alt=""></div>

You can easily customize the **Boolean format** of the widget’s exported value based on your application scenarios.

By setting the "**Main Boolean parameter format**", you can change the **Boolean format** of the widget’s imported and exported **main value** (see the picture below).

<div align="left"><img src=".gitbook/assets/2" alt=""></div>

Using the "**Export additional parameter**" settings, the **Switch** widget allows exporting other Boolean formats as additional parameters to the main one configured in the "**Main Boolean parameter format**" function.

<div align="left"><img src=".gitbook/assets/3" alt=""></div>

The **Switch** widget includes **preselection** features. You can use:

* The **Default value** feature to set a value or a parameter as the widget’s initial values when opening the page or resetting the **Switch** button to its default value via the **\<basename>\_reset** parameter.
* The **\<basename>** parameter to set the widget with pre-selected values. When this parameter is used on the page, it will override the **Default value** feature configured in the widget.

In the **Switch** widget, you can reset the input field to its initial value(s) via the widget import parameter **\<basename> \_reset** (see example below).

![](.gitbook/assets/4)

<div align="left"><img src=".gitbook/assets/5" alt=""></div>

{% hint style="info" %}
The picture shows an example method to generate the value using the **\<basename>\_reset** parameter, but you can get it at will depending upon your business needs. Just make sure the reset event is different from the previous one.

The reset occurs every time the import parameter **\<basename>\_reset** is changed.
{% endhint %}

See the **Widget Parameters** section for more information about parameters imported and exported by the widget.

There are several features you can leverage to customize the appearance and usage of this widget. For example, you can:

* Disable the **Switch** to make the button unusable and unclickable (it is rendered in gray) so that it is not submitted on the page;
* Specify a label for the **Switch** button and choose its placement on the left/right;
* Use different options to zoom the button;
* Reduce the space around the button.

It is possible to customize its functionality and behavior, using the specific configuration properties in the Page Design.

See the **Properties** section for all applicable configurations.

## Properties <a href="#toc68171606" id="toc68171606"></a>

The properties that are specific for the configuration of the **Switch** widget on **Decisyon App Composer** are listed below:

<table><thead><tr><th width="221">Group</th><th width="200">Name</th><th width="313">Description</th><th align="center">Type</th><th width="163" align="center">Default Value</th><th align="center">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Boolean format and parameters (Behavior/Options)</strong></td><td><a href="./#boolean-format-and-parameters-behavior-options"><strong>Main Boolean parameter format</strong></a></td><td>Allows you to specify which type of Boolean format the widget has to use as the main parameter value to import and export (<strong>&#x3C;basename></strong> parameter) on the page</td><td align="center">SWITCH</td><td align="center">no/yes</td><td align="center"></td></tr><tr><td><strong>Boolean format and parameters (Behavior/Options)</strong></td><td><a href="./#boolean-format-and-parameters-behavior-options"><strong>Export additional false/true parameter</strong></a></td><td>When enabled, the widget exports false/true boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the <strong>Main boolean parameter format</strong> property (<strong>&#x3C;basename>_bool</strong> parameter)</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Boolean format and parameters (Behavior/Options)</strong></td><td><a href="./#boolean-format-and-parameters-behavior-options"><strong>Export additional 0/1 parameter</strong></a></td><td>When enabled, the widget exports 0/1 boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the <strong>Main boolean parameter format</strong> property (<strong>&#x3C;basename>_int</strong> parameter)</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Boolean format and parameters (Behavior/Options)</strong></td><td><a href="./#boolean-format-and-parameters-behavior-options"><strong>Export additional no/yes parameter</strong></a></td><td>When enabled, the widget exports no/yes boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the <strong>Main boolean parameter format</strong> property (<strong>&#x3C;basename>_no_yes</strong> parameter)</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Boolean format and parameters (Behavior/Options)</strong></td><td><a href="./#boolean-format-and-parameters-behavior-options"><strong>Export additional off/on parameter</strong></a></td><td>When enabled, the widget exports off/on boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the <strong>Main boolean parameter format</strong> property (<strong>&#x3C;basename>_off_on</strong> parameter).</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Content (Layout/Form)</strong></td><td><strong>Label</strong></td><td>Allows you to define a label for the Switch button. It usually represents the unselected /selected status (i.e. Off-On). The property allows page parameters</td><td align="center">TEXTFIELD</td><td align="center">Undefined</td><td align="center">Yes</td></tr><tr><td><strong>Content (Layout/Form)</strong></td><td><strong>Zoom</strong></td><td><p>Allows you to zoom the <strong>Switch</strong> button. This facilitates displaying it in a maximized form. You can set the following options:</p><ul><li><strong>Normal (Default)</strong></li><li><strong>Medium</strong></li><li><strong>Large</strong></li><li><strong>Xlarge</strong></li></ul></td><td align="center">SELECT</td><td align="center">Normal</td><td align="center"></td></tr><tr><td><strong>Content (Layout/Form)</strong></td><td><a href="./#disabled"><strong>Disabled</strong></a></td><td>When it is set to <strong>1/true</strong>, the Switch widget is disabled</td><td align="center">SELECT</td><td align="center">0</td><td align="center">Yes</td></tr><tr><td><strong>Content (Layout/Form)</strong></td><td><strong>Style</strong></td><td>Allows you to set a theme for the Switch widget. You can choose between the option <strong>Primary</strong> and <strong>Accent</strong></td><td align="center">SELECT</td><td align="center">Primary</td><td align="center"></td></tr><tr><td><strong>Content (Layout/Form)</strong></td><td><a href="./#label-position"><strong>Label position</strong></a></td><td>Allows you to change the placement of the label</td><td align="center">SELECT</td><td align="center">Right</td><td align="center"></td></tr><tr><td><strong>Content (Layout/Form)</strong></td><td><strong>No padding</strong></td><td>When enabled, it reduces the space around the component</td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Values (Behavior/Options)</strong></td><td><a href="./#invert-additional-parameter-value"><strong>Invert additional parameter value</strong></a></td><td>When enabled, it reverses the logic (false/true) between the main value and the additional exported value </td><td align="center">SWITCH</td><td align="center">0</td><td align="center"></td></tr><tr><td><strong>Values (Behavior/Options)</strong></td><td><a href="./#default-value"><strong>Default value</strong></a></td><td>Allows you to set a value or a parameter as the widget’s initial value</td><td align="center">TEXTFIELD</td><td align="center">Undefined</td><td align="center">Yes</td></tr></tbody></table>

#### **Boolean format and parameters (Behavior/Options)**

* **Main Boolean parameter format** property allows you to specify which type of Boolean format the widget has to use as the main parameter value to import and export (**\<basename>** parameter) on the page. You can set the following types of Boolean format:

**false/true:** (Default) The widget imports and exports on the page false/true Boolean format, based on the unselected/selected status, as the main parameter value (**\<basename>** parameter).

**0/1:** The widget imports and exports on the page 0/1 Boolean format, based on the unselected/selected status, as the main parameter value (**\<basename>** parameter).

**no/yes:** The widget imports and exports on the page no/yes Boolean format, based on the unselected/selected status, as the main parameter value (**\<basename>** parameter).

**off/on:** The widget imports and exports on the page off/on Boolean format, based on the unselected/selected status, as the main parameter value (**\<basename>** parameter).

<div align="left"><img src=".gitbook/assets/6" alt=""></div>

* **Export additional false/true parameter:** When enabled, the widget exports false/true boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the **Main boolean parameter format** property (**\<basename>\_bool** parameter).
* **Export additional 0/1 parameter:** When enabled, the widget exports 0/1 boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the **Main boolean parameter format** property (**\<basename>\_int** parameter).
* **Export additional no/yes parameter:** When enabled, the widget exports no/yes boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the **Main boolean parameter format** property (**\<basename>\_no\_yes** parameter).
* **Export additional off/on parameter:** When enabled, the widget exports off/on boolean format, based on the unselected/selected status, as an additional parameter value to the main one set in the **Main boolean parameter format** property (**\<basename>\_off\_on** parameter).

<div align="left"><img src=".gitbook/assets/7" alt=""></div>

#### **Disabled**

The **Disabled** property allows you to disable the Switc&#x68;**.** When it is set to **1/true**, the Switch widget is disabled. The user cannot interact with the component (it is rendered in gray). By default, the widget is enabled. The property allows page parameters.

<div align="left"><img src=".gitbook/assets/8" alt=""></div>

#### **Label position**

The **Label position** property allows you to change the placement of the label. Select the **left** or **right** options in the drop-down list to set the label before/after the control.

<div align="left"><img src=".gitbook/assets/9" alt=""></div>

#### **Invert additional parameter value**

The **Invert additional parameter value** allows you to reverse the logic (false/true) between the main value and the additional exported value (i.e. when the **Main Boolean parameter format** is set to **false/true**, the **Export additional false/true parameter** is enabled, and the widget is unselected, it will export on the page the "**false**" value as main parameter and the "**true**" value as additional parameter).

<div align="left"><img src=".gitbook/assets/10" alt=""></div>

#### **Default value**&#x20;

The **Default value** allows you to set a value or a parameter as the widget’s initial value when you open the page or reset the **Switch** to its default value via the **\<basename>\_reset** parameter. The property allows page parameters (see the example below).

{% hint style="warning" %}
The value format set in the **Default value** property must match the boolean format configured in the **Main boolean parameter format** property.
{% endhint %}

<div align="left"><img src=".gitbook/assets/11" alt=""></div>

![](.gitbook/assets/12)

{% hint style="info" %}
In addition to the **Default value** feature, the widget allows **preselection** of values through the use of the **\<basename>** parameter. The difference between these features is that:

* The **Default value** feature allows you to set the widget’s initial value when opening the page or resetting the **Switch** to its default value via the **\<basename>\_reset** parameter.
* The **\<basename>** parameter, instead, allows you to set the widget with pre-selected values. When this parameter is configured on the page, it will override the **Default value** feature.
{% endhint %}

## Widget Parameters <a href="#toc63261619" id="toc63261619"></a>

**Imported Parameters**

The following parameters are imported by the Switch widget:

| Name               | Description                                                                   | Note                                                                                                                                        |
| ------------------ | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| \<baseName>        | Imports the parameter value of the selected status of the widget (false/true) |                                                                                                                                             |
| \<baseName>\_reset | Reset the Switch to its default value                                         | If the **Default value** property is defined, the parameter will reset the Switch to the value configured in the **Default value** property |

**Exported Parameters**

The following parameters are exported by the widget when the Switch status change:

| Name                 | Description                                                                                                                                                              | Note                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<baseName>          | Exports the parameter value of the selected status of the widget (false/true) as the main parameter value                                                                | <p>According to the <strong>Main Boolean parameter format</strong> setting, the widget's will export the value in the following Boolean formats:</p><ul><li><strong>false/true</strong></li><li><strong>0/1</strong></li><li><strong>no/yes</strong></li><li><strong>off/on</strong></li></ul><p>When this parameter is used on the page, it will override the Default value feature configured in the widget</p> |
| \<baseName>\_bool    | Exports the parameter value of the selected status of the widget in the **false/true Boolean format** as an additional parameter to the main one (\<baseName> parameter) | The configuration property **"Export additional false/true parameter"** must be enabled                                                                                                                                                                                                                                                                                                                           |
| \<baseName>\_int     | Exports the parameter value of the selected status of the widget in the **0/1 Boolean format** as an additional parameter to the main one (\<baseName> parameter)        | The configuration property **"Export additional 0/1 parameter"** must be enabled                                                                                                                                                                                                                                                                                                                                  |
| \<baseName>\_no\_yes | Exports the parameter value of the selected status of the widget in the **no/yes Boolean format** as an additional parameter to the main one (\<baseName> parameter)     | The configuration property **"Export additional no/yes parameter"** must be enabled                                                                                                                                                                                                                                                                                                                               |
| \<baseName>\_off\_on | Exports the parameter value of the selected status of the widget in the **off/on Boolean format** as an additional parameter to the main one (\<baseName> parameter)     | The configuration property **"Export additional off/on parameter"** must be enabled.                                                                                                                                                                                                                                                                                                                              |

## Example <a href="#toc68171608" id="toc68171608"></a>

**Configuration:** Using the following specific properties:

**Label, Main boolean parameter format, Export additional … parameter, Default Value.**

**Description:** The example shows how to configure the **Switch** widget initialized with default value that exports all the additional parameters on the page.

* Create a new Page in the Page Design and add the **Switch** widget.
* Specify in the page the parameters exported by the widget:

In the **Switch** properties, enter the **basename**. In this example “**wdgswitch**”;

On the page, add one “**PlainText**” widget. Specify both the **Main** **parameter** (**\<baseName> parameter**) and the **Additional parameters** (**\<baseName>\_bool**, **\<baseName>\_int, \<baseName>\_no\_yes, \<baseName>\_off\_on)** exported by the widget when changing the status of the **Switch** button (see the picture below):

<div align="left"><img src=".gitbook/assets/13" alt=""></div>

* Configure the following specific properties for the **Switch** widget:

**Label:** Set a label for the Switch button (i.e. Switch Widget Example);

**Main boolean parameter format:** Set the Boolean format of the main parameter value exported by the widget to off/on;

**Export additional … parameter:** enable all the “**Export additional…parameter”** properties to export all the additional parameter values of the widget on the page;

<div align="left"><img src=".gitbook/assets/14" alt=""></div>

* **Default Value:** Set the initial value of the widget when you open the page, for example, enter "**On**" to set the selected status as the default value of the **Switch** button.

The value format must match the Boolean format configured in the “**Main boolean parameter format**”.

* Display the **Switch** widget in the Web Application.

<div align="left"><img src=".gitbook/assets/15" alt=""></div>
