# SQL Interactions

Reports in DAC accept the SQL statements to be run before and/or after execution of the report itself.

These properties are in the SQL group:

* _**sql-pre-execution**_ to define the statement to execute BEFORE the report. Multiple statements are also accepted (separated by '; ')
* _**sql-post-execution**_ to define the statement to execute AFTER the report. Multiple statements are also accepted (separated by '; '). In this statement, you can use the `%DATAMART_TABLE%` variable associated with the datamart generated for the report.

In example, you could execute the following SQL statement to modify the date format of the data displayed in the datamart:

```sql
ALTER SESSION SET nls-format = 'yyyy-mm-dd'; 
ALTER TABLE %DATAMART_TABLE%;
```

