# Editable mode for smart grid

## Introduction <a href="#introduction-editable-report" id="introduction-editable-report"></a>

The Editable Report is a particular report that allows to interact with the report data. It’s possible to insert, delete and modify the data and select which user groups can modify them.

In addition to the restriction on user groups, it is also possible to decide which column can be edited by configuring the columns-definitions property of the main group.

To allow the end-users, to use an Editable Report, it is necessary to associate the report with the Dcy Smart Grid Widget (see the widget Smart Grid documentation).

You can change or insert new data importing **Excel** files. You will have the possibility to download the excel template of the report, modify the data and export again the file to update the data.

The editable report feature, is available for all the OLAP report while for the SQL reports you can associate it with the widget, but are not editable.

![](<../../../.gitbook/assets/image (829).png>)

&#x20;

## How to make a report editable <a href="#how-to-make-a-report-editable" id="how-to-make-a-report-editable"></a>

To activate the report editing, access the report properties >> Editing group of the Properties folder.

The properties allow you to:

* **enable-editing:** Enable the table to modify the data
* **data-deletion-message:** Set a message to be displayed when a report data is deleted
* **editing-grants :** select which user group can modify the data of an editing report.
  * **read-only-filter:** Set a SQL filter for making matching Report's rows read-only.
  * **read-only-columns:** Allow to select wich columns are read only..
* **insert-query:** Define inset query to manage how the data are added to the Report. It' is also possible to use parameters available in the page.
* **update-query:** Define Update query to manage how the Report data are updated. It' is also possible to use parameters available in the page.
* **delete-query:** Define Date query to manage how the data are deleted from the Report. It' is also possible to use parameters available in the page.
* **enable-audit:** Enable the audit logging for all the operations performed on the data of the Report
  * **audit-datasource:** Set the data source where to store the audit logging data
  * **audit-table-name:** The table storing the audit logging data

{% hint style="info" %}
IT’s possible to write the query of editable report even when there are no metrics available in the report .

It’s possible to use the system variable in the CRUD statement.
{% endhint %}

The **Column-Definition** properties of Main group defines report columns settings.

It’s possible to configure the column definition properties "Key", "mandatory" and "read-only" even without enabling the property "enable-editing". In this way the smart grid widget can use them even when enable-editing is disabled.

After enabling the report to modify data, it will be necessary to associate it with a Smart Grid Widget.

![](<../../../.gitbook/assets/image (434).png>)

**Column item details:**

* **Column**: show the list of levels and metrics present in the report.
* **Data Type:** a drop-down menu allows selection of data type (Number, String/Text , Date, Epoch, URL, Picture/Icon, Boolean)
* **Date Pattern**: Sets the pattern the date type column value must comply with.
* **Input type:** Sets the type of data to be entered allowing the use of the suitable input interface (Number, Text, Checkbox, Date, Value List)
  * **data-type** = _Number_
    * **reportColNumMin:** set the minimum value.
    * **reportColNumMax:** set the maximum value.
  * **data-type** = _Text_
    * **reportColTextMxL:** set the maximum length for the text to be inserted.
    * **reportColTextMnL:** set the minimum length for the text to be inserted.
    * **reportColTextRgx:** set the regular expression for the text to be inserted.
  * **data-type** = _Value List_
    * **values**: select the type of insertion of the value list
    * **report**: Define the report associated to the object
    * **id-column**: Allow you to select which column of the associated report will be used
    * **description-column**: Allows you to select which column of the associated report will be used as description.
    * **params-binding**: Allow you to configure for each parameter available in the associated report its binding with a column of the configuring report or a parameter coming from the page.
    * **depends-on-column:** Allow to set items displayed dependent on the value selected in another column available in the report.
* **Define Value:** If column with input type "Value list", allows you to configure the id value to use in order to open the drop down with a default value.
* **Visible:** Set if the column is visible. The columns defined as "not visible" are exported as hidden columns in the XLS file
* **Key**: Set if the column is a key column.
* **Mandatory:** Set if the column is mandatory.
* **Read only**: Set if the column is read only.
* **Auto-increment:** Set if the column is auto incremented

**NOTA:** The Smart Grid Widget is not present in the widget catalog of the Page Designer, therefore it must be imported into the application via the Widget Designer.

{% hint style="info" %}
The enable-editing properties can not be enabled in the following case:

* When the report is built on a read-only data source
* When an ID formula in applied on the levels
* When the report is a SQL report
{% endhint %}

{% hint style="info" %}
**API**: DAC Expose a REST Api to write (insert, update, delete) rows of a Report. Please see the REST API documentation on RunTime.
{% endhint %}

***

## Load Data Via excel <a href="#load-data-via-excel" id="load-data-via-excel"></a>

Importing data via excel file allows to edit and insert data within a report. Only a business user with writing permission can import data via Excel. Permission can be assigned to user only if “enable-editing” property of the report is flagged. In addition, the “enable-editing” property on the widget must also be enabled.

Those are the operations allowed:

* **Update:** allows you to update all the rows of the report exported via Excel file. During the data import, only the non-Read-Only columns are updated and a check will be made on the key fields. Data whose key values ​​are not present in Excel should not be changed.
* **Insert:** Allows to insert new lines into the report. In this case the data already present in the table is not updated.
* **Insert / Update:** Allows you to insert and update multiple rows simultaneously.
* **Delete / Update:** allows you to delete and update multiple lines at the same time. The table will be updated with only the data present in the excel file. Therefore all the lines not present in the excel file will be deleted in the table.

The type of operation, allowed when importing data via Excel, is defined in the Page Designer through the property (import-operation-type) of the widget.

{% hint style="info" %}
Before importing data from an Excel template into a report, the system validates the excel template and its data.

**Structural Validation Criteria:**

* All columns mapped in the sheet must be valid (existing column header).
* The Excel Template must contain a column for each corresponding column of the Report.

**Data Validation Criteria**

* Each row of the Excel Template must contain non-null values for the corresponding key columns of the Report and mandatory metrics;
* Each cell of the Excel Template must contain a value of the corresponding Report columns' datatype.

In case any of the above criteria are not meet, the Excel Template is invalid.

The system will return to the business user a detailed description of result:

* **Structural invalidation:**
  * Invalidating reason;
  * Missing columns (if any).
* **Data invalidation:**
  * Coordinates of the invalid cells;
  * Invalidating reason.

You can enable import into Excel in case your report doesn't use metrics.

Please see the Example How to configure the Editable Report [(Page Designer ](../../page-designer/)module)
{% endhint %}



## &#x20;<a href="#page-designer" id="page-designer"></a>
