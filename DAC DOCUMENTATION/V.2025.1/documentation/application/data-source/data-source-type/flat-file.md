# Flat File

## Introduction

Flat files can be used as a data source. The file must be rechable from Design Studio in order to properly configure the data source and from the web application in order to read it at run time.

The flat files available in the DAC are as follows:

* [Excel file (.xlsx)](flat-file.md#data-source-for-excel-files)
* [CSV file](flat-file.md#data-source-for-csv-files)

The file on the client is used to define the selection queries:the file is displayed like a table: the file name is used as “table name” and each file’s column is displayed as “table column”. The file on the server will be used when the connection to the data source requests the data from pages and widgets in the web application.

**Note:** Closing DAC-DS will close all connections opened by the data source.

### Data Source for Excel Files

<figure><img src="../../../../.gitbook/assets/image (440).png" alt=""><figcaption></figcaption></figure>

For the connection to Microsoft Excel, proceed as follows:

1. Select Excel file (.xlsx) as data source type.
2. In **File Path on Client** enter the path, including the Excel file on the _client_. The _Browse_ button opens the window to select the file.This file must be in the same client where Design Studio is executed
3. In **File Path on Server,** enter the path, including the Excel file on the DAC server. The path must start from the name of the unit present on the AS server, which must have visibility privileges on the folder where the file resides.

It is not possible to enter the HTTP path. In this case it is necessary to map the link as the folder on the server but reachable from the webapp.

![](<../../../../.gitbook/assets/4 (10)>)

Some validation criteria exist, which are applied to the Excel type data source:

* The name of the Excel file and the names of the first row of the same file must start with a letter
* The names of the columns can’t start with a character or with “\_”
* The first row cannot be empty because it is used as column name
* The first line of data cannot be a numerical value and the successive ones text, the contrary is allowed. Textually defining the values in the first line of data is sufficient (putting the first character in the cell for the first value).

### Data Source for CSV Files

Proceed as follows to connect to a CSV file:

1. Select CSV file as data source type.
2. Enter the path, WITHOUT the name of the local file, in **File Path on Client**. The Browse button opens the window to select the file.
3. Enter in **File Path on Server**, the path, WITHOUT the name of the file on the DAC AS server. The path must start from the name of the unit present on the AS server, which must have visibility privileges on the folder where the file resides.
4. Type the separator of the values (**Values** **Separator**), the **File Extension** and if the first row must be used for the names of the columns (**Use** **first row as column names**)

<figure><img src="../../../../.gitbook/assets/image (417).png" alt=""><figcaption></figcaption></figure>

If several CSV files exist in the folders indicated, the system will interpret them as differen tables.

## Flat File Data source Properties

Properties for the data source are explained in the table below. Some of these properties are in common between the various data sources Excel and CSV file



| PROPERTIES         | DESCRIPTION                                                                                                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Main**           |                                                                                                                                                                                                         |
| metadataInfo       | Information about the metadata of the data surce.                                                                                                                                                       |
| alias-name         | It’s a mandatory properties that is used to uniquely identify this data source in the application. The alias will be displayed when you need to select an external data source during the data mapping. |
| max-rows-selected  | To define the maximum limit allowed for responses to queries on the data source                                                                                                                         |
| dsrest-call-body   | To define the call body                                                                                                                                                                                 |
| dsrest-call-method | To define the call method                                                                                                                                                                               |
| is-read-only       | For data sources where writing is not permitted; the flag is already selected for the native data source for the reading only, like the flat files.                                                     |

