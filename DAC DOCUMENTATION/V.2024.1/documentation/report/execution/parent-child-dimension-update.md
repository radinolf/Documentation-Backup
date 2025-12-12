# Parent-child dimension update

DAC dimensions also support the mapping of structures with recursive hierarchies. Used for structures on homogeneous elements, such as a company organizational chart (see _Mapping on Levels with Recursive Hierarchy (parent-child)_ section), dimensions of this type are supported by a denormalization table that contains information on the hierarchy, facilitating the management of asymmetric branches and preventing the drill to empty levels.

The table is generated during the creation of the dimension itself, but you may need to to update it. For example, an update may be necessary because a new branch was added to the structure, or a new child was added to one of the levels.

The table is updated each time the report is run (only if it is not in cache), if the _**denormalize-PC-hierarchies**_ property is enabled in the _Execution_ group.

Therefore, this property can be used to schedule the update of the denormalization table: we just have to enable the property on one of the reports that includes the recursive dimension, and to insert it in an updating rule _with the Scheduler_ module (see the _Scheduler_ chapter).

We remind users that it is possible to configure on the dimension the type of creation of the denormalization table, whether the table is created from scratch or repopulated. If the table is created from scratch, structural modifications to the dimension, such as the addition of another level to the recursive hierarchy, are supported. If the table is repopulated, only the value or number of branches is updated inside the structure.
