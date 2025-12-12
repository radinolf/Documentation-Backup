# Social Spaces



The Social spaces Widget correspond to those used in DAC by the administrators of the social spaces.

In the Page Designer, it will be possible to use and configure them based on the properties. The property present in all social spaces widgets is:

* **Spaces-associated**

The categories are as follows:

| ![](<../../../.gitbook/assets/120 (3).png>)[Others](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Others)                                                                                                                                                              | ![](<../../../.gitbook/assets/121 (3).png>) [Users](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_User)         | ![](<../../../.gitbook/assets/122 (3).png>) [Contents](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Content)   | ![](<../../../.gitbook/assets/123 (2).png>) [Sub-Spaces](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Sub-Spaces) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| <p><img src="../../../.gitbook/assets/124 (2).png" alt=""> <a href="/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Signal">Signals</a></p><p><img src="../../../.gitbook/assets/125 (2).png" alt=""> <a href="/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Task_2">Tasks</a></p> | ![](<../../../.gitbook/assets/126 (2).png>) [Bookmarks](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Bookmark) | ![](<../../../.gitbook/assets/127 (2).png>) [Documents](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Document) |                                                                                                          |

### Content

The _Content List_ is the widget for generic content. All of the other content has properties that have already been assigned a value, so that they can be offered as pre-packaged items in the Web environment.

The specific properties of **Content View** are:

* _**content-association-type**_: criteria that need to have the following items:
  * _MOST-LIKED_, the most voted as liked
  * _MOST\_RECENT_, the most recent
  * _MOST\_VIEWED_, the most viewed
* _**content-types:**_ select the content to be published, selected from the Documents, Blog Posts, and Signals

![](<../../../.gitbook/assets/128 (2).png>)

The _Content View_ allows you to view a Document or Blog post in an expanded manner.

The specific properties of **Content View** are:

* _**content-association-type:**_ criteria with which the document or blog post was selected:
  * _MOST-LIKED_, the most voted as liked
  * _MOST\_RECENT_, the most recent
  * _MOST\_VIEWED_, the most viewed
  * _SELECTED, to select a specific document or blog post. This property enables:_
    * _content-selected_: content to be published, selected from a list of all of the documents or blog posts (based on that specified in the successive properties)
* _**content-types:**_ type of content to be published, selected from the Documents and Blog Posts
* _**Template-style**_: publication style, selected from the preview or editing

The other widgets are:

* **List of latest Contents** displays the list of the latest content

Equivalent to a Content List configured with:

*
  * _**content-association-TYPE**_ _MOST\_ RECENT_
* **List of most viewed content** displays the list of the most viewed content

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_VIEWED_
* **List of popular contents**, displays the list of the most popular content

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_

### Document

All the widgets related to documents can be customized b&#x79;_:_

* **List of most popular content** displays the list of the most popular signals

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_
  * _**content-types**_: Document
* **List of latest Contents** displays the list of the latest documents

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ RECENT_
  * _**content-types**_: Document
* **List of most viewed documents** displays the list of the most viewed documents

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_VIEWED_
  * _**content-types**_: Document
* **Most popular documents** displays the most popular document

Equivalent to a _Content List_ configured with:

*   _**content-association-TYPE**_ _MOST\_ LIKED_

    _**content-types**_: Document
* **Latest documents** displays the latest documents

Equivalent to a _Content List_ configured with:

*   _**content-association-TYPE**_ _MOST\_ RECENT_

    _**content-types**_: Document
* **Most viewed documents** displays the most viewed document

Equivalent to a _Content List_ configured with:

*   _**content-association-TYPE**_ _MOST\_VIEWED_

    _**content-types**_: Document
* **DOCUMENT** displays a specific document

Equivalent to a _Content List_ configured with:

* _**content-association-TYPE**_ _SELECTED_
* _**content-types**_: Document

This component has the following properties enabled:

*
  * _**content-selected**_: document to be published
  * _**Template-style**_: publication style, selected from the preview or editing

### Bookmark

The _All Bookmarks_ widget is the generic way of collecting bookmarks sent to the associated spaces; all of the others have a property with a value that has already been assigned in order for the items to be filtered based on the object type.

The properties of the **All bookmarks** are:

* _**object-types:**_ type of objects to which the bookmarks are assigned, including:
  * _AREA\_GROUP_, bookmarks assigned to the social groups
  * _AREA\_INITIATIVE_, bookmarks assigned to the initiatives
  * _AREA\_NORMAL_, bookmarks assigned to the areas
  * _BLOG_, bookmarks assigned to the blog posts
  * _DOCUMENT_, bookmarks assigned to the documents
  * _TASK_, bookmarks assigned to the _tasks_
  * _REPORT_, bookmarks assigned to the _reports_
  * _USER_, bookmarks assigned to the users
  * _DASHBOARD_, bookmarks assigned to the page

The other widgets are:

