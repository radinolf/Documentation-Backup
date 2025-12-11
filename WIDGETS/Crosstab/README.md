# Crosstab

The Crosstab component inherits the properties defined in the report; those that can be changed in the component are those relating to the _ObjectStyle_ grou&#x70;_._

The properties which can be customized on the Crosstab component in the Page are:

* _**show-page-by**_ enables the header of the report
* _**show-body**_ enables the display of the content of the report (page-by is excluded)
* _**rowsLocked:**_ locks the rows of the report while scrolling
* _**colsLocked:**_ locks the columns of the report while scrolling
* _**object-**_&#x74;ransparency defines the transparent color for the cells of the crosstab
* _**< none >**_ no transparency
* _**< body >**_ transparency only for the cells of the body of the report
* _**< body & header >**_ transparency for the body of the report and the headers

The property is applicable and visible only if the row and column lock properties are not enabled.

* **force-auto-expand-height (Group Page PDF Export)** sets the auto-expand value in the container during exportation of the PDF Page, so that all the values in the crosstab are printed.
* _**show-rows-cols-numbers:**_ enables the display of the number of rows and columns of the report. The information is visible in the toolbar of the report. Therefore the show-toolbar property must be enabled.
