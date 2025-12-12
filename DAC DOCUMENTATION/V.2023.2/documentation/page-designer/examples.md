# Examples

## Examples -Interaction between components of a Page

The following are examples of interaction between components of a Page:

* Dependence between two Styled Selector widgets
* Checklist component filtered by Styled Selector widget
* Crosstab component filtered by Checklist and Styled Selector widget
* Indicator components filtered by Styled Selector widget
* Graph component filtered by Crosstab widget
* Crosstab component filtered by a date range



### **Dependence between Two Styled Selector Widgets**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/33.jpg)

The following example shows how to “condition” the list of values of a Select object from the selection made for another Select object. The figure shows two Select objects inserted in a Page.

Example: **Dependency of a Select object by an object Select**

https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/32.jpg

_For the first Select object, which selects the geographical area, the following properties are involved:_

* _the formName property specifies the name that identifies the component in the parameter selection windows (Area);_
* _the sql-formula property specifies the query (select LK\_AREA.ID \_ AREA, LK\_AREA.DS\_AREA from DEMO\_BI.LK\_AREA) to run to populate the component itself;_

_For the second Select object, which selects the regions, the following properties are involved:_

* _the formName property specifies the name that identifies the component in the parameter selection windows (REGION);_
* _the sql-formula property specifies the query (select LK\_REGION.ID\_REGION, LK\_REGION.DS\_REGION from DEMO\_BI.LK\_AREA) to run to populate the component itself; To “condition” the list of regions based on the area selected, the parameter ?AREA? is used in the filter as a where condition. Note that AREA is the name given to the formName property of the first Select object and that to identify it as a parameter, it is put between two question marks “?”._
* _The figure also shows the above Page page displayed in DAC before and after the filters are applied._
* _Note how in the second Select object, only the regions belonging to the geographical area of the first Select object can be displayed and selected_

### **Checklist Component Filtered by Select**

The following example shows how to “condition” the list of values of a Checklist object from the selection made for a Select object. In the Page page defined in the previous example, a Checklist type object is added in which the provinces belonging to the region selected by the Select object can be viewed and selected.

**Example: Dependence of an Object from an Object Select Checklist**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/34.jpg)

_For the Checklist object, which allows days to be selected, the properties involved are the same as those indicated for the Select components in the preceding example._

_So the name PROVINCE was specified for the formName property._

_Particular attention should be paid to the setting of the sql-formula property: in fact, to “condition” the list of the provinces to the selection made for the region, in the query (select LK\_PROVINCE.ID\_PROVINCE,LK\_PROVINCE.DS\_PROVINCE from DEMO\_BI.LK\_PROVINCE where LK\_PROVINCE.ID\_REGION=?REGION?) the ?REGION? parameter is used in WHERE condition. Note that REGION is the name given to the formName property of the second Select object and that to identify it as a parameter, it is put between two question marks “?”._

_The geographical area is selected in DAC. The system filters the regions belonging to the area just selected; a region is selected (Lazio)._

_The PROVINCE section allows selecting only the provinces in the selected region._

### **Crosstab Component Filtered by Checklist and Select**

The following example shows how to “condition” a report from the selection made both for a Select object and for a Checklist object. In the Page page defined in the previous examples, a report is added whose data is filtered by the selection of the area and region parameters defined respectively by the Select object and Checklist object.

Example

**Step 1: Dependence of a Report from an Object Select an Object and Checklist**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/35.jpg)

&#x20;_The figure shows the Page page structure in DAC. Note that the components used to apply filters and described in the previous examples were placed at the top, while a Crosstab type report was inserted at the bottom._

_For the Crosstab component, the property involved to allow the application of filters based on the selections of the Select and Checklist objects, is the filter property._

_In the example, the report is filtered by Area, Region and Province. Note that AREA, PROVINCE and REGION are the names assigned to the formName property of the objects and that to identify them as parameters, they are placed between two question marks “?”._

**Step 2:** Page in DAC

_The figure shows the above Page page displayed in DAC. Note how the report data is filtered based on the selection of the parameters AREA, REGION and PROVINCE defined in the Select and Checklist objects._

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/36.jpg)

### **Indicator Components Filtered by Select**

The following example shows how to “condition” an indicator from the selection made for a Select object. In the Page page defined in the previous examples, an indicator is added whose data are filtered by the selection of the Region and Province parameters defined in the Select and Checklist object.

**Step1: Dependency of indicators from an object Select**

_The figure shows the Page page structure in DAC._

