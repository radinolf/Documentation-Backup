---
description: How to create Cubes and Measures
---

# Custom Measures

Follow the steps below to create a customized measure:

![](<../../../.gitbook/assets/16 (13).png>)

The + button (in the top left) lets you add a customized measure: a row for the new measure is created at the end of the list, with the name _**Custom Measure**_

1. Enter the logical name and display name for the measure (_**Logical name, Display name**_)

**Note:** We strongly advise against using the same Display Name of another measure, even if the system allows it. The system warns you when you assign a name that was already used by highlighting it in yellow, and a tooltip also informs you that the name entered is a duplicate.

1. Click on _**Formula**_ to open the window used to define the formula to be applied to calculate the customized measure.

The Fact Table fields and those corresponding to the dimensional levels are indicated to define the formula (note that since they are grouped by Cubes, only Dimensions matched to at _least_ one Cube are accessible).

The dimensional levels and the Fact Table fields are indicated in the formula definition area by double-clicking.

The difference between a customized measure (column formula) and a Composite lies in managing the aggregation of the datum.

For a custom measure, the operation is performed at row level (first the formula between simple measures is performed and afterwards they are aggregated). For compound metrics the operation is performed after aggregating the simple measures (operation on aggregates).

_For example:_

_Customized measure: SALES\_UNIT\_PRICE \*SALES\_QTY, which a first level metric derives from:_

_Sum(SALES\_UNIT\_PRICE \*SALES\_QTY)_

_Compound metric: Sum(SALES\_UNIT\_PRICE)\* Sum(SALES\_QTY)_
