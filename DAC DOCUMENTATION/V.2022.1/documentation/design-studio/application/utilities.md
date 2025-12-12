# Utilities

You manage objects created in the application (Cubes, Dimensions, Metrics, reports, alerts, etc.) in the window opened using the _**Application>> Utilities>>Objects explores**_ menu item or with the last button on the toolbar.

## Object Explores&#x20;

![](<../../../.gitbook/assets/image (94).png>)

The window lists all the objects in the application and indicates the following for each of them (in order):

* Display name
* Type of object (report, Metric, Filter, ...)
* User who last modified the object
* Date of the last modification
* Date of the last execution

The system also displays the following details, when _Show detailed information is checked_:

* User who created the object
* Creation date
* Object ID (for Cubes, this coincides with the name of the Fact Table)
* Object container (for Metrics, this is the Cube, while it is the Dimension for levels)

Use the ![](<../../../.gitbook/assets/1 (12).png>) button to update the above-listed information.

All the objects created in the application may be exported in the CSV format by selecting the ![](<../../../.gitbook/assets/2 (1).png>) button.

![](<../../../.gitbook/assets/3 (3).png>)

By **Double-clicking** the object the corresponding management window is opened in modify mode.

![](<../../../.gitbook/assets/image (92).png>)

Each object listed features a pop-up menu for operations involving modifying (the same as double-clicking), deleting the object and displaying dependencies. Dependencies can also be displayed in the bottom section of the window.

Different object search methods are also available.

### Object Deletion

You can delete an object directly from the object by selecting it and opening the pop-up menu.

When you click on delete, the system checks for the existence of objects that use the one to be deleted.

You are informed if any objects depend on it, and can open the dependencies window directly from the _alert_ message. This window shows all objects that use the one being deleted.

![](<../../../.gitbook/assets/image (98).png>)

### Object Search Mode

You can search for objects by using the simple text search mode for the display name of the object.

As you enter the characters in the _**Search**_ field, the search results are simultaneously shown in a list of objects beginning with the text entered.

We recommend using the special character (\*) to facilitate partial searches.

![](<../../../.gitbook/assets/6 (3).png>)

Another available search method is by each type of object feature (name, type, creation date, etc.). Right-click on the column of the list of objects to open the list of values in the column. The list can also be selected and contains both a value search field and _All_ for selecting/deselecting all values.

Searching for objects

![](<../../../.gitbook/assets/image (180).png>)

When you check _**View unused objects**_, you can apply a Filter so that only objects are displayed with no type of dependency on other objects (i.e. not used in other objects). For example, this type of search will allow you to quickly display all Metrics not used. When you select all Metrics not used and combine this with the delete function, you can quickly clean up any objects you feel are unnecessary.

### View Unreferenced Objects

![](<../../../.gitbook/assets/image (97).png>)

_In the example above, first the Filter was applied on the Advanced Metric type and then display unused elements was checked._

When _**Shows detailed information**_ is checked, you can obtain additional information:

* &#x20;_**created by**_ the name of the user who created the object
* _**creation date**_ the date when the object was created
* _**ID**_ the key field of the object
* _**container**_ the container of the object

### Object Dependencies (Using and Used By)

The bottom section of the window shows the dependencies of each object selected, including those _used_ (i.e. the objects using the selected one), and those _used by_ (i.e. the objects used by the selected one). Then two examples are shown.

* The first one is for the _used_ dependencies of a Metric, i.e. reports or Composite Metrics that use it.

Used Dependencies of a Metric

![](<../../../.gitbook/assets/image (110).png>)

* The second one is for the used by dependencies of a report, i.e. all objects it uses (Filters, Metrics, levels).

Used by Dependencies of a Metric

![](<../../../.gitbook/assets/image (104).png>)

‌\


## **Validating DAC objects**

Validation is an automatic process which makes it possible to verify that the metadata underlying the application loaded and used for report definition are correct, and to ensure that tables and links exist.

After accessing the **Application>>Utilities>>Validate** menu, it is possible to:

* validate all application objects (**Validate All…**)
* validate individual objects categories (**Validate cubes, Validate dimensions, Validate metrics, Validate** filters)
* verify the SQL syntax underlying the application reports (Test **model reports**)
* execute the report using the cache or not (**Execute reports (cache)** or **Execute reports (full**)

During the execution of the validation processes, the system shows a window which lists the objects being validated (with a green check for those successfully validated and a red cross for the invalid ones)

![](<../../../.gitbook/assets/image (105).png>)

If an error occurs, the reason for the failures is registered and displayed by the **log** folder, while the validation process continues on the remaining objects. In addition, you can interrupt the execution of the validation (**Abort** button) and export the log of the validations up to that point (**Export** button).

A progress bar shows the process execution in real time.
