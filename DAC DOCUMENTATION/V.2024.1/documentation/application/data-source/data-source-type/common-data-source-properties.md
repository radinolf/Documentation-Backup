# Common Data Source Properties

There are properties that are applicable for any type of data source (Main Group) and properties that are specific to the selected data source (Database Group)

The properties of the Main group are

_**alias-name**_ it’s a mandatory properties that is used to uniquely identify this data source in the application. The alias will be displayed when you need to select an external data source during the data mapping.

This name will appear in the list of the external data sources (**Remote**) (only for Excel file (.xlsx) CSV XML Rest/JSON)

* _**max-rows-selected**_ to define the maximum limit allowed for responses to queries on the data source
* _**is-read-only**_ for data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.

The native data sources for read only have the property enabled and not modifiable; some example are the flat files.

If the property is disabled, i.e. for NOT READ-ONLY data source, the property is available:

* _**integrate-metric-functions**_ can be enabled only on the data sources which ARE NOT READ-ONLY. If enabled, in case the operation being performed (for example the execution of a report) includes the _metric- functions_, these will not be run on the remote database, but the temporary tables will be created in the local Data Model and the metric-functions will be applied here.
