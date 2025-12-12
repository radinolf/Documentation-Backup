# What's New in this version

## Version 2.1

### Improvements of preselection functionality of the Switch widget <a href="#download_contents_from" id="download_contents_from"></a>

In version 2.1, the **Switch** widget includes improvements that simplify the preselection functionality.

The following changes have been introduced:

* The **Import value** property has been renamed as **Default value** and now is acquired only on the first widget rendering (to be the default value). Other changes of the Default value property will be considered only using the reset function **(\<baseName>\_reset).**
* The **Pre-selection** feature of the widget is now based on the **\<basename>** parameter instead of the **Import value** parameter of the previous release (**Default Value** in this version).
* The **\<basename>** parameter, when configured on the page (i.e. via the **pre-selection-values** page feature), will override the **Default value** feature.

### New properties for setting the Boolean format of the imported and exported parameters by Switch widget <a href="#new_properties_for" id="new_properties_for"></a>

In version 2.1, the **Switch** widget introduces:

* The “**Main Boolean parameter format”** new configuration property to set the Boolean format of the main imported and exported parameter (**\<basename>** parameter) by the widget. It is possible to specify the following types of Boolean format:
  * **false/true (default)**
  * **0/1**
  * **no/yes**
  * **off/on**
* The **Export additional false/true parameter**
* The **Export additional 0/1 parameter**
* The **Export additional no/yes parameter**
* The **Export additional off/on parameter**

These properties, when enabled, will export on the page additional parameters in the Boolean format specified in each property. The additional parameters exported by the widget are:

* **\<baseName>\_bool:** Exports the additional false/true parameter
* **\<baseName>\_int:** Exports the additional 0/1 parameter
* **\<baseName>\_no\_yes:** Exports the additional no/yes parameter
* **\<baseName>\_off\_on**: Exports the additional off/on parameter