_Note that the components used to apply filters and described in the previous examples, including the Crosstab type report, were placed at the top; an indicator was inserted._

**Step 2: Dependency of indicators from an object Select**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/37.jpg)

_For the Indicator component, the property involved to allow the application of filters based on the selections of the Select object is the filter property (as for the Crosstab component). Filters can be copied from the crosstab object and pasted to the Indicator, as shown in the figure._

**Step 3: Dependency of indicators from an object Select**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/38.jpg)

_The figure shows the above Page page displayed in DAC before and after the filters are applied. Note how the indicator is modified according to the selection of the parameters Area, Region and Province defined in the Select components._

### **Graph Component Filtered by Crosstab**

The following example shows how to “condition” a graph from the selection made on a level in a report.

Step 1: **Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/39.jpg)

_The figure shows the Page page structure in DAC._

_Note that the components used to apply filters and described in the previous examples, including the Crosstab type report and the indicator, were placed at the top._

_Insert a new graph component. Copy the filters from the crosstab component and paste them on the Graph component as shown in the previous exercise._

**Step 2: Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/40.jpg)

_The fundamental properties for allowing the component of the Crosstab type to export its levels as parameters belong to the Main group and are: activateExpParams and exp-levels._

_The activateExpParams property enables exporting parameters relating to the levels of the associated report. However, the exp-levels property specifies the levels of associated report to be exported as parameters and used as filters for other objects on the page. Then the Business Unit level is exported._

**Step 3: Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/41.jpg)

&#x20;_For the second Graph component, the property involved to allow the application of filters based on the selections of the levels of the first report is the filter property, as shown on the left._

_Note that Business\_Unit is the name of the layer exported and shown in the exp-levels property of the first report which is put between two question marks “?” to identify it as a parameter._

**Step 4: Dependence of a chart from a report**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/42.jpg)

_The figure shows how the selection of the Business Unit level on the report “conditions” the graph._

### **Crosstab Component Filtered by a Date Range**

The following example shows how to “condition” a report from the selection made for a range of dates using two calendar type TextField objects.

**Step 1: Dependency of a Report by Two TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/43.jpg)

_As shown in the figure, TextField type objects and a Crosstab type report were inserted in a Page page._

**Step 2: Dependency Between Report and TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/44.jpg)

_The first TextField was assigned the name From, and the second To._

_For both TextField objects, the objectInputType property was set to DATE, so the date can be selected from a calendar._

_Therefore the two TextField objects allow a start and end date to be selected to define a time interval based on which the data in the report are to be filtered._

**Step 3: Dependency Between Report and TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/45.jpg)

_For the Crosstab component, the property involved to allow the application of filters based on the selections of the dates is the filter property, as shown in the figure._

_Note that From and To are the names assigned to the param base name property of the TextField objects and that to identify them as parameters, they are put between two question marks “?”._

**Step 4: Dependency between report and TextField**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Parameters/46.jpg)

_In the figure, the report is filtered by the range that runs from February 1, 2007 to February 8, 2007_

## Example - How to use the editable report into the Smart Grid Widget

To use a report in editable mode (see Property [Report](../report/report/#introduction-to-reports)) it is necessary to use the Smart Grid Widget.

(view the Smart Grid Widget Documentation).

The specific properties of the Smart Grid Widget are:

**Object** group:

**Editing**

* **enable-editing** Enable widget data
  * **edit-mode**: select the editing mode (in-line, dialog, batch)
  * **enable import via Excel:** enable data setting via excel file
    * **import operation type:** select the type of operation that will be performed after importing the excel file (Update, Insert, Update/insert, Delete/Insert)
* **Data CRUD (Grid/Configuration)**\
  **Use report CRUD:** Use the CRUD method configured inside the report before\
  **Add button:** set the name of ADD button. Trigger to insert the item\
  **Update button:** Set the name of update button. Trigger to update the excel file\
  **Delete button:** Set the name of delete button. Trigger to delete the item

### Example - How to configure the report editable.

In this example you can understand how to configure the editable report and how to associate the report to the Smart Grid Widget.

**Prerequisites:** The Smart Grid Widget was previously imported via Widget Designer.

See Tutorial:

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/DataGrid/DataGrid2.mp4" %}



### Example - How to import the recod using the Excel files.

\
When you enable the "enable import via Excel" property present in the property group of the page designer for the Smart Grid Widget, you have the possibility to import the data through an excel file.

See Tutorial:

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/DataGrid/DownloadUpload.mp4" %}

