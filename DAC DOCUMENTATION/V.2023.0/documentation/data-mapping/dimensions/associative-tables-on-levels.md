# Associative tables on levels

## Mapping on Registry and Associative Tables (description table)

DAC recognizes the hierarchical link between levels with a corresponding link between the tables associated with the levels. In the case of hierarchy between year and month, DAC considers it valid if there is a link between the key field of the parent table, for the year, and one of the fields of the child table, for the month (external key).

There are cases where the link between two entities is not implemented this way, but rather on a third table, called associative. The scheme appears in a form of the type in the figure below, where the associative table contains the keys of the entities that are in relation to each other, while the descriptive part of the entity resides on an anagraphic table.

_For example, the link between product, category, customer and supplier is saved in the associative table, which only contains the keys of the entities. However, the descriptions of the entities are in the anagraphic tables, each of which being linked to the associative table through its key._

![](<../../../.gitbook/assets/image (262).png>)

The first type of parent-child hierarchical link is set with automatic or manual mode in the last step of the new dimension creation wizard.

The second type of hierarchical link, on the associative table, is defined in the second step of the new Dimension Creation Wizard, as follows:

1. Create each level by selecting the associative **table** in Table.

![](<../../../.gitbook/assets/image (348).png>)

1. Enable the **description-table checkbox** in the **Property** section, which enables the **table-name property** where the name of the anagraphic table is entered.



![](<../../../.gitbook/assets/image (735).png>)

After you have entered the table name, **Column@DS** lists the fields of the anagraphic table (**table-name**) and no longer those of the associative table (selected in **Table**). The fields of the associative table remain in **Column@ID.**

![](<../../../.gitbook/assets/image (1052).png>)

1. Select the key field (**Column@ID**) of the level on the associative table, and the descriptive field (**Column@DS**) on the anagraphic table.



![](<../../../.gitbook/assets/image (752).png>)

1. Move to the next step to define the hierarchy. The hierarchical order of the levels defined on the associative table is not important, however it will be validated.
