# Report Indexing

DAC allows users to create indexes for reports carrying a high volume of information, which provides a quick and efficient way of processing data. The indexes are created in the table of the final datamart associated with the report and they are updated automatically every time you add filter criteria to the report relating to:

* Page-By
* User filters, only if applicable to the result of the report
* View filter

Indexes related to filter criteria are created in the course of the navigation of the report and even before this is executed. At every change of page-by or of data selection criteria, the system will then create an index, unless this can already be found inside the table. If the index for the columns in the report has already been created, the system will not create a new index, but it will use the one that already exists.

Indexing is done through the **indexingType** property (_Main_ group), where with:

* _\<no-index>_, default setting, indexing is disabled
* _\<Index-cache-only>_ indexes are created only for reports in cache. In this case, Indexes created on request by one user during navigation are made available to all the others
* _\<Index-_&#x61;lways> always indexes the report, whether in cache or not

Example: Report Indexing

![](<../../../.gitbook/assets/10 (5).png>)

_In the picture, before executing the report, we can see how the system automatically creates indexes for the corresponding levels in page by, that is, for product and month:_

_MONTH\_ID, PRODUCT\_ID._

_If you insert a view filter in the report: Business\_Unit =2_

_a new index will be created:_

_MONTH\_ID,PRODUCT\_ID,BUSINESS\_UNIT._
