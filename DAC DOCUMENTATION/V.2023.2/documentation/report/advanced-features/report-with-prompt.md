# Prompt

You can enable a prompt in the report, in which you can select the values of any parameters that are in the report itself. The prompt may also be defined in a complex mode, by associating a Page.

In the **prompts-associated** property, set the prompt with one of the following possibilities:

* _**\<none**_> no prompt
* _**\<Page**_ >[ Page type prompt](report-with-prompt.md#page-type-prompt)
* <_**\<prompts>**_ [prompts for the parameters in the](report-with-prompt.md#report-parameter-prompts) report (in the metrics or on filter conditions relating to levels/metric)



<figure><img src="../../../.gitbook/assets/image (907).png" alt=""><figcaption></figcaption></figure>

### Page Type Prompt

Page type prompts are usually used to define filters that perform better than page-bys, as well as to insert components that enrich the report itself (indicators, graphs, etc.). The Page should be created in advance with the _Page Designer._

Enable this type of prompt by selecting the <**Page**> item in the **prompts-associated** property, which enables the following:

* _**PageAssociated**_ selection of the prompt Page.

Selecting a Page enables the two following properties:

*
  * _**paramsImportedSetting**_ defines the correspondence between the parameters of the Page and those of the report (see figure below).

![](<../../../.gitbook/assets/0 (10).png>)

* _**refreshMethod**_ mode for passing parameters from the Page to the report, chosen from either _Synchronized_ or _OnSubmit._ Also see _Presentation Administrator, Passing parameters in the Page_
* _**refreshMethod**_ mode for passing parameters from the Page to the report, chosen between:
* _**Syncronized**_
* _**OnSubmit**_.

The On Submit selection enables the property:

* _**mandatory-first-submit**_**:** if activated the report is performed only after clicking the Submit button.

You can also define mandatory parameters for the report. These are chosen directly _on the Page (see Presentation Administrator_), _Mandatory parameters_ section.

The example below shows a report that examines monthly quantities sold by product. You can associate a Page to the report set for selecting the year and the region; in addition, a text field allows you to enter a target quantity, so that the report shows data with a lower quantity.

To create a report with a Page header, first of all we need to define a rule for passing the parameters from the Page to the report: either synchronized or on submit.

The example below shows the second case. Therefore, you will need to insert a Submit type _button_ on your Page and set the report property shown above _**refreshMethod**_ to _'OnSubmit_'.

Step 1: Creating Reports with Parametric Filters

![](<../../../.gitbook/assets/1 (30).png>)

_We construct the report with the levels Year, Month, Region and Product_

_We define report custom filters (folder Custom, report editing window) with respect to the year, region and product, as shown in the figure._

Step 2: Creating Page for Selecting Parameters

![](<../../../.gitbook/assets/2 (24).png>)

_We define the Page to be used as report prompt, containing the following elements:_

* _Olap Selector for selecting the year, region and product_
* _Text Field for entering the target quantity_
* _Submit to pass parameters to the report in OnSubmit mode_
* _Indicator for the publication of two indicators, one to evaluate actual versus budget, and the other actual versus last year._

_The figure shows both the Design section and the Page preview._

Step 3: Configuring Page Type Prompt in the Report

![](<../../../.gitbook/assets/3 (16).png>)

_You can configure the Page type prompt in the following way:_

* _In prompts-associated you select the item\<Page>_
* _In PageAssociated you associate the Page constructed previously_
* _In paramsImportedSetting you associate report parameter/Page parameters:_

_The first column lists the report parameters, while the second column contains a drop down menu which lists all parameters exported from the Page._

_Leave the default selection \<auto> for all parameters with the same name in both the Page and in the report._

_You select the corresponding parameter for the quantity parameter (see figure)._

* _In refreshMethod, you can set the method for passing parameters from the Page to report in OnSubmit, in order to apply the filters on the report after you click the Submit button in the Page._

Step 4: View in DAC

![](<../../../.gitbook/assets/4 (10).png>)

_The report then opens in DAC (through the catalog). The associated Page has a section for selecting the year, month and product._

_The selection of the parameters is reflected in both the graph of the Page (with the quantities sold) and on the report._

### Report Parameter Prompts

You can enable a prompt in the report, in which you can select the values of any parameters that are in the report itself.

You can enable this mode by selecting the <_**prompt**_> item in the **prompts-associated** property, which enables the following:

* _**prompts-description**_ to describe mail as header in the prompts section.
* _**prompts-alias**_ for defining an alias for the parameters.
* _**prompts-type**_ assigning the selection/entry type for each parameter:

opens a window with the list of report parameters, where you can define the type and value for each of them

| _TYPE_                                                                 | _Value_                                                                                                                                   |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| _List_ and _List\_Multi_ for single or multiple _lists_                | <p>the application levels are listed:</p><p>in DAC the list will present the values of the chosen level</p>                               |
| _Text_ and _Number_ for the text and numeric fields                    | it is not possible to set the value for these types                                                                                       |
| _Date_ for the date fields where you can enable the calendar selection | <p>in Value you can insert the format to which the date must be converted</p><p>(by default the proposed format is DAY TIME level)</p>    |
| _Text\_Pattern_ for the text fields with pattern                       | <p>you enter the regular expression that must be respected</p><p>(by default the regular expression shown in the figure is proposed).</p> |

![](<../../../.gitbook/assets/5 (30).png>)

* **prompts-default** default values of each parameter; if the default value is not valued, the system issues: _total_, in the case of selector; _empty_, for the text fields.
* **prompts-not-visible** visibility of the parameters (visible by default).
* **prompts-mandatory** permits selection of mandatory parameters:
  * _\<all>_ all parameters are required
  * _\<none>_ no parameters are required
  * _\<selection>_ some parameters are required. Selecting this item enables the property
    * prompts-selection opens a pop-up window for selecting parameters to be required

When the report is run, the window for inserting the test parameters will open.

![](<../../../.gitbook/assets/6 (17).png>)

Selecting one or more parameters enables the buttons below:

* **Default** to save the test values as default only for selected parameters (e.g. in the figure the default value is 'Fridge' for the parameter **' Select\_Product).**
* **Init** to initialize the values of the selected parameters to those set as default (_**prompt-default property**_ shown above).

The default values are indicated by the notation "(D)" before the value.

The following example shows how to configure the default values.

The sorting of the prompts associated with a report coincides with that given to the filters: by acting on the order of the filters, while creating the report, there is the possibility of defining a vertical sorting for the prompts displayed on DAC.

Where you access a report with prompt activated via drill through, the selectors relating to the past parameters in drill through are valued based on the values received.

In DAC, to add a new parametric filter and, therefore display the respective selector, the parameters in the filter must correspond to the name of the level of the related pageBy. This is because in Web environment it is not possible to define the mapping manually.

By adding a preset parametric filter (direct filter), the system displays the selector. Naturally also in this case the parameter in the filter must correspond to the name of the related pageBy level.

Step 1: Creating Reports with Parametric Filters

![](<../../../.gitbook/assets/7 (11).png>)

_We build the report with the levels Year, Month, Product (full name and code) and Customer (name and address). The relevant metric is the quantity. We define the custom filters of the report (Custom folder, report editing window) with respect to the following parameters:_

* _Select\_Product for the product_
* _Select\_Region for the region_
* _Select\_Date for the date_
* _Insert\_Code to enter the product code._
* _Search\_Address for searches on the customer address._
* _Insert\_Qty for analysis on figures that exceed a target quantity._

Step 2: Aliases and Types for Prompt Parameters

![](../../../.gitbook/assets/8.png)

_In the report prompt properties, under the prompts-associated property, you can set the \<prompt> item for defining a prompt with the parameters from the previous step._

_For each parameter, you set the aliases in the prompt-alias property, while in the prompts-type property you define the type for each parameter, as shown in the figure._

Step 3: Assigning DEFAULT Values (in Test params))

![](<../../../.gitbook/assets/9 (3).png>)

_It is more practical to assign default parameters in the test parameters window, where you can easily select lists of values, directly selecting the level values._

_Hence, the report is run and you can set the default values for the desired parameters in the window that opens (those selected in the figure)._

_Click the Default button, and the values are saved in the prompts-default property, while they appear in the window with the symbol (D) before the value. If you cancel the values entered (Clear button) and initialize back to default with the Init button, you can verify that the parameters entered are actually saved as default_

Step 3: Displaying DEFAULT Values in DAC

![](<../../../.gitbook/assets/10 (7).png>)

_The example shows the report displayed in DAC where prompts have the default value set in the previous steps._

##
