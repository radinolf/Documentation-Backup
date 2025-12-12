# Fix Defect

This section lists bugs that have been resolved. Each fix improves the stability and reliability of the platform.

**DACXX-2037 – Incorrect Widget Spacing/Sizing on Page Load When Mandatory Parameters Are Present**\
Added a timeout to correctly calculate the widget container fill when flex behavior is present.

**DACXX-2049 – Filtered State from a Widget Persists When Reopening the Same Page**\
Fixed the Data Presentation widget refresh so it now considers all associated reports, allowing the Kanban to refresh correctly.

**DACXX-2068 – Modifying the User Attributes Generates an Error**\
Resolved a caching issue that prevented overwriting existing user attribute values.

**DACXX-2085 – Widget Not Rendered on Pages**\
Fixed the issue preventing widgets from displaying in Pages and causing canceled calls in the browser console.

**DACXX-2086 – Multi Language Label Not Translated**\
Restored proper translation of multilingual labels in the Pages application.

**DACXX-2131 – Talend Job Execution Restricted Only to ADMN Licensed Users on Pages**\
Fixed the behavior that limited Talend Job execution to ADMN-licensed users. Any user with page access can now execute the job.

**DACXX-2142 – Discussions Are Not Updated When Another User Modifies Them**\
Enabled real-time updates in the discussion panel to display changes and new messages without refreshing the page.

**DACXX-2145 – Calendar Not Opening for TextField Widget with ObjectInputType = DATE**\
Restored the calendar opening when the field’s ObjectInputType is set to DATE.

**DACXX-2146 – Info Icon Tooltip Does Not Show Widget Description and Throws Console Error**\
Fixed the tooltip behavior for the info icon so the widget description is now displayed correctly without console errors.



