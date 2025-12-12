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
*

![](<../../../.gitbook/assets/image (179).png>)



Example of mapping for the territory dimension, with levels for the geographic area, region and province.

Step 1:Territory Dimension Mapping

![](<../../../.gitbook/assets/image (395).png>)

_The dimension was represented with some elements, which indicate:_

* _On the left the dimensional level (logical application side)_
* _On the right the table (between square brackets) with the respective fields, containing the data (data warehouse side)._

_The hierarchy among the elements is represented from top (more aggregating element) to bottom (more detailed element)._

_For level mapping, the field of the table is associated:_

* _LK\_GEO\_AREA.DESCRIPTION for the Geography Area level,_
* _LK\_GEO\_REGION..DESCRIPTION for the Region level_
* &#x20;_LK\_GEO\_PROVINCE.DESCRIPTION for the Province level_

_The hierarchy mapping between Geography Area and Region is expressed by the link between the keys (join):_

_LK\_GEO\_REGION.ID\_AREA=LK\_GEO\_AREA.ID\_AREA_

_The hierarchy mapping between Region and Provinces is expressed by the link between the keys (join):_

_LK\_GEO\_PROVINCE.ID\_REGION=LK\_GEO\_REGION.ID\_REGION_

In DAC, the dimensions are created inside an application and may be shared among several cubes of the same application, but it is not possible to use them on other applications.

In DAC, you can define the attributes of a dimensional level, that is, all the additional information that does not have an aggregate function. For example, for a dimensional level on the customer, the address and the reference person are considered attributes.

DAC supports cases where the dimensional tables of the data warehouse are linked through an associative table: fields reporting the descriptive part in an anagraphic table, and fields reporting the relations among levels in an associative table.

![](<../../../.gitbook/assets/image (575).png>)



DAC also supports dimensional level mapping with recursive hierarchical links.

![](<../../../.gitbook/assets/image (521).png>)

The Dimensions defined on remote databases must then be _matched to_ a Cube defined on the same database. For the analysis between cubes/dimensions which focus on different databases, it is necessary to configure the Global Dimensions.

DAC has _**complex forecasting functions**_, whose calculations are performed with respect to the time levels. For the system to be able to correctly recognize the data it is necessary to supply the format of the time data on the associated dimensional level.

The new Dimension Creation Wizard is launched from the menu item:

**Data Model>> Dimensions management…,**

or from the toolbar by pressing the button ![](/broken/files/-MeULeJZZQabE_Z43oDZ)

A window with a list of Dimensions opens on the left side of the page.

![](<../../../.gitbook/assets/image (736).png>)

When a Dimension is selected, the following appears on the right:

* details on the logical name, creation date, last modification, creator and author of the last modification;
* the Cubes in which the Dimension is associated
* the dimensional levels
* by selecting the dimensional levels and the Cubes (by double-clicking), you can directly access the object management window, with the preselection of the selected element.

To create a new Dimension, use the _**New**_ button or alternatively start from the pop-up menu (right-click) under _Dimensions_.

![](<../../../.gitbook/assets/image (176).png>)

A Wizard is run with the following five steps for defining:

1. The Dimension, in terms of descriptive parameters and data source. DAC also allows dimensions to be mapped on other databases, other than the DWH.
2. Dimensional levels, in terms of:
   * **mapping**, on the descriptive fields of the dimensional tables
   * setting the **key**, used for the hierarchies
   * **customizations**, for both the descriptive part and the level key
   * report **sorting**
3. The hierarchical link between dimensional levels
4. Hierarchy mapping, by identifying the external key of the child, to be linked in join to the parent key (defined in step 2)

A dimension is modified by selecting it then clicking on _**Edit**_ from the pop-up menu. The item _**Delete**_ cancels the dimension.

The _**Edit as copy**_ item creates a copy of the dimension. _**Dependencies**_ displays the dependencies with other objects.

