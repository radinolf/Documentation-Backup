# Creating Dimensions

The new Dimension Creation Wizard is launched from the menu item:

**Data Model>> Dimensions management…,**

or from the toolbar by pressing the button ![](<../../../.gitbook/assets/image (197).png>)

A window with a list of Dimensions opens on the left side of the page.

<figure><img src="../../../.gitbook/assets/image (208).png" alt=""><figcaption></figcaption></figure>

When a Dimension is selected, the following appears on the right:

* details on the logical name, creation date, last modification, creator and author of the last modification;
* the Cubes in which the Dimension is associated
* the dimensional levels
* by selecting the dimensional levels and the Cubes (by double-clicking), you can directly access the object management window, with the preselection of the selected element.

To create a new Dimension, use the _**New**_ button or alternatively start from the pop-up menu (right-click) under _Dimensions_.

![](<../../../.gitbook/assets/image (239).png>)

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

![](<../../../.gitbook/assets/image (267).png>)

## Step 1 - Definition

The first step of the wizard defines the new dimension in terms of descriptive parameters and data source.

![](<../../../.gitbook/assets/image (587).png>)

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

![](<../../../.gitbook/assets/image (243).png>)

In case the connection to the data source fails, it will not be displayed in the list.

Selecting a remote data source enables the _**Scheme Owner**_ field where the remote database schemes are listed. The menu is empty if the connection with the data source fails.

Once the descriptive parameters and the data source are defined, press **Next** and the system moves to the next step of the dimension creation wizard. You are not asked to save the settings in this step (this occurs at the end of the Wizard in STEP 4).

## Step 2 - Levels

The second step of the create new dimension wizard creates the dimensional levels and the mapping setting on the physical tables.

![](<../../../.gitbook/assets/image (28).png>)

Use the button or the pop-up menu to create a row for each level selecting by _**Create level.**_

![](<../../../.gitbook/assets/image (929).png>)

With the ![](/broken/files/-MeULeJkwGPeMlijQpD9) button, delete the level selected, or through the pop-up menu by choosing _**Delete level**_.

![](<../../../.gitbook/assets/image (777).png>)

A dimensional level is defined on each row by setting, for the **mapping**:

* the table (_**Table**_), where the key and the descriptive information of the level are present
* the key field (_**Column @ID**_), used to map manual hierarchies.

### Multiple Key

In the case of **multiple keys**, the other fields which contribute to defining the key are defined in the _**Additional joins**_ section.

Selecting _Additional joins_ opens a window listing the fields in the table that can be used to form the key (excluding the one in _**Column@ID**_).

* the descriptive field of the level (_**Column @DS**_).

The settings for the _**dimensional level**_ of the logical object are:

* _**Logical Name,**_ unique among the levels of all the Dimensions of the application
* _**Display Name,**_ used in the report.

{% hint style="info" %}
We strongly advise against using the same Display Name, even if the system allows it.
{% endhint %}

_The system warns you when you assign a name that was already used at another level by highlighting it in yellow. A tooltip also informs you that the name entered is a duplicate._

![](<../../../.gitbook/assets/image (299).png>)

_If a level with duplicate Display Name is used in a formula (such as in Filters) the logical name (rather than the display name) of the level will be displayed._



**Example: Level Mapping**

![](<../../../.gitbook/assets/image (178).png>)

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



![](<../../../.gitbook/assets/image (976).png>)

Once you have made a selection, press the **OK** button. The pop-up menu closes and a dimensional level is created for each field selected, with a:

* _key (_(**Column @ID**_)_ )_and description (_(**Column @DS**_)_) _mapped on the same field_
* (**Logical Name** _and_ ) (**Display Name**) _coinciding with the one of the table field_

Example: The Next Example Explains the Use of this Function

Step 1: Levels on the Same Table

![](<../../../.gitbook/assets/image (106).png>)

_A table is hypothesized for the Business Unit managers, which contains the information on the manager and his JOB CODE. In this case two levels must be created, associated with the same table (SM\_LK\_BUSINESS\_UNIT\_MANAGER):_

* _BU Manager on the field DS\_BUSINESS\_UNIT\_MANAGER_
* _JOB CODE BU Manager on the DS\_JOB\_BUSINESS\_UNIT\_MANAGER field_

