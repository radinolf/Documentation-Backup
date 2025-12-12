# Crosstab Layout

### Introduction <a href="#toc498423773" id="toc498423773"></a>

Through the formatting bar, you can change the style of the elements of the report, both at single cell level and by type of element (such as the dimensional levels); a particular metric; the total rows, etc.

The formatting bar appears as in the figure below.

![](<../../../.gitbook/assets/0 (1)>)

To enable formatting capabilities, you must select one of the report elements from the drop-down list. Formatting disabled is the default. Selecting any element enables the commands, indicated in the following figure.

**Note**_**:**_ The formatting bar is disabled on Tablet devices.

![](<../../../.gitbook/assets/1 (2)>)

Selecting the box ![](../../../.gitbook/assets/2) (see figure) applies the changes you made, and disables the formatting bar again. To make the changes effective, just save the report.

**Note:** The type of Font is set by the administrator and it is the same for the whole web environment.

The items that can be formatted are:

* Single **cells** (_Cells_), **rows** (_Row dimensions_), **columns** (_Column dimensions_), **headers** of the levels (_Headers_), **totals** (_Totals_)
* **Values of the metrics** (_body metrics_); see example in the next paragraph
* **Header of the metrics** of the report (\[_name of the metrics]_)
* **Values of the levels** of the report (\[_name of the levels]_)

The formatting of cells may also be applied to:

* _Cell groups:_ you can select groups of cells of a report by holding down the CTRL key on the keyboard and left clicking on the desired cells.
* _Contiguous cells_: contiguous cells may be selected in two ways: by clicking on the first and dragging the mouse on those cells to be selected; or, by selecting the first and last cell of the interval and keeping the SHIFT key pressed on the keyboard.

You can **cancel** the selection **of** one or more cells of a report by clicking with the left button of the mouse in the area outside the report.

![](<../../../.gitbook/assets/3 (6)>)

### Table Layout Form <a href="#toc34301093" id="toc34301093"></a>

The appearance of the layout may be customized through the functions available in the _Visualization_ section of the toolbar (or pop-up menu).

![](<../../../.gitbook/assets/4 (2)>)

The functions are as follows:

* lock of the rows and the columns
* span on rows/columns
* _**text wrapping**_ on rows/columns: enabled from the **Rows wrap** item, for the rows, and **Cols wrap**, for the columns
* to show the name of the levels as well as the descriptive value.

### **Row/Column Lock**

The row/column lock scrolls through the report through the scroll-bar, so the headers of the report always remain visible, both for the rows and for the columns.

Example: Enabling Row Lock

![](<../../../.gitbook/assets/5 (6)>)

_On the report the row lock was activated. The report is entered inside a window, where the scroll-bars are enabled. Horizontal scrolling leaves the levels of the rows locked: the Business Unit is always visible, while the columns on the months scroll horizontally._

Example: Enabling Column Lock

![](<../../../.gitbook/assets/6 (6)>)

_On the report the row column was activated. The report is entered inside a window, where the scrollbars are enabled. Vertical scrolling leaves the levels of the rows locked: the Business Unit is always visible, while the columns on the years and months scroll vertically._

### **Row/Column Span**

The _Span_ function consists of grouping the items of the dimensional levels that have the same value in a single box. By default, the Span function is enabled on the rows and columns. If disabled (by simply selecting the corresponding buttons), you get a report where the same value is repeated, for all the rows/columns of the report.

This format is particularly suitable for exports as an Excel file.

Example: Disabling Span on Rows

![](../../../.gitbook/assets/7)

_In the sample report, the span on the rows was disabled, obtaining the visualization shown._

### **Show Level Name**

The _Show parent levels_ function shows the name of the dimensional level, next to its value (it is disabled by default).

The function is enabled by selecting the **Show parent levels** item from the toolbar (_Visualization_ section).

This function is useful in cases where the name of the levels is hidden, such as when it is in a column, or grouped for drill operations. In these cases, the header only appears for the more aggregating level.

Example: Show Parent Levels

![](<../../../.gitbook/assets/8 (2)>)

_In a report with aggregated levels for the drill, the Show parent levels function was enabled. By running a drill, for each level the name is indicated between square brackets, before the value of the same level._

### Tutorial

{% embed url="https://bitbucket.org/decisyon/manual/downloads/CrosstabLayout.mp4" %}

