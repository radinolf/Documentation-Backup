# Enhancement

**Component Refactoring**\
Multiple tickets addressed a major refactor of core components to improve performance, maintainability, and consistency.

* DACXX-834: A correlation ID has been introduced to make it easier to trace and identify log entries belonging to the same request, even when the request involves multiple microservices.
* DACXX-1932:  A new loading management system has been introduced, designed to handle both full-page loading and the loading of individual widgets.
* DACXX-2130 Improvements have been made to the dialog used for managing exceptions, enhancing both its clarity and usability.

At the bottom, a list of the tickets that have been processed is displayed:

(DACXX-805,DACXX-835,DACXX-838,DACXX-839,DACXX-1025,DACXX-1026,DACXX-1027,DACXX-1028,DACXX-1029DACXX-1030,DACXX-1031,DACXX-1032,DACXX-1127, DACXX-1128,DACXX-1129,DACXX-1495,DACXX-1496,DACXX-1497,DACXX-1858,DACXX-1859,DACXX-1860,DACXX-1861,DACXX-1862,DACXX-1863,DACXX-1864,DACXX-1865,DACXX-1866,DACXX-1867,DACXX-1868,DACXX-1869,DACXX-1948,DACXX-1986,DACXX-1987,DACXX-1990,DACXX-2011,DACXX-1033,DACXX-1034,DACXX-2063,DACXX-2095,DACXX-2096,DACXX-2097,DACXX-2099,DACXX-2100,DACXX-2101,DACXX-2113,DACXX-2133,DACXX-2062,DACXX-2151,DACXX-2153 ,DACXX-1843,DACXX-1874 )

**Widgets**

&#x20;**D4C-10625- Migrate loading handling for TabSelector and TabPanel widgets**

With this fix, the old loading spinner has been replaced by the new page loading indicator on the tab panel.