![](<../../../.gitbook/assets/image (637).png>)

## Copying a Dimension

Launch copy the Dimension from the Dimension pop-up menu by selecting _**Edit as copy**_

![](<../../../.gitbook/assets/image (656).png>)

The Creation Wizard is run again. It has all the elements preselected in the first step, except **the logical name of the Dimension.** Copy of \[name of original Dimension] is suggested for _the_ one displayed.

![](<../../../.gitbook/assets/image (423).png>)

In the next step the **logical names of the levels** are shown in red, indicating that they must be modified. Remember that the logical names of the levels must be unique for the application. They are shown in yellow _where a name is assigned that is already given to another level._

![](<../../../.gitbook/assets/image (474).png>)

## Name and Data Source (STEP 1)

The first step of the wizard defines the new dimension in terms of descriptive parameters and data source.

![](<../../../.gitbook/assets/image (362).png>)

The descriptive parameters are:

* _**Logical name**_, univocal inside the model and not editable after the creation of the dimension
* _**Display name**_ the name shown in the reports, which can also be edited after the dimension is created
* _**Description**_, optional

For the data source (_**Connection Settings**_), you can decide where the dimension data are retrieved:

* _**Model default**_, to be specified if the dimension data is reported in the data warehouse associated with the model.
* _**Local**_, to be specified if the dimension data are retrieved in a database on the same instance of the Data Model which DAC is connected to.

The selection of this item enables the _**Scheme Owner**_ field where the Data Model instance schemes are listed.

* _**Remote,**_ to be specified if the dimension data is reported in a remote Remote Connection.

&#x20;Selecting this item enables the menu with the list of data sources configured using the Datasource

the datasources are listed which an alias has been assigned to (_**alias-name property**_, on the Datasource Designer). For those _Custom_ types, also the Java communication class with DAC must be assigned (in _**customDBAdapterClass property**_).

![](<../../../.gitbook/assets/image (669).png>)

In case the connection to the data source fails, it will not be displayed in the list.

Selecting a remote data source enables the _**Scheme Owner**_ field where the remote database schemes are listed. The menu is empty if the connection with the data source fails.

Once the descriptive parameters and the data source are defined, press **Next** and the system moves to the next step of the dimension creation wizard. You are not asked to save the settings in this step (this occurs at the end of the Wizard in STEP 4).

## Mapping of Dimensional Levels Section (STEP 2)

The second step of the create new dimension wizard creates the dimensional levels and the mapping setting on the physical tables.

![](<../../../.gitbook/assets/image (239).png>)

Use the button or the pop-up menu to create a row for each level selecting by _**Create level.**_

![](<../../../.gitbook/assets/image (366).png>)

With the ![](/broken/files/-MeULeJkwGPeMlijQpD9) button, delete the level selected, or through the pop-up menu by choosing _**Delete level**_.

![](<../../../.gitbook/assets/image (747).png>)

A dimensional level is defined on each row by setting, for the **mapping**:

* the table (_**Table**_), where the key and the descriptive information of the level are present
* the key field (_**Column @ID**_), used to map manual hierarchies.

In the case of **multiple keys**, the other fields which contribute to defining the key are defined in the _**Additional joins**_ section.

Selecting _Additional joins_ opens a window listing the fields in the table that can be used to form the key (excluding the one in _**Column@ID**_).

* the descriptive field of the level (_**Column @DS**_).

The settings for the _**dimensional level**_ of the logical object are:

* _**Logical Name,**_ unique among the levels of all the Dimensions of the application
* _**Display Name,**_ used in the report.

**Note:**

_We strongly advise against using the same Display Name, even if the system allows it._

_The system warns you when you assign a name that was already used at another level by highlighting it in yellow. A tooltip also informs you that the name entered is a duplicate._

![](<../../../.gitbook/assets/image (326).png>)

_If a level with duplicate Display Name is used in a formula (such as in Filters) the logical name (rather than the display name) of the level will be displayed._

