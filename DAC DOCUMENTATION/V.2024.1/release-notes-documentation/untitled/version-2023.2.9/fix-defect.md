# Fix Defect

**D4C-10413 Web report - rename and delete don't work and rename icon is broken** Fixed an issue in the Web interface where the rename and delete functions for reports in the "My report" section were not working, and the rename icon was broken.

**D4C-10294 Export in CSV of a report with a level set with custom ordering - column** Fixed an issue where exporting a report to CSV with a level configured with custom ordering added an extra column showing the ID used for the ordering.

**D4C-10271 Web editor report does not delete the reports** Resolved an error that prevented reports created with the Web Editor from being deleted, causing a console error without completing the operation.

**D4C-10236 Report on Oracle datasource show null metrics if built on two cubes with only one common level** Fixed a bug occurring only with Oracle datasources, where a report using two cubes with only one shared level displayed null metrics even though the final table contained data.
