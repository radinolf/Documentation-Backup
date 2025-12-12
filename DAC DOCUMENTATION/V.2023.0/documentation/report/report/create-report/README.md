# Create Report

The creation of a report involves the selection of levels, metrics, and possibly filters; once the report has been created, it can be customized using the Editing Report window.

When a report is open, a second toolbar is enabled, with rapid commands for some of the functions described above (see the figure below).

![](<../../../../.gitbook/assets/0 (19).png>)

The customization of report properties can take place, not only from the _Editing Report_ window, but also from the _Report Properties_ window which can be opened with the ![](<../../../../.gitbook/assets/1 (1).png>) Button.

Reports are saved in a catalog, with a folder system identical to the standards and the logics found in Windows, so that users are working with a familiar interface.

The publication of reports for DAC users takes place through the allocation of privileges both on individual reports and on folders. Published reports can be changed by DAC users, but, when saved, a copy of the published report will be created and placed in the user’s Favorites folder. This ensures that reports published by DAC can never be changed by DAC.

The report display provides a pop-up menu with commands that allow you to directly access the elements that make up the report, such as metrics, levels, totals, etc.

![](<../../../../.gitbook/assets/2 (26).png>)

Using the same pop-up menu, you can apply report functions, such as totals, or directly access the properties of the item under consideration.

The generic functions that apply are:

* _**Remove “\[level/metric name]”**_: remove the level or the metric
* _**Edit “\[level/metric name]”**_: The window opens of the dimensional (Step 2 of the wizard) or metric levels, to allow changes.

If the report is populated by queries, this item is disabled since the levels and the dimensions are not in the application, but exist only for the report.

* _**Enable/Disable span**_: enables/disables the grouping for the same row or column value
* _**Enable/Disable wrap**_: enables/disables the text wrapping, by row, column or header.
* _**Set alias/Remove alias**_ sets/removes the alias for the levels or metrics.

The _**Set alias**_ command is always active and lets you change the alias previously assigned

Example: **Edit Metric**

![](<../../../../.gitbook/assets/3 (29).png>)

_The image above shows how you can open the editing window of a single object in the report._

_A right-click with the mouse opens the metrics window, already positioned on the # of alerts: by clicking on the item: Edit metric "# of alerts ", you can enter the metrics page to make changes._

Reports are created and changed in the _**Editing**_ _**Report**_ window, which is accessed:

* To create,clicking on the button ![](<../../../../.gitbook/assets/image (113).png>)
* To change, select the button below, which is only activated for already open reports ![](<../../../../.gitbook/assets/image (941).png>)

<figure><img src="../../../../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

As shown in the figure above, the folders in the top left section allow you to choose metrics and filters, both direct and range, that are available on the application. Filters and metrics to associate with the report must have been created earlier, using the corresponding modules for the management of metrics, direct filters and range filters .

You can also define filters for exclusive use by the report, both on the elements of the report itself and on those of the application.

Metrics and filters are selected simply by double-clicking and are then reported in the _**Elements**_ box (top center).

![](<../../../../.gitbook/assets/7 (26).png>)

In _Type_ the type of metric is selected, whether first level, advanced or composite, then the (_Name_) is indicated, while in _Description_ the reference cube for the metric is indicated (for composite metrics all the cubes of the metrics involved in the formula are specified).

To change the order of display of the metrics, just click the up and down arrow buttons. To remove a metric from the report, double-click on the corresponding _Type_ field.

In the section at the bottom you’ll find the dimensional levels for the application grouped by cubes, dimensions and hierarchies. This helps users to choose dimensional levels consistent with the multicube analysis. The choice of a level, shared by two or more cubes, can be made on any cube even one that is different from that of the chosen metrics.

<figure><img src="../../../../.gitbook/assets/image (946).png" alt=""><figcaption></figcaption></figure>

Dimensional levels are inserted directly in the desired layout position, chosen from Page-by, rows or columns. The selection is made by dragging the level onto the desired cell; the level can then be moved from one cell to the other by dragging it to the new location. To delete a level from the report just drag it to the central selection area.

<figure><img src="../../../../.gitbook/assets/10 (24).png" alt=""><figcaption></figcaption></figure>

By right clicking the cells which represent the rows, columns or page-by, respectively, you can add 10-cell blocks.

Metrics must be grouped and connected to a single axis. For example, you cannot have one metric on a row and another one in a column.

The Metrics element ![](<../../../../.gitbook/assets/11 (13).png>) groups the metrics. These are initially placed in columns. Later they can be moved through drag & drop operations like those for dimensional levels.

The folders in the top center section provide access to **properties** that can be customized by users:

* the _**Properties**_ _folder_ contains the generic properties, subdivided by groups
* the _**Page**_-_**By**_ folder contains the properties related to the levels/ metrics positioned at the top of the report
* in the _**Drill-Through**_ folder, you can access the properties that define the links associated with the levels/metrics of the report
* in the _**Prompt**_ folder, you can define the prompt associated with the report (and displayed in DAC)
* the folder _**Chart**_ groups all the properties related to the formatting of the graphs.

On the right- side, there are command buttons for:

*   the execution of the report

    <figure><img src="../../../../.gitbook/assets/12 (14).png" alt=""><figcaption></figcaption></figure>
* the SQL code generated by the report, with or without formatting of SQL commands
* **validation** of the report structure (and not the query generated), to verify the existence of the elements introduced in the report (levels, metrics, and filters)
* the opening of another report (_**Open**_)
* saving the report (_**Save**_)
* saving a copy with a different name (_**Save**_ _**as**_)
* closing the dialog without making any changes (_**Cancel**_)

You can open or save the reports on the catalog.

**Note:** If a Report is opened which is already being edited by another user, it will be possible to use it but in read only mode, and saved with another name.

When the user accesses a report in read only mode, for the entire duration of the usage session he can save the report as new, without overwriting the existing report. To be able to have the writing rights, he must access the report only when it is not being edited by another user.
