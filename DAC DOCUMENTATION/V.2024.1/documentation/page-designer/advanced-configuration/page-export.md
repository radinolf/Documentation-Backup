# Page Export

## Exporting With Template

Exporting a page using an Excel template provides a powerful way to customize the layout and formatting of your exported data. This process requires the creation of an Excel file (in `.xlsx` format) to serve as the template. The template must be designed and saved within the **Design Studio** environment and can include custom formatting and placeholders (tags) to tailor the output.

To enable and configure template-based export, the following properties can be utilized:

* _**export-with-template enables**_ Allows exporting using a predefined template. By default, this property is disabled.
  * _**template**_ Enables the selection of a template from the resource catalog window. The template file must be uploaded to the [Resource Catalog](../../app-functionality/resource-catalog/)
  * _**auto-adjust-col-width**_ utomatically adjusts the dimensions of columns and rows to fit their largest content (default behavior). If disabled, the columns and rows retain the dimensions specified in the template.
  * **repeaed-export:** Enables the export of a report to separate Excel spreadsheets, with each spreadsheet corresponding to a different "Page-by" value within the report.

Templates can consist of one or more Excel sheets, and cells may include any type of formatting. Specific tags embedded in the template enable customization during the export. Each tag is replaced with its corresponding object during the process. If a template includes incorrect or invalid tags, or if tags reference non-existent objects, the resulting file will highlight the errors with red cells. The following sections will demonstrate how to construct templates

### Excel Export TAGs

The export TAGs for Pages reference the Page itself and the reports contained within it. The primary TAGs related to the mashboard are:

* `<PAGE_TITLE/>`: Represents the title of the Page, corresponding to the value of the `title-text` property of the Page (found in the _Container_ folder, _ContainerStyle_ group).
* `<PAGE_DESCRIPTION/>`: Represents the description of the Page, corresponding to the value of the `description-text` property of the Page (found in the _Container_ folder, _ContainerStyle_ group).
* `<Parameter? KEY:?Parameter?/>`: Exports the values of the Page parameters, where the parameter name corresponds to the specific parameter key.



<table data-full-width="true"><thead><tr><th width="148">Subject</th><th width="417">TAGS</th><th width="161">TYPE</th><th width="100">Excel cell occupation</th></tr></thead><tbody><tr><td><strong>Crosstabs</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num /></em></td><td>Table form of the report</td><td>1 Cell</td></tr><tr><td><strong>Chart</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num [type:val]/>&#x3C;OBJECT_BODY ID: id_num [type:val|img]/></em></td><td>Table form of the report</td><td>Number of cells equal to the number of row by the number of columns of the body</td></tr><tr><td></td><td><em>&#x3C;OBJECT_BODY ID: id_num [type:val|img]/></em></td><td>Graphic form of the report</td><td>Cell number on which the image is overlapped.</td></tr><tr><td><strong>Flag Setup</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num [type:val]/></em></td><td>Table form of the report</td><td>Number of cells equal to the number of row by the number of columns of the body</td></tr><tr><td></td><td><em>&#x3C;OBJECT_BODY ID: id_num [type:val|img]/></em></td><td>Chart form of the report</td><td>Cell number on which the image is overlapped.</td></tr><tr><td><strong>Map</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num/></em></td><td>Table form of the report</td><td>Number of cells equal to the number of row by the number of columns of the body</td></tr><tr><td><strong>Textfield</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num/></em></td><td>Selected item</td><td>1 Cell</td></tr><tr><td><strong>Textarea</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num/></em></td><td>Selected item</td><td>1 Cell</td></tr><tr><td><strong>Image</strong></td><td><em>&#x3C;OBJECT_BODY ID: id_num/></em></td><td>image</td><td>Cell number on which the image is overlapped.</td></tr><tr><td><strong>Text</strong></td><td><em>&#x3C;object_body ID: id_num/></em></td><td>Text of the element</td><td></td></tr></tbody></table>

The TAGs relating to the reports of the Page to be exported are a subset of those defined for the Excel exporting of the reports (see _Report Administrator, TAG exporting reports in Excel section_) and namely:

* _\<MODEL/>_
* _\<OBJECT\_TITLE ID:id\_num/>_
* _\<OBJECT\_DESCRIPTION ID: id\_num/>_
* _\<OBJECT\_BODY ID: id\_num \[type:val|img]/>_
* _\<METADATA ID: id\_num/>_
* _\<METRICS ID: id\_num/>_
* _\<LEVELS ID: id\_num/>_
* _\<FILTERS/> ID: id\_num/>_
* _\<LEVELS ID: id\_num/>_
* _\<RANGE\_FILTERS/> ID: id\_num/>_
* _\<CUSTOM\_FILTERS/> ID: id\_num/>_