_Then click on the button which opens the Level Selection pop-up window where you can select the LK\_BUSINESS\_UNIT\_MANAGER table and then the fields containing the desired information._

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fpothole%2F-MeUFovgsj25ttwWVve7%2F-MeULeJs8NiEGAS0mSVz%2F24.png?generation=1626171160346688\&alt=media)

Step 2: Levels on the same table

_When the pop-up closes, in the dimension creation window, the same amount of rows will be created as the fields selected in the pop-up. Column @ID and Column @DS are valued with the respective chosen field. The logical name and the display name also take on the field name of the table._

## Step 3 - Hierarchy

The third step (please refer to step 1 and 2 of the previous example) of the new dimension creation wizard defines the hierarchies among the levels entered in the previous step.

Press the **New** button (bottom left) to create a new hierarchy. The system enables the fields for setting the descriptive parameters and hierarchy between the levels.

For the descriptive parameters the following is defined:

* logical name (_**Name**_), required
* _**Display Name**_), required
* the description (_**Description**_), optional

For the hierarchy between levels, select the levels that belong to the hierarchy from the one with the highest hierarchical order to the one with the most detail.

Levels are selected using the arrow ![](/broken/files/-MeULeK1hDXPakIdcFuw), from the Available _**levels**_ pane to the _**Selected levels pane**_.

![](<../../../.gitbook/assets/image (703).png>)

The selection of the levels must respect the hierarchical order. A hierarchy establishes the criterion to resolve the relations and retrieve the information of a level.

The arrows (next to the _Selected levels_ pane) allow you to modify the order of the hierarchy levels.

![](<../../../.gitbook/assets/image (290).png>)

![](<../../../.gitbook/assets/image (799).png>)

The hierarchies must share the last level of the dimension.

At the end of the level selection, press **Save** (bottom left) to save the settings.

The **New, Edit, Delete** and **Save** buttons create a new hierarchy, edit, delete or save it, respectively. In edit or creation mode, in place of the **Delete** button the **Cancel** button activates, which lets you clear the modifications. Advancing to the next step is also blocked (**Next** button disabled) in the edit phase.

If a hierarchy level no longer appears in the level definition screen, or it has become an attribute, it is highlighted in red in the create hierarchy step.

The order of the levels will be validated when Dimension creation is complete. A check is run to ensure the key field (Column@ID) defined for the parent level is in the table associated with the child level.

![](<../../../.gitbook/assets/image (258).png>)

_Let’s consider two levels, for example:_

_Table Customer Group LK\_CUSTOMER\_GROUP Column@ID: ID\_CUSTOMER\_GROUP_

_Customer Table: LK\_CUSTOMER_

_The hierarchy between the levels (Customer Group as parent of Customer) is validated if:_

_**LK\_CUSTOMER\_GROUP.ID\_CUSTOMER\_GROUP = LK\_CUSTOMER.ID\_CUSTOMER\_GROUP**_



## Step 4 - Joins

The fourth and last step defines the manual mapping of the hierarchies defined in the previous step, when the one recognized automatically by the system is not valid. Please remember that if the names of the columns of the tables used to define the link between the various levels of a hierarchy are not identical, the system generates an error in the dimension creation. In this case, you must specify the join link to be performed.

![](<../../../.gitbook/assets/image (333).png>)

The system displays (on the left part of the screen) a tree menu (**Layers**) listing all the **hierarchies** defined by Dimension and whose levels of pertinence are specified for each one of them.

By selecting a dimensional level, belonging to a hierarchy, on the top right area, the key fields of the chosen level and the child level are reported; the latter is editable with one of the values, proposed by the system, from the table associated with the level during step 2 of the dimension creation wizard. The value selected will be used to create the relation (join) between the two tables.

_If the parent level and the child level are mapped on the same table, this operation is disabled._

The join between the two levels is directly specified in the bottom right text area. The area is enabled by activating the **Custom join** checkbox.

Press the **Finish** button, after performing all the activities, and the systems starts the consistency controls.

If the controls performed are successful, the new dimension creation wizard is successfully completed.

If the controls performed are not successful, the system shows an error message for each problem detected. The new Dimension is created when all the errors have been corrected.
