---
description: >-
  It is possible to change the display formats and the formatting details for a
  tabular report to meet the user’s needs and preferences.
---

# Formatting

The report formatting can be set:

* from [the formatting toolbar](table-layout.md#formatting-toolbar),
* from [the specific report properties](table-layout.md#specific-formatting-properties).

If a report is exported in PDF and EXCEL format, the applied formatting will be maintained.

It is possible to modify the wiDSh of the columns and the height of the rows in the report, by simply dragging the row/column to the desired position. The height and wiDSh formatting set is preserved when printing or exporting. In the report, rows or columns that were changed are indicated by a different color.

![](<../../../.gitbook/assets/0 (8).png>)

Double-clicking on the row or column that has been resized returns you to the initial default position.

It is possible to hide rows or columns by putting the wiDSh to zero: this way, they will no longer be visible from the DAC.

Clicking on the row header (numbering) opens a menu to set the height of a single row (_**Row**_ _**height**_), or the default height of all the rows in the report (_**Default**_ _**height**_).

![](<../../../.gitbook/assets/1 (12).png>)

By contrast, for columns you can only set the wiDSh of a single column (therefore, the default wiDSh set by the browser is absent, by adjusting it with respect to the dimensions of the window).

You can open the _**Column wiDSh**_ menu by clicking on the heading of the column you want to size.

![](<../../../.gitbook/assets/image (1125).png>)

## Formatting Toolbar

You can use the formatting toolbar to set the styles available in instant mode (i.e. without setting them from the associated properties of the report).

![](<../../../.gitbook/assets/3 (28).png>)

As indicated in the figure above, the style configurations available are:

* The formatting of fonts (background, color, style and size);

**Note: the Font Family of the font is set at Tools level** _(**font-family**_ property _in Tools properties, Web section, Appearance group)._

_Remember that the underlined style is not visible on DAC, but only on DAC._

* Alignment, border and wrap text

Note: -_Cells with text wrap option have the_ ![](<../../../.gitbook/assets/4 (1).png>) _Button. You can remove this option by first selecting the cell and then clicking the wrap text button._![](<../../../.gitbook/assets/5 (23).png>)_._

In _**Formatting**_ you can select the elements to format by choosing one of the following options:

* Individual cells (<_Cells>),_ rows (<_Row dimensions>),_ columns (<_Column dimensions>),_ headers (<_Headers>),_ totals _(\<Totals>)_)
* Single metrics or dimensional levels present in the report
* Cells that contain the values of the metrics (<_body metrics>)_

When _**Formatting**_ is _disabled_ you cannot format report elements.

Example: Formatting a Report from the Formatting Toolbar

![](<../../../.gitbook/assets/6 (25).png>)

The paragraphs below show other examples with cases other than those presented in the figure above.

Example of Formatting Totals

![](<../../../.gitbook/assets/7 (24).png>)

_From the Formatting menu select the Totals item, to enable the formatting of the totals present in the report_

_selecting one of the types of formatting available is applied to the totals, both cumulative (in the example) and level._

_If another level is inserted, the corresponding total item inherits the chosen formatting._

Example of Formatting \<Body metrics>

![](<../../../.gitbook/assets/8 (1).png>)

_The item \<Body metrics> in the Formatting menu enables the formatting of the values of the metrics (in this example we chose a blue color, instead of the default white)._

## Specific Formatting Properties

From the editing window of the report or the properties window, you can customize the formatting of the tabular form of the report:

* On the [style of the report](table-layout.md#report-style-object-style-group)
* On the [body of the report](table-layout.md#report-body-bodygroup)
* On the [columns](table-layout.md#table-columns-columns-group)
* On the [rows](table-layout.md#table-rows-row-group)
* On the [header](table-layout.md#header-header-group)
* On the [totals](table-layout.md#table-totals-totals-group)
* On the [title](table-layout.md#title-report-title-report-group)

The formatting can be set for the single report or at model level, starting from the application properties (see _chap. Model properties_).

The ![](<../../../.gitbook/assets/9 (10).png>) symbol indicates that the property has been set in _override_. To change them, just open the application properties and deselect override .

### Report Style (Object Style Group)

* _**col-number**_ number of columns displayed per page (from 1 to 30, 8 by default)
* _**row-number**_ number of rows displayed per page (from 3 to 200, 50 by default)
* _**fitToPage**_ readaptation of the wiDSh of the report to the wiDSh of the window of the browser in DAC. Disabled by default, and the report has a wiDSh equal to 60% of the one of the browser. The report will not be re-adjusted if lock rows and columns is enabled;
* _**show-drill-down**_ enables the drill function

**Note:** _When this function is enabled_ **on the graphs**_, even if there are no elements in drill in the graph, the system reloads the graph, as if a drill operation were performed, representing the previous graph._

* _**show-row-headers**_ enables the header of the rows
* _**show-col-headers**_ enables the header of the columns
* _**show-page-scrollers**_ enables the report scrollers:
* _\<rows-_&#x6F;nly> at row level
* _\<cols-_ only> at column level
* _\<both>_ at rows and columns level
* _\<none>_ scroll not enabled

If this property has a different value from \<none> it enables:

* **page-scrollers-align** specifies the position of the paging bar compared to the body of the report. The permitted values are: _\<Center> , \<Right> and \<Left>_ (_see figure below_)

![](../../../.gitbook/assets/10.png)

* _**show-toolbar**_ enables the table formatting bar of the report (_see_ _figure below_)

![](<../../../.gitbook/assets/11 (23).png>)

These properties are only displayed by the DAC (except for _**col-number**_ and _**row-number**_)

### Report Body (Bodygroup)

The properties of the Body group relating to report formatting are:

* _**wrapBody**_ to enable text wrapping in the cell content (visible ONLY in DAC)
* _**inherit-dimension-cell-format**_ to propagate the formatting of a cell to all child elements. See example of cell formattin&#x67;_**.**_
* _**drillColVar**_ for the color grading to apply to the children cells, according to the background color of the parent cell (default 1. 5, accepted values from -200 to 200).

**Example: Property “drillColVar”**

![](<../../../.gitbook/assets/12 (3).png>)

_The figure shows the results of setting the property drillColVar._

_The report elements are grouped by level; when a drill to display the sublevels is executed, a color is set by default. In this example, we have set a bluish color for negative values (-50)._

* _**bodyWrap**_ to enable text wrapping in the cell content (visible ONLY in DAC)
* _**bodyBackground:**_ sets the background color of the body
* _**bodyForeground**_: sets the font color used by the body
* _**bodyFontSize:**_ sets the size of the font used in the body
* _**bodyBolsd:**_ specifies the bold style in the text used in the body
* **bodyItalic:** specifies the italics style of the font used in the body
* **bodyUnderlined:** specifies the underlined style of the font used in the body
* **bodyTextAlign:** sets the alignment of text (Left/right/Center) in the body
* **bodyMaxElements:** sets the maximum number of items to be displayed in the report in relation to the selection made for data extraction
* **db-paging (large results):** If enabled, it carries out the paging of the report result using database functionality instead of loading the entire data to memory. The property should only be active where the body of the report is large with tens of thousands of records. As regards the value of the property "bodyMaxElements", if enabled, it is preferred that there are 2-3000 records, to speed up the loading of the first page of the report. This property is compatible with the following databases:
  * Oracle
  * SQL server
  * DB2
  * As400
  * MySQL
  * PostgreSQL

If the report is defined on a Database and/or Data source different from those listed, the system will display an error message.

Example: With the Property "inherit-dimension-cell-format"

![](<../../../.gitbook/assets/13 (14).png>)

_In this example we have enabled the property_ _inherit-dimension-cell-format which extends the chosen formats to all children cells (in this case cells on the same row), including totals, if present._

_If you choose cells containing levels, as in this example, the formatting chosen for a level value (Puglia region) is shown on all the cells containing the same value. This condition is independent from the inherit-dimension-cell-format property._

### Table Columns (Columns Group)

The properties of the _**Columns**_ group enable the formatting of report columns:

* _**colsBackground**_ and _**colsForeground**_ background and font color
* _**colsFontSize**_ font size
* _**colsItalic and colsBold**_ for italics or bold
* _**colTextAlign**_ column heading alignment (right, _left_ and _center_).

_The following properties apply only in DAC:_

* _**dimSpanCols**_ to show a single column aggregating all the detail ones, instead of showing a parent column for every child
* _**colsLocked**_ to freeze column headings during scrolling
* _**colsGradient**_ to show the gradient on column headings
* _**dimWrapCols**_ for text wrapping
* _**rowsUnderlined**_ for underlining

### Table rows (Row group)

The properties of the _**Row**_ group allow you to customize the layout of report rows:

* _**rowsDefaultHeight**_ sets the row height default value
* _**rowsBackground**_ and _**rowsForeground**_ background and font color
* _**colsFontSize**_ font size
* _**rowsItalic and rowsBold**_ for italics or bold
* _**rowTextAlign**_ row header alignment (right, _left_ and _center_).

_The following properties apply only in DAC:_

* _**dimSpanRows**_ to show a single row aggregating all the detail ones, instead of showing a parent row for every child
* _**rowsLocked**_ to freeze row headers during scrolling
* _**rowsGradient**_ to show the gradient on row headers
* _**dimWrapRows**_ for text wrapping
* _**rowsUnderlined**_ for underlining

### Header (Header group)

The properties of the _**Headers group**_ allow you to set the characteristics of the report headings:

* _**showHeaders,**_ when enabled, displays the following properties:
  * _**headersBackground**_ and _**headersForeground**_ background and font color
  * _**headersFontSize**_ font size
* _**headersItalic and headersBold**_ for italics or bold
* _**headersTextAlign**_ header alignment (_right,_ _left_ and _center_)

_The following properties apply only in DAC:_

* _**HeadersTextWrap**_ text wrapping
* _**headersUnderline**_ underlined style

### Table Totals (Totals group)

The formatting of totals, both cumulative and partial, can be customized through the properties of the Totals group, found both at application and at single report level.

On the _**font**_ you can customize:

* **Font-size** for the font type and size
* **Bold**, **Italic** and **Underlined**, (visible only in DAC)
* **totalTextAlign**, or text placement in the cell (Left - Right- Center)
* **totalTextWrap**, for automatic text wrapping
* **total-formatting**, for the coloring of background and text for PARTIAL TOTALS

If disabled, the formatting of the metric on which the total is computed is inherited (by default always given a bold style).

If enabled, the properties **foreground-color** and **background-color** are activated to give a different coloring from that of the metric. By default _**total-formatting**_ is enabled.

* **total-cumulative-formatting**, for the coloring of background and text for CUMULATIVE TOTALS.

If disabled, the formatting chosen for the partial totals is inherited (both if the formatting of the metric or a customized one is assigned).

If enabled, the properties **foreground-color** and **background-color** are activated to customize colors. By default _**total-cumulative-formatting**_ is disabled.

* **apply-format-to-custom-totals**, for background and text coloring for CUSTOM TOTALS **(**&#x45;xcel like).

If disabled, the formatting of the metric on which the total is computed is inherited.

![](<../../../.gitbook/assets/14 (8).png>)

_If you insert a custom total, for example the sum of the first three months of the year (‘First Quarter’= COL(C)+COL(D)+COL(E)), the formatting given to every row metric is inherited by the total:_

_‘First Quarter’ for ‘Sales Val’ and ‘Bdg Sales Val’ has a black font; ‘First Quarter’ for ‘Sales Qty”, has instead red/green fonts, respecting the thresholds set in ‘Sales Qty’._

_This property is applied only if the custom total refers to the data of a metric itself._

By default _**apply-format-to-custom-totals**_ is enabled, therefore the formatting chosen for the partial totals is inherited. If disabled, the formatting of the metric on which the total is computed is inherited.

**Example: Formatting Totals Layout**

![](<../../../.gitbook/assets/15 (13).png>)

_Open the report property window and select the Totals group; set italics for the totals (Italics property)._

_Modify the foreground-color and background-color for partial totals and cumulative totals (first enable Custom-cumulative)._

### Title Report (Title Report Group)

The settings for the properties of Report Title group are only displayed in DAC.

When a new report is created, a name is given when saving. In any report, it is possible to set the format for the title that will be the name associated with the report.

Font size is set from the _**fontSize**_ property _(size from 1 to 30)_ . From the _**foregroundColor**_ property you can set the foreground color of the title box.

![](<../../../.gitbook/assets/16 (9).png>)

_In this example note how DAC displays the report title after it was set in DAC._

_We set the font TAHOMA with size 30 and red text color._
