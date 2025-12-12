# Report Features

## Pop-up Menu

A pop-up menu is available in the report, which can be activated from dimensions and metrics, in row and column, and from the cells containing the data. The items listed depend on the where the drop-down menu is activated:

* **Main, Visualization, Object Explorer:** Some items from the Toolbar pop-up for the reports are displayed. In addition, depending on whether the menu was called from the dimensions on the rows or columns, the respective items for the wrap function, span function and the lock of the rows and columns are present.
* **Filters:** Shows the pop-up filters in the rows and columns.
* **Enable Cells Selection:** Select the cells to be formatted. After selection, the **Disables Selected cells** item is activated, to deselect them.

### Pop-up Filter

The _**Filter**_ menu item allows you to immediately filter the elements of the report. It is applied to the rows and columns of the report. Depending on the position the menu was opened from, the sub-items of the _Filter_ menu will appear:

* _Remove selected rows (_&#x6F;r _columns)_ deletes the row;
* _View selected rows (_&#x6F;r _columns)_ applies a filter on the selected row, deleting the others;
* _Remove element_ and _View object_ have the same type of behavior.

### Chache

Reports are generally managed in a **cache system**, which increases the response performance. Cache may be generated from schedules configured at system level, or automatically at the first request of a user, which will make it available to all the others.

The cache is generated automatically only if the reports do not have immediate execution times (typically for executions above 3 seconds).

Date and time when the cache was created is shown next to the name of the report (outlined in red in the figure below). By viewing this cache information, you’ll know the period the displayed data refers to.

![](<../../../.gitbook/assets/image (26).png>)

If the message does not appear, the report is not using the cache and therefore the data relates to the time of the request.

You can always request the data directly from the database and not from the cache, through the **Reload Data** command, available on both the toolbar and the pop-up menu of the report (_Main_ section).

![](<../../../.gitbook/assets/image (49).png>)

**Reload report** reloads the report in the form it was published in by the administrator. The data is taken from the cache, if available, otherwise the report is generated again.

### Tutorial

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/5.ReportFeature/3.Pop-UpMenu/PopUpMenu.mp4" %}

## Paging

You can establish the number of rows and columns the report is to be arranged into. This lets determine the number of pages needed to display the extracted data.

Simply choose the number of rows and columns from the menu available for the **Rows** and **Cols**; for each one of these, the actual number of rows and columns in the report is indicated in brackets. Use the drop-down lists to select a different number of rows and/or columns.

![](<../../../.gitbook/assets/image (89).png>)

## Sorting



You can sort the values of the metrics by clicking on the header of the metric to be sorted:

* **Single click**: a descending sort is applied.
* **Double click**: an ascending sort is applied.
* **Third click**: the list of items follows the normal report ordering.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/5.ReportFeature/2.ReportMetricSorting/ReportSorting.mp4" %}

## Decorated Metrics

#### Decorated Metrics

The administrator can define metrics so they include decoration in the form of bars, indicator, or another report.

* Bar decoration (outlined in blue, in the example below):

![](<../../../.gitbook/assets/image (93).png>)

* With indicator(outlined in blue, in the example below):

![](<../../../.gitbook/assets/image (105).png>)



* With another report, which is typically displayed in a graph form.

In the example in the figure below, two options are show. At the top of the example, the image of the graph respects the levels of the report, on the rows (the three Business Units). At the bottom of the example, the image of the graph respects the page-by (the year).

![](<../../../.gitbook/assets/image (91).png>)

View : How to create a decorated metrics in Design Studio [#format-with-decoration](../../design-studio/data-model/metrics.md#format-with-decoration "mention").



## Drill-Through

It is possible to have reports where there are links that open a:

* Another report
* A Page
* An App
* A Web Page

You can open these pages on the same page from which it is called, and on a new one.

In addition the links are associated with the dimensions and the metrics and may pass their values as parameters.

The graphic presentation of the links may be an image, for example ![](<../../../.gitbook/assets/1 (3).png>) . The image is selected by the administrator.

## Report Navigation with Page By <a href="#toc392237725" id="toc392237725"></a>

With the report pages elements it is possible to apply filters to the report.



![](<../../../.gitbook/assets/image (74).png>)

The report pages elements are listed in a drop-down menu, as shown in the following figures, where the different selection possibilities are shown:

![](<../../../.gitbook/assets/image (69).png>)

The selection type is set by the administrator.

In some selection types the element search is active: just type part of the name of the element in the menu to obtain a list of only the elements that contain the typed text.

Buttons are available to scroll up and down the list (see figure below).

![](<../../../.gitbook/assets/image (37).png>)











