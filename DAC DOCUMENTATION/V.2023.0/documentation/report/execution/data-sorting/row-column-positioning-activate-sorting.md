# Row/Column Positioning (activate-sorting)

DAC allows you to change the arrangement of rows and columns in a report, through simple drag & drop operations.

The sorting functionality for rows and columns should be activated through the report _**activate**-sorting_ property (_Main_ group) which allows users to shift the row/columns in the report (the shift is not performed on the aggregating levels, but only on the detail levels).

This property enables the following:

* _**sort-axis**_ to enable the shift of rows alone _\<rows-only_>, columns alone _\<cols-only_> or both _\<both>_
* _**index-by-levelKey**_ to maintain the chosen sorting even during a level shift; this property allows users to index rows or columns with respect to the shifted level only, rather than to the whole row. It is then possible to maintain the chosen sorting, even if the aggregating levels are shifted (see next example).

**Note:** The number of rows that are indexed for placement is equal to 1000.

If you insert a custom total, the activate-sorting property is automatically enabled. According to the position of the total (column/row), the system automatically sets the _sort-axis_ property with the corresponding sorting (row or column only).

![](<../../../../.gitbook/assets/6 (10).png>)

When the _**sorting**_ property is activated, an icon will appear on the top left corner of the report to indicate that it is possible to carry out sorting operations on the rows of that report .

Step 1: Sorting Rows and Columns

![](<../../../../.gitbook/assets/7 (16).png>)

_We activate the sorting function for rows and columns by selecting the activate-sorting property (flag selected)._

_In the report it is now possible to shift the rows of the level of detail (Product), whereas the rows of the aggregating level (Category) cannot be shifted. In the example, Product 14 of Product Family 10 is dragged under Product 124._

_The section highlighted in yellow shows the position the report cell is shifted to._

Step 2: Sorting Rows and Columns

![](<../../../../.gitbook/assets/8 (12).png>)

_If we shift in page by the aggregating level (Category), the report does not maintain the initial sorting:_

_Product 14 is no longer under Product 124, but goes back to its initial position._

Step 3: Sorting Rows and Columns

![](<../../../../.gitbook/assets/9 (26).png>)

_If we activate the index-by-levelKey property, we can instead fix the rows and columns of the report in the desired position._

_If we shift the column for the category in page by, the chosen sorting will be maintained._
