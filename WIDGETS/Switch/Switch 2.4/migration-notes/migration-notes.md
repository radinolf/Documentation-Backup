# Migration Notes

This section of the document indicates the changes and impact in migrating the Switch widget in version 2.3 that require management by the Administrator.

With the improvements of the **Switch** widget **-** see the Change Log section, the following changes have been applied:

* The **Import value** property has been renamed as **Default value** and now is acquired only on the first widget rendering (to be the default value). Further changes of the **Default value** property will be considered only using the reset function **(\<baseName>\_reset**).
* The **Pre-selection** feature of the widget is now based on the **\<basename>** parameter instead of the **Import value** parameter of the previous release (**Default Value** in this version).
* The **\<basename>** parameter, when configured on the page (i.e. via the **pre-selection-values** page feature), will override the **Default value** feature.
* In the previous version, the widget imported and exported false/true values (**\<baseName> parameter**) and 0/1 values in a second parameter (**\<baseName>\_int parameter**). In this version, the widget introduces:
  * The “**Main Boolean parameter format**” configuration property to set the Boolean format (**false/true**, **0/1**, **no/yes**, **off/on**) of the main imported and exported parameter (**\<basename>** parameter)
  * The **“Export additional false/true parameter”**
  * The **“Export additional 0/1 parameter”**
  * The **“Export additional no/yes parameter”**
  * The **“Export additional off/on parameter”**

These properties, when enabled, will export on the page additional parameters in the Boolean format specified in each property. The additional parameters exported by the widget now are:

* **\<baseName>\_bool:** Exports the additional false/true parameter
* **\<baseName>\_int:** Exports the additional 0/1 parameter
* **\<baseName>\_no\_yes:** Exports the additional no/yes parameter
* **\<baseName>\_off\_on:** Exports the additional off/on parameter

During the migration:

* It is necessary to set the preselected values in the **Switch** widget using the **\<basename>** parameter when the value needs to be changed from other widgets.

If this step is skipped, the default value will only be considered in the first rendering.

* In case the preselection feature has been used on the page only for default values, it is necessary to verify that the **Import value** feature and the **\<basename>** parameter are not concurrently used on the page.
* The exported **\<baseName> \_int** parameter will be disabled after upgrading. It is necessary to enable the **“Export additional 0/1 parameter”** property on the pages that require it.
* In case the **Invert additional parameter value** feature has been used on the page (it reverses the logic false/true between the main value and the additional exported value), after upgrading, it will be necessary to enable a specific additional parameter.