Properties are available for each level.

In the _Main_ group:

* _**description**_ the description
* _**default-sort**_ for the predefined sorting of the level on the reports, for the key field (_\<ID>_), the description field (_\<Description>) or (\<Custom Column>)._
  * _**Costum Column** :_&#x4C;evel items are sorted by selected column. The level will always keep sorting to the scenting level. Please see [data-sorting.md](../application/report-management/data-sorting.md "mention")&#x20;
* _**sort-type**_ sorting mode: ascending (_ASC_) or descending (_DESC_).
* _**level-type**_, format of the time data
* _**description-table**_ for mapping on associative data record and hierarchy tables
* _**parent-name**_, visibility of the parent level for the attribute levels
* _**level-global-name**_, configuration of the Global Dimension
* _**catalogue-web-visibility**_, visibility of the dimensional level to the end users

For the alternative keys, in the _Main_ and _Read SQL group:_

* _**ID-formula**_ and _**description-formula**_ (Main grou&#x70;_),_ _**Read-ID-formula**_ and _**Read-description-formula**_ (_Read SQL_ group) for the alternative keys and descriptions for the fields selected in _Column@ID_ and _Column@DS_

In the _PageBy_ group:

* _**default-opening-selection**_ establishes which value to propose as default, in case the level is placed in page-by in reports. The selectable items are:
  * _Selection_ saves the selected values
  * _First_ or _Last_ shows the first or last value
  * _Total_ to select the totaling element
  * _Page-by-content_ to automatically select all the elements in the list
* _**default-total-visibility**_, if the level is placed in page-by in the reports, the property establishes whether, by default, the level has the totaling item enabled or not.

In the _Parent-child-hierarchy group:_

* property for the mapping on dimensional levels with hierarchical links of the recursive type

Follow the procedure in the paragraph below for the levels to be defined as attributes.

The levels created are grouped by table and sorted by the _Display Name field_. Each grouping of levels on the same table has the same color as the rows.

Example: Level Mapping

![](<../../../.gitbook/assets/image (755).png>)

_Let’s hypothesize the creation of the Dimension on the product (PRODUCT), with the levels:_

_Product, Brand and Product Family,_

_This data is in the tables respectively as:_

_LK\_PRODUCT, LK\_BRAND and LK\_PROD\_FAM_

_To create each level, enter a row using the_![](/broken/files/-MeULeJnl3chXeMUdJRZ)_button and set:_



![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fpothole%2F-MeUFovgsj25ttwWVve7%2F-MeULeJnl3chXeMUdJRZ%2F19.png?generation=1626171160337186\&alt=media)

* _the table in Table_
* _the key field in Column @ID_
* _the descriptive field in Column @DS_

_Note that the system automatically completes the Logical Name ad Display Name with the name of the key field (without the ID suffix or prefix)._

_It is possible to create several dimensional levels which exist on the same table (_**Multiple selection**_) by selecting the table and the fields on which the levels are mapped._

Press the  button to open the **Level selection** window and select the following:



![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fpothole%2F-MeUFovgsj25ttwWVve7%2F-MeULeJoRiIzS1qgpVPn%2F20.png?generation=1626171160352544\&alt=media)

* table, from a drop-down menu listing the tables and on which text search is enabled (_read-only_ initial and not contained in the table name).
* the field/s, from the field list of the selected table. The list can be selected in multiple mode (checkbox).



![](<../../../.gitbook/assets/image (646).png>)

Once you have made a selection, press the **OK** button. The pop-up menu closes and a dimensional level is created for each field selected, with a:

* _key (_(**Column @ID**_)_ )_and description (_(**Column @DS**_)_) _mapped on the same field_
* (**Logical Name** _and_ ) (**Display Name**) _coinciding with the one of the table field_

Example: The Next Example Explains the Use of this Function

Step 1: Levels on the Same Table

![](<../../../.gitbook/assets/image (658).png>)

_A table is hypothesized for the Business Unit managers, which contains the information on the manager and his JOB CODE. In this case two levels must be created, associated with the same table (SM\_LK\_BUSINESS\_UNIT\_MANAGER):_

* _BU Manager on the field DS\_BUSINESS\_UNIT\_MANAGER_
* _JOB CODE BU Manager on the DS\_JOB\_BUSINESS\_UNIT\_MANAGER field_

_Then click on the button which opens the Level Selection pop-up window where you can select the LK\_BUSINESS\_UNIT\_MANAGER table and then the fields containing the desired information._

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fpothole%2F-MeUFovgsj25ttwWVve7%2F-MeULeJs8NiEGAS0mSVz%2F24.png?generation=1626171160346688\&alt=media)

