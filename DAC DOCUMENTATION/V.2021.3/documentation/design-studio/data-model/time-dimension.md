# Time Dimension

The Time Dimension may be created directly using DAC according to the following methods, which you can access from the **Metadata >> Time Dimension menu:**

* _Creation Tables_

For the creation of tables in the data warehouse (data scheme, selected in the DAC application)

* _**Populate time tables**_

For the population of the time tables

* _**Creating dimension**_

For the creation of the time dimension (TIME): the system automatically performs the mapping among the dimensional levels _Day, Week, Month, Quarter, Year_ and the respective tables created in the first step.

The TIME dimension uses the time functions to be applied to the metrics of the application, such as the one of the previous year or the previous month and so on.

When the data application of the data warehouse is used for several DAC applications, the table creation and population operations will be performed only on one DAC application; for the other applications only the creation of the TIME dimension is required.

### Table Creation

When _**Table Creation**_ is selected, the system creates the actual structure of the TIME dimension, with the tables:

**LK\_DATE** is the dimensional table relating to the Day and Week levels;

**LK\_MONTH** is the look-up relating to the Month level;

**LK\_QUARTER** relates to the Quarter level;

**LK\_YEAR** relates to the Year level.

![](<../../../.gitbook/assets/image (223).png>)



All of the time tables are deleted and recreated.

All of the transposition tables are also created to apply the time functions to the Metrics.

### Populating Tables

When _**Populate Tables**_ is selected, the system populates the TIME Dimension tables using a Wizard, as illustrated below.

![](<../../../.gitbook/assets/image (210).png>)

In the first window, select the **Begin date** and **End date** for the time interval.

The interval must cover the entire time period on which you want to perform an analysis.

In the second window of the wizard, select the **language** and **format** that you want for each level.

For each of them two formats are selected:

* one for the **short description**, associated by default to the _**Column @DS**_
* and the other for the **extended description**.

After the format is selected, a preview appears on the side.

![](<../../../.gitbook/assets/image (214).png>)

If the formats listed in the drop-down menus do not satisfy your needs, you may define others.

with the **+** button near the description (short or extended) of the level to be edited, a window opens where you set the new format. The legend below the Insert date format field shows you the valid formats.

With the Next button, the population of the time tables starts according to the settings in the wizard.

The time Dimension may also be populated several times, without having to repeat step 1 in table creation. In this case, the system warns you that it will delete all the data in the time tables and that it will replace them with the new settings.

### Creating a TIME Dimension

By selecting the last item, _**Creating dimension**_, the system asks the user to confirm the operation and warns that it has ended with a successful creation message.

At the end of the procedure, you will have the new **TIME** Dimension defined, as shown in the figure.

![](<../../../.gitbook/assets/image (201).png>)

You can integrate additional levels within the TIME Dimension, such as:

* **Month of the year**
* **Quarter of the year**;

during the creation of the physical structure, in the data warehouse also the two tables LK\_MONTH\_OF\_YEAR and LK\_QUARTER\_OF\_YEAR are created.

**Note:**

_TIME Dimension levels cannot be deleted because they are required when using Metrics with time transformation._

_Hierarchy cannot be edited or deleted either. You can add additional levels to the Dimension and associate them with a new hierarchy._
