# Fix Defects

* **DACXX-1242 - Scheduled Action List Not Working on SQL Server**\
  Resolved scheduled action issues on SQL Server by enabling a specific Quartz job store configuration. Introduced a custom `UpdateLockRowSemaphore` used when the `sqlserver` Spring profile is active.
* **DACXX-1808: The 'refresh-opener-report' property of the 'execute button' WDG is not working, and the crosstab from which the DT is called is not refreshing.**\
  Fixed an issue where the source report was not refreshing after returning from a Drill Through. The fix corrected a backend parameter name and a frontend function that miscalculated the dialog return window.
* **DACXX-1807: Application available when no pages granted to user**\
  Fixed behavior where applications were still visible even when no pages were assigned to the user.
* **DACXX-1759: Widget renders successfully in AppComposer but cause exception in Pages**\
  Resolved rendering error in the custom widget within Pages, which was causing crashes not present in AppComposer. The crash was due to a `NullPointerException` during cell generation.
* **DACXX-1746: Missing loading indicator for long-running Crosstab/Report**\
  Enabled loading indicators on page objects (such as crosstabs) to improve user experience during long data processing. A loading layer is now shown during processing but requires care to ensure it is always removed correctly.
* **DACXX-1745: Row container visibility property problem if set with a page parameter**\
  Fixed dynamic visibility of Row/Column containers controlled by page parameters, including scenarios with nested containers. The fix ensures parameter updates work even without widgets on the page.
* **DACXX-1744: "No data to display" is shown instead of data in the "Chart" widget**\
  Removed a one-second delay in the Chart widget rendering that was preventing data display in some cases. The improvement leverages updated capabilities of the FusionChart library.
* **DACXX-1743 - Crosstab record preselection does not update on dropdown change**\
  Fixed an issue with record preselection in the Crosstab widget. When a parameter was updated via JavaScript, the selected record was not refreshed correctly. The logic now correctly triggers a refresh even when exported parameters change.
* **DACXX-1108: hibernate\_sequence created 2 times on SqlServer Brand New Installation**\
  Removed the duplicate creation script of `hibernate_sequence` from Pages and AppComposer, keeping it only in the Tenant Metadata Installer.
* **D4C-10495 Exception raised on SQL repor when using create-temp-table**\
  Fixed an issue where a report crashed Design Studio due to an invalid advanced-sorting value `"Inherit Report"` set for a metric. The value was corrected to `"Ignore"` or a specific position, resolving the issue that appeared only when `"create-temp-table"` was enabled.
* **D4C-10481 Report SQL Direct | metric error when attribute has description associated**\
  Fixed a null pointer exception that occurred when a metric was used in SQL direct reports with an associated ID-description pair. The error was triggered during the metric resolution phase and has been resolved.
* **D4C-8405 Not possible to select Page on Group's Landing Page**\
  Corrected a mapping issue between database fields and the Java bean that caused the group’s landing page dropdown to show an empty list. Also resolved a UI bug that blocked saving the landing page selection.
*   **D4C-10538 An error occurred while saving the SQL report.**

    It has not yet been possible to clearly identify the root cause. No recurring patterns have been observed, and the current logs have not provided sufficient information to determine the issue.

