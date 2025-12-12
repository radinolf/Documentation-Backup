---
description: How to create Cubes and Measures
---

# Cubes and Measures

The Dimensions in a Business Intelligence analysis are the analysis reports (as defined and described in the Dimensions section). Sizes that quantify the analysis data are the **measures** (e.g. in a sales analysis, the measures might be the sales _quantity_ or _amounts_).

The set of analysis reports (dimensions) and the corresponding measures provide the complete information content for the Business Intelligence analysis. This _set_ of data is called a **Cube**, which traditionally depicts the information in an n-dimensional Cube, where the coordinates are the Dimensions and each element contains the quantitative values (the measures). In the example below a three-dimensional cube is shown.

Example: Cube for sales

![](<../../../.gitbook/assets/0 (12).png>)

_In this example data is represented for the sales analysis, where:_

* _the analysis reports (Dimensions) are where (GEOGRAPHY), when (TIME) and what (PRODUCT) was sold_
* _the analysis measures, i.e. relating to the quantitative values are quantity (SALES QUANTITY) and amount (SALES VALUE) of the sales_

_The dimensions, on the coordinates, identify the element of the cube, which contains the quantitative values (measures)._

The dimensions, such as coordinates of the cube, are considered at a specific hierarchy level (_in_ _the example: Time, on the year level, Geography, on the city level, etc._). Aggregate operations, which are useful for the analyses, may be performed from this level (_in this example, you can aggregate Geography by territorial areas at a higher level, such as: central, north and south)._

The data depicted in the Cube are saved in the data warehouse. The table which contains _the quantitative_ data (values for the measures) is called a Fact Table. The qualitative data (values for Dimension levels) are also saved in it.

To create a cube you must:

1. Select the Fact Table on the data warehouse
2. Select the dimensional levels, with mapping between the fields in the Fact Table and the ones in the dimensional table (containing the values of the Dimension levels)
3. Define the analysis measures, by associating them with the respective fields in the Fact Table

In DAC, the cubes are created within an application, and so they may not be reused by other applications in the Data Model.

You can also define Cubes on remote DWHs

A Wizard is used to create Cubes, in which the following is defined:

**Data Model>> Cubes Management**

or from the toolbar button ![](<../../../.gitbook/assets/1 (17).png>) .

A window opens (on the left) with a list of the Cubes for the application.

![](<../../../.gitbook/assets/2 (8).png>)

When a Cube is selected, the following appears (on the right):

* details on the logical name, creation date, last modification, creator and author of the last modification;
* the Dimensions associated with the Cube
* the Metrics calculated on the Cube measures.

Select the Cube Dimensions and Metrics (by double-clicking) to directly access the object management window, with the preselection of the selected element.

To create a new Cube, go to _Cubes_ and select _**New**_ from the pop-up menu (right-click) or click on the button on the top left part of the page.

![SNAGHTML18d4897](<../../../.gitbook/assets/3 (13).png>)

A four-step Wizard is run for defining the following:

1. Descriptive parameters and data source DAC also allows you to map Cubes on other databases (other than the application DWH).

The type of Dimension mapping on the Cube is defined in the first step (manual or automatic).

1. Fact Table containing the measures
2. The Dimensions whose levels are in the Fact Table
3. Mappin&#x67;**,** between dimensional levels and their respective fields in the Fact Table
4. The Cube measures

At the end of the Wizard, in addition to the cube, you will have created a first-level metric for each measure of the cube:

the Metric is an aggregate of the sum of values mapped for the measure.

The copy the Cube function is also available.

### Copying a Cube

_**Edit as copy**_ is used to copy a Cube. This command runs the Cube Creation Wizard again, with all the elements preselected in the first step, except the logical name of the Cube. _Copy of_ \[name of original Cube] is suggested for the one displayed.

![](<../../../.gitbook/assets/4 (14).png>)

Remember that the logical names of the measures must be unique for the application.

![](<../../../.gitbook/assets/5 (16).png>)

### Name and Data Source (Step I)

The first panel requires the descriptive information, data source and mapping type for the Cube.

![](<../../../.gitbook/assets/6 (12).png>)

The descriptive parameters are:

* _**Logical name**_, univocal for the dimensions of the model and not editable after creation
* _**Display name,**_ the name shown in reports, which can be edited after it is created
* _**Description**_, optional

For the data source (_**Connection Settings**_) it is possible to decide where the data of the cube is reported:

* _**Model default**_, on the data warehouse associated with the model
* _**Local,**_ on a database on the same instance of the Data Model, which DAC is connected to. When you select this item, you enable the _**Data schema**_ field where the Data Model schemes are listed.
* _**Remote,**_ on a remote database. Selecting ![](<../../../.gitbook/assets/7 (16).png>)this item enables the menu with the list of data sources configured using the [Datasource Designer](/broken/pages/-MfHrzbfigrQbGP53aPH#_Server_NT) module:

the data sources are listed which an alias has been assigned to (_**alias-name property**_, on the _Datasource Designer_).

In case the connection to the data source fails, this is not presented in the list.

Selecting a remote data source enables the _**Scheme Owner**_ field where the remote database schemes are listed. The menu is empty if the connection with the data source fails.

Only Dimensions mapped on the same data source can be _matched_ for this type of Cube.

**Note:**

_Reports that use Cubes on remote DWHs have the same cache management as the models on remote DWHs._

The **Next** button allows you to go to the next step without saving the data. Data is only saved in the Cube creation step (last step).

### Selecting the Fact Table (Step II)

Select the Fact Table in the second screen.

Fact Table

![](<../../../.gitbook/assets/8 (10).png>)

The box on the left contains the list of tables of the schema selected in the previous step (**Schema**). You can select the Fact Table from here. A quick search can also be performed by entering the name of the table involved in the _Search_ field (top left).

Double-click or use the right arrow button to move the selected table into the box on the right, where it will remain as a Fact Table for the Cube. To remove the table from the box on the right, simply double-click it.

**Note:** You may not move more than one table into the box on the right.

### Dimension Selection (Step III)

In this step, you select the **Dimensions to be associated with the Cube**. The level for each Dimension will be selected in the next step.

The pane on the left lists the Dimensions of the application (all of them, including those associated with other Cubes). Use the arrow button (![](<../../../.gitbook/assets/9 (18).png>)) or simply double-click to add them to the right pane and therefore associate them with the Cube. To remove the dimension from the right pane (the association of the dimension with the cube), simply double click it or select the reverse arrow button ![](<../../../.gitbook/assets/10 (9).png>).

Selecting Dimensions

![SNAGHTML19d4ec3](<../../../.gitbook/assets/11 (13).png>)

**Note:** If the Cube points to a remote data source, only the Dimensions mapped on the same data source will be listed.

### Mapping of the Dimensions (Step IV)

In this step, you define the manual **mapping** between the dimensional levels and the Fact Table. The Dimensions selected in the previous step are listed and the following is selected for each of them:

1. the level to _be matched_ to the fact table: in the **Level** field all the levels of the dimension are listed; after having been chosen, in **Level column** the system reports the respective ID field (chosen in Column@ID in the creation of the dimensional levels).
2. the field of the fact table corresponding to the **Fact table column**; the system proposes a field with a name coinciding with that of the level, if any.

![](<../../../.gitbook/assets/12 (18).png>)

Dimensions chosen at the previous step

Selecting fields for multiple keys

Level ID field

Fact Table fields (columns)

Dimension levels![](<../../../.gitbook/assets/13 (15).png>)

If the Dimension level was defined with a multiple key, the respective level fields selected during the creation step are indicated in **Additional joins**. By double-clicking the following window is open:

* the dimensional level field (**Level column**)
* the Fact Table fields (**Fact Table column**). The selected ones will be used to link the Fact Table and the dimensional table.

![](<../../../.gitbook/assets/14 (8).png>)

### Measures (Step V)

In the last step the cube **measures** are defined; in the window the Fact Table fields are listed (selected in step II), and the user will choose the field which he wants to define as a measure.

In addition to the measures already in the Fact Table, others can be defined by customizing them, as described in the next paragraph.

![](<../../../.gitbook/assets/15 (9).png>)

#### Custom Measures

Follow the steps below to create a customized measure:

![](<../../../.gitbook/assets/16 (6).png>)

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

### Global Dimensions for Cubes on Different Systems (Global dimension)

In addition to defining Cubes on different data sources, you can also establish whether or not these Cubes have global Dimensions.

Please remember that each cube on a data source can only have dimensions mapped on the same data source. Local Cubes (i.e. mapped on the application DWH) can only have Dimensions mapped on the local database.

To define global dimensions among cubes of different data sources, or among cubes on remote data sources and local cubes, the _**Global dimension**_ function is used.

This function assigns a label to a level, which if used for another dimensional level, will indicate that the two represent the same level, even if on two different environments.

Proceed as follows:

1. Cube precondition: in the application there are several cubes on different environments, for example one in local and the other on a remote DWH.
2. Dimension precondition: levels exist for all the cubes which represent the same entity, for example the level of the province for the local cube and the one on the remote DWH is the same (the key fields mapped in both environments have the same values).
3. You modify the level of one of the global dimensions by defining a list for the global levels in the _**level-global-dimension**_ property:

A pop-up menu opens from the _level-global-Dimension_ property of the level. It is empty in this initial phase and will be used to define the list for the global dimensional levels. Enter the name to be given to the list in _Global Level name._ Proceed with creating the Dimension (up to the last step).

![](<../../../.gitbook/assets/17 (8).png>)

1. You modify the level of the other global Dimensions by assigning it to the same list defined for the first level (previous point).

A pop-up menu opens from the _level-global-Dimension_ property of the level. It contains the list for the global levels. In this phase it displays the name entered previously (_Global name list_), where the previous level is listed on the right. With a double click, select the name of the list to assign the level being modified to it. Complete the procedure by going to the last step in creating a dimension.

![](<../../../.gitbook/assets/18 (12).png>)

At the end of the procedure, the list will contain all the levels that represent the same entity.

This list may be accessed and displayed from the menu item _**Data Model >> Show Global Level.**_

To **delete a level from the list** just access the dimension editing level, open the pop-up from the _level-global-dimension_ property and select the _**Clear**_ button. At the end of the dimension editing, the level will be deleted from the list.

**Global levels in a report** are used only if you enable the _**join-global-names property.**_ Subsequently, it is possible to select metrics in the cubes with levels defined as _Global-dimension_; the levels that can be selected are only those defined in this way.

The cache by default is always created on the Data Model.

## User Filters (Data Privileges)

User Filters restrict data viewing by users on all logical objects published in DAC, such as crosstabs, graphs, indicators, etc.

To start the user filter wizard: from the menu bar, select **Data Model** and **User filter management**; otherwise from the tool bar, select the ![](<../../../.gitbook/assets/19 (11).png>) button.

![\\\fserver\projects\Manuali e training\Manuali\AppData\sdifranc\AppData\Local\Temp\SNAGHTML1655cc6.PNG](<../../../.gitbook/assets/20 (4).png>)

The Filter condition is applied to the groups selected in the bottom left pane.

In the example a User filter was created which limits, for all the users of the _Developers Group_, the display of the data only relating to the specific Asset (_Asset@ID = 1 condition_)

The User Filter will be applied to each analysis containing at least one Metric, which belongs to a Cube containing the selected dimension.

It is worth using the cache (Cache section), entering the dimensional levels used in the security filter condition, to improve the execution speed of the reports.

In addition, if the report is enabled to use the **automatic cache**, **in no case will this cache be created**.

In the security filters section the System Parameters can be used. They are described in the DAC TAGS and System Parameters section.

The use of these parameters is especially useful to define a dynamic User Filter.

For example, if you have to enable a user with regard to a specific Asset, you may work in two ways:

* _**STATIC**_, where the phases are:

1. create a group for each Asset
2. associate the competent users
3. define a User Filter on the Asset for this group

* _**DYNAMIC:**_

1. create a unique group for the users concerned with the enabling on the Asset
2. create a table where the users are associated with the competent Asset
3. create a dimensional level (or a new dimension) on this table
4. create a dynamic User Filter containing the condition like the one shown in the figure

![](<../../../.gitbook/assets/21 (12).png>)

In this last case, maintenance is certainly less expensive than for the static case. In addition, the creation of a user-asset association table is less expensive in the definition phase than the creation of a group and a user filter for each province.
