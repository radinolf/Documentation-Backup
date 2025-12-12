---
description: How to create Cubes and Measures
---

# Creating a cube

## Step 1 - Definition

To create a cube you must:

1. Select the Fact Table on the data warehouse
2. Select the dimensional levels, with mapping between the fields in the Fact Table and the ones in the dimensional table (containing the values of the Dimension levels)
3. Define the analysis measures, by associating them with the respective fields in the Fact Table

In DAC, the cubes are created within an application, and so they may not be reused by other applications in the Data Model.

You can also define Cubes on remote DWHs

A Wizard is used to create Cubes, in which the following is defined:

**Data Model>> Cubes Management**

or from the toolbar button ![](<../../../.gitbook/assets/1 (9).png>) .

A window opens (on the left) with a list of the Cubes for the application.

![](<../../../.gitbook/assets/2 (3).png>)

When a Cube is selected, the following appears (on the right):

* details on the logical name, creation date, last modification, creator and author of the last modification;
* the Dimensions associated with the Cube
* the Metrics calculated on the Cube measures.

Select the Cube Dimensions and Metrics (by double-clicking) to directly access the object management window, with the preselection of the selected element.

To create a new Cube, go to _Cubes_ and select _**New**_ from the pop-up menu (right-click) or click on the button on the top left part of the page.

![SNAGHTML18d4897](<../../../.gitbook/assets/3 (20).png>)

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

### Name and Data Source&#x20;

The first panel requires the descriptive information, data source and mapping type for the Cube.

![](<../../../.gitbook/assets/6 (6).png>)

The descriptive parameters are:

* _**Logical name**_, univocal for the dimensions of the model and not editable after creation
* _**Display name,**_ the name shown in reports, which can be edited after it is created
* _**Description**_, optional

For the data source (_**Connection Settings**_) it is possible to decide where the data of the cube is reported:

* _**Model default**_, on the data warehouse associated with the model
* _**Local,**_ on a database on the same instance of the Data Model, which DAC is connected to. When you select this item, you enable the _**Data schema**_ field where the Data Model schemes are listed.
* _**Remote,**_ on a remote database. Selecting ![](<../../../.gitbook/assets/7 (19).png>)this item enables the menu with the list of data sources configured using the [Datasource Designer](/broken/pages/-MfHrzbfigrQbGP53aPH#_Server_NT) module:

the data sources are listed which an alias has been assigned to (_**alias-name property**_, on the _Datasource Designer_).

In case the connection to the data source fails, this is not presented in the list.

Selecting a remote data source enables the _**Scheme Owner**_ field where the remote database schemes are listed. The menu is empty if the connection with the data source fails.

Only Dimensions mapped on the same data source can be _matched_ for this type of Cube.

**Note:**

_Reports that use Cubes on remote DWHs have the same cache management as the models on remote DWHs._

The **Next** button allows you to go to the next step without saving the data. Data is only saved in the Cube creation step (last step).

## Step 2 - Dimensions

In this step, you select the **Dimensions to be associated with the Cube**. The level for each Dimension will be selected in the next step.

The pane on the left lists the Dimensions of the application (all of them, including those associated with other Cubes). Use the arrow button (![](<../../../.gitbook/assets/9 (14).png>)) or simply double-click to add them to the right pane and therefore associate them with the Cube. To remove the dimension from the right pane (the association of the dimension with the cube), simply double click it or select the reverse arrow button ![](<../../../.gitbook/assets/10 (2).png>).

Selecting Dimensions

![SNAGHTML19d4ec3](<../../../.gitbook/assets/11 (19).png>)

**Note:** If the Cube points to a remote data source, only the Dimensions mapped on the same data source will be listed.

## Step 3 - Columns Mapping

In this step, you define the manual **mapping** between the dimensional levels and the Fact Table. The Dimensions selected in the previous step are listed and the following is selected for each of them:

1. the level to _be matched_ to the fact table: in the **Level** field all the levels of the dimension are listed; after having been chosen, in **Level column** the system reports the respective ID field (chosen in Column@ID in the creation of the dimensional levels).
2. the field of the fact table corresponding to the **Fact table column**; the system proposes a field with a name coinciding with that of the level, if any.

![](<../../../.gitbook/assets/12 (8).png>)

Dimensions chosen at the previous step

Selecting fields for multiple keys

Level ID field

Fact Table fields (columns)

Dimension levels![](<../../../.gitbook/assets/13 (1).png>)

If the Dimension level was defined with a multiple key, the respective level fields selected during the creation step are indicated in **Additional joins**. By double-clicking the following window is open:

* the dimensional level field (**Level column**)
* the Fact Table fields (**Fact Table column**). The selected ones will be used to link the Fact Table and the dimensional table.

![](../../../.gitbook/assets/14.png)

## Step 4 - Measures

In the last step the cube **measures** are defined; in the window the Fact Table fields are listed (selected in step II), and the user will choose the field which he wants to define as a measure.

In addition to the measures already in the Fact Table, others can be defined by customizing them, as described in the next paragraph.

![](<../../../.gitbook/assets/15 (12).png>)





