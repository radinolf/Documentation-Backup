# Parent Child Dimension

DAC allows you to define the mapping on levels in recursive hierarchy among homogenous elements.

DAC also allows you to map unbalanced recursive hierarchy levels, like in the hierarchy between homogeneous elements. Typical examples are the hierarchy of the resources, compared to the company roles, or the income statement items. This unbalance is due to the fact that each branch of the hierarchy may have a variable number of levels.

These types of relations are recursive and are represented by the entity linked to the element in the hierarchy, in relation to itself, as shown in the figure.

![](<../../../.gitbook/assets/image (192).png>)

These relations are implemented through a table which contains at least the two fields relating to the parent and the child. This makes it easy to save unbalanced and recursive structures.

Step1: Recursive and Unbalanced Hierarchical Structure

![](<../../../.gitbook/assets/image (1296).png>)

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

![](<../../../.gitbook/assets/image (950).png>)

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

![](<../../../.gitbook/assets/image (145).png>)

_The report presents the dimensional levels with data in a denormalized form; in the grouping of the dimensional levels, the drill on the levels that have the same name is disabled:_

_the system enters the_ _TAG <@DRILL=0>_ _automatically on the levels with the repeated value (on level 3 for SALES DIRECTOR and HR MANAGER)._

The creation of the denormalized table may take place when editing the dimension or when executing the report containing the levels.

In addition, it is possible to choose whether the table must be generated from scratch or only repopulated. If the table must be generated from scratch, structural modifications to the dimension are supported, such as the addition of another level to the recursive hierarchy. If the table must only be repopulated, only the value or number of branches is updated inside the structure, therefore in a design end phase, where the levels of the hierarchical structure have now been established.

This configuration is set in the _**hierarchy-build-method property**_, enabled for the first level (_selected hierarchy-root_):

* With _\<drop-create>,_ the denormalized table is recreated at each request (running a report or modifying a Dimension).
* With _\<delete-insert>,_ the denormalized table is repopulated at each request.

The table creation takes place when saving the dimension. It may also be regenerated at each execution of the report with parent-child type levels: if this is the case, the creation of a denormalized table respects the methods set in the _hierarchy-build-method property_.
