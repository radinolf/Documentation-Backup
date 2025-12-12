# Form

The entry components available are:

* [Text field](/broken/pages/-MgnwoeR4rnLcH21DIFw#text-field) of text type, such as simple strings, numbers, dates or codes
* [Text area](/broken/pages/-MgnwoeR4rnLcH21DIFw#text-area) to enter the subject text



The values of the components are the result of a query, executed either on the connected database or any data source defined in the system section. The query is defined in the _Query_ group, where:

* _**custom-datasource enables/**_&#x64;isables the selection of a data source other than the one of the application; selecting this property enables the
  * _**datasource**_ to select the DB where the query is to be executed.
* &#x20;_**sql-formula**_ where the query can be set based on the methods described in the Appendix.

The following is defined for this type of object:

* _**Param base name**_ the name of the component which will be used as the parameter in the Page
* _**disabled**_ enable/disable component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered.![](<../../../.gitbook/assets/30 (4).png>)

* characteristics of the text that appears next to the object:
  * _**formFontSize**_ font size (the height of the text field is adjusted to that of the font, chosen in this property)
  * _**formForegroundColor**_ font color
  * _**formBackGroundColor**_ background color
* _**textField effect**_ type of layout effect:
* _(none):_ no effect is applied
* _page default:_ inherits the effect [set at page level](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Stile_di_default) (reported between parenthesis)
* _shadow_: shading
* _rounded:_ rounding effect
* _gradient:_ effect with gradient

![](<../../../.gitbook/assets/31 (7).png>)

**Note:** _The shadow and rounded effect are not supported by the IE8_ _browser._

_In addition the shadow effect is not displayed correctly (the right external side is missing) if the auto-expand property is disabled. This is the property that automatically expands the length of the component._

* _**placeholder**_ enters display only text when the field is empty (see figure below); as soon as the user clicks inside the field, the text is eliminated.

![](<../../../.gitbook/assets/32 (4).png>)

### Text Area

The Text Area component is a text field consisting of multiple rows and columns, where you can enter unlimited free text.

The specific properties of the component are (Form _Group_):

* _**enable-validation**_ enables the following properties for validation through _Pattern_
* **objectInputPattern** Lets you define a text format which respects a regular expression

_For example A{3}\[0-9]{8} defines the rule that the text entered is to contain the letter A repeated 3 times, followed by an 8-digit numerical code: a valid code can be AAA12345678._

* **objectInputPatternError:** Specifies the message to be shown in the case of an invalid code. The error messages of the PATTERN support the multilanguage (see similar property for Text Filed)

The height of the Text Area is a few pixels lower than the [height defined in the container](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Dimensionamento_componente_\(Contain)

**Note:** _The border turns yellow when writing._

![](<../../../.gitbook/assets/33 (5).png>)

### Text Field

The Text Field component is a text field on a single line, where you can type text that matches the rules set up on the component, as explained later in this manual.

The specific properties of the component are (Forms _Group_):

* _**txtMaxLength**_ maximum length of the text (while the wiDSh is defined by the _wiDSh_ and _height_ property of the _ContainerStyle_)
* **text-align:** alignment of the text inside the Text Field. The values available are: left(default), center, right.

![](<../../../.gitbook/assets/34 (5).png>)

* _**objectInputType**_ field format:
* _STRING_ simple text
* _NUMBER_ numeric text
* _DATE_ date format;
* _PATTERN_ text on a regular expression

&#x20;**Note:** _The border turns yellow when writing._

![](<../../../.gitbook/assets/35 (3).png>)

#### Text Field of the DATE type

A Text Field of the date type is defined with the property (_Form_ group):

* _**objectInputType**_ with selection of the _**DATE item**_

The field configured in this way will show, on DAC, a calendar for the date selection.

![](<../../../.gitbook/assets/36 (2).png>)

This selection enables:

* _**inputDateFormat**_, date field format, defined via a configuration pop-up

The format of the date field is the one admitted for the parameter associated with the text field, used on any filter.

This format must also be respected in case there is a field population through loading queries.

* **selection-start-date** and **selection-end-date**: establish the time range within which the date may be set.

These properties can also be managed by using a parameter and must comply with the format specified by the _inputDateFormat_ property. In this case the date range which may be selected will be conditioned by the value assumed by the parameter.

Example: DATE type Text Field with date range![](<../../../.gitbook/assets/37 (6).png>)![](<../../../.gitbook/assets/38 (6).png>)

_The days in the calendar of the Date text field are managed by the values entered in the Start Date and End Date text fields_

#### Text Field of the PATTERN type

A Text Field of the PATTERN type is defined with the property (_Form_ group):

* _**objectInputType**_ with selection of the _**PATTERN**_ _item_

In this case the field is subject to a validity check of the entered text, which must respect a specific format. This selection enables:

* _**objectInputPattern**_ regular expression that must respect the field

&#x20;_For example A{3}\[0-9]{8} defines the rule that the text entered is to contain the letter A repeated 3 times, followed by an 8-digit numerical code: a valid code can be AAA12345678._

* _**objectInputPatternError**_ customized message in case an invalid code is entered. An error pop-up is opened by default, which reports the text validity rule.

The error messages of the PATTERN support the Multilanguage.

By entering the ID of a label in the ML\_LANGUAGE\_STRINGS table (ID\_STRING field) in the property mentioned above, and having it precede by the sequence of characters "**###%%%**", the system will display, DAC, the message associated with the specified label translated according to the language of the connected user.

![](<../../../.gitbook/assets/39 (8).png>)

The selection of values, which can be used to filter Page components, is defined using the following components:

* [PageBy Selector](/broken/pages/-MgnwoeR4rnLcH21DIFw#pageby-selector) for selections on a list via a rather similar object to the page-bys of the reports
* [StyledSelector](/broken/pages/-MgnwoeR4rnLcH21DIFw#styled-selector) for selections on checklist type lists through customized command keys

Other selectors are the page-by of the crosstabs and images.

### Styled Selector (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

The **Styled** Selector offers an object that has selector characteristics, where you can associate an attractive graphic style.

The list of values may be loaded _through_ a dimensional level (OLAP) or through a QUERY.

Different styles are available to present the elements of the list, when set the property:

* **style** (_Style_ _Settings_ group)
  * [Tab Menu](/broken/pages/-MgnwoeR4rnLcH21DIFw#tab-menu-style)
  * [Tooltip Selector](/broken/pages/-MgnwoeR4rnLcH21DIFw#tooltip-selector-style)
  * [List Selector](/broken/pages/-MgnwoeR4rnLcH21DIFw#list-selector-style)
  * [Radio Button](/broken/pages/-MgnwoeR4rnLcH21DIFw#radio-button-style)
  * [Table Selector](/broken/pages/-MgnwoeR4rnLcH21DIFw#table-selector-style)
  * [Checkbox](/broken/pages/-Mgnx9C6LGMGn1uwUlTx#_Stile_Checkbox) (default)
  * [Toggle Button](/broken/pages/-MgnwoeR4rnLcH21DIFw#toggle-button-style)

For each of these, specific customization properties are available. Those present for almost all the components are:

* **show-label-noSelection**

enables the management of the absence **of a selection**, defined in the property:

*
  * **custom-label-noSelection** text to be displayed in case the selection of a value has not be made (default “_No selection_”)

The _Check List_ and _Table Selector_ styles do not manage the selection absence, for which these properties are not enabled

* **object-transparency:** sets the transparent background for the elements which make up the object, except for the selected elements or those on which the mouse is positioned; in these two cases the background of the elements is the same as the one for the selected theme.

The _Check List_ and _Radio Button_ styles are always transparent and do not have this property enabled

**Note:** _The transparency of the Styled Selector widget is not supported on IE8._

* **disabled** Enables/disables the component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered (disabled for the value entry components).

An application example is shown at the end of this section.

#### Loading values from dimensional level (OLAP)

Selecting list values from a dimensional level is set using this property:

* **load-type** (_Form_) group by selecting _\<Olap>_

this selection enables the _Olap_ group properties:

* **level-associated**

selecting the dimensional level to load the values in the list.

After selecting the level, in the properties **Filter** (_OLAP_ group) ONLY the hierarchies levels will be presented, in which that level is present.

**Note:** _The param base name property is not editable in this case._

#### Loading values from QUERY

Selecting list values from a selection query is set through the property:

* **load-type** (_Form_) group by selecting _< SQL Query >_ which enables the following
* **exportType**

type of exported data from the query (_NUMBER_ or _STRING_)

Selecting _< Query >_ enables the properties of the group with the same name:

* _**custom-datasource**_ in the case of queries on data sources different from the one for the process
* _**sql-formula**_ where the query is defined.

#### Tab Menu Style

The **Tabbed&#x20;**_**Menu**_ style displays a menu, where each piece of data is entered in a special TAB.

This type of menu is single-selection (one item at a time), and you can enable the item for no selection. You can also customize the orientation.

![](<../../../.gitbook/assets/40 (6).png>)

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _Tab Menu_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **display orientation** orientation (default _on top_)

#### Tooltip Selector Style

The **Tooltip Selector style** displays the data available in a tooltip, open to the selection of a specific box, where the item selected in a previous phase is highlighted (see figure below).

![](<../../../.gitbook/assets/41 (6).png>)

Data is selected by single element, which is shown on the box.

Set this style using the property:

* **style** ( _Style Settings_ group) by selecting _Tooltip Selector_

#### List Selector Style

The _List Selector_ style displays a menu opened by selecting the arrows placed to the side. You can select a value by ticking the checkbox; multiple selection and enabling of the element search in the value list are available. The other features are shown in the figure.

![](<../../../.gitbook/assets/42 (2).png>)

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _List Selector_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **multi-selection** enables the multiple selection (disabled by default)
* **showFilter** it shows a text filter

#### Radio Button Style

The _**Radio Button**_ style displays a list that can be selected via radio button.

The list is single-selection (one element at a time), and you can enable the item for no selection. You can also customize the orientation.

![](<../../../.gitbook/assets/43 (8).png>)

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _Radio Button_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

*
  * **formAlign** sets the type of alignment (VERTICAL or HORIZONTAL)

#### Table Selector Style

The _**Table Selector**_ style allows you to have two adjacent lists, one containing the data available and one containing the selected data.

![](<../../../.gitbook/assets/44 (7).png>)

Data selection occurs:

* by single element

Clicking on the element to be selected moves it to the list of the selected ones.

Clicking on the selected elements moves it to the list of the available ones.

The ![](<../../../.gitbook/assets/45 (4).png>) button opens a field for the rapid search of the element to be selected.

* On all the elements

Clicking the ![](<../../../.gitbook/assets/46 (4).png>) button moves all the elements to be selected into the list of those selected.

Clicking the ![](<../../../.gitbook/assets/47 (3).png>) button puts all the selected elements back in the list of the available ones.

Data is selected by single element. You can search the data in the list, and you can transfer data from one section to another in massive or single mode.

Set this style using the property:

* **style** (_Style Settings_ group) by selecting _Table Selector_

#### Checkbox Style

The _**Checkbox**_ style displays a list that can be selected through a checkbox. The list is single-selection, and you can enable the item for no selection. You can also customize the orientation.

![](<../../../.gitbook/assets/48 (7).png>)

Set this style using the property:

* **style** ( _Style Settings_ group) by selecting _Checkbox_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **formAlign** sets the type of alignment (VERTICAL or HORIZONTAL)

#### Toggle Button style

The _Toggle Button_ style displays a menu, where each value is entered in a special TAB and you can also customize the orientation.

![](<../../../.gitbook/assets/49 (5).png>)

Set this style using the property:

* **style** ( _Style Settings_ group) by selecting _Toggle Button_

this selection enables the specific properties of the template (_Style Settings_ group)_**:**_

* **formAlign** sets the type of alignment (VERTICAL or HORIZONTAL)
* **disabled** Enables/disables the component (enabled by default)
* **multi-selection** enables the multiple selection (disabled by default)

### PageBy Selector

A particularly useful object is the _**PageBy Selector**_, of the same type as the drop-down menu, but much easier to define and more flexible to use. For all intents and purposes, the pageby selector corresponds to the page-by of a report as regards its definition and features, because most of the properties of the Page-bys of the reports are actually present in the selector.

The _**PageBy Selector**_ object, belonging to the Form _group_ of the Page Designer _components_, lets you build a selector starting from one or more dimensional levels.

The selected levels will be displayed as real page-bys and will behave in the same way as the page-bys defined in a report.

The levels defined in this object are available as filter parameters for the other objects contained in the Page.

The **specific properties** of the object are:

* **levels-associated** (_Main_ group)

to select the dimensional levels to be used as selectors.

A window opens listing the levels of each application cube; use the double arrow keys to move those to be associated with the object.

![SNAGHTML7ee2d9](<../../../.gitbook/assets/50 (1).png>)

* **alias-level** (_Main_ group)

associates the aliases to the dimensional levels selected in the previous property.

**default-select-type** and **selection-type** (_Page-by group_)

similar to those of the reports for the selection method where you set the selection type, among single, single with research or multiple with research; in _default-select-type_ set the default one to be assigned to all the elements in Page-By, while in _selection-type_ change the default for some of these elements.

* _**opening-selection**_ (_Page-by_ group)

same as the one of the report, for the positioning of the values in the list.

* _**num-elements-row (web)**_, _**selector-wiDSh (web)**_ and _**show-initializer (web)**_ (_Page-by_ group)

similar to those of the report for the layout on DAC, where _num-elements-row (web)_ indicates the number of page-by to be displayed on the same row before using the enter button; _selector-wiDSh (web)_ the wiDSh of the page-bys; _show-initializer (web)_ enables the reset button of the page-bys to the opening values of the report.

* _**total-visibility**_ and _**levels**_ (_Page-by_ group)

similar to those of the report for the page-by totals, where in _total-visibility_ you set the presence of the item \[Total] for all, no or just some of the levels, (chosen in _levels_)

**Below is an example of configuring the PageBy Selector object**

#### Step 1: PageBy Selector

![](<../../../.gitbook/assets/51 (7).png>)

_A Page was created in the example where the PageBy Selector component is configured._

_From the levels-associated property, the levels YEAR and MONTH are selected._

_These will become the selectors that filter all the objects on the page, which in turn contain the same levels._

_Aliases were configured for the levels: ‘Select Year’ for YEAR and ‘Select Month’ for MONTH._

_The selection types for page-bys are multiple for the Month level and single for the Year level (set in selection-type)._

#### Step 2: PageBy Selector

![](<../../../.gitbook/assets/52 (7).png>)

_The figure shows how the Page created in the previous step is displayed. Note that the levels defined in the PageBy Selector object are displayed as page by. The selection is single for the year and multiple for the month and the report and graph below are valued based on the selection._

### File Selector (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

The File Selector component allows a file to be selected by the Client, then allows it to be uploaded and associated with a setting used in the Page page.

![](<../../../.gitbook/assets/53 (5).png>)

The file can be loaded in two ways:

* **Easy**, for files uploading, where you specify the allowed types.
* **Excel Integration**, to load an Excel file, which will then be uploaded into a database table. The component that transfers the file data into the table is the Execute button, Excel Integration type.

The File Selector component is available under the _Form_ group. The specific properties are as follows:

* **Upload-type** (group _Form_), type of upload:
  * EXCEL\_INTEGRATION to upload an Excel file, to be integrated into the data table.

Files with the "xlsx" extension are permitted (mime-type: _application/vnd.openxmlformats-officedocument.spreadsheetml.sheet_).

*
  * SIMPLE\_UPLOAD to load a generic file. This selection enables the following properties:

**mime-type,** for the selection of the mime-type allowed for the Files to be uploaded.

Several mime-types can be selected and, if none are selected, the system will allow any type of file (default).

![](<../../../.gitbook/assets/54 (7).png>)

It is possible to add the mime-type if not present in the predefined list. In order to add a new mime-type, it is necessary to enter the new mime-type using the list of standard mime-types ([http://www.iana.org/assignments/media-types/media-types.xhtml](http://www.iana.org/assignments/media-types/media-types.xhtml)).

* **maxUploadFileSize (MB)** (_Form_ group), maximum size permitted for the file to be uploaded (default 50 MB, maximum value 200 MB).

The file uploaded with the File Selector by the user is entered in the repository, thereby creating a new resource.

The system generates two settings associated with this resource:

* The first has a name that coincides with the name assigned to the property _param base name_ for the componen&#x74;_._

This type of setting will contain the **identification of the resources associated with the file** uploaded by the user.

* The second has a name that coincides with the first, to which "\_NAME" is added and which will include the **name of the file** uploaded by the user.

![](<../../../.gitbook/assets/55 (7).png>)

These settings can be used in the Page page. For the SAMPLE UPLOAD type, the setting may be used:

* in an Execute button type of Query, referencing the setting in the query

_One example is uploading the image resources to be associated with a size: it is assumed that the uploaded images correspond to a product. The entry query may be set with respect to the product, resources, or image type._

For the EXCEL INTEGRATION type, the setting is used directly in the following configuration:

* from the Execute button [Excel Integration](/broken/pages/-MgnwoeR4rnLcH21DIFw#excel-integration)

All of the uploaded resources are automatically deleted after 7 days, except for those resources used in the Executive Object component for the _QUERY_.

For the use of the component _(file selection)_ section.
