# HeatMap 1.2

## Overview <a href="#toc69811335" id="toc69811335"></a>

Use the **HeatMap** to show tabular data values as solid color variations starting from a simple report.

![](.gitbook/assets/0)

In the picture, the **HeatMap** widget is built with a simple report. Data are displayed as a combination of rectangles with solid color variations. The chart shows the annual revenues between sales employees in a company.

The **HeatMap** widget is a graphical representation of data where values contained in a table are represented as a combination of rectangles with solid color variations. It is mostly used to plot large and complex data.

Each rectangle represents a data value element. Low and high values are represented in different colors with different gradients so that users can quickly grasp the status and impact of 2 components simultaneously (i.e., X and Y-axis).

You can display additional information about data points. The widget's interface provides:

* A **Legend:** It is a control rendered at the bottom of the chart and used to summarize the range of colors in the **HeatMap**. This gives a visual guideline for mapping between value and color.

![](.gitbook/assets/2)

* **Tooltips:** Display information for the data points when hovering the mouse over them.

![](.gitbook/assets/3)

## Report Mapping <a href="#toc69811336" id="toc69811336"></a>

The **HeatMap** widget is a Data Presentation type widget. Its data source consists of a report that requires the following **mandatory fields:**

1. **HM\_XLABEL:** This field represents the x-axis coordinate of the heat map element (rectangle).
2. **HM\_YLABEL:** This field represents the y-axis coordinate of the heat map element (rectangle).
3. **HM\_VALUE**: This field represents the value of the heat map element (rectangle).

![](.gitbook/assets/1)

This data source is used to load the list of rectangles in the widget. Each row of the report is a rectangle.

To build your data source, you can use real values. The widget accepts both integer and decimal values, positive and negative.

The widget supports more than one report.

## Example <a href="#toc69811337" id="toc69811337"></a>

**Description:** The example shows the use of the **HeatMap** widget to observe the annual revenue of Sales employees in a company.

* Create the data source report of the widget. The report must have three mandatory fields **(HM\_XLABEL, HM\_YLABEL, HM\_VALUE).**

![](.gitbook/assets/4)

* Create a new Page in the Page Design and use the **HeatMap** widget. Associate the report created in the first step to the widget.
* Map the columns of the report in the **fields association** property of the widget.

![](.gitbook/assets/5)

* Display the **HeatMap** widget on the Web Application.

![](.gitbook/assets/6)
