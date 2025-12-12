# Drill Through

## What is a Drill Through

**Drill Through** is a report's feature that allows to create contextual link between the record in a report and a target object, such as another page or report in the application or an external URL.

For example, if you have a report that shows total production by plant and line, using the drill through feature business user click on the specific line to open a more detailed page or report that shows production splitted by shift and product.

To use drill-through, app developers need to define a relationship between the report and the target object, specifying the columns where the drill through will be rendered and visible to the business user.&#x20;

When the business user click on a drill through link available in the report (or in a widget), App Composer opens the target object and pass to it all the parameters available in the source report, the "**context**".

A Drill through can be configure to open a target object such as:

* Another report in the same application
* A Page in the same application
* An external web page

The drill through (in short **DT**) can be activated both from dimensional levels and metrics available in the report.&#x20;

You can also associate it with the report for opening a Page, including some forms, from which you can “command” the calling report, i.e., to filter it in real time according to the choices made in the forms (Top-type DT).

<figure><img src="../../../../.gitbook/assets/image (698).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
During DT there is a parameter transfer from the report to the target object, every time the opening parameters are modified, the object will not be taken by the user session cache, but it will have to be re–executed by accessing the Data Model, of cache or on the data, according to the settings.
{% endhint %}

Once activated the user displays a predefined icon (only in DAC). The system allows you, however, to set custom icons.

A DT is activated by setting the properties of the **Drill-through**, group in the report editing window.

To activate the DT within the report select the Drill-Through TAB and select the activate drill-through property 1.

<figure><img src="../../../../.gitbook/assets/image (674).png" alt=""><figcaption></figcaption></figure>

You can activate one of the DTs enabling the corresponding _**"activate drillthrough \[n]"**_ property, each of which enables the specific configuration properties:

* the [DT activation mode](https://docs.decisyon.com/report-design-studio/#_Modalit%C3%A0_di_attivazione)[ ](./#creating-drill-through-dt-activation-mode) (_drill-through_), that tells us whether it is on a specific report level/metric or on the whole report;
* the[ DT target object ](./#action-type-dt-destination-object)(_open ActionType_);
* the page [**opening mode**](./#page-opening-mode)**;**
* the setting of an [image and description associated with the DT](./#image-and-description-associated-with-the-dt);
* the [parameters transfer](./#parameters-transfer)

You can apply the DT **contextually** or **non-contextually.**

<figure><img src="../../../../.gitbook/assets/image (672).png" alt=""><figcaption></figcaption></figure>

The difference between these two modes is that a contextually enabled DT is applied to the individual values of the levels and metrics present in the report having the possibility to filter the Page, URL or Report (opened in DT) based on the selected value.

The non-contextual mode applies the DT to the object level for example on the title of the report or on a column so the DT is not related to a specific value of the report.

To define the type of open mode of the DT on the report, select the **show-on** property.

<figure><img src="../../../../.gitbook/assets/image (967).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Attention this type of display can be applied to a report that is then associated within the Smart Grid widget. For more details please read the widget documentation [Smart Grid](https://widgets.decisyon.com/smart-grid/documentation/smart-grid-8.0#_contextual_menu_).
{% endhint %}

## Creating Drill Through&#x20;

Depending on the type of purpose for which a report is created and the DT configured, there are two different scenarios and different modes of property configuration. The DT may be applied:

* on the standard Report that can be displayed both in the catalog of reports from the Web and associated with the Crosstab widget
* on a Report used as a data source for Smart Grid Widgets

In both cases the steps to create a DT within the report are the same but may change the properties for displaying the DT on the Report.

A DT is activated by setting the properties of the **Drill-through**, group in the report editing window:

<figure><img src="../../../../.gitbook/assets/image (671).png" alt=""><figcaption></figcaption></figure>

In **D**_**rill-through groups**_, you can define the number \[_n]_ of DTs that you want to set in the report; for each of them, the properties _activatedrillthrough\[n]_ are repeated.It is possible to set more than one DT (up to 25) for the same report, each of which can execute different actions.

## Drill Through Properties

* [**Rendering**](./#rendering)**:** Configure the DT **rendering** mode properties in widgets
* [**Target action**](./#action-type)**:** Configure the properties related to **destination DT**.
* [**Parameters management**](./#passing-parameters)**:** Configure the properties related to **parameter** management.
* [**Grants:** ](./#dt-visualization-grants)Configure the **grants** on Drill-through used to implement data security logic. For example, access to Drill-through can be denied to specific users or groups.

### Rendering

Through the **Show-on** property, it is possible to decide where to activate the DT at Contextual or non-Contextual level.

<figure><img src="../../../../.gitbook/assets/image (666).png" alt=""><figcaption></figcaption></figure>

As mentioned above, if you are configuring the DT on a report that you will associate with a standard widget or displayed in the catalog of reports from the web only some of the listed modes will be applicable. In case the report is associated with a Smart Grid widget then all display modes will be supported.

Below we have created an example where we show you which of the DT types are applicable to a report Associated with a Crosstab widget and a report Associated with a Smart Grid widget.

**Contextual rendering**

{% tabs %}
{% tab title="Link" %}
<figure><img src="../../../../.gitbook/assets/image (963).png" alt=""><figcaption></figcaption></figure>

Opening the DT via Link on a report level is applicable to both the reports used in the Smart Grid Widget and the reports used in the Crosstab Widget.
{% endtab %}

{% tab title="Kebab menu" %}
<figure><img src="../../../../.gitbook/assets/image (964).png" alt=""><figcaption></figcaption></figure>

The DT via Kebab menu only applies to reports associated with the Smart Grid Widget. For the Reports Associated with the Crosstab Widget, the Classic link is displayed.
{% endtab %}

{% tab title="Icon and Text" %}
<figure><img src="../../../../.gitbook/assets/image (667).png" alt=""><figcaption></figcaption></figure>

The DT displayed in Icon and Text format is visible both on the reports Associated with the Smart Grid widget and the report Associated with the Crosstab widget.
{% endtab %}

{% tab title="Icon Only" %}
<figure><img src="../../../../.gitbook/assets/image (367).png" alt=""><figcaption></figcaption></figure>

The DT displayed via Icon is only visible for reports Associated with the Smart Grid Widget. For reports associated with the Crosstab widget, the DT is still visible but in the classic Text and Icon format.
{% endtab %}
{% endtabs %}

**Not Contextual rendering**

{% tabs %}
{% tab title="TOP" %}
<figure><img src="../../../../.gitbook/assets/image (676).png" alt=""><figcaption></figcaption></figure>

The DT on Top is visible for both the report used in the Smart Grid widget and the report used in the Crosstab Widget.
{% endtab %}

{% tab title="Context Menu" %}
<figure><img src="../../../../.gitbook/assets/image (972).png" alt=""><figcaption></figcaption></figure>

Il Context Menu è visiibile sia per il Widget Smart Grid il per il widget Crosstab
{% endtab %}

{% tab title="Duble Click" %}
<figure><img src="../../../../.gitbook/assets/image (681).png" alt=""><figcaption></figcaption></figure>

Opening the DT via Duble Click is only applicable to the report used in the Smart Grid Widget
{% endtab %}

{% tab title="Command Column" %}
<figure><img src="../../../../.gitbook/assets/image (688).png" alt=""><figcaption></figcaption></figure>

The Command Column DT automatically defines a new column within the Report that contains only DT . This configuration is only valid for reports associated with the Smart Drig widget.
{% endtab %}
{% endtabs %}

### Action Type

The settings for the object open by a DT are chosen with the property _**openActionType**_:

* **PAGE :** Opens a DAC page. Widgets on the page can be filtered by the value selected by the DT. See the Example

<figure><img src="../../../../.gitbook/assets/image (673).png" alt=""><figcaption></figcaption></figure>

* **REPORT:** Opens another report. The values of the open trqamite DT report can be filtered according to the value selected by the DT. See the Example

<figure><img src="../../../../.gitbook/assets/image (701).png" alt=""><figcaption></figcaption></figure>

* **OPEN URL:** Opens a page or web application, using the report parameters. See the Example

<figure><img src="../../../../.gitbook/assets/image (694).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Drill-throughs are links associated with the dimensional and metric levels in the reports, which allow you to open different types of new pages, such as other reports, Pages, URLs, etc. You can condition visibility using a [DAC TAG](../../../app-functionality/tags.md). This is particularly useful when several drill-throughs (DT) are defined on the same level or Metric.
{% endhint %}

#### Page Opening Mode

The DT can open in a new page, or it can replace the calling page: the opening mode is set in the _**openNewWindow**_ property.

If the DT opens in a new window (_**openNewWindow**_ enabled), the following properties are enabled:

* **openNewWindow:** open the target object in a dedicated dialog&#x20;
* **full-screen:** open the dialog in full screen mode&#x20;
* **enable-esc-to-close:** enable dialog closure using `ESC` button&#x20;
* **allow-user-to-close:** enable the closing of the dialog
* **click-outside-to-close:** enable closing the dialog clicking outside&#x20;
* **allow-full-screen:** enable the button to allow the end user to enlarge the dialog in full screen&#x20;
* **repaint-opener**: to redraw the calling report when the dialog closes. The report reads again the records from the datamart table.

#### Image and Description Associated with the DT&#x20;

You can associate an image and a tooltip to the DT in the properties:

* _**drillThroughImage**_, which will replace the default one, by selecting one of those loaded previously to the _Resource Catalog_ . This property enables the following:
  * _**image-width**_ and _**image-height**_ where we specify the height and width to assign to the image (default 0, value for which the image is displayed with the original dimensions)

The properties listed above are applicable to standard repots. For reports used as data source of the Smart Grid widget the Icon Only display mode is used.

{% tabs %}
{% tab title="DT Image Report Standard" %}
<figure><img src="../../../../.gitbook/assets/image (669).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="DT Image Data Grid" %}
<figure><img src="../../../../.gitbook/assets/image (713).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

* _**drillThroughDesc**_ the description of the DT is inserted, which will be presented as a tooltip to the DT link and as the title of the dialog opened by the App Composer (see example below).

If the description is not set, this title shows the title of the Page (containing the report) of the DT points to a Page, or does not show any title of the DT points to other types of object.



<figure><img src="../../../../.gitbook/assets/image (365).png" alt=""><figcaption></figcaption></figure>

### **Passing Parameters**&#x20;

When you select a DT to a Page a Link or a Report you can filter the data using the passage of parameters.

For example, if you have a report showing the production data of a specific Plant, you may want to pass the Plant name as parameter to another report showing the production data of the individual lines for the selected plant. When the parameter is passed, the data in the destination report will be filtered to show only the individual line production data for the selected Plant.

The choice of levels exported through DT is set by the sent-parameters property, which allows the selection of the report levels to be set through Drill-through. If no selection is made, all levels of the report will be sent.

<figure><img src="../../../../.gitbook/assets/image (678).png" alt=""><figcaption></figcaption></figure>

See the [example page](examples.md) to see how parameters are passed.

#### Parameters Transfer

When a DT opens a report or a Page, you can transfer the following to these:

* the elements associated with the rows (or column) of the calling report
* the parameters in the Page that includes the calling report

You can customize the parameter management using the drill-through properties, in the calling report.

For all the types of _**openActionType**_ the following are available:

* _**change-param-names**_ to modify the name of the levels and metrics transferred through the DT ; a window opens in which you can assign the new names.

{% hint style="info" %}
The change of parameters is particularly useful if you need to distinguish the parameter passed in the new page from the one present in the same page.
{% endhint %}

For example, the transfer of the level MONTH to a second dashboard, opened in DT, is necessary as a filter on some objects, while for others it is not: you can rename this level in the **change-param-names** property of the calling report and you can use this second name in the filters of the destination objects.

* _**total-behavior**_ to set the transfer mode for the values of the levels in page-by, when they are selected in \[Total]. You can choose one of the following:
  * _\<total>_ ignores the level, so that no value is passed
  * _\<page-by-content> all values listed_ in the page-by are instead passed
  * _\<Previous drill-through- value_> the values selected in page-by are passed, not those of the calling report, but those selected in a previous DT :

this property is especially useful when there are at least three DT levels , to transfer the parameters selected in the first page to a third, going through an intermediate level, where it is possible to set the _**total-behavior**_ property to _\<Previous drill-through- value>_.

The target page will only show the parameters chosen in the starting page. The following example illustrates this behavior.

*   **onlyReportParams**: to transfer to the target page only the parameters of the report.

    If this property is not selected, all parameters of the Page that includes the report are passed.
* **openActionType:** allows you to choose the type of DT. Whether to open a Page a Report or a URL
  * **Page / Report / URL** Depending on the type of action you can choose a Page a Resport or enter a URL

For openActionType selected on Report and Page the following are available:

* _**apply-sel-as-filter**_, if selected, allows you to automatically filter the target report or Page with the values exported from the starting report. This is allowed when the destination object has the same levels as the starting report. Selecting this property enables
  * _**filter-type**_ where we choose whether the filter _**is**_ _\<custom_> or _\<view>_>
* _**clear-params**_ if we do not want to use the parameters placed in the user session cache.
* **sent-parameters:** to select the levels that must be passed as parameters to the called object. If no level is selected, the property assumes the \<all-parameters> value and all the levels of the report are passed as parameters.&#x20;

In the following figure, we highlight the list of parameters exported and used by the destination object.

<figure><img src="../../../../.gitbook/assets/image (675).png" alt=""><figcaption></figcaption></figure>

#### Exporting all the values of the Report in DT

The property **export-body-content** enable the export of the values of the dimensional levels contained in the report on enabling of the Drill Through from items in Page-By or \<TOP>.

### Grants

The property  **drill-through-grants** allow to select which user groups can view the drill through. It's possible select one of this options:

* **All groups** : the DT is visible for all the users.
* **Selected groups:** the DT is visible just for a group of users.
* **All group excepted:** displays the DT to all groups except the one selected
