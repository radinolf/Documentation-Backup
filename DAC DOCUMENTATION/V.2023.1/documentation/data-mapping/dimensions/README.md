---
description: How to create Dimensions
---

# Dimensions

Dimensions are the analysis _reports on a Business Intelligence process_. In a sales analysis, for example, possible analysis reports are: where, when and what was sold, thus identifying the dimensions of the territory, time and product respectively.

Each dimension features _specific elements_, for example the time dimension will be characterized by the year, quarter, month or day, or the territory dimension by the geographic area, region or province.

Furthermore, these elements (_**dimensional levels**_) are in _**hierarchical relation**_ to each other, where the hierarchy is set by the aggregate degree of one with respect to the other.

Thus for the _territory_ dimension, a hierarchical relation may be defined from the geographic area to the province, where the geographic area aggregates the regions and the regions aggregate the provinces.

This hierarchy will process the OLAP analysis on the data with the use of _**drill-down/roll-up**_ functions, through which it will be possible to detail or aggregate the elements of the same dimension or perform the same operations among different dimensions.

All dimensional levels may not be in hierarchical relation to one another.

For example, a _product_ dimension could be characterized by elements such as the product family or the supplier, in addition to the product.

Both the product family and the supplier are aggregating the product but neither of them is aggregating the other. The relation between the three levels is shown in the figure. In this case, we have a dimension with two different hierarchies (_**multi-hierarchy**_):

* _Product family_ aggregating (parent) the _Product_
* _Supplier_ aggregating (parent) the _Product_

The retrieval of the information relating to the Dimension is defined by _**MAPPING**_ the data in the data warehouse (DWH):

* among the _**dimensional levels**_ and the fields of the table containing the information on the same level;
* among the _**hierarchical**_ _**link**_ (parent-child) and the corresponding link on the tables associated with the levels, indicating the key fields that contribute to the join

![](<../../../.gitbook/assets/image (1065).png>)



Example of mapping for the territory dimension, with levels for the geographic area, region and province.

**Step 1:Territory Dimension Mapping**

![](<../../../.gitbook/assets/image (1057).png>)

_The dimension was represented with some elements, which indicate:_

* On the left the dimensional level (logical application side)
* On the right the table (between square brackets) with the respective fields, containing the data (data warehouse side).

The hierarchy among the elements is represented from top (more aggregating element) to bottom (more detailed element).

For level mapping, the field of the table is associated:

* LK\_GEO\_AREA.DESCRIPTION for the Geography Area level,
* LK\_GEO\_REGION..DESCRIPTION for the Region level
* &#x20;LK\_GEO\_PROVINCE.DESCRIPTION for the Province level

The hierarchy mapping between Geography Area and Region is expressed by the link between the keys (join):

`LK_GEO_REGION.ID_AREA=LK_GEO_AREA.ID_AREA`

The hierarchy mapping between Region and Provinces is expressed by the link between the keys (join):

`LK_GEO_PROVINCE.ID_REGION=LK_GEO_REGION.ID_REGION`

In DAC, the dimensions are created inside an application and may be shared among several cubes of the same application, but it is not possible to use them on other applications.

In DAC, you can define the attributes of a dimensional level, that is, all the additional information that does not have an aggregate function. For example, for a dimensional level on the customer, the address and the reference person are considered attributes.

DAC supports cases where the dimensional tables of the data warehouse are linked through an associative table: fields reporting the descriptive part in an anagraphic table, and fields reporting the relations among levels in an associative table.

![](<../../../.gitbook/assets/image (963).png>)



DAC also supports dimensional level mapping with recursive hierarchical links.

![](<../../../.gitbook/assets/image (83).png>)

The Dimensions defined on remote databases must then be _matched to_ a Cube defined on the same database. For the analysis between cubes/dimensions which focus on different databases, it is necessary to configure the Global Dimensions.

DAC has _**complex forecasting functions**_, whose calculations are performed with respect to the time levels. For the system to be able to correctly recognize the data it is necessary to supply the format of the time data on the associated dimensional level.

##

## **TUTORIAL**

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/CreateDimension/CreateDimension.mp4" %}



##
