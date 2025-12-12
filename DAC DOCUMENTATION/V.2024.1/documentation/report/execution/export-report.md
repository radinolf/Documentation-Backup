---
icon: repeat
---

# Export Report

### Introduction <a href="#exporting-reports" id="exporting-reports"></a>

You can export reports in various formats to meet different needs. Supported formats include:

* [PDF](export-report.md#pdf-export)
* [Excel](export-report.md#excel-file)
* [CSV](export-report.md#csv)

These export functions are accessible directly from the report toolbar in AppComposer, located in the main section, as well as from the pop-up menu of the report in Pages.

<figure><img src="../../../.gitbook/assets/image (2284).png" alt=""><figcaption><p>From the pop-up menu of the report in Pages.</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2287).png" alt=""><figcaption><p> From the report toolbar in AppComposer, </p></figcaption></figure>

## Adobe PDF   <a href="#pdf-export" id="pdf-export"></a>

To export a report as a PDF file, select the corresponding command from the pop-up menu.

The report export window includes four sections: **Settings**, **Header**, **Footer**, and **Description**:

* **Settings**: Allows you to configure the document's parameters.
* **Header**, **Footer**, and **Description**: Enable you to manage the respective elements of the document, with a wide range of text formatting options available in each section.

### **Settings**&#x20;

The **Settings folder** configures the interface of the document.

&#x20;

<figure><img src="../../../.gitbook/assets/image (2266).png" alt=""><figcaption></figcaption></figure>

&#x20;

The **Settings** section allows you to configure the overall layout and interface of the exported PDF document.

In this section, you can define the following attributes to customize the document's pages:

* **Title**: Sets the document title; by default, it displays the name of the report being exported.
* **% Font Dimension**: Specifies the font size percentage for text within tables.
* **% Graph Dimension**: Adjusts the size of graphs as a percentage.
* **Margins**: Configures the top, bottom, left, and right margins (measured in pixels).
* **Header Height** and **Footer Height**: Sets the heights of the header and footer sections (in pixels).
* **Size**: Specifies the page size, with A4 as the default.
* **Orientation**: Determines the page layout as either portrait (vertical) or landscape (horizontal).
* **Fit to Page**: When enabled, scales the report to fit the page by evenly distributing column widths (e.g., 10 columns at 10% each).

{% hint style="info" %}
&#x20;**Note:** The columns may be narrower than their content.
{% endhint %}

If the width is set to all of them, the button "**Fit to Page**" will be ignored, even if selected.

* **Pdf protection:** _if selected, people receiving the PDF file will not be able to make changes to it. They will only be able to Print_ and _Copy_ the file.
* **Division level:** sets the page change: select one of the levels of the report, whose values generate a page with the respective table.&#x20;

<figure><img src="../../../.gitbook/assets/image (2297).png" alt=""><figcaption></figcaption></figure>

Below are the export pages of the report shown in the example above, where the dimensional level selected is the one named _Title_. You will notice that for each value present in the _Title_ column, a dedicated page is generated in the PDF export.

{% tabs %}
{% tab title="Report Exported " %}
<figure><img src="../../../.gitbook/assets/image (2302).png" alt=""><figcaption></figcaption></figure>

In the example, we can see how a report is exported to PDF with a dimensional level selected from the **Dimensional Level** property.In this case the level selected is **Status**.&#x20;
{% endtab %}

{% tab title="Page 1" %}
<figure><img src="../../../.gitbook/assets/image (2299).png" alt=""><figcaption></figcaption></figure>

Included are the report details, such as levels, filters, and parameters that compose it, along with the complete report in its entirety.
{% endtab %}

{% tab title="Page 2" %}
<figure><img src="../../../.gitbook/assets/image (2300).png" alt=""><figcaption><p>Status: Closed</p></figcaption></figure>

By activating the filter for the Status level, the report export will be divided based on the number of statuses present in the report. In our case, the statuses are two: _Closed_ and _Open_.
{% endtab %}

{% tab title="Page 3" %}
<figure><img src="../../../.gitbook/assets/image (2301).png" alt=""><figcaption><p>Stus: Open</p></figcaption></figure>

We can observe that the page exports only the rows with the status set to "Closed."

In conclusion, a separate page is generated for each status present in the report because the selected level is "Status."
{% endtab %}
{% endtabs %}

* **Export page-by on every page**_**:**_ when selected, the values of the page-bys will be shown on all the pages of the PDF document, and not just on the first page (which is the default). This property does not affect the level chosen in _Division Level._ In the previous example, the _Customer Group_ level would also appear on subsequent pages, in addition to the level, as well as the _Year_ level chosen as subdivision level.
* **Export all page:** exports all report pages, displayed with the scroll on the columns and rows. The column number reported on each page respects the one indicated in the column scroll, while the number of rows is set by the system (to fill the same page).
* **Apply the rows per page limit:** applies the limit to the number of rows selected in the scroll of the page (this is selected by default).
* **Start from second page:** allows the report to be printed starting from the second page instead of the first. By default it is disabled. &#x20;
* **Logo:** selecting this option requires that you add the logo image. The image will be displayed to the left of the report title. The logo image is set in the [PDF specific properties ](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2768142340/Export)of the report.

&#x20;

<figure><img src="../../../.gitbook/assets/image (2271).png" alt=""><figcaption></figcaption></figure>

### Heder, Footer, and Description <a href="#heder-footer-and-description" id="heder-footer-and-description"></a>

The sections _**Header, Footer**_ and _**Description,**_ respectively, allow you to:

* customize the header of the document (_Header_);
* set the footer (_Footer_);
* enter a description of the report (_Description_) in the top part of the document.

<figure><img src="../../../.gitbook/assets/image (2272).png" alt=""><figcaption></figcaption></figure>

Each of these sections has a toolbar for text formatting.

The “Plus” button opens the menu with the TAGs available to export the document to PDF.

<figure><img src="../../../.gitbook/assets/image (2273).png" alt=""><figcaption></figcaption></figure>

You can position TAGs in any part of the document, and apply different formatting to each tag.

The TAGs with the information for the **page** are:

* **Current Page**: number of the current page;
* **Total Page**: total number of pages;
* **Title**: title of the report;
* **Application:** the app that the report belongs to;
* **User**: user who requested the exported report;
* **Day**: current day of the export request;
* **Month**: current month of the export request;
* **Year**: current year of the export request;
* **Hours**: current hour of the export request;
* **Minutes**: current minute of the export request;
* **Logo**: default logo image;

Other TAGs publish the information on the **reports** items:

* **Report Metrics:** publishes the report metrics. For combined metrics, the formula is also displayed.
* **Report Levels:** publishes the report levels, whether by row, column, or page
* **Report Filters:** publishes the filters applied to the reports, both direct and ranges.

&#x20;

<figure><img src="../../../.gitbook/assets/image (2275).png" alt=""><figcaption></figcaption></figure>

* _**Report Parameter:**_ publishes _the parameters exported by the report_
* **Metadata Report:** publishes all of the items, metrics, levels, filters and prompt. _(Visible even if the report property **Prompt-Associated**_ is _set to Mashboard)_
* **Report Path :** displays the publication course of the report, including the form

&#x20;

<figure><img src="../../../.gitbook/assets/image (2276).png" alt=""><figcaption></figcaption></figure>

## Excel File

The reports can also be exported in Excel format. In **Design Studio**, it is possible to configure specific properties to customize the export of each report based on particular formatting needs.

To access the formatting options for Excel export, simply edit the report, go to the **Properties** tab, and select the **Excel**.

<figure><img src="../../../.gitbook/assets/image (2307).png" alt=""><figcaption></figcaption></figure>

Reports can be exported in two modes:

1. **Simple mode**, where data is exported directly without additional configurations.
2. **Template mode**, where a predefined Excel template (created and saved beforehand) determines what elements to include in the export. Templates allow customization of the exported content, including data, report components, and user parameters, using designated TAGs.

### Export Properties

* **Full-export (Excel group)**: Enables the full export of the report. This property is enabled by default. If disabled, only the rows and columns visible on the screen are exported.
* **Export-report-parameters (Excel group)**: Includes the report parameters and their corresponding values in the export.
* **xlsBreakLevel**: You can configure the export of a report into several Excel spreadsheets by specifying the subdivision level using the following properties:
  * **xlsBreakLevel**: This property allows you to choose a report level to serve as the break level for the export. As a result, each instance of the selected level will be exported to a separate Excel spreadsheet. If the \[Total] item is included, a spreadsheet will also be generated for the aggregated data.\
    For exports without a template, selecting a level also activates the following options:
  * **repeat-title**: Ensures that the report title appears on all sheets in the export file.
  * **repeat-page-by**: Enables the display of the page by level on each sheet of the report.\
    By default, both properties are disabled, meaning the title and page-by information will only appear on the first page of the export file.\
    The example below demonstrates how these settings are applied.
* **excel-font-size-adapt**: Allows users to adjust the font size in the exported file. The input value (between 0 and 9) is subtracted from the font size, helping prevent special characters (e.g., `#####`) from appearing when the font is too large for the cell size.
* **apply-report-col-size**: When enabled, the system preserves the row and column sizes defined in the report during the export.
* **excel-default-col-size**: Sets the width of the columns in the exported Excel file. This property is applied only if **apply-report-col-size** is disabled.
* **excel-description**: Allows users to add a description that appears below the report title in the exported Excel file. The text is displayed with default formatting.
* **Excel template additional reports**: Specifies the number of additional reports to be included in the export using the Excel template.

### Preventing Excel Formula Injection

XLS Formula Injection is a security risk where user input can execute formulas in Excel when the file is opened. To mitigate this risk, the **`xls-Formula-Injection-Mitigation`** property in the [**Tool Preferences** ](../../instance-configuration/tools/preferences.md#main)section of the Design Studio can be enabled. By default, this property is disabled.&#x20;

When this option is enabled, and when the export field is a string, and when the string begin with one char among Equals (`=`), Plus (`+`), Minus (`-`), At (`@`), Tab (`0x09`), Carriage return (`0x0D`) App Composer will automatically prepend a single quote at the beginning of the text. This prevents Excel from interpreting the content of the cell, ensuring it is treated as plain text.

**Mitigation Example:**\
**Original Input**: `=1+1`\
**Mitigated Output**: `'=1+1`

{% hint style="info" %}
This option does not modify numbers or other types of non-string data. It ensures that all exported data is interpreted as text in Excel, preventing the unintended execution of formulas.
{% endhint %}

### Exporting Large Reports

For reports containing extensive data, activate the **full-export** properties. This allows exporting all rows from the report corresponding to the selected page-by filter.

**Key Considerations**:

* In this mode, the formatting defined in the report is limited to settings made in the Headers, Columns, and Rows properties.
* Using a template or setting break levels is not supported.
* Font formatting is retained, but custom fonts default to Arial during export. The system approximates the original font size.



### Exporting with a Template

To export a report using a template, you must have an Excel file (in `.xlsx` format) saved in the system. This template defines the structure and content of the exported file.

**Configurable Properties**:

* **export-with-template**: Enables template-based exports (disabled by default).
  * **template**: Specifies the template file, which must be saved in the Resource Catalog
  * **auto-adjust-col-width**: Automatically adjusts column and row dimensions to fit content (enabled by default). If disabled, dimensions from the template are used.

Templates may consist of one or more spreadsheets, with customizable formatting. TAGs embedded in the template allow dynamic insertion of report data. Invalid or incorrect TAGs will result in red-highlighted cells to indicate errors.

{% hint style="info" %}
Notes on Excel Formatting

* Templates cannot include images, as they may cause issues such as document corruption or images being canceled.
* If images are included in the export, save the document in Excel to ensure compatibility and prevent distortion.
{% endhint %}

### TAGs for Report Export

The following TAGs can be used to export data and elements from reports to Excel. Each TAG occupies a single cell in Excel but may expand into multiple rows and columns based on the associated data.

<table data-header-hidden data-full-width="true"><thead><tr><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>TAG</strong></td><td><strong>Exported Object</strong></td><td><strong>Excel Cell Occupation</strong></td><td><strong>NEW_ROW/NEW_COL Support</strong></td></tr><tr><td><code>&#x3C;MODEL/></code></td><td>Application name</td><td>1 cell</td><td>Not supported</td></tr><tr><td><code>&#x3C;OBJECT_TITLE/></code></td><td>Report title</td><td>1 cell</td><td>Not supported</td></tr><tr><td><code>&#x3C;OBJECT_DESCRIPTION/></code></td><td>Report description</td><td>1 cell</td><td>Not supported</td></tr><tr><td><code>&#x3C;OBJECT_BODY/></code></td><td>Report body</td><td>Rows x columns of the body</td><td>Supported</td></tr><tr><td><code>&#x3C;PAGE_BY/></code></td><td>Page-by filters</td><td>2 cells per filter</td><td>Only NEW_COL supported</td></tr><tr><td><code>&#x3C;METRICS/></code></td><td>Report metrics</td><td>Title + 3 cells per metric</td><td>Supported</td></tr><tr><td><code>&#x3C;LEVELS/></code></td><td>Report levels</td><td>Title + 2 cells per level</td><td>Supported</td></tr><tr><td><code>&#x3C;DIRECT_FILTERS/></code></td><td>Direct filters</td><td>Title + 3 cells per filter</td><td>Supported</td></tr><tr><td><code>&#x3C;RANGE_FILTERS/></code></td><td>Range filters</td><td>Title + 3 cells per filter</td><td>Supported</td></tr><tr><td><code>&#x3C;CUSTOM_FILTERS/></code></td><td>Custom filters</td><td>Title + 3 cells per filter</td><td>Supported</td></tr><tr><td><code>&#x3C;FILTERS/></code></td><td>Combined filters</td><td>Varies</td><td>Supported</td></tr><tr><td><code>&#x3C;METADATA/></code></td><td>Combined metrics, levels, and filters</td><td>Varies</td><td>Supported</td></tr><tr><td><code>&#x3C;USER_ATTRIBUTE:%attribute%/></code></td><td>User attribute value <code>%attribute%</code></td><td>1 cell</td><td>Not supported</td></tr><tr><td><code>&#x3C;REPEAT/></code></td><td>Multi-sheet export based on xlsBreakLevel</td><td>1 cell</td><td>Not supported</td></tr></tbody></table>



{% hint style="info" %}
**Formatting Notes**:

* Templates preserve formulas, references, formatting, and static information.
* Rows and columns generated during export dynamically update cell references.
{% endhint %}

#### Example

The following example demonstrates exporting a report using a template saved in the "example" folder of the repository. The report output aligns with the configurations specified in the Excel template, allowing for customized and efficient data presentation.

<figure><img src="../../../.gitbook/assets/image (2306).png" alt=""><figcaption></figcaption></figure>

The report can be exported in Excel format by clicking the Excel button in the contextual menu of the Report.&#x20;

<figure><img src="../../../.gitbook/assets/image (2256).png" alt=""><figcaption></figcaption></figure>

DAC prompts the user with a dialog window to specify the folder where the file should be saved. By default, DAC assigns the file the same name as the report, but the name can be changed by typing a new one in the dialog box.

If the report is saved successfully, DAC displays a confirmation message indicating the path where the report was saved as an MS Excel file.



{% tabs %}
{% tab title="Report " %}
<figure><img src="../../../.gitbook/assets/image (2254).png" alt=""><figcaption></figcaption></figure>

In this example we can see whare is the result of the report exported in Excel
{% endtab %}

{% tab title="File Excel" %}
<figure><img src="../../../.gitbook/assets/image (2252).png" alt=""><figcaption></figcaption></figure>

In the image we can see the Report exported in Excel Format
{% endtab %}
{% endtabs %}

## CSV

The property are defined in the Design Studio in the _Tab Properties >>csvExportSettings_

<figure><img src="../../../.gitbook/assets/image (2304).png" alt=""><figcaption></figcaption></figure>

### CSV Properties

The configurable properties in the CSV configuration window include the following:

* **ExportLevels**: Allows the inclusion of the dimensional level ID along with the description.
* **DecimalSeparatorChar**: Specifies the character to be used as the decimal separator.
* **NumberFormat**: Sets the format for numerical values in the exported file. You can choose from predefined formats or define a custom format. A preview is provided to demonstrate the result on a sample number (e.g., `-1.234,567`).

<figure><img src="../../../.gitbook/assets/image (2305).png" alt=""><figcaption></figcaption></figure>

* **TextQualifierChar**: Defines the character used as the separator for text strings. This property is optional.
* **ColSeparatorChar**: Determines the character used to separate columns in the report. This property is also optional.
* **Apply-page-filters**: Specifies whether the page-by filters should be applied during the export. When enabled, only the values filtered by the page-by are included in the exported report.

You can export the report in CSV format by clicking the CSV button located in the contextual menu of the Report.&#x20;

<figure><img src="../../../.gitbook/assets/image (2257).png" alt=""><figcaption></figcaption></figure>

\
DAC will prompt you with a dialog window to confirm the export. The CSV file will use the report name by default, and it is not possible to change the file name during the export process.

If the file is opened with a complex editor such as Microsoft Excel, the data may be displayed differently compared to DAC. For example, decimal number formatting may not match DAC's specifications, and columns might not align correctly if the column separator and text qualifier settings differ between DAC and Excel. To ensure data consistency between the DAC report and the CSV export, it is recommended to review the file using a plain text editor, such as Notepad.



{% tabs %}
{% tab title="Report" %}
<figure><img src="../../../.gitbook/assets/image (2259).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="File CSV" %}
<figure><img src="../../../.gitbook/assets/image (2260).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

When the 'Applies Page-by Filters' option is selected, the page-by filters are applied to the export. If enabled, only the values filtered by the report’s pages will be exported."

<figure><img src="../../../.gitbook/assets/image (2255).png" alt=""><figcaption></figcaption></figure>

### Preventing CSV Formula Injection

XLS Formula Injection is a security risk where user input can execute formulas in CSV when the file is opened. To mitigate this risk, the **`CSV-Injection-Mitigation`** property in the [**Tool Preferences** ](../../instance-configuration/tools/preferences.md#main)section of the Design Studio can be enabled. By default, this property is disabled.&#x20;

When this option is enabled, and when the export field is a string, and when the string begin with one char among Equals (`=`), Plus (`+`), Minus (`-`), At (`@`), Tab (`0x09`), Carriage return (`0x0D`) App Composer will automatically prepend a single quote at the beginning of the text. This prevents CSV from interpreting the content of the cell, ensuring it is treated as plain text.

**Mitigation Example:**\
**Original Input**: `=1+1`\
**Mitigated Output**: `'=1+1`

{% hint style="info" %}
This option does not modify numbers or other types of non-string data. It ensures that all exported data is interpreted as text in CSV, preventing the unintended execution of formulas.
{% endhint %}



## Video Tutorial - Export Report in PDF formats

{% embed url="https://bitbucket.org/decisyon/manual/downloads/Exporting_Report.mp4" %}