* **Documents as bookmarks** displays the list of bookmarks assigned to the reports

Equivalent to a _Tasks List_ configured with:

*
  * _**object-types:**_ _DOCUMENT_
* **Documents as bookmarks** displays the list of bookmarks assigned to the pages

Equivalent to a _Tasks List_ configured with:

* _**object-types:**_ _Dashboard)_
* **Spaces as bookmarks** displays the list of bookmarks assigned to the social spaces, for any type

Equivalent to a _Tasks List_ configured with:

*
  * _**object-types:**_ _AREA\_GROUP, AREA\_INITIATIVE, AREA\_NORMAL_
* **Documents as bookmarks** displays the list of bookmarks assigned to the documents

Equivalent to a _Tasks List_ configured with:

* _**object-types:**_ _DOCUMENT_
* **Blog posts as bookmarks** displays the list of bookmarks assigned to the Blog posts

Equivalent to a _Tasks List_ configured with:

* _**object-types:**_ Blog

### Task

The specific properties of the **TASK List** are the following:

* _**statuses**_, task status:
  * _NEW_, newly created tasks
  * _ACCEPTED_, accepted tasks
  * _CLOSED_, closed tasks
* _**group-by**_, type of grouping of the listed tasks, with respect to:
  * _CATEGORY_
  * _ASSIGNEE_
  * _PRIORITY_
  * _STATUS_
  * _AREA,_ social space
  * _SCHEDULE\_DATE_
* _**assignee-type**_, whether or not the assignee has been defined:
  * _ASSIGNEE\_STATUS\_DEFINED_
  * _ASSIGNEE\_STATUS\_NOT\_DEFINED_
  * _ASSIGNEE\_STATUS\_ALL_, all tasks independent of whether or not an assignee has been assigned
* _**additional-info**_, additional information to be entered in the tasks in the list:
  * _CATEGORY_
  * _ASSIGNEE_
  * _STATUS_
  * _Area,_ social space
  * _SCHEDULE\_DATE_, schedule date
  * _DUE\_DATE_, due date

The other widgets are

* **All tasks** displays the list of active tasks, ordered by priority and grouped by schedule date

Equivalent to a _Tasks List_ configured with:

*
  * _statuses NEW, ACCEPTED_
  * _group-by SCHEDULE\_DATE_
  * _order-by PRIORITY_
* **Tasks assigned by category** displays the list of tasks grouped by category

Equivalent to a _Tasks List_ configured with:

*
  * _group-by CATEGORY_
* **Task assigned by person** displays the list of tasks grouped by assignee

Equivalent to a _Tasks List_ configured with:

*
  * _group-by ASSIGNEE_
* **Tasks assigned by category** displays the list of tasks grouped by priority

Equivalent to a _Tasks List_ configured with:

*
  * _group-by PRIORITY_
* **Tasks assigned by schedule date** displays the list of tasks grouped by schedule date

Equivalent to a _Tasks List_ configured with:

*
  * _group-by SCHEDULE\_DATE_
* **Unassigned task** displays the list of tasks without assigning them

Equivalent to a _Tasks List_ configured with:

*
  * _assignee-type ASSIGNEE\_STATUS\_NOT\_DEFINED_

### Signal

All the widgets related to the signals are customized by the following _Content list_:

* **List of most popular Signals** displays the list of the most popular signals

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_
  * _**content-types:**_: Signal
* **List of latest Blog Posts** displays the list of the most recent posts

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ RECENT_
  * _**content-types:**_: Signal
* **List of Most viewed blogs posts** displays the list of the most viewed posts

Equivalent to a _Content List_ configured with:

*
  * _**content-association-TYPE**_ _MOST\_ LIKED_
  * _**content-types:**_: Signal

### User

The widgets for **Associated members** displays the list of associated members There are not any specific properties.

### Sub-Spaces

The other widgets are:

* **The sub-areas** displays the list of the sub-spaces for the area type

Equivalent to a _Tasks List_ configured with:

*
  * _**Sub-Spaces-types:**_ _SOCIAL\_AREA_
* **The sub-areas** displays the list of the sub-spaces for the group type

Equivalent to a _Tasks List_ configured with:

*
  * _**Sub-Spaces-types:**_ _SOCIAL\_GROUP_
* **The sub-areas** displays the list of the sub-spaces for the area type

Equivalent to a _Tasks List_ configured with:

*
  * _**Sub-Spaces-types:**_ _SOCIAL\_INITIATIVES_

### Others

_Activity Streams_ is the widget which displays the list of activities made by the users in the social space.

The specific properties for this component are:

* **Discussion type associated with the** type of discussions that need to be collected in the activity stream

A pop-up list of the available types: signals, documents, blog posts, tasks, and discussions opened directly in the activity stream (standard)

_Selected Page_ is the widget which displays a page in the social space.

The specific properties for this component are:

* **Application**-**selected**:
* **page-selected:** selection of the page to be displayed in the social space
