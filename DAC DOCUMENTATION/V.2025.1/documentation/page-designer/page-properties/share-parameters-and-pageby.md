# Share parameters and pageby

## Share Page-By

The page-level properties on Page-by are defined in the _**Shared**_ _**page-by**_ group. In this section, two properties can be set that are always enabled by default:

* **apply-shared-page-by:** Enable receipt of the values for the Page-by shared with the other pages\
  **modify-shared-page-by:** Enable changing the values for the page-by shared with other page

Below is an example showing the behavior of both properties.

![](<../../../.gitbook/assets/image (911).png>)

_In the example mentioned above there are three Pages._

* _Page "A": the apply-shared-page-by and modify-shared-page-by properties are set._
* _Page "B": the apply-shared-page-by property is set._
* _Page "C": the modify-shared-page-by property is set._

_If you select a parameter from Page "A", it will only be displayed in Page "B" because the apply-shared-page-by property is enabled._

_It will not be displayed in Page "C" because the modify-shared-page-by property is enabled. If changes are made to Page page "C", they will affect Page pages "A" and "B" because the apply-shared-page-by property is enabled._

In order for parameters to be shared between Pages, you must define the global page-bys at the application level. (see Properties on the Pages, page-by sharing section).

## **Passing Parameters among Several Pages**

It is particularly useful to make Pages interact with each other, in order to transmit the analyses from one to another, reporting the choices of the filters on all the pages of interest.

There are different interaction modes among the Pages:

* shared parameters and page-bys
* Page open in DS

### **Shared Parameters and Page-bys**

It is possible “to share” the parameters defined in a Page, to all the other Pages of the application, so that the choices made in Pages can affect all those which use the same parameter.

Also for page-bys you can activate sharing, so that the user has the same choices repeated on every Page. For example if a particular year is chosen in a Page, all the Pages will show the same year in the page-by levels.

The sharing of parameters and page-bys is applied at application property level (see _Parameters shared among several Pages_ section).

It is possible to "update" the page-bys with respect to the selections made in a "SELECT" or "CHECKLIST" object. By enabling the property of the **align-page-by-to-params Page** pag&#x65;**,** the following type of behavior is obtained:

·        a "SELECT" or "CHECKLIST" object defined at a specific level and named with the same name as the corresponding dimensional level

·        a "CROSSTAB" object, which has the same dimensional level defined in "SELECT", placed in page-by

&#x20;by selecting a level value in "SELECT", the same will be automatically displayed in the report of the same Page page.

### Property of Page (align-page-by-to-params)



&#x20;**Example**

_One "Select" object and one "Crosstab" object are on the following Page. Note how by selecting any value in the "Select" object (in the above example "2004"), the same will be displayed in the report of the same Page page. The align-page-by-to-params property then allows aligning the parameters of a "Select" or "Checklist" object, to the page-bys (with the same name) of the reports on the same page._

<br>

### **Passing Parameters Through Page Open in DS**

In the case of Drill-through towards another Page page, the parameters on the latter can be used both of the calling report and of the Page containing the report (it therefore becomes the calling Page).

Using the property:

* _**apply-dt-auto-filters**_ (_Filter_ group)

The automatic filters are applied originating from the drill-through in which the "apply-sel-a&#x73;_**-filter" option is enabled**_”.
