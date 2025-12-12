---
description: How to create Report
---

# Report

This section describes the functions to **develop reports**. The table lists the main subjects, with a short description and the link to the sub section where they are described.

Reports are tools that allow users to carry out accurate data analysis: it is possible to use cubes and metrics of the application. It will be then possible to request analysis on dimensional levels and metrics for different application cubes, ensuring congruence among elements: dimensional levels and metrics must be linked by at least one cube.

After choosing the desired dimensional levels and metrics for analysis, you can apply filters to restrict the field of observation. Applicable filters are created with the _Direct_ _Filter_ and _Range_ _Filter_ modules, but it is also possible to create filters exclusively for the report.

Once the report has been defined, the system generates one or more SQL queries to retrieve the data. Report execution produces a series of temporary tables to store intermediate results until the final table is produced with the data requested by the report. This table represents the datamart for the requested analyses.

In DAC, you can define reports populated with data from a SQL query. These reports will define the cubes and dimensions valid exclusively for the current report, which will be integrated with data from BI cubes.

DAC offers a series of functions to increase the effectiveness and efficiency of report analysis, such as:

* mode of data visualization, such as tables and graphs
* customization of the graph or table section
* aggregation of dimensional levels (so that _navigation_ can be enabled for drill-down and roll-up operations) and the navigation mode
* definition of standard or Excel-like type totals
* customization of the behavior of levels used as filters (Page-by)
* using the report analysis as a filter for other reports, Pages, database queries or as parameters for web-type applications (Drill-through)
* inserting a Page as report prompt
* exporting the report, in PDF, Excel or CSV format
* customized sorting of data
* enabling custom functions on the toolbar of the report functions



###

###

###

###

##

##

##

###