Step 2: Levels on the same table

_When the pop-up closes, in the dimension creation window, the same amount of rows will be created as the fields selected in the pop-up. Column @ID and Column @DS are valued with the respective chosen field. The logical name and the display name also take on the field name of the table._

### Dimensional Level Attributes

On each level created it is possible to associate attributes, through the _**Select levels as attributes**_ item of the pop-up menu. The levels attributed will be used in the report, similarly to the normal levels, but will not contribute to the definition of the hierarchy, making the construction easier.

The attributes of a dimensional level are defined in the following way:

1. Create the dimensional level using the multiple-selection mode . One or more fields can be selected to map both the parent level and the attributes.
2. Open, on the main dimensional level, the pop-up menu (right button) and select _**Select levels as attributes:**_ a pop-up opens which shows all the levels mapped on the same table (those chosen in the next step).
3. Select the levels you want to set as attributes
4. Close the pop-up: the _attribute_ _levels_ appear indented compared to the main one

The **parent-name** property (in the **Property** section,**)** allows the level it is an attribute of, to be displayed.

Example: Dimensional Level Attribute

Step 1: Creating a Level and Its Attributes![](/broken/files/-MeULeJwmb9kGuDC5s52)



![](<../../../.gitbook/assets/image (42).png>)

_In the example, the customer dimension must be created, with the Client level having the information on the address, the telephone number and the city as attributes. All the data is in the SM\_LK\_CUSTOMER table._

_A multiple selection of the main level (DS\_CUSTOMER) and its attributes is performed (ADDRESS, CITY and PHONE\_NO)._

_Right-click on the main level and the pop-up menu appears. When selecting the item Select levels as attributes, the pop-up opens with the previously mapped levels, on the same table._

Step 2: Creating a Level and Its Attributes

![](<../../../.gitbook/assets/image (523).png>)

_By selecting the levels as attributes, when the pop-up closes, the attribute levels will be indented under the main one._

### Alternative Keys and Descriptions

You do not have to follow the standard procedure to define level keys and descriptions. Two modes are available:

* calculating the keys/descriptions before you create the datamart containing the report results, that is in the data selection query which is run on the source tables.

The **ID-formula** and **description-formula** properties are available to edit the key or the description, respectively. Both enable the corresponding **formula** property. Then a window opens where an SQL string can be entered. This will constitute the level key or description.

* calculate the keys/descriptions after the creation of the datamart, or in the data selection query performed on the generated datamart table (**Read-ID-formula/Read-description-formula**).

The following **Read SQL**: **Read-ID-formula** and **Read-description-formula** properties of the group are available, to edit the key or the description, respectively. Both enable the corresponding **formula** property. From this a window opens where it is possible to enter a SQL string and where the references to the application levels are permitted.

The keys and descriptions selected in one of these modes replace the choices made in **Column@ID** and **Column@DS**.

To replace the description in the properties (description-formula, Read-description-formula) using DAC TAGs is permitted.

Example: Description Formula

![](<../../../.gitbook/assets/image (129).png>)

