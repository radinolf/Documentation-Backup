# Page Export

_The title and description of the Page are shown at the top, as requested using the export-title and export-page-description properties._

_Had the separate-sheets property also been set, the two tables would have been positioned on two separate sheets, with the title and description of the Page on the first sheet._

#### Exporting With Template

Exporting a Page through a template requires the existence of an Excel file to be used as a template (xlsx format), built and saved in DAC-DS.

You can set the export with template via the following properties:

* _**export-with-template enables**_ the export through a template (by default the property is disabled)
  * _**template**_ lets you select the template _**from**_ the window of the resource catalog. The file containing the template must be previously loaded in the suitable catalog.
  * _**auto-adjust-col-wiDSh enables**_ the automatic dimensioning of the columns and rows to the larger content (default). If disabled, the columns and rows have the dimension set in the template.

The template may be made up of one or more Excel spreadsheets. The cells may have any formatting.

A set of specific TAGs will allow you to customize the export. Therefore, the export operation will replace each TAG with the object indicated.

If the template contains TAGs that are incorrect or are associated with non-existent objects, the resulting report will contain some cells in red, signaling the error in question.

The two examples show the construction of a template both in the case of exporting static Pages, i.e. whose tables do not change their number of rows depending on the choices made in the report, and dynamic Pages.

**Excel export TAG**

The exporting TAGs of the Page refer to the same Page and the reports contained in them.

Those relating to the mashboard are:

* _**\<PAGE\_TITLE/>**_

Title of the Page, corresponding to the value of the _**title-text**_ property of the Page (_Container_ folder, _ContainerStyle_ group).

* _**\<PAGE\_TITLE/>**_

Description of the Page, corresponding to the value of the _**description-text**_ property of the Page (_Container_ folder, _ContainerStyle_ group).

* _**\<Parameter? KEY:?Parameter?/>**_

Exporting values of the Page parameters (parameter name of the parameter)

| **Subject**                                     | **TAGS**                                                                                | **TYPE**                                      | **Excel cell occupation**                                                       |
| ----------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------------------------- |
| **Crosstabs**                                   | _\<OBJECT\_BODY ID: id\_num />_                                                         | Table form of the report                      | 1 Cell                                                                          |
| **Graph**                                       | _\<OBJECT\_BODY ID: id\_num \[type:val]/>\<OBJECT\_BODY ID: id\_num \[type:val\|img]/>_ | Table form of the report                      | Number of cells equal to the number of row by the number of columns of the body |
| _\<OBJECT\_BODY ID: id\_num \[type:val\|img]/>_ | Graphic form of the report                                                              | Cell number on which the image is overlapped. |                                                                                 |
| **Flag Setup**                                  | _\<OBJECT\_BODY ID: id\_num \[type:val]/>_                                              | Table form of the report                      | Number of cells equal to the number of row by the number of columns of the body |
| _\<OBJECT\_BODY ID: id\_num \[type:val\|img]/>_ | Graphic form of the report                                                              | Cell number on which the image is overlapped. |                                                                                 |
| **Map**                                         | _\<OBJECT\_BODY ID: id\_num/>_                                                          | Table form of the report                      | Number of cells equal to the number of row by the number of columns of the body |
| **Textfield**                                   | _\<OBJECT\_BODY ID: id\_num/>_                                                          | Selected item                                 | 1 Cell                                                                          |
| **Textarea**                                    | _\<OBJECT\_BODY ID: id\_num/>_                                                          | Selected item                                 | 1 Cell                                                                          |
| **Image**                                       | _\<OBJECT\_BODY ID: id\_num/>_                                                          | image                                         | Cell number on which the image is overlapped.                                   |
| **Text**                                        | _\<object\_body ID: id\_num/>_                                                          | Text of the element                           |                                                                                 |

The TAGs relating to the reports of the Page to be exported are a subset of those defined for the Excel exporting of the reports (see _Report Administrator, TAG exporting reports in Excel section_) and namely:

* _\<MODEL/>_
* _\<OBJECT\_TITLE ID:id\_num/>_
* _\<OBJECT\_DESCRIPTION ID: id\_num/>_
* _\<OBJECT\_BODY ID: id\_num \[type:val|img]/>_
* _\<METADATA ID: id\_num/>_
* _\<METRICS ID: id\_num/>_
* _\<LEVELS ID: id\_num/>_
* _<\<FILTERS/> ID: id\_num/>_
* _\<LEVELS ID: id\_num/>_
* _<\<RANGE\_FILTERS/> ID: id\_num/>_
* _<\<CUSTOM\_FILTERS/> ID: id\_num/>_

