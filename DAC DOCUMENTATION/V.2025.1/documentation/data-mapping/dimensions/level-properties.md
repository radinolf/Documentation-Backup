# Level properties

## Properties

For each dimensional level you can configure specific properties that explain below.

<figure><img src="../../../.gitbook/assets/image (1201).png" alt=""><figcaption></figcaption></figure>

Properties are available for each level.

In the _**Main**_ group:

* **metadataInfo**&#x20;
* **description** : Enter a description for the dimensional level.
*   **data-type:** It is possible to define the type of data containing the dimensional level:

    \<Auto>\<Number >\<String/Text >\<Date >\<Epoch >\<URL >\<Picture/Icon >\<Boolean>
*   &#x20;**level-type** It's used for time-related applications (forecasting). \<Year>\<Month>\<Week>\<Day>

    \<Date>

    * **time-format:** Set the data format for the level ID field. It is used for time.related applications (forecasting).
* **description-table :** Enables the use of a table containing the level description. The system will automatically join the table in the form: TABLE\_LEVEL.ID\_LEVEL.
  * **table-name:** Set the name of the table containing the level description
* **id-formula:** Enables the use of a SQL formula to be used the level ID field, for the select statement. It is used as an alternative to the level column.
  *   **formula**: configure the SQL formula used as ID af the level, for the select statement

      <figure><img src="../../../.gitbook/assets/image (807).png" alt=""><figcaption></figcaption></figure>


* **default-sort:** Sets the methods for arranging level values inside the report.
  * \<iD>:sort level values by ID
  * \<Description>:sort level values by Description
  *   \<Custom Column>: Sort the values of the layer based on the values of a specific layer. Selecting this orination enables the property :&#x20;

      * **custom-column: Sets** the column that should be used to sort the level's values

      See example [Data sorting ](../../report/execution/data-sorting/)
* **sort-type:** sets the sorting type of layer items (_ASC_) or  (_DESC_).
* **null-sort** : sets the NULLs values sorting strategy (FIRST) or (LAST). NULLs appear before of after non-NULL values. Warning! Clause activate only on datasource that natively support it.&#x20;
* **parent-name:** Name of the parent level that is associated the attribute level.
* **catalogue-web-visibility** Enables the visualizzation of the object within its catalog in the web environment.
  * **groups-enabled:** It sets the groups or users enabled to view the object. If no elemente is selected, all the users will be enabled automatically .

In the _**PageBy**_ group:

* _**default-opening-selection**_ establishes which value to propose as default, in case the level is placed in page-by in reports. The selectable items are:
  * _Selection:_ saves the selected values
  * _First:_ or _Last_ shows the first or last value
  * _Total_ : to select the totaling element
  * _Page-by-content:_ to automatically select all the elements in the list
* _**default-total-visibility**_, Sets the default value for presence of totalization value \[Total] in a page by where the level is associated with. The behavior is aplied in the opening phase of a report in which th level is arranged in a page-by.

In the _**Parent-child-hierarchy** group:_

* _**parent-child -level**: set the level as belonging to the parent-child hierarchy_
  * **hierarchy-root:** set the level as the root of parent-child hierarchy. Only one levels can be the root of the hierarchy
    * **root-where-condition** Sets the SQL necessary condition to identify the root of the hierarchy (eg."PARENT\_COLUMN")
    * **parent-colum:** set the table column used to make the join action in parent-child relationship
    * **hierarchy-build-method:** Sets the method for generating denormalization table.&#x20;
      * &#x20;**< drop-create >** drop and create again the denormalized table. This option should be used only in the design phase of the dimension or when changing its structure
      * **\<delete-insert>** delete and the insert again the records of the denormalized table.&#x20;

For the alternative keys, in the _Main_ and _Read_ **SQL group**_:_

*   _**Read-ID-formula:**_ enable the parametrization of th query to read data associated with the level, carried out when the same is incorporated within a report

    * _**formula:**_ The property allows customiation of the query for loading data corresponding to the level, when it is incorporated within a report. LogicalName@id and LogialName@Description notation may be used in the formula to refer to the ID and Level Description elements.

    _E.g. (CASE WHEN Status@id in (1,2,3) then 'approved' alese 'Rejected end). The formula cannot contain Decisyon TAG (eg: ) or tags (eg:<@FILE)_
* _**Read-description-formula**_ _&#x65;_&#x6E;able the parametrization of th query to read data associated with the level, carried out when the same is incorporated within a report
  *   **formula** The property allows customiation of the query for loading data corresponding to the level, when it is incorporated within a report. LogicalName@id and LogialName@Description notation may be used in the formula to refer to the ID and Level Description elements.

      _E.g. (CASE WHEN Status@id in (1,2,3) then 'approved' alese 'Rejected end). The formula cannot contain Decisyon TAG concatenated to the value of the level (eg Oravle: CASE WHEN Status@ID)_

## Visibility

The dimensions defined in the application are available to the end users on DAC (only if matched to a cube).

![](<../../../.gitbook/assets/image (1619).png>)



The users may enter a dimensional level in the published or new reports.

If you want to hide one or more levels of a dimension from the end user, disable the [_**catalog-web-visibility property**_](level-properties.md#properties) of the level (_Properties_ section, _Main group_).

Instead if you want to make the visibility of a level dependent on the user, it is necessary to set the permissions at user group level.