_In this example, “Short DS” concatenated with a short description also appears next to the product name. The result of this mode replaces the one selected in Column @DS._

### Level Visibility on DAC

The dimensions defined in the application are available to the end users on DAC (only if matched to a cube).

![](<../../../.gitbook/assets/image (483).png>)



The users may enter a dimensional level in the published or new reports.

If you want to hide one or more levels of a dimension from the end user, disable the _**catalog-web-visibility property**_ of the level (_Properties_ section, _Main group_).

Instead if you want to make the visibility of a level dependent on the user, it is necessary to set the permissions at user group level.

## Dimensional Level Hierarchy (STEP 3)

The third step (please refer to step 1 and 2 of the previous example) of the new dimension creation wizard defines the hierarchies among the levels entered in the previous step.

Press the **New** button (bottom left) to create a new hierarchy. The system enables the fields for setting the descriptive parameters and hierarchy between the levels.

For the descriptive parameters the following is defined:

* logical name (_**Name**_), required
* _**Display Name**_), required
* the description (_**Description**_), optional

For the hierarchy between levels, select the levels that belong to the hierarchy from the one with the highest hierarchical order to the one with the most detail.

Levels are selected using the arrow ![](/broken/files/-MeULeK1hDXPakIdcFuw), from the Available _**levels**_ pane to the _**Selected levels pane**_.

![](<../../../.gitbook/assets/image (661).png>)

The selection of the levels must respect the hierarchical order. A hierarchy establishes the criterion to resolve the relations and retrieve the information of a level.

The arrows (next to the _Selected levels_ pane) allow you to modify the order of the hierarchy levels.

![](<../../../.gitbook/assets/image (650).png>)

![](<../../../.gitbook/assets/image (346).png>)

The hierarchies must share the last level of the dimension.

At the end of the level selection, press **Save** (bottom left) to save the settings.

The **New, Edit, Delete** and **Save** buttons create a new hierarchy, edit, delete or save it, respectively. In edit or creation mode, in place of the **Delete** button the **Cancel** button activates, which lets you clear the modifications. Advancing to the next step is also blocked (**Next** button disabled) in the edit phase.

If a hierarchy level no longer appears in the level definition screen, or it has become an attribute, it is highlighted in red in the create hierarchy step.

The order of the levels will be validated when Dimension creation is complete. A check is run to ensure the key field (Column@ID) defined for the parent level is in the table associated with the child level.

![](<../../../.gitbook/assets/image (355).png>)

_Let’s consider two levels, for example:_

_Table Customer Group LK\_CUSTOMER\_GROUP Column@ID: ID\_CUSTOMER\_GROUP_

_Customer Table: LK\_CUSTOMER_

_The hierarchy between the levels (Customer Group as parent of Customer) is validated if:_

_**LK\_CUSTOMER\_GROUP.ID\_CUSTOMER\_GROUP = LK\_CUSTOMER.ID\_CUSTOMER\_GROUP**_





## Manual Hierarchy Mapping (STEP 4)

The fourth and last step defines the manual mapping of the hierarchies defined in the previous step, when the one recognized automatically by the system is not valid. Please remember that if the names of the columns of the tables used to define the link between the various levels of a hierarchy are not identical, the system generates an error in the dimension creation. In this case, you must specify the join link to be performed.

![](<../../../.gitbook/assets/image (605).png>)

The system displays (on the left part of the screen) a tree menu (**Layers**) listing all the **hierarchies** defined by Dimension and whose levels of pertinence are specified for each one of them.

By selecting a dimensional level, belonging to a hierarchy, on the top right area, the key fields of the chosen level and the child level are reported; the latter is editable with one of the values, proposed by the system, from the table associated with the level during step 2 of the dimension creation wizard. The value selected will be used to create the relation (join) between the two tables.

_If the parent level and the child level are mapped on the same table, this operation is disabled._

The join between the two levels is directly specified in the bottom right text area. The area is enabled by activating the **Custom join** checkbox.

