# Fix Defects

The following bugs have been fixed:

* **DACXX-1403 - 404 Error When the `openNewWindow` Property is Not Enabled in Drill-Through**\
  The issue causing a 404 error when the `openNewWindow` property was disabled in drill-through configurations has been resolved. The redirection now correctly navigates to the target page without requiring the deprecated loading page.
* **DACXX-1401 - DAC Wrongly Stores "null" as a String in Smartgrid Widget**\
  The system no longer stores the string `"null"` in the database when no value is inserted into a string column in the Smartgrid widget. The correct `NULL` value is now stored instead.
* **DACXX-1399 - Database Connection Leak When Using REST/JSON Datasource**\
  A database connection leak was identified and fixed in scenarios where multiple widgets used the same REST/JSON datasource. The application now properly releases connections to prevent connection pool saturation, improving system stability and responsiveness.
