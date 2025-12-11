# Users

User Filters (Data Privileges)
------------------------------

User Filters restrict data viewing by users on all logical objects published in DAC, such as crosstabs, graphs, indicators, etc.

To start the user filter wizard: from the menu bar, select **Users** and **User filter** management; otherwise from the tool bar, select the button.

![](<../../.gitbook/assets/image (19).png>)

![](<../../.gitbook/assets/image (24).png>)

The Filter condition is applied to the groups selected in the bottom left pane.

In the example a User filter was created which limits, for all the users of the Developers Group, the display of the data only relating to the specific Asset (Asset@ID = 1 condition)

The User Filter will be applied to each analysis containing at least one Metric, which belongs to a Cube containing the selected dimension.

It is worth using the cache (Cache section), entering the dimensional levels used in the security filter condition, to improve the execution speed of the reports.

In addition, if the report is enabled to use the **automatic cache**, **in no case will this cache be created**.

In the security filters section the System Parameters can be used. They are described in the DAC TAGS and System Parameters section.

The use of these parameters is especially useful to define a dynamic User Filter.

For example, if you have to enable a user with regard to a specific asset, you may work in two ways:

*   **STATIC**, where the phases are:

    * create a group asset
    * associate the competent users
    * define a User Filter on the asset for this group


* **DYNAMIC:**
  * create a unique group for the users concerned with the enabling on the asset
  * create a table where the users are associated with the competent asset
  * create a dimensional level (or a new dimension) on this table
  * create a dynamic User Filter containing the condition like the one shown in the figure

In this last case, maintenance is certainly less expensive than for the static case. In addition, the creation of a user-asset association table is less expensive in the definition phase than the creation of a group and a user filter for each province.