Press the **Finish** button, after performing all the activities, and the systems starts the consistency controls.

If the controls performed are successful, the new dimension creation wizard is successfully completed.

If the controls performed are not successful, the system shows an error message for each problem detected. The new Dimension is created when all the errors have been corrected.

## Time Level Format (level-type)

The **level-type** property is used by the time levels to define the format types they may assume: year, month, week and day.

This setting is only necessary if the level must be used by functions which require the time format type, as the forecasting functions.

![](<../../../.gitbook/assets/image (385).png>)

The setting of the time format type, for a certain level, is performed by selecting one of the items, proposed by the system, of the **level-type** property, in the **Property** section.

When you select an item other than the \<Normal>default item for the **level-type** property, the _following_ property is enabled:

* **time-format** to define the level format type. A window opens (shown in the figure) where the time data format corresponding to the one mapped in **Column@ID** is entered in the **Value** field based on the information in the legend. The result obtained from the format selected is shown in **Preview**.

When you select _\<DAY>_ for the **level-type** property the following property is also enabled:

* **format as locale**, to enable the display of the dates depending on the language set by the user (**Multilanguage function).**

Therefore, the date will be shown in the same language used by the user to access DAC.

You select one of the date formats listed in the format-type _**property.**_ The listed formats are differentiated according to the language you are connected to DAC with. For English, the formats will be month, day and year. In Italian, the format will be day, month and year, and so on for all languages supported by DAC.

![](<../../../.gitbook/assets/image (59).png>)

Selecting _\<Date>_ for the **level-type property** also enables the property:

* **view-format** which sets a customized formatting of the data fields of the database. From the button near the property, a window is opened, where in the **Value** field the time data format corresponding to the one mapped in **Column@ID** is entered by respecting the indications of the legend; in **Preview** the result is shown which is obtained from the chosen format.
*
*

![](<../../../.gitbook/assets/image (379).png>)

Example of How to Set the Local Date Format

![](<../../../.gitbook/assets/image (429).png>)

_The example shows how to set the formatting on local._

_On the dimensional level ID\_DAY, the formatting on local was applied. In this case, English is selected and the format type will be English._

![](<../../../.gitbook/assets/image (396).png>)

_The figure shows the report with the dimensional level ID\_DAY formatted._

## Mapping on Registry and Associative Tables (description table)

DAC recognizes the hierarchical link between levels with a corresponding link between the tables associated with the levels. In the case of hierarchy between year and month, DAC considers it valid if there is a link between the key field of the parent table, for the year, and one of the fields of the child table, for the month (external key).

There are cases where the link between two entities is not implemented this way, but rather on a third table, called associative. The scheme appears in a form of the type in the figure below, where the associative table contains the keys of the entities that are in relation to each other, while the descriptive part of the entity resides on an anagraphic table.

_For example, the link between product, category, customer and supplier is saved in the associative table, which only contains the keys of the entities. However, the descriptions of the entities are in the anagraphic tables, each of which being linked to the associative table through its key._

![](<../../../.gitbook/assets/image (292).png>)

The first type of parent-child hierarchical link is set with automatic or manual mode in the last step of the new dimension creation wizard.

The second type of hierarchical link, on the associative table, is defined in the second step of the new Dimension Creation Wizard, as follows:

1. Create each level by selecting the associative **table** in Table.

![](<../../../.gitbook/assets/image (132).png>)

1. Enable the **description-table checkbox** in the **Property** section, which enables the **table-name property** where the name of the anagraphic table is entered.



![](<../../../.gitbook/assets/image (634).png>)

After you have entered the table name, **Column@DS** lists the fields of the anagraphic table (**table-name**) and no longer those of the associative table (selected in **Table**). The fields of the associative table remain in **Column@ID.**

![](<../../../.gitbook/assets/image (381).png>)

1. Select the key field (**Column@ID**) of the level on the associative table, and the descriptive field (**Column@DS**) on the anagraphic table.



