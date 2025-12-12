# Table Write

It is possible to activate the creation of a table that can contain a copy of the report using the property (_TableWrite_ group):

* _**activateTableWrite**_ enables the following properties for the creation and configuration of the table, which will contain the report data:
  * _**drop-create**_ enables the deletion and later creation of the table, on every report execution; if the property is not enabled the table is only emptied (DELETE-INSERT and repopulated).

This property is especially useful if the report is not _stable_, that is, if the report undergoes changes, such as addition of levels and/or metrics:

in these cases, if the _drop-create_ property is not enabled, the system notices a discrepancy between report and table columns and returns an error message.

Therefore, if you use the DELETE-INSERT mode (i.e. if the property is disabled) the report's structure cannot change after the first creation of the table.

* _**write-content-type**_ sets the type of content of the table, i.&#x65;_**., the columns generated for the table:**_
* with < _report-datamart > the_ columns coincide with those of the datamart.
* with < _report-body >_ the columns coincide with the report elements; therefore columns to contain composite metrics, not in the datamart, will also be created, while columns for component metrics will not be created.

Step 1: Creating Report

![](<../../../../.gitbook/assets/20 (12).png>)

_You can create a report with the dimensional levels and the desired metrics._

_In the report in the example the levels are Customer Group and Customer Description while the metric of reference is Sales Quantity._

_Enable the activateTableWrite property, in the table-name property enter “Customer\_Group”, the name of the table that will be created in the database. Finally the report is executed._

Step 2: Customer Group Table

![](<../../../../.gitbook/assets/21 (13).png>)

_Accessing the metadata database, we display the Customer\_Group table with the data for the previously created report._

_The names of the columns in the table correspond to the logical name set at the time when dimensions and metrics were created._
