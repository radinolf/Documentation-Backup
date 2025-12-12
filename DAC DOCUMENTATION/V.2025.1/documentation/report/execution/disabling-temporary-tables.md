# Disabling Temporary Tables

For reports that do not require multi-step execution, the use of temporary tables can be disabled:

* _**create-temp-table**_ (_Main_ group) if unchecked, disables the use of temporary tables for the report (disabled by default)

In these cases, the report result not will be saved in the temporary table (table of type FX…) and cache use is disabled.

This property is ignored if the report includes the execution of more than one query (multi-step).

Reports executed in this mode will display in the levels in page-by all the values found in the level registry.For example, if a report has produced results for only three products, all the products found in registry will be listed in page-by anyway.