![](<../../../.gitbook/assets/image (766).png>)

1. Move to the next step to define the hierarchy. The hierarchical order of the levels defined on the associative table is not important, however it will be validated.

## Mapping on Levels with Recursive Hierarchy (Parent-Child)

DAC allows you to define the mapping on levels in recursive hierarchy among homogenous elements.

DAC also allows you to map unbalanced recursive hierarchy levels, like in the hierarchy between homogeneous elements. Typical examples are the hierarchy of the resources, compared to the company roles, or the income statement items. This unbalance is due to the fact that each branch of the hierarchy may have a variable number of levels.

These types of relations are recursive and are represented by the entity linked to the element in the hierarchy, in relation to itself, as shown in the figure.

![](<../../../.gitbook/assets/image (373).png>)

These relations are implemented through a table which contains at least the two fields relating to the parent and the child. This makes it easy to save unbalanced and recursive structures.

Step1: Recursive and Unbalanced Hierarchical Structure

![](<../../../.gitbook/assets/image (553).png>)

_Consider as an example the hierarchy structure of company roles, such as the one indicated in the figure. The structure has three branches with different lengths:_

* _The first two have three levels (from CEO to Sales Director and HR Manager)_
* _The last branch is structured on five levels (from CEO to Program Manager_**).**

Step 2: Implementation table

| **RESOURCE\_ID** | **RESOURCE\_NAME** | **ROLE**         | **PARENT\_ID** |
| ---------------- | ------------------ | ---------------- | -------------- |
| **1**            | Mario Rossi        | CEO              | 999            |
| **2**            | Filippo Verdi      | COO              | 1              |
| **3**            | Jennifer Tilly     | SALES DIRECTOR   | 2              |
| **4**            | Anna Bianchi       | HR MANAGER       | 2              |
| **5**            | Lisa Hamilton      | DELIVERY MANAGER | 2              |
| **6**            | Gavin Smith        | CLIENT ACCOUNT   | 5              |
| **7**            | Susan Terry        | PROGRAM MANAGER  | 6              |

_The table that saves the structure has the following fields:_

* _RESOURCE\_ID resource key_
* _RESOURCE\_NAME name of the resource_
* _ROLE description of the role_
* _PARENT\_ID external parent key_

_The first hierarchical element does not have a parent and is defined in this implementation as a condition for identifying this first level ID\_PARENT = 999._

DAC provides the mapping of these structures, by suitably configuring the dimension:

* a sufficient number of levels is defined to contain the hierarchical structure (STEP 2)

_In the previous example there are 5 levels to map, each corresponding to a hierarchical level, starting from the CEO up to the PROGRAM MANAGER._

* each level is mapped on the same table, containing the parent-child relations
* the key and description for each level are mapped on the respective table fields, which refer to the child

_In the example the levels are mapped on RESOURCE\_ID for the key, and RESOURCE\_NAME or ROLE for the description, depending on whether you wish to publish the structure by resource or role._

* the levels are enabled to the recursive parent-child configuration, through the _**parent-child-level**_ property (_Parent-child-hierarchy group_); this enables the property:
  * _**hierarchy-root**_ to assign the level as root (first level in the hierarchy), which in turn enables:
    * _**root-where-condition**_, for the condition that identifies the first level
    * _**parent-column**_ for selecting the field containing the parent key

The property _**parent-child-level**_ is essentially enabled for all the levels and ONLY for the first hierarchical level (_the CEO in the example_) is the _**hierarchy-root**_ enabled, and the other two are configured properly.

* A hierarchy is defined among the level that respects the one to be represented, without forgetting that it must defined in a descending order (level 1level 2 level 3, etc.)

When you create the Dimension, the system performs a series of checks on the definition of the hierarchy (such as the presence of a single root). Then it generates a denormalized table containing a number of columns, which coincides with the levels defined in step two. The value of the last sheet is repeated on the missing levels for the unbalanced branches.

