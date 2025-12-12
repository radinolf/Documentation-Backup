# OLAP Functions

## Introduction

DAC provides a set of functions for OLAP analysis. These functions allow you to easily select and display data dynamically, and examine it from different points of view. OLAP analysis is available on dashboard components, and on reports opened from the catalog. OLAP [drill](/broken/pages/-Me-Djrx7PJNVnjHYNQ2#Drill) or [slice & dice](/broken/pages/-Me-Djrx7PJNVnjHYNQ2#Slice) type analysis can be run on the dashboard components, such as graphs and tables

On reports opened from the catalog, you can move the dimensional levels to any position. This allows you to perform [pivoting operations](/broken/pages/-Me-Djrx7PJNVnjHYNQ2#Moving) and any change of perspective when viewing the data.

The drill-up and drill-down analyses allow you to display the data of a multidimensional report with different levels of detail; in fact, the hierarchical structuring of the dimensions allows you to see the information at different _aggregate_ (**drill-up**) or _sidebar_ (**drill-down**) levels. DAC offers various grouping methods:

* Drill on the report elements
* Drill with **new dimensional levels**
  * By creating **new groupings** in _custom_ mode
  * By inserting layers of the application, using **Pop-up drill**
* Making or not making the _parent_ level visible, i.e. depending on whether or not the [hierarchical drill](/broken/pages/-Me-Djrx7PJNVnjHYNQ2#Hierarchical) is active.

## Drill on Report Items

The reports typically have several dimensional levels in the rows and/or columns. By default, they are presented as tables without any aggregate level: the reports show maximum detail; a group by dimensional levels would facilitate the analysis of the reported information.

Grouping modes on report elements are set in the report toolbar’s _Visualization_ section, or from the pop-up menu of the report (always on the same item):

* Grouping by dimension (**Dimensions**), with aggregation with respect to each specific dimension;
* Grouping by layout (**Layout**), with complete aggregation that follows the order of the levels in the layout of the report at rows and/or columns.

Select the No grouping item to obtain the report **without grouping**.

![](<../../../.gitbook/assets/image (1194).png>)

## Hierarchical Drill

When you run drill-down operations in standard mode (shown in the previous paragraph), the metric values of all the levels chosen in the drill operation remain visible.

### Example: Table/Graph Hierarchical Drill

![](<../../../.gitbook/assets/image (908).png>)



_For the report in the figure, a drill-down was run for year 2006 and month February, thus showing the Business Unit, which is the maximum level of detail._

_For each level chosen on the in drill navigation, the corresponding value of the metric remains visible._

_If the same report is published as a graph, the same drill-down navigation will be possible, by simply selecting the graphic element (in this case the bar)._

_Also, for the graph, the value of the level chosen for the drill is stored._

As shown in the example, the in drill-down navigation on the graphs tends to push the values downwards, because the aggregate levels typically show higher values.

For this reason, the graphs are generally published by adhering to a second drill navigation mode, which envisages disabling of the hierarchical drill.

In this mode, you _lose_ the reference value of the parent level and only the values of the _child_ levels are show&#x6E;_._ This lets the graph show the values on a scale set only by the child levels, thus improving the readability of the graphic presentation.

When the in drill dimension is selected, this disappears from the report and is reported in a **drill path** at the top; the path levels can be selected, allowing drill-up operations.

Disabling the hierarchical drill takes place by deselecting the item of the toolbar of the **Hierarchical-drill** report (_Main_ section).

![](<../../../.gitbook/assets/image (1776).png>)

## Moving Analysis Reports (Including Pivoting)

On a report in table form, you can move the dimensional levels to any position that you choose from the rows, columns or page-by. To do this, go to the level (place the cursor in the values, not the header area) and drag the level to the new position. An arrow will indicate where the level will be inserted when you release the left mouse button.

The double arrow indicates where the exchange of levels happened. This permits the pivoting operation, i.e. the exchange of the visualization axes.

If the levels are in drill, all the aggregating levels will be dragged to the new position, or exchanged, still remaining in this grouping mode. The exception is if the aggregating levels are moved to page-by, where they will be moved to the new position, but the levels won’t remain grouped.

## Slice-and-Dice

The _**Slice-and-dice**_ operation sets the value of at least one dimension or keeps it in a range.

It allows you to select and project a subset of data by “_slicing_ _and_ _dicing_” a particular portion of the aggregated data along one or more dimensions.

The use of page levels (Page-by) allows this type of behavior
