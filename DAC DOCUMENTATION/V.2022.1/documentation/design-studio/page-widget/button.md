# Button

### Execute button

The **Execute button** component lets you perform operations which interact with other systems or other DAC objects.

The execution of the _Execute button_ is only allowed after having assigned values to the parameters defined as mandatory.

The type of operation is set in the **execution**_**-type**_ property (_Execution group_):

* _**QUERY**_ performs one or more queries
* _**CODE\_SNIPPET**_ _execution_ of a code snippet.
* **NOTIFICATION** starts notifications
* **DLR** starts data transfer. This property enables:
  * _**DLRS**_ associates data transfer processes, previously defined

**Note:** _The system also supports passing parameters from the Page page to any parametric filters of the source report_.

* **REFRESH RULE** _execution_ of the scheduled updating in DAC. This property enables:
  * _**refresh-rules**_ associates the refresh-rules, previously defined.

**Note:** _The system also supports the passage of parameters from the Page page to any parametric filters used as components of the refresh-rule._

* [**DRILL THROUGH**](button.md#opening-a-page-using-drill-through)_,_ to open a page in drill-through
* **APPLY\_SELECTIONS\_OPENER\_PAGE** applies the selections made in a page opened in a pop-up to the underlying page. This makes it possible to open a secondary Page in drill-through, when starting from a main Page. The secondary page selections are then applied to the main Page on the click of the button. The secondary Page will thus be the selector, and what is selected will be applied to the main Page.
* [**EXCEL\_INTEGRATION**](/broken/pages/-MgnwoeR4rnLcH21DIFw#excel-integration) allows an Excel file to be generated and for the data from that file to be entered in a database. The files are uploaded using the [File Selector](/broken/pages/-MgnwoeR4rnLcH21DIFw#file-selector-file-selection) component, with the Excel Integration procedure.
* [**TALEND\_INTEGRATION**](/broken/pages/-MgnwoeR4rnLcH21DIFw#talend-integration), allows the start of a Talend JOB.
* **JAVASCRIPT\_ONLY** allows you to run JavaScripts that are only set in the _**javaScript-code-before**_ and _**javaScript-code-after**_ property

It is possible to enter the JavaScript code to be run before and/or after the execution of the operation associated with the component:

* **javaScript-code-before JS** code run BEFORE the operations of the component
* **javaScript-code-after JS** code run AFTER the operations of the component

The properties support the use of parameters within them.

For Pages open in _**drill-through**_ and containing the _Execute button_:

* _**close-on-execution-success sets**_ the closing of the Page, when component execution has completed;
* _**refresh-opener-report specifies**_ the refresh of the _calling_ report (the one which opened the Page in drill-through).

Using the properties:

* _**post-execution-button**_ Sets another Execute button, present in the Page page, executed immediately after the action associated with this Execute button. The other configurations defined in the Execute button chosen in this property are ignored.

_For example, if this property is on Execute button A, and Execute button B is chosen in this property, the following actions will be executed in sequence: the action defined in Execute button A and the action defined in Execute button B. Any settings of Execute button B, such as the JavaScript code to be run before or after the action, are ignored._

This enables you to define a chain of executions.

For the text properties:

* _**button-text**_ (_Main_ group) for the button text (default “_Execute"_).

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button

Finally, the properties:

* **disabled** Enable/Disables the component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up where the name of the parameter is entered.

#### Mandatory Parameters

The _**mandatory**_-params property (Execution group) enables the various types of mandatory parameters:

* _**\<all-parameters>**_ specifies that all the parameters used are considered mandatory. The button may be run only after all the parameters have been valued.
* _**\<none>**_ specifies that no parameter used is considered mandatory. The button may be run whether or not the parameters are valued.
* _**\<selection>**_ specifies that only some of the parameters used are considered mandatory. This type activates:
  * the parameters property which specifies the mandatory parameters.

While running the Execute button:

* a pop-up will be shown next to the mandatory parameters that do not have values.
* in the case of mandatory parameters inherited from other pages, or for which a selector is not explicitly present in the page, a window will be opened instead which indicates the parameters to be valued.

If the _Execute button_ is associated and run in a **Wizard**, and executed at the end of the flow, DAC checks that the mandatory parameters for each step are valued. If not, access to the next step will be prevented.

#### Starting a Query

Starting a query is set by selecting _QUERY_ in the **execution-type** property: the _**sql-formula**_ property is enabled to define the query.

The query can either be added or updated, allowing you to interact with the data warehouse or other databases.

The query statement allows the use of parameters. In this case, using the property:

* _**mandatory-params**_ you can define if the parameters are mandatory (property selected, default) or not (property unselected).

**Note:** _If, the mandatory parameters are not valued before clicking on Execute query, the system shows the fields, and signals an error message._

![](<../../../.gitbook/assets/56 (2).png>)

If the application interacts with databases other than the data warehouse (set in the application), initially a data source is defined for the connection to the database, using the _Datasource Designer_ module (see _Connections to remote data sources section_).

Then the data source is associated with the component:

* the _**Custom-datasource**_ property is selected
* the _**datasource**_ property is enabled, with which the previously created datasource can be selected

Also see Appendix I for more details on the settings of the SQL statement and the reference to the data source.

#### Starting a Notification

The _Execute button_ component allows you to start a notification previously defined using the _Notification Designer_ module (see _Notifications_ section).

When notifications are being executed, the parameters currently selected in the Page can be used within email notifications to customize the content.

The recipients of the notification can also be made dynamic by adding users selected within the Page to those set in the notification itself. New recipients selected in the Page should be defined as follows:

* A selection or input _form_ object is inserted, to which the special name **NOTIFICATION\_RECEIVERS** is assigned
* For selection objects (Select or Checklist), the query is entered to load DAC users (from the Data Model database), which is defined as:

**Select&#x20;**_**SUBJECTS.SUBJECT\_ID,SUBJECTS.SUBJECT\_NAME**_ _\[or SUBJECTS.USERNAME]_

**From&#x20;**_**\[metadati].SUBJECTS**_

To associate one or more notifications with the _Execute button_ component, simply

* select the NOTIFICATION _item_ in the **execution-type** property
* enable the notifications property, which allows associating notifications created previously

There is an example below of sending an e-mail notification from the Page.

#### Opening a page using Drill-Through

Using the Execute button object, you can open a Page page in Drill-Through.

Starting from a main Page, you can open a secondary Page through drill-through.

The Page opened in DS may be displayed in a new page or in a modal type window.

When the **execution-type** property is set to **DRILL\_THROUGH**, the following properties are enabled:

* **openNewWindow:** by default it is disabled and therefore the Page is opened in the same page.

If you select the openNewWindow property, the Page is opened in a new page, and the following subproperties are enabled:

* **dialog-title:** set the window title,  support variable (ex. ?variable? ).
* **show-on**: Defines where to render the drill through (contextual rendering and no contextual rendering).
* **openNewWindow :** opens the URL on a new page
* **drill-through-grants:** allows you to select which user groups can.
* **full-screen:** opens the whole screen
  * **window-width:** sets the width of the window (visible if the full-screen property is not enabled)
  * **window-height**: sets the height of the window (visible if the full-screen property is not enabled)
* **enable-esc-to-close:** Allows user to close the dialog by pressing ESC keyboard button" default true
* **allow-user-to-close:** Allows user to close the dialog" default true)
* **click-outside-to-close:** Allows the user to close by clicking outside the dialog" default false
* **allow-full-screen:** Allows user to enlarge the dialog to full screen" default true
* **openActionType**: sets the type of action to be associated out of:
  * **Page** : for the opening of a Page page. If selected enables the subproperty:
    * **Page** selects the Page that will be opened by the DS
  * **Report** for the opening of a report. If selected enables the subproperty:
    * **Report:** selects a specific report
    * **clear-params:** if selected, cleans all the parameters in the destination report.
  * **Open URL: opens a web page**. If selected enables the subproperty:
    * **url:** lets you enter the internet address of the page you want to open.
* **mandatory-params:** lets you establish which parameters must be mandatory, if any.
* **< all-parameters** >all the parameters in the page.
* **< selection >**&#x6F;nly the selected parameter&#x73;**.**
* **< none >** no parameter.
* **post-execution-button :** sets a button whose execution will be carried out after the action associated with the same button, to define a sequence of executions. The action associated with the button will be performed, the other settings defined in it will be ignored
* **javaScript-code-before:** define the javascript code to execute before executing the button.
* **javaScript-code-after:**&#x64;efine the javascript code to execute after executing the button.



#### Excel Integration

The type of Excel Integration allows the files to be processed and for data to be entered in a table from a database.

The files are Excel files and are uploaded using the [**Files Selector**](/broken/pages/-MgnwoeR4rnLcH21DIFw#file-selector-file-selection), configured for Excel integration, i.e. with:

* **upload-type** (_Form_ group set to EXCEL\_INTEGRATION

When the user clicks on _Executive Object_ the transfer of the data from the Excel files is started (uploaded with the _Files Selector_) in a database table:

The selection of the database is carried out on the Manual level and may be modified with the _Executive Object_ properties.

The properties for the configuration of the Execute button component for the EXCEL\_INTEGRATION are (_Execution_ group):

* **integration-name:** name of the setting that univocally identifies the last data imported from the Excel file.
* **file-selector-name:** name of the File Selector component used to upload the Excel file.

It is selected from a list of all of the Page File Selectors, which have the _**upload-type**_ property set for the _EXCEL\_INTEGRATION_.

* **destination-table-name**: name of the [integration table](/broken/pages/-MgnwoeR4rnLcH21DIFw#excel-integration), to which the Excel spreadsheet data is transferred.
* **Sheet-to-copy**, name of the Excel spreadsheet containing the data to be transferred to the table.
* **destination-table-definition**: open a window for the configuration and validation of the destination table
* **custom-datasource**: to edit the system database
* **post-import-procedures**: procedures that are carried out after uploading the data, in order to carry out the different SQL operations on the same data source as for the imported table.

The post-import operations may work for the last rows inserted or modified in the integration table: the setting is assigned a value in the _integration-name_ properties that identifies it univocally.

The Excel file is uploaded in the table until the first empty row is reached:

* The row is considered empty when all of the cells in the row, corresponding to the columns defined for import, are empty.

**Selection of the database for table integration**

The database that needs to contain the integration table is selected from the system level in the _**Tools**_ properties:

* **excel-integration-tables** (_Storage table schema_ group): overview of the database that will contain the integration table with the Excel files, uploaded using the _File Selector/Execute button_ **components**.

The scheme may be selected from those for the default Data Model databases and configured based in the Data Model scheme.

In the individual _**Execute button**_, for the _**Excel Integration**_, another database can be set, in the following properties:

* **custom-datasource**: to activate a database selection that is different from that for the system.

The activation of this property enables the following:

*
  * **datasource**: to select the data source that will contain the integration table.

A pop-up is opened with the list of the editable data sources (_not read only_) defined by the administrator in the Datasource Designer.

In the _**Datasource Designer**_ , when a data source is defined that needs to be associated with the Executive Object, in the properties:

* **Excel-integration-tables** (_Storage table schema_ group): select the screen where the integration table will be saved

**Creating an integration table**

The integration table is entered manually in the properties for the **destination-table-name**.

For the name, the prefix "EI\_" is always entered, so that the Data Model tables are not involved, in fact, the default database for saving these tables is the Data Model schema.

If the table still does not exist a Page save is created, so that the table already exists at the time of import.

The table is created using the settings defined in the **destination-table-definition** properties, and, the following columns are added:

* USERNAME\_ID: user identification
* DATE\_OPERATION: date of the operation
* EXPORT\_PARAMETER: operational identification, related to the Page setting.

If the table exists, the system, requesting confirmation, will delete the existing table and replace it with the structured defined in the **destination-table-definition**.

**Configuration of the Integration Table**

From the properties _**destination-table-definition**_ , a window is opened, such as the one in the figure below, which allows the table columns to be defined manually or using an Excel file that is used as a template.

![](<../../../.gitbook/assets/57 (5).png>)

To **define the columns in the Excel file**, select the key indicated in the figure, which opens a window to select the file.

![](<../../../.gitbook/assets/58 (2).png>)

Remember that there needs to be an ".xlsx" extension. After selecting the file, the spreadsheet containing the data must be selected.

![](<../../../.gitbook/assets/59 (3).png>)

After selecting the Excel file, the rows in the configuration window are assigned a value as follows:

![](<../../../.gitbook/assets/60 (3).png>)

* **Name** of the column for the **Excel spreadsheet**, corresponding to the first row in the spreadsheet that is not empty.
* **Name** of the column for the **table integration**, automatically defined by the system
* **Type** of column, automatically evaluated by the system. The data supported are NUMBER, STRING and DATE.
* **Requirement**, evaluated by the system on the values of the row following the header;

if not empty, it is set as required.

This procedure can be repeated by selecting another file/Excel spreadsheet. The system will manage the changes introduced by the new template.

**Note:** _The header columns in the Excel spreadsheet cannot be numerical_.

**Manual configuration** can be carried out by entering the column name in the appropriate space and by clicking on the “+“ key (see the figure below).

![](<../../../.gitbook/assets/61 (5).png>)

The name entered may have a maximum of 60 characters and does not have constraints regarding the type of characters.

Even in this case, a row is added to the window, with the following assigned values:

* Name entered in the top field
* Name of the table integration table, as automatically defined by the system
* STRING column type
* Selection requirement

By selecting the _**Column Type**_ key, a pop-up is opened to define the following:

* **data-type**: modify the column type using the default setting.

The selection of the type of enabled STRING:

*
  * **validation-pattern**: to define a pattern for the column data.

The selection of the enabled type of NUMBER:

*
  * **precision**: maximum number of decimal places (default 5)
* **length**: maximum length (default for STRINGS: 4000, default for NUMBERS: 18)

**Note:** _In order to load the columns defined by the type of number, the empty cells are managed by entering a null value._

**Change in the Integration Table**

When a new Excel template is loaded, the system manages the structural differences and the types of incongruent data, based on the following definitions:

* the columns present in the first definition are highlighted in RED but are no longer present in the new template. The columns that are manually entered and not present in the template are highlighted in RED.
* the columns that have **a different type of data** with respect to the previous definition are highlighted in YELLOW.

If there is a change in the type of data, and/or length, and/or required criteria, with respect to that defined in this database table, and the database does not allow this operation to be carried out, the system will provide a warning, asking for confirmation that _the table will be recreated and that all of the data contained therein will be lost_.

In the event that a column is added or deleted, the system updates the table present in the database, in order to be able to reflect the settings made during the configuration phase.

If the database does not lead to the termination of the operation to update the table (for example: _insufficient_ tablespace or missing privileges), the user is advised that it isn’t possible to create the table, and the exception is reported.

The following is an example of a template modification for the circumstances described in the preceding paragraph.

![](<../../../.gitbook/assets/62 (3).png>)

**Validation of the Integration Table**

After configuring the integration table, any validations are executed.

The key indicated in the figure allows the columns that have already been defined to be validated with the columns in a file.

![](<../../../.gitbook/assets/63 (8).png>)

By clicking on the validation key, a window is opened for file selection.

After selecting the file and the Excel folder, the system checks that the fields match for the first row and that the name of the _**Files Column> Name**_ match, verifying the following:

* Type of data
* Requirements

If an error message indicating the type of error is displayed, the table is generated anyway if a save operation is carried out.

#### Talend Integration

The Talend Integration type allows you to start a Talend Job through Execute button.

The Job, created on Talend, should be loaded as a resource in the Resource Catalog, which will recognize it as a Talend Job resource type. A series of variables, used during the execution of the job, can be defined in Talend. Together, these variables define the context; a default value can be assigned to the variables.

Besides the default value, these Job parameters can be configured to assume the values of the Page parameters.

If the associated resource contains multiple jobs, the one associated with the Main Class, recognized by DAC (contained in the bat file), will be executed. If the associated resource contains a job with multiple child jobs, the parent job will be executed first and, in sequence, the child jobs.

Selecting the **TALEND\_INTEGRATION** option in the _**execution-type**_ property will enable the following:

* job, opens a pop-up for the selection of the job to execute. The window lists all Talend Job resource types loaded in the Resource Catalog.
* input-params-mapping, opens a pop-up for the mapping of the job context. For every parameter of the context, the following can be assigned:
  * \<Default>, in order to consider the given definitions as default in the Talend Job context.
  * One of the Page parameters. All parameters present in the dashboard are, in fact, listed

![](<../../../.gitbook/assets/64 (6).png>)

If one or more of the context parameters were not configured, or rather the Page parameters have not been assigned values, then the default values will be assigned when the Job is executed.

If the resource associated with the job contains multiple child jobs, parameters can be passed directly only to the parent job. The parent job will then propagate them to the child jobs.

#### An Example of Opening a Page in Drill-Through

The example below explains the use of the execute button inside a Page.

Specifically, it describes how to use this object in the following instances:

* to open a new page of a Page (_**DRILL\_THROUGH**_)
* to enter the data through SQL query (**QUERY**) and at the same time _**(**_**post-execution-button**) to start a second button to automatically send a notification e-mail (**NOTIFICATION**).

Step 1: Execute button as DS and use the post-execution-button

![](<../../../.gitbook/assets/65 (6).png>)

_The Page in the figure is an Order form._

1. _The user enters his personal data in the User Information and Address section._

_Through the New Order button, open a Page page, where you can select the type of product you want to order._

1. _After closing the window ("OK" button), the fields of Your Order section will be valued, through the automatic passing of the parameters._
2. _The third step is the confirmation of the order request that takes place via the Confirm Order button._

_This button, in addition to saving data entered by the user inside the database, will execute a second object (invisible to the user) which will send an e-mail relating to the order request_

Step 1:Execute button as DS and use the post-execution-button

![](<../../../.gitbook/assets/66 (2).png>)

_The Page consists of many objects. The example below shows how the three Execute buttons are configured._

1. _The first execute button (New Order) opens the Page page for selection of the new order through the DS._

_The object was configured as follows:_

* _the execution of the object of the DRILL\_THROUGH type (execution-type)_
* _the Page will open in a new page but in the same window (openNewWindow and Open-in-same-window)._
* _The new page will have a size of 900 by 700 (window-wiDSh and window-height)._
* _From the openActionType property, select the Page Page option and in a Page, select the Page which will be opened by DS._

1. _The second execute button (Send E-Mail) automatically sends an e-mail. This button will not be visible to the end user since it was created to be used by the third button, after sending data to the database._

_The object was configured as follows:_

* _the execution of the object is of the NOTIFICATION type (execution-type)_
* _from the notification property select the notification to send the e-mail._
* _select all the parameters available in the Page \<all-parameters> (mandatory-params)._

1. _The third execute button (Confirm Order) enters the data of the form in a table of the database._

_The object was configured as follows:_

* _the execution of the object is of the QUERY type (execution-type)_
* _the entry query was entered through the sql-formula property_

_After entering the data, the second execute button will be automatically enabled, which will send the e-mail._

_This is possible by recalling the execution object Send Mail inside the post-execution-button._

_Thus with a simple click, the system automatically sends the e-mail and enters the data in the database._

Step 3: Execute button as DS and use the post-execution-button![](<../../../.gitbook/assets/67 (5).png>)![](<../../../.gitbook/assets/68 (4).png>)![](<../../../.gitbook/assets/69 (2).png>)![](<../../../.gitbook/assets/70 (3).png>)

_The figure shows the configuration of the Page opened through DS by the New Order button._

_The Page consists of several objects including Checklists and Text Fields. parameter , the same Form Name as the one of the corresponding objects in the calling Page was assigned._

&#x20;_the Execute button was configured in order for it to pass the parameters to the Page page called._

_The object was configured as follows:_

* _the execution of the object is of the APPLY\_SELECTION\_OPENER\_PAGE type (execution-type). This setting will let you pass all parameters (mandatory-params) to the requested page. In this case the parameters will populate the Your Orders section of the main Page._

Step 4:Execute button as DS and use the post-execution-button

![](<../../../.gitbook/assets/71 (4).png>)

_The figure shows the final Page._

_When accessing the Page for the first time, the user enters his data in the User Information and Address section._

_The New Order button opens the Page to select the products to be ordered. The user selects the desired product, specifies the quantity, and saves the order by pressing OK._

_The window closes and the main Page automatically values the fields referring to the order (Your Orders)._

_Finally the user confirms the order (Confirm Order button) and the system automatically enters the data in the database and sends an e-mail with the information relating to the user and chosen product._

#### Example of Database Update (QUERY) and Sending an E-mail (Notification)

The Page in the figure was designed to plan the working activities of the DAC users.

The system will be able to inform users, via an e-mail notification, of the activities they have been assigned.

Step 1: Page

![](<../../../.gitbook/assets/72 (1).png>)

_The Page in the figure was designed using the following components:_

* _a Checklist (Select Activities) for selecting one or more work activities_
* _another Checklist (Select User) for selecting the user, to assign these tasks to_
* _two Text Fields (Start Date/End Date), set as calendar (date type), which allow selecting the period when the task is to be carried out_
* _the Assign Task button which assigns a task to a user , and which updates the tasks/appointed user table (the respective size is mapped on that table)_
* _the report (User Activities), built on the tasks/appointed user size, which shows the tasks with the associated user_
* _a Gantt chart, which provides an immediate perception of the tasks established_
* _by using the Send e-mail button, the notification is e-mailed to the selected user initially on the tasks the user was assigned to_

Step 2: Page

![](<../../../.gitbook/assets/73 (2).png>)

_The following are main properties set for the components shown in the figure:_

* _The first Checklist (Ds\_Attivita) displays a list of tasks and allows selecting multiple tasks since it is set to multi-selection mode (multi-selection)._

_Population was executed using a query._

* _The second Check List ( (NOTIFICATION\_RECEIVERS) will let you select the users to send the notification e-mail to._

_For correct operation, the name NOTIFICATION\_RECEIVERS must be assigned in the \<formname>._

_The query used to load the DAC users is entered (from the Data Model database), which is defined as:_

_select SUBJECTS.SUBJECT\_ID,SUBJECTS.SUBJECT\_NAME \[or SUBJECTS.USERNAME]_

_From \[metadati].SUBJECTS._

* _The Text Fields (Start Date and End Date) are set as calendar and are used to select the period when the selected task is to be performed._
* _The report will contain the dimensional levels relating to tasks and users._
* _The graph will display the tasks assigned to each user and the start and end date of the schedule._

Step 3: Page

![](<../../../.gitbook/assets/image (173).png>)

_The Execute button, called Assign Task, uses a query to update the table used by the User Task report, and assigns the user to the selected task._

_From the \<execution-type> property, the type of operation is selected, which is to be assigned to the Execute button, which in this case will be of Query type._

_The update query is entered in the sql-formula, and will be of the type:_

_UPDATE table-name_

_SET_

_field1-table='?Name\_User?_

_field2-table=?Start\_Date?,_

_field3-table=?End\_Date?_

_WHERE field-table IN ('?Ds\_Task? ')_

_Note that the relative parameter transferred in the Page was assigned to every field in the table._

Step 4: Notification Designer

![](<../../../.gitbook/assets/76 (4).png>)

_The notification is created, which will then be associated with the Execute button object on the Page._

_Access Notification Designer from the Application section of the DAC._

_A new e-mail notification is created._

_Right-click on the root and select Create Mail Notification. ._

_Assign a name to the notification (in this case, Assign Task mail)._

_In the Title section, a title is entered and in this case, the attribute % SUBJECT% was entered to make the title of the notification dynamic, based on the user to whom it is sent._

_An HTML code was entered in the Body section to create a table that will contain the information about the user name, the task and the start and end date._

_This information will be made dynamic since the code contains the exported parameters of the Page components._

**The following HTML code is entered:**

![](<../../../.gitbook/assets/77 (3).png>)

```
<table wiDSh=50 border="3" bordercolor=#616f79 >
  <tr>
       <td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">User Task</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date%SUBJECT%?</td>
</tr>
    <tr> 
       <td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">List Of Assigned Tasks</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date?Ds_Attivita?</?</td>
   </tr>
<tr>
      <td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">Start Date</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date?Start_Date?</?</td>
</tr>
   <tr>
<td bgcolor="#7a3588"> <font color="#ffffff" size=4 face="Calibri">End Date</font></td>
<td bgcolor="#c9c5e4"> <font color="#660066" size=4 face="Calibri">?End_Date?End_Date??</td>
 </tr>
</table>

```



**THE PARAMETERS ARE HIGHLIGHTED IN RED.**

Reports or Pages can be attached to the e-mail.

In the _Attachments_ section, you can either select a report from the ![](<../../../.gitbook/assets/78 (2).png>) button or a Page by selecting the.![](<../../../.gitbook/assets/79 (4).png>) button.

In this case, a detail report was selected.

Step 5: Notification Designer

![](<../../../.gitbook/assets/80 (3).png>)

_The Execute button named (Send e-mail) is a button that allows sending an e-mail to the recipient, after the tasks have been selected. In \<execute-type>, the operation to be assigned to the object is selected, which will be of the NOTIFICATION type. The \<notification> property is enabled from which, using a selection window, the notification created previously (Assign Task mail) is selected._

Step 6: E-mail

![](<../../../.gitbook/assets/81 (3).png>)

_Based on the graphical settings set using HTML code, the Body of the notification e-mail will be displayed as shown in the figure._

### Submit

The action of the **Submit** component consists of making the page parameter changes effective on the data presentation objects.

In the Analysis by pane _of this_ Page, we select the values, which are filter parameters for the two graph and table objects.

Selecting the parameters has no effect on the two presentation objects. Whereas, if you click the _Send_ button (**Submit** component), the values of the parameters are applied to the graph and table, which will show the result of this filtering.

Also the **Submit** action is only enabled for data presentation components with the **refreshMethod** property set to _OnSubmit_.

For the text properties:

* _**button-text**_ (Group _Main_(Text) for the button (DEFAULT “_Submit_”)

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button

Finally, the properties:

**disabled** Enable/Disables the component

This property **may also be assigned a parameter**, so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered .

### Parameters Cleaner

This object serves to restore the parameters of the page to the initial conditions.

![](<../../../.gitbook/assets/82 (3).png>)

The configuration of this component takes place through the properties of the _Main_ group:

* _**clean-type**_ type allows you to select whether to apply the reset operation to all parameters of the page (_\<all-params>_) or to a subset of them (_\<selection>_), which enables the property:
  * _**param-selection**_ for the selection of the parameters to be reset.
* _**reinit-page-By**_ to restore initial conditions, also of the values of the page-bys on the Page
* _**Custom-JS-code-after-params-clean**_ JavaScript code to be executed when the component is selected.

Restore the initial values of the parameters at the page level can also be enabled, rather than from the _Params Cleaner component._

For the text properties:

* _**button-text**_ (Group _Main_(Text) for the button (DEFAULT “_Settings cleaner_”) .

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button.
