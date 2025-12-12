# Display Mode

DAC allows users to display reports in one of the following modes:

* Table&#x20;
* Graph&#x20;
* Document (with both graph and table formats)

The display can be defined both with the report function bar, found on the main screen, and from the specific properties of the report.

<figure><img src="../../../.gitbook/assets/image (1674).png" alt=""><figcaption></figcaption></figure>

In the top section there are three buttons enabling the display of the report in the different modes (Table, Graph, Document).

You can browse the report pages using the page buttons, indicated by arrows. The arrow buttons, on the left, just above the report, allow two different types of shift: horizontal shift (of columns) and vertical shift (of rows) The single arrow allows you move one page forward or backward; the double arrow allows you to access the first or last page.

<figure><img src="../../../.gitbook/assets/image (1448).png" alt=""><figcaption></figcaption></figure>

On the right of the Rows and Cols labels, respectively, the row total and the column total for the displayed report are indicated in round brackets. You can set the number of rows and columns displayed on the screen by selecting a value from the drop-down menu next to the two labels.

![](<../../../.gitbook/assets/22 (10).png>)

![](<../../../.gitbook/assets/image (1669).png>)The button at the top on the right side closes the main window from the layout of the last executed report.

On the bar, at the bottom of the report window, you’ll find information on:

* name of user connected in DAC (_**User**_)
* the server to which the user is connected (_**Connection**_)
* the application (_**Application**_)
* the report name (_**Report**_)

The display mode, chosen during editing, requires setting the **publish** **Type** property for the report (**Main** group **Properties** section), where the three available display formats are listed and can be selected.

The _Crosstab_ value, the system default, allows users to display the executed report with a table structure.

The _Graph_ value, set by the user, allows you to display the executed report with a graph structure.

The _Document_ value, set by the user, allows users to display the executed report with both structures, table and graph, on the same page.

#### Table Visualization

The _**Table**_ format allows you to display all dimensions, metrics, and any page-by set during the report editing phase in a table structure.

<figure><img src="../../../.gitbook/assets/image (1461).png" alt=""><figcaption></figcaption></figure>

The headers indicated on the first row refer to the levels (or metrics) on the rows.

If the levels are grouped in drill, the header will only include the parent level.

<figure><img src="../../../.gitbook/assets/image (1730).png" alt=""><figcaption></figcaption></figure>

The headers related to levels or metrics placed in columns are displayed only if more than one element is present: the most detailed element always remains without a header.

<figure><img src="../../../.gitbook/assets/image (1221).png" alt=""><figcaption></figcaption></figure>

In the report in the figure two elements have been placed in the column: YEAR level and the axis of the metrics. The detailed element (in this case the axis of the metrics) does not have a header, while the one for the YEAR level is visible.

These settings placed in rows and columns may be customized in DAC by using the formatting bar, which is described in the next paragraph.

#### Graph and Document View

By viewing the report in **graphical** mode, you can visualize the data in a graph format.

The _**Document**_ format allows you to display the report in both formats on the same page: graph (at the top), table (at the bottom).&#x20;

{% hint style="info" %}
The display of the report in graphical mode is available only from web. If you want to view the report in this mode you will need to save it and access the run time and view them in the Reports section.
{% endhint %}

&#x20;

<figure><img src="../../../.gitbook/assets/image (1352).png" alt=""><figcaption></figcaption></figure>
