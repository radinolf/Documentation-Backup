# EXCEL INTEGRATION

## Overview

The Excel Integration allows the user of an Excel file to be loaded in a database table and later processed. Files are uploaded using the **File Selector** widget, choosing the EXCEL\_INTEGRATION option available in the **upload-type** property.

When the user clicks on Execute button, the copy of the data from the Excel files (uploaded with the Files Selector widget) is started in a database table.

### Execution-type Properties

The properties that are specific for the configuration of the **Execution-type EXCEL\_INTEGRATION** are listed below:

<table><thead><tr><th width="275">Specific Properties</th><th width="252">Description</th><th width="133" align="center">Type</th><th width="148" align="center">Default Value</th><th width="358" data-type="checkbox">Allow Page Parameters</th><th data-hidden>Group</th></tr></thead><tbody><tr><td><strong>integration-name*</strong></td><td>Enter the name of the parameter exported by the object. It will contain the identifier of the last data imported from the Excel file. </td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>file-selector-name*</strong></td><td>Select the page parameter containing the identifier of the <strong>File selector</strong> widget used to upload the Excel file. </td><td align="center">SELECT</td><td align="center"></td><td>true</td><td></td></tr><tr><td><strong>sheet-to-copy*</strong></td><td>Enter the name of the Excel spreadsheet containing the data to be copied to the table.</td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>destination-table-name*</strong></td><td>Allows you to set the table in which to copy the data read from the Excel file.</td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>destination-table-definition</strong></td><td>Allows definition of the table structure where data read from the Excel file will be copied.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>custom-datasource</strong></td><td><p>Enable the property to use a custom data source for the destination table of data read from the Excel file. The activation of this property enables: </p><ul><li><strong>data source</strong>:  select the data source that contains the integration table. A dialog is opened with the list of the editable data sources defined in the <strong>Data sources designer</strong>.</li></ul></td><td align="center">SWITCH</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>post-import-procedures</strong></td><td>Allows you to define SQL code to be executed after the uploading of data from Excel. The post-import operations may work for the last rows inserted or modified in the integration table: the setting is assigned a value in the <strong>integration-name</strong> property that identifies it univocally.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr></tbody></table>







