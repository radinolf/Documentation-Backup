# Fix Defect

**DACXX-368**: Fixed error when opening a page that is not found, improving user navigation and error handling.

**DACXX-549**: Resolved issue with redirecting to the internal login page when two browser tabs are opened on Pages, ensuring proper session handling.

**DACXX-570**: Addressed the random display of the message 'Connection to the server discontinued. Check the network settings.' despite stable network conditions.

**DACXX-616**: Corrected the Helm show values not displaying all required properties, ensuring complete configuration visibility.

**DACXX-627**: Fixed issue where Cockpit wouldn't render when the "Pages" service is down, improving system resilience.

**DACXX-628**: Resolved the invalid date issue in the Action List log within Cockpit.

**DACXX-637**: Fixed problem that made it impossible to attach discussions on SmartGrid.

**DACXX-649**: Corrected issue where attributes were not selectable when selecting multiple entries.

**DACXX-679**: Fixed the tab panel widget not refreshing the page when parameter values change.

**DACXX-685**: Addressed issue where the mandatory parameter dialog did not auto-close in DAC 2024.1.0.

**DACXX-693**: Resolved issue where the 'terms of use' page in "Pages" was visible even when the Term of Use document was not uploaded in App Composer.

**DACXX-707**: Fixed issue where right-clicking on a crosstab widget generated multiple 404 errors.

**DACXX-713**: Addressed problem where users were not logged off immediately after a disconnect in Pages with IDMS on version 2024.1.0.

**DACXX-715**: Fixed the exception "Error - Cannot Read Properties of Null (Reading 'querySelector')".

**DACXX-770**: Resolved error during the creation of a scheduled action list.

**DACXX-779**: Fixed issue with incorrect MIME type application for SVG images.

**DACXX-790**: Resolved rendering issue in DataGrid when a field contains only the character "-".

**DACXX-800**: Fixed Smart Excel Import on Smart Grid that failed to upload data.

**DACXX-814**: Corrected inverted multilingual labels on the user profile page (EN displaying when IT was selected, and vice versa).

**DACXX-816**: Fixed issue where users could delete, disconnect, or disable their own account in the "Pages" service.

**DACXX-831**: Resolved FusionChart expired license issue.

**DACXX-874**: Implemented versioning control for static resources.

**DACXX-896**: Fixed issue with multilanguage labels not functioning correctly in the Plain Text widget after updating to Cherrim 2.

**DACXX-900**: Fixed exception that occurred during widget synchronization in a target environment for porting processes.

**D4C-10223**: Resolved issue with built-in parameters in filter parsing. Now, when executing a report with filters containing system parameters, these parameters must be properly valued in both the validation panel and during report execution to ensure successful validation.This behavior is applied wherever something can be written that ends up in the query, such as custom filters, direct filters, view filters, metrics, and security filters

**D4C-10228**: Fixed issue where it was not possible to schedule the action list on Mondays, ensuring full scheduling flexibility across all days of the week.

**D4C-10245**: Fixed exception that occurred when synchronizing widgets in a target environment, improving synchronization stability.