For each TAG referring to a component of the report, the ID of the same report must be indicated:

_for example \<METADATA ID: id\_num/>, where id\_num is the ID number of the object you want to export;_

When exporting reports the \<OBJECT\_BODY/> TAG is used to export the body of the report in table form. For Pages, this tag is used to move the body of the report both in table and graph format, regardless of the object it is associated with.

The syntax is as follows:

* **\<OBJECT\_BODY ID: id\_num \[type:val|img]/> :** In the event that the id\_num refers to an image object, the type is indicated if the table or image part is exported, as described in the following table.

{% hint style="info" %}
**An Example of Using Static Template Files:** The static template may be used if you are sure that the rows and columns of the reports do not incur any change in height and wiDSh. The static templates are configured without the help of the NEW\_COL and NEW ROW tags. In the Excel file each object must have as many rows and columns available as there are in the associated report. Below is an example.
{% endhint %}

**Example How to use the Excel Tempale**

**Step 1: Page Designer**

![](<../../../.gitbook/assets/80 (4).png>)

The example above shows the Page page to be exported. Starting from the other, the following objects were entered

**Step 2: Template Configuration**

![](../../../.gitbook/assets/81.png)

The Excel export template mirrors the objects displayed on the Page but arranges them in the following structure:

1. **Header Section**:\
   At the top of the page, a banner includes:
   * **Company logo and address**
   * **User details**: The name of the user who performed the analysis
   * **Timestamp**: Date and time when the export was generated
2. **Details Below the Banner**:
   * **Left Side**:
     * Year of analysis
     * Product brand type
   * **Right Side**:
     * Reports for _Direct Unit Cost_ and _Unit Cost of Sales_
3. **Content Layout**:
   * **Next Row**:
     * **Left**: Column headers will represent the Year report, accompanied by a dropdown menu offering options such as Unit Sales, Unit Price, and Sales reports.
     * **Right**: The Marketing Expense Budget report and the Annual Expense Budget graph, both centered for alignment with the left-side reports.
   * Below this, the _Actual vs Year_ report will be aligned with the _Marketing Expense Budget_ report.
4. **Footer Section**:\
   At the bottom of the Excel spreadsheet, there will be a dedicated section for **Notes and signatures for approval**, intended to be filled out after printing.

Additionally, the image above illustrates how the Excel file is configured. Each object is positioned according to the described structure, with placeholder rows and columns left blank to define their placement.

**Step 3: Template Configuration**

![](<../../../.gitbook/assets/82 (1).png>)

For example we know that the Unit Sales report occupies exactly 4 rows and 13 columns. Thus, in the Excel spreadsheet, this object was reserved as many rows as the columns required for the correct display. The same method was also used for the other elements which make up the Page.

**Step 4: Export with Template**

![](<../../../.gitbook/assets/83 (1).png>)

After configuring the template, return to the Page Designer and activate the **export** property by setting `activateExcExport` to `true`.\
Next, choose the **export with template** option in the `export-mode` property and enter the name of the previously created file in the `template-file-name` property.

The figure illustrates the results of the export, showing that each object aligns precisely with the positions defined in the template.

**Exporting with a Dynamic Template**

The export is managed using a dynamic template because the components on the Page do not always have fixed dimensions. Additionally, the number of rows and columns in the reports can vary depending on the selections made on the Page.

**Step 1: Page Designer**

![](<../../../.gitbook/assets/84 (1).png>)

The example above demonstrates the Page to be exported. Starting from the initial configuration, the following elements were added:

* **Images** to display the company logo
* **Five text fields** populated with parameters passed to the Page
* **Four reports**
* **An indicator**

Step 2: Template Configuration

![](<../../../.gitbook/assets/85 (1).png>)

The template should include the same objects as the Page but arranged differently:

* **Header Section**: A banner at the top containing information about the user, access date, year, brand, status, and logo.
* **Next Row**: Displays the indicator along with the values of the associated metrics.
* **Reports Section**: A dropdown menu provides access to the reports.
* **Footer Section**: At the bottom of the spreadsheet, a "Notes and Signatures for Approval" section will be included, which can be completed after printing.

The image above illustrates the Excel file configured as described.

Additionally, the Page includes the tags `NEW_ROW` and `NEW_COL`. These tags allow the system to automatically calculate the dimensions of each object, allocating the appropriate number of cells required for proper display.

**Step 3: Export with Dynamic Template**

![](<../../../.gitbook/assets/86 (2).png>)

After configuring the template, return to the **Page Designer** to activate the **export** property by setting `activateExcExport` to `true`.\
Next, select **Export with Template** in the `export-mode` property and specify the name of the template file in the `template-file-name` property.

The figure illustrates the results of the export using the dynamic template. Each object aligns with the positions defined in the template, and the system automatically calculates the space required for each element.
