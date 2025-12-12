# Execution logs

It is possible to choose whether execution of a report should be tracked on the table of Log of the system (table FT\_OBJECT\_EXECUTION found in the Data Model). We choose how execution should be tracked by selecting the _**log**_-_**execution**_ property (_Main_ group).

The values that can be set are:

* _**\<log disabled**_>: no report execution will be tracked.
* _**\<out of cache only>:**_ only the execution of reports not in cache will be tracked. This allows users to highlight only high-cost executions.
* _**\<every execution>:**_ the execution of all reports, both those accessing the cache and those that do not, will be tracked.

The properties can be set at application level, so that a default is applied to all reports in the application.
