# Alternative Keys and Descriptions

You do not have to follow the standard procedure to define level keys and descriptions. Two modes are available:

* calculating the keys/descriptions before you create the datamart containing the report results, that is in the data selection query which is run on the source tables.

The **ID-formula** and **description-formula** properties are available to edit the key or the description, respectively. Both enable the corresponding **formula** property. Then a window opens where an SQL string can be entered. This will constitute the level key or description.

* calculate the keys/descriptions after the creation of the datamart, or in the data selection query performed on the generated datamart table (**Read-ID-formula/Read-description-formula**).

The following **Read SQL**: **Read-ID-formula** and **Read-description-formula** properties of the group are available, to edit the key or the description, respectively. Both enable the corresponding **formula** property. From this a window opens where it is possible to enter a SQL string and where the references to the application levels are permitted.

The keys and descriptions selected in one of these modes replace the choices made in **Column@ID** and **Column@DS**.

To replace the description in the properties (description-formula, Read-description-formula) using DAC TAGs is permitted.

Example: Description Formula

![](<../../../.gitbook/assets/image (1798).png>)

_In this example, “Short DS” concatenated with a short description also appears next to the product name. The result of this mode replaces the one selected in Column @DS._
