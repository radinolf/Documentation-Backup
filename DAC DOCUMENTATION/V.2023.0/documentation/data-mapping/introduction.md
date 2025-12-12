# Introduction

The Dimensions in a Business Intelligence analysis are the analysis reports (as defined and described in the Dimensions section). Sizes that quantify the analysis data are the **measures** (e.g. in a sales analysis, the measures might be the sales _quantity_ or _amounts_).

The set of analysis reports (dimensions) and the corresponding measures provide the complete information content for the Business Intelligence analysis. This _set_ of data is called a **Cube**, which traditionally depicts the information in an n-dimensional Cube, where the coordinates are the Dimensions and each element contains the quantitative values (the measures). In the example below a three-dimensional cube is shown.

Example: Cube for sales

![](<../../.gitbook/assets/0 (23).png>)

_In this example data is represented for the sales analysis, where:_

* _the analysis reports (Dimensions) are where (GEOGRAPHY), when (TIME) and what (PRODUCT) was sold_
* _the analysis measures, i.e. relating to the quantitative values are quantity (SALES QUANTITY) and amount (SALES VALUE) of the sales_

_The dimensions, on the coordinates, identify the element of the cube, which contains the quantitative values (measures)._

The dimensions, such as coordinates of the cube, are considered at a specific hierarchy level (_in_ _the example: Time, on the year level, Geography, on the city level, etc._). Aggregate operations, which are useful for the analyses, may be performed from this level (_in this example, you can aggregate Geography by territorial areas at a higher level, such as: central, north and south)._

The data depicted in the Cube are saved in the data warehouse. The table which contains _the quantitative_ data (values for the measures) is called a Fact Table. The qualitative data (values for Dimension levels) are also saved in it.
