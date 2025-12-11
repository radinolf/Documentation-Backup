---
description: >-
  A report presents the portion of one or more cubes and takes the form of a
  table and/or graph with different aggregation...
---

# Report

A report presents the portion of one or more cubes and takes the form of a table and/or graph with different aggregation levels, which can be browsed in depth (drill down) according to the natural hierarchy principle.

Reports are created and published by the DAC administrator. You can consult a report directly from the [catalog](https://docs.decisyon.com/report-catalog/) or in a page.

![](https://docs.decisyon.com/wp-content/uploads/2020/07/ReportIntroduction.jpg)



A report typically looks like the one in the figure below:

The report name and its folder are displayed in the top left. Selecting each folder displays its contents and directs browsing back to the catalog.

You can execute the [OLAP functions](https://docs.decisyon.com/olap-functions/) directly in the report.

The published reports may be edited, although the edits remain at user session level, in such a way as to give full freedom of analysis, leaving the environment prepared by the DAC administrator unchanged.

The functions available on DAC can be applied using the commands from the:

* [report toolbar](https://docs.decisyon.com/report-toolbar/)
* [pop-up menu](https://docs.decisyon.com/report-features/) to the report cells.

Any reports modified using the functions available on DAC will be visible only to the user who made the modification, and they will be kept only until the next login, or when a restart is carried out by the administrator.

After modifying the report, you can use the Reload Report item on the report toolbar (_Main_ section) to restore the report to its original form.

Reports can be presented in the form of a table, graph or both (document). The user may apply **custom styles** with the

* graph or
* table.

Commands and buttons quickly let you change the [paging](https://docs.decisyon.com/report-features/) of the report or [sort the metrics](https://docs.decisyon.com/report-features/).

The data can be filtered through the levels placed in the [Report Pages.](https://docs.decisyon.com/report-features/)

When you open a report, even if recently consulted by you, or if consulted by another user, it is executed again, but it is simply removed from the cache of the system.

When publishing a report, specific functionality may only appear on the web:

* the decoration of the metrics
* a [prompt ](https://docs.decisyon.com/report-features/)for selecting or analyzing above the report
* a [drill-through link](https://docs.decisyon.com/report-features/) to open a new page from the analyzed data

## Load Data Via excel

Importing data via excel file allows to edit and insert data within a report. Only a business user with writing permission can import data via Excel. Permission can be assigned to user only if “enable-editing” property of the report is flagged. In addition, the “enable-editing” property on the widget must also be enabled.

Those are the operations allowed:

* **Update:** allows you to update all the rows of the report exported via Excel file. During the data import, only the non-Read-Only columns are updated and a check will be made on the key fields. Data whose key values are not present in Excel should not be changed.
* **Insert:** Allows to insert new lines into the report. In this case the data already present in the table is not updated.
* **Insert / Update:** Allows you to insert and update multiple rows simultaneously.
* **Delete / Update:** allows you to delete and update multiple lines at the same time. The table will be updated with only the data present in the excel file. Therefore all the lines not present in the excel file will be deleted in the table.

The type of operation, allowed when importing data via Excel, is defined in the Page Designer through the property (import-operation-type) of the widget.

{% hint style="info" %}
Before importing data from an Excel template into a report, the system validates the excel template and its data.
{% endhint %}





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

You can enable import into Excel in case your report doesn’t use metrics