The saving schema of the table depends on the datasource of the dimension, chosen in the first step of creation of the same dimension:

* If a local data source, this coincides with the Data Model schema
* If a remote data source, this coincides with the database schema, pointed to by the connection defined in the remote data source.

A final message shows the name of the table (with prefix DZ).

Step 1: Mapping Dimension on DAC

![](<../../../.gitbook/assets/image (45).png>)

_Regarding the example, the mapping which defines the dimension on Decisyon is created in the following way:_

* _The same number of levels is created as those in the hierarchy structure: 5 (those of the longest branch)_
* _For each level the table created previously is associated (step 2 of this example): the key is the resource one, the description is the field relating to the role; the parent-child-level property is selected at each level_
* _The hierarchy-root property is enabled at the first level (Role1) and the following is defined:_
  * &#x20;_the condition which identifies the first level: PARENT\_ID = 999; a window opens with the fields of the table associated with the level. Conditions on different tables may also be included in the formula._
  * _The key field relating to the parent: PARENT\_ID_
* _The hierarchy is defined among the 5 levels, in the standard mode: at the top of the highest level of hierarchical order, down to the lowest order_

Step 2: Denormalized table of the Dimension

| ROLE1\_ID | ROLE1\_DS | ROLE2\_ID | ROLE2\_DS | ROLE3\_ID | ROLE3\_DS        | ROLE4\_ID | ROLE4\_DS      | ROLE5\_ID | ROLE5\_DS       |
| --------- | --------- | --------- | --------- | --------- | ---------------- | --------- | -------------- | --------- | --------------- |
| 1         | CEO       | 2         | COO       | 3         | SALES DIRECTOR   | 3         | SALES DIRECTOR | 3         | SALES DIRECTOR  |
| 1         | CEO       | 2         | COO       | 5         | DELIVERY MANAGER | 6         | CLIENT ACCOUNT | 7         | PROGRAM MANAGER |
| 1         | CEO       | 2         | COO       | 4         | HR MANAGER       | 4         | HR MANAGER     | 4         | HR MANAGER      |

_The generated denormalization table is the one shown in the figure, where there is a number of rows equal to the branches of the hierarchical structure._

_Note that for the shortest branches, the last useful level is repeated on those missing: HR MANAGER and SALES DIRECTOR are repeated on levels four and five (missing for these first two branches)._

Step 3: Report on the Dimension (DRILL)![](/broken/files/-MeULeKPvtDT1boWVIHN)

![](<../../../.gitbook/assets/image (548).png>)

_The report presents the dimensional levels with data in a denormalized form; in the grouping of the dimensional levels, the drill on the levels that have the same name is disabled:_

_the system enters the_ _TAG <@DRILL=0>_ _automatically on the levels with the repeated value (on level 3 for SALES DIRECTOR and HR MANAGER)._

The creation of the denormalized table may take place when editing the dimension or when executing the report containing the levels.

In addition, it is possible to choose whether the table must be generated from scratch or only repopulated. If the table must be generated from scratch, structural modifications to the dimension are supported, such as the addition of another level to the recursive hierarchy. If the table must only be repopulated, only the value or number of branches is updated inside the structure, therefore in a design end phase, where the levels of the hierarchical structure have now been established.

This configuration is set in the _**hierarchy-build-method property**_, enabled for the first level (_selected hierarchy-root_):

* With _\<drop-create>,_ the denormalized table is recreated at each request (running a report or modifying a Dimension).
* With _\<delete-insert>,_ the denormalized table is repopulated at each request.

The table creation takes place when saving the dimension. It may also be regenerated at each execution of the report with parent-child type levels: if this is the case, the creation of a denormalized table respects the methods set in the _hierarchy-build-method property_.

## **TUTORIAL**

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/CreateDimension/CreateDimension.mp4" %}



##
