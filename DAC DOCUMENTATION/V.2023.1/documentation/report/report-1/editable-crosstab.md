# Editable Crosstab

## Load Data Via excel

Importing data via excel file allows to edit and insert data within a report. Only a business user with writing permission can import data via Excel. Permission can be assigned to user only if “enable-editing” property of the report is flagged. In addition, the “enable-editing” property on the widget must also be enabled.

Those are the operations allowed:

* **Update:** allows you to update all the rows of the report exported via Excel file. During the data import, only the non-Read-Only columns are updated and a check will be made on the key fields. Data whose key values are not present in Excel should not be changed.
* **Insert:** Allows to insert new lines into the report. In this case the data already present in the table is not updated.
* **Insert / Update:** Allows you to insert and update multiple rows simultaneously.
* **Delete / Update:** allows you to delete and update multiple lines at the same time. The table will be updated with only the data present in the excel file. Therefore all the lines not present in the excel file will be deleted in the table.

The type of operation, allowed when importing data via Excel, is defined in the Page Designer through the property (import-operation-type) of the widget.

## Note

Before importing data from an Excel template into a report, the system validates the excel template and its data.

**Structural Validation Criteria:**

* All columns mapped in the sheet must be valid (existing column header).
* The Excel Template must contain a column for each corresponding column of the Report.

**Data Validation Criteria**

* Each row of the Excel Template must contain non-null values for the corresponding key columns of the Report and mandatory metrics;
* Each cell of the Excel Template must contain a value of the corresponding Report columns’ datatype.

In case any of the above criteria are not meet, the Excel Template is invalid.

The system will return to the business user a detailed description of result:

* **Structural invalidation:**<br>
  * Invalidating reason;
  * Missing columns (if any).
* **Data invalidation:**<br>
  * Coordinates of the invalid cells;
  * Invalidating reason.

You can enable import into Excel in case your report doesn’t use metrics

