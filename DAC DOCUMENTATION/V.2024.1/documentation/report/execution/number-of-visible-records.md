# Number of Visible Records

Reports in DAC show a maximum number of rows to avoid excessive data loads, which would affect performance.

This limit is set in

* bodyMaxElements (Body _group_) to set the maximum number of elements to display in the report, independently from those extracted (by default it is set to 3,000, the maximum that can be set is 30,000)

If you want the report to contain all data, even in cases where it exceeds the maximum of 30,000, you activate the properties:

* db-paging (large results) (_Body_ group): which enables the paging of the database on the report result, instead of loading the entire data to memory.

The feature considerably speeds up the opening of reports with large amounts of data: only a subset of data from the result is loaded to memory.

In page exchange operations, if necessary, the system loads other result data, by using database functions that allow you to do this.

**Paging** enabled via this property is only compatible with the following databases: Oracle, Sql Server, MySQL.