For each TAG referring to a component of the report, the ID of the same report must be indicated:

_for example \<METADATA ID: id\_num/>, where id\_num is the ID number of the object you want to export;_

When exporting reports the \<OBJECT\_BODY/> TAG is used to export the body of the report in table form. For Pages, this tag is used to move the body of the report both in table and graph format, regardless of the object it is associated with.

The syntax is as follows:

**\<OBJECT\_BODY ID: id\_num \[type:val|img]/>**

In the event that the id\_num refers to an image object, the type is indicated if the table or image part is exported, as described in the following table.

**An Example of Using Static Template Files**

The static template may be used if you are sure that the rows and columns of the reports do not incur any change in height and wiDSh. The static templates are configured without the help of the NEW\_COL and NEW ROW tags. In the Excel file each object must have as many rows and columns available as there are in the associated report. Below is an example.

Step 1: Page Designer

![](<../../../../.gitbook/assets/80 (3).png>)

_The example above shows the Page page to be exported. Starting from the other, the following objects were entered:_

Step 2: Template Configuration

![](../../../../.gitbook/assets/81.png)

_The template to export to Excel shows the same objects of the Page though arranged in the following way:_

1. _in the initial part of the page, a banner containing:_

* _Company logo and address_
* _The user who performed the analysis_
* _Date and time when the printing was carried out._

1. _in the lower part of the banner:_

* _left:_
* _year of analysis_
* _type of product brand_
* _right:_
* _Direct Unit Cost and Unit Cost of Sales report_

1. _next row:_

* _left:_

_the Year report will be used as the header of the columns, a drop-down menu will show the Unit Sales, Unit, price, Sales reports._

* _right_

_The Marketing Expense Budget report and the Annual expense Budget graph. These objects will be aligned to the center compared to the left reports. Below we will enter the Actual vs Year report in line with the Marketing Expense Budget report._

1. _In the lower part of the Excel spreadsheet, we will enter a section, Notes and signatures for approval, which will be compiled after printing._

_The image at the top shows the Excel file configured as previously described. For each object entered within, the rows and columns which will be occupied were left blank._

Step 3: Template Configuration

![](<../../../../.gitbook/assets/82 (3).png>)

_For example we know that the Unit Sales report occupies exactly 4 rows and 13 columns. Thus, in the Excel spreadsheet, this object was reserved as many rows as the columns required for the correct display. The same method was also used for the other elements which make up the Page._

Step 4: Export with Template

![](<../../../../.gitbook/assets/83 (1).png>)

_After the configuration of the template, the Page Designer is accessed again where the export property_

_activateExcExport will be activated._

_Choose the export with template from the export-mode property, while in the template-file-name property the name of the file created previously is entered._

_The figure shows the results of the export. Note that each object respects the position given inside the template._

Exporting With Dynamic Template

Exporting is defined with a dynamic template since the components of the Page do not always maintain the same dimensions, and the number of rows and columns of the reports change depending on the choices made on the Page.

Step 1: Page Designer

![](<../../../../.gitbook/assets/84 (3).png>)

_The example above shows the Page page to be exported. Starting from the other, the following objects were entered:_

* _images to display the logo_
* _five text fields populated by the parameters transferred to the page_
* _four reports_
* _An indicator_

Step 2: Template Configuration

![](../../../../.gitbook/assets/85.png)

The template must contain the same objects of the Page but with different arrangements:

1. a banner in the initial part containing the information relating to: User, access date, year, brand, status and Logo.
2. On the next row, you want to display the indicator and the values relating to the associated metrics.
3. A drop-down menu will subsequently show the reports.
4. In the lower part of the spreadsheet a section, Note _and signatures for approval_, will be entered which may be compiled after printing.

The image at the top shows the Excel file configured as described previously.

Note that in the page, the tags NEW\_ROW and New\_Col were entered. The system automatically calculates the dimension the object occupies in the page by occupying for each one as many cells as are necessary for the correct display.

Step 3: Export with Dynamic Template

![](<../../../../.gitbook/assets/86 (2).png>)

After the configuration of the template, the Page Designer is accessed again where the export property

_activateExcExport_ will be activated.

Choose the export with template from the expor&#x74;_-mode property_ while in the _template-file-name property_ enter the name of the template file.

The figure shows the results of the export with Dynamic Template. Note how each object respects the position given inside the template and how the system automatically calculates how much space is required by each element.
