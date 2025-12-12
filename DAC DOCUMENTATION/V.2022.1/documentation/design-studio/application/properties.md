# Properties

## Introduction

It is possible to set properties that are valid at application level, from the **Application > > Properties** menu. These include:

* [Enabling the report and Page](properties.md#properties-of-pages) catalog, in DAC (_Generic_)
* the standard setting for [reports ](properties.md#properties-of-reports)and Metrics
* the[ configuration of the Pages](properties.md#properties-of-pages)
* [cache](properties.md#properties-of-cache) management at application level
* the management of messages received from the application

By setting a property at application level, the setting will be extended to all the objects created from that time onwards inside the application.

By selecting at least one checkbox **Overwrite on a setting,** the value selected is applied to all the objects existing in the application, including those created before the application of the property.

The Overwrite column is only visible as it corresponds to the properties relating to the Report and Metric groups.

Also note that you can extend the settings of an entire group of properties by selecting the **Override** checkbox relating to an entire group of properties.

The property extended with Overwrite will also be applied to the reports that are in the cache and will not be set in a definitive mode but may be applied if needed.

## Generic - Enabling the Report and Page

The **Generic** group only includes the property which determines the visibility, on DAC, of the objects of the application: thus it is possible to publish both the sections relating to the dashboards and reports (default setting), or just one of the two, or neither one.

The property for this is called _**modelObjectVisibility**_: for this property, you can select or deselect two checkboxes called _**showDashboard**_ and _**showReport**_.

By default the Dashboard and Report sections are visible from the web, so the two checkboxes selected by default.

It is possible to deselect Pages and Reports, to stop a section from being displayed.

If both are disabled, the application will not be visible in the welcome list.

## Report - Properties of Reports

All available report properties can be configured at the application level, except for those typically specific to the single report, such as properties regarding the selection of report levels and metrics, or ones that define the drill-through to be activated when executing the report.

The table below reports the properties at the application level in the Report section, and the corresponding properties of individual Reports.

| Section/Group in the properties of the application | Property                                        | Section/Group report properties |
| -------------------------------------------------- | ----------------------------------------------- | ------------------------------- |
| Main                                               | All group properties                            | _Main_                          |
| Drills                                             | All group properties                            | _Drills_                        |
| Join                                               | <p>autoDistinctKeys</p><p>join-global-names</p> | _Join_                          |
| Graph/Graph Style                                  | All group properties                            | _Graph Style_                   |
| Graph/Graph Title                                  | All group properties                            | _Graph/Graph Title_             |
| Graph/Graph Axis                                   | All group properties                            | _Graph/Graph Axis_              |
| Graph/Graph Legend                                 | All group properties                            | _Graph/Graph Legend_            |

These properties cannot be set at application level as they specifically refer to metrics and dimensional levels belonging to each report.

For exporting PDFs the properties coincide with those of the single report except for:

* _**pdfEditable header/footer**_: which enables/disables the end user when editing the header and footer

![](<../../../.gitbook/assets/0 (24).png>)

_**pdfEditable header/footer**_ disabled

_**pdfEditable header/footer**_ enabled (DEFAULT)

## Cache - Properties of Cache

DAC has a cache system to optimize the performance of the response times of the analysis data.

At application level it is possible to set the properties listed below (_Cache_ section):

* _**defaultExpTime**_ (_Cache_ group) the maximum time of permanence of the reports in the cache: period in hours, starting from the creation date and time, after which the automatic cache expires
* _**maxElementNum**_ (_Cache_ group) the maximum number of reports which may be in the automatic cache at the same time
* _**minExecTime**_ (_Cache_ group) the minimum execution time (in seconds), so that a report may be saved in the automatic cache
* _**invalidation-rule (on save)**_ (_Cache_ group) the management of the cache and the cube-view invalidation following modifications to cubes, dimensions, metrics, direct filters, range filters. You can decide whether the invalidation is to be managed independently by the system (_\<synchronized>_) or if it must be requested at each change (_\<prompt>_)

## Page - Properties of Pages

### Javascript and CSS

Pages can use JavaScript and CSS files, to give an improved graphical impact. These files can be chosen at application level in the properties to make them available for all of the application Pages:

* _**javascript**_ (JavaScripts _group_) Sets the JS script, and their, which must be run by default in the pages.
* _**css**_ (Cascading _Style Sheets (CSS) group_) sets the style sheet (Css), and their order, which must be applied as default in the pages

### Parameters Shared among Several Pages

It is possible “to share” the parameters defined in a Page, to all the other Pages of the application, so that the choices made in Pages can affect all those which use the same parameter.

Also for page-bys you can activate sharing, so that the user has the same choices repeated on every Page. For example if a particular year is chosen in a Page, all the Pages will show the same year in the page-by levels.

The sharing of the parameters and the page-bys, among the Pages of the model, is set using the properties:

* **activate-dsh-global-params** (_Params_ group) activates parameter sharing between Pages; this property enables the following:
  * **dsh-gloabal-params** to select the parameters to be made global, chosen from a list containing those defined in all the Pages of the application
* **share-page-by** (_Page-by_ group) activates the sharing of page-bys among the Pages of the application, so that the user has uniform values in the various pages; this property enables the following:
  * **shared-levels** for the selection of the levels to be shared

## **Metric - Properties of Metrics**

The properties in the **Metrics** section that can be set are:

* In the _**Middle**_ section, the formatting of the style, including the alternation of color of the rows/columns and the thousand and decimal separators, depending on the language of the web user (_Metrics_, _Metric formatting, Value style section_)
* In the _**Positive**_ and _**Negative**_ sections, the formatting available compared to the threshold values (_Metrics_, _Metric Formatting, Threshold value formatting section_)
* In the _**Null Values**_ section, the default management of null values (_Null value management_ section). In this case it is not possible to apply the override to the metrics already in the application. concern
