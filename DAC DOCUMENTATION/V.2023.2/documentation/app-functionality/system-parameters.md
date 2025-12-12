---
description: List of System Parameters
---

# System Parameters

The built-in parameters are application’s parameters whose value is automatically set by the back-end and can not be modified at runtime.

DAC build-in parameters can be used to create additional business logic in the application and they can be used in pages, reports, metrics, levels etc, in example:

* User filters (please see User Filters Section).
* View Filter of the reports (see Customized Filters section).
* Default values or filter conditions in the pages (see Page Behaviour Section).

The built-in parameters can be grouped in the following categories:

* [User parameters](system-parameters.md#user-parameters)
* [Application parameteres](system-parameters.md#application-parameters)
* [System parameters](system-parameters.md#system-parameters)
* [Page parameters](system-parameters.md#page-parameters)
* [OLAP parameters](system-parameters.md#olap-parameters)

### **User Parameters**

These built-in parameters depends on the connected user. Some of them may depend on the application that the user is currently using.

<table data-full-width="true"><thead><tr><th width="175">Name</th><th>Description</th><th width="200">Example</th><th>Scope</th></tr></thead><tbody><tr><td><strong>%SUBJECT_ID%</strong></td><td>The unique ID of the user. The same ID is also visible in the user administration page.</td><td>111111111111111</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%U_username%</strong></td><td>The username of the user</td><td>JohnDoe</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%U_subjectFullName%</strong></td><td>The concatenated name and surname of the user.</td><td>Doe John</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%U_subjectName%</strong></td><td>The name of the user</td><td>John</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%U_subjectSurname%</strong></td><td>The surname of the user</td><td>Doe</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%U_attribute_[n]%,</strong></td><td><p>The value of the user attribute set for the connected user.</p><p>The user attributes can be defined in the dedicated administration page, where it’s possible to define the name of the custom <a href="https://documentation.decisyon.com/documentation/run-time/administration/users-administration#create-new-user">user attribute</a> and other properties.</p></td><td>Decisyon Plant</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%U_mail%</strong></td><td>The email of the user.</td><td>john.doe@example.com</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%user_decimal_separator%</strong></td><td>The decimal separator of the user, depending on his/her language setting.</td><td>. (dot) or 0 , (comma)</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%user_timezone%</strong></td><td>The time zone of the user, as defined in his/her profile.</td><td>(UTC+01:00) Central European Standard Time</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%CURRENT_TENANT%</strong></td><td><p>The ID of the tenant currently selected by the connected user.</p><p>If the user is not associated to any tenant, the parameter return -1 value</p></td><td>111111111111111</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%TENANTS%</strong></td><td>The ID of all tenants associated to the connected users, separated by a comma.</td><td>111111111111111</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%GROUPS%</strong></td><td><p>The list of groups associated to the user.</p><p>If the user belongs to more than group, the parameter lists the group ID in square brackets, separated by a comma: e.g. [123,345]).</p></td><td>111111111111111,<br>222222222222222,<br>333333333333333</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%G_attribute_[n]%</strong></td><td><p>The attributes set on each group to which the connected user is associated to.</p><p>with n=1-5, for the 5 attributes that can be assigned to an Group</p></td><td>GroupAdministrator</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul><p></p></td></tr><tr><td><strong>%ACCESS_TOKEN%</strong></td><td>The value of the Access Token issued by the OIDC server and assigned to the user</td><td>XXXXXXBWAKPYC1EL21JX</td><td><ul><li>API Rest</li><li>Datasource Rest</li><li>Page as Preselection values</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%ID_TOKEN%</strong></td><td>The value of the ID Token issued by the OIDC server and assigned to the user</td><td>XXXXXXYYYZZZ</td><td><p>API Rest<br>Datasource Rest</p><p>Page as Preselection values</p></td></tr></tbody></table>

### **Application Parameters**

These built-in parameters depends on the application that the user is currently using.&#x20;

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Example</th><th>Scope</th></tr></thead><tbody><tr><td><strong>%application_name_ml%</strong></td><td>The current application’s name. If the application name contains a multi language tags, the name is translated accordingly to the user language.</td><td>MyApplication</td><td>Page</td></tr><tr><td><strong>%application_name_html_enc%</strong></td><td>The current application’s name without translation and HTML encoded</td><td>MyApplication</td><td>Page</td></tr><tr><td><strong>%application_owner%</strong></td><td>The owner of the application, that is the unique identifier of the application in the instance.</td><td>HTTED1H</td><td>Page</td></tr><tr><td><strong>%MODEL_OWNER%:</strong></td><td>ID of the application (indicated in the metadataInfo property of the components).</td><td>HTTED1H</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%MODEL_SCHEMA%</strong></td><td>The <a href="https://documentation.decisyon.com/documentation/design-studio/connection">database schema</a> defined as default for the current application. In the case of synchronization, this type of configuration allows making the name of the target data application dynamic, since the target application often has a different name from the originating name. If an SQL Server database type is used, the following is the correct syntax: &#x3C;nameDB>.&#x3C;scheme>.&#x3C;table>:</td><td>my_data</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%metadata_schema%</strong></td><td>The database’s schema used for DAC metadata, including database name.</td><td>my_database.my_schema</td><td><ul><li>Page</li><li>read-id-formula and Read-description-formula of Dimensional Level</li><li>Direct Filter,</li><li>Custom Filter</li><li>View Filter</li><li>User Filter</li><li>Report</li><li>Metrics</li></ul></td></tr><tr><td><strong>%DATAMART_TABLE%</strong></td><td>The name of the <a href="../report/execution/post-execution-sql/sql-interactions.md">datamart table</a> generated from report execution</td><td>DX2121218912</td><td>Report</td></tr></tbody></table>

### **System parameters**

These built-in parameters are independent from the logged user and from the application in use.

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Example</th><th>Scope</th></tr></thead><tbody><tr><td><strong>%current_utc_epoch%</strong></td><td>Current UTC timestamp measured in epoch (the number of seconds);</td><td>1653039744</td><td>Page</td></tr><tr><td><strong>%current_utc_epoch_millis%</strong></td><td>Current UTC timestamp measured in epoch with millis precision;</td><td>1653039744196</td><td>Page</td></tr><tr><td><strong>%current_local_ISO8601%</strong></td><td>Current local timestamp in ISO 8601 format.</td><td>20220520T114224</td><td>Page</td></tr><tr><td><strong>%current_utc_ISO8601%</strong></td><td>Current UTC timestamp in ISO 8601 format.</td><td>20220520T094224</td><td>Page</td></tr></tbody></table>

### **Page Parameters**

These built-in parameters depends on the page that the user is currently using.&#x20;

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Example</th><th>Scope</th></tr></thead><tbody><tr><td><strong>%page_id%</strong></td><td>ID of the current page.</td><td>631653037690882</td><td>Page</td></tr><tr><td><strong>%page_name%</strong></td><td>Current page name. If the page contains the multi language tags ("enableMultiLanguage" property active) the name will not translate.</td><td>Plant Configuration</td><td>Page</td></tr><tr><td><strong>%page_name_html_enc%</strong></td><td>Current page name HTML encoded without any translation and interpretation</td><td>&#x3C;#PLANT_CONFIGURATION/></td><td>Page</td></tr><tr><td><strong>%page_name_ml%</strong></td><td>Current page name. If the page contains the multi language tags ("enableMultiLanguage" property active) the name will translate.</td><td>Plant Configuration</td><td>Page</td></tr><tr><td><strong>%page_public_url%</strong></td><td>Public url of the current page. It provides the Direct Link to the page in the default view. Authentication is automatic and any page parameters are set automatically. You can get the same link from the Action Bar of the page (Share menu).</td><td>https://decisyon.site/content/page/HTTED1G_631653037690882/view?tenant=111111111111111</td><td>Page</td></tr><tr><td><strong>%page_public_url_embed%</strong></td><td>Public url of the current page. It provides the Link for the page embedding into other contents.</td><td>https://decisyon.site/content/page/HTTED1G_631653037690882/embedView?tenant=111111111111111</td><td>Page</td></tr><tr><td><strong>%opener_page_id%</strong></td><td>Page ID of the opener page. This information is available and valid only when the the "opener" is a page and not a report.</td><td>111111111111111</td><td>Page</td></tr><tr><td><strong>%opener_page_name%</strong></td><td>Page name of the opener page. This information is available and valid only when the "opener" is a page and not a report. If the page contains the multi language tags ("enableMultiLanguage" property active) the name will not translate.</td><td>My Page</td><td>Page</td></tr><tr><td><strong>%opener_page_name_html_enc%</strong>:</td><td>Current page name HTML encoded without any translation and interpretation.</td><td>&#x3C;#MY-PAGE/></td><td>Page</td></tr><tr><td><strong>%opener_page_name_ml%</strong></td><td>Current page name. If the page contains the multi language tags ("enableMultiLanguage" property active) the name will translate.</td><td>My Page</td><td>Page</td></tr><tr><td><strong>%opener_page_owner%</strong></td><td>Owner of the opener page</td><td>HTTED1H</td><td>Page</td></tr></tbody></table>

### **OLAP Parameters**

These built-in parameters can be used in a composite metric.

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Example</th><th>Scope</th></tr></thead><tbody><tr><td><strong>%REPORT_LEVELS%</strong></td><td>Logical names of all levels used in the current report. It returns a comma separated list.</td><td>[PLANT,LINE,YEAR,MONTH,SHIFT]</td><td>Composite metric</td></tr><tr><td><strong>%SELECT_LEVELS%</strong>:</td><td>Logical names of the levels VISIBLE in the report; levels in page-by or used to drill down (when the report is in “group by” mode) are excluded from the list. It returns a comma separated list.</td><td>[PLANT,LINE,YEAR,MONTH]</td><td>Composite metric</td></tr><tr><td><strong>%PAGE_BY_LEVELS%</strong></td><td>Logical names of ALL levels in the page-by of the current report.</td><td>[YEAR,MONTH]</td><td>Composite metric</td></tr><tr><td><strong>%PAGE_BY_FILTER_LEVELS%</strong></td><td>Logical names of the levels in page-by of the current report that have a selection (page-by in which the “total” is selected are excluded from the list). It returns a comma separated list.</td><td>[PLANT,YEAR]</td><td>Composite metric</td></tr><tr><td><strong>%SELECT_IS_AGGREGATE%</strong></td><td>Returns 1 when the report is displaying a matric value aggregated on one of the level, 0 when the data is not aggregated on any level.</td><td>0 or 1</td><td>Composite metric</td></tr><tr><td><strong>%SELECT_IS_TOTAL%</strong></td><td>Returns 1 the level associated with the metric is a total, 0 when it’s not a total.</td><td>0 or 1</td><td>Composite metric</td></tr><tr><td><strong>%SEC_FILTERS%</strong></td><td>The ID of all the “user filter” associated to the current user. User filters are separated by a comma.</td><td>111111111111111,111111111111111</td><td>Composite metric</td></tr></tbody></table>

### EXAMPLE - How to use the User Parameters

This example shows how to use the user parameters in a page.

Assume we want to create an input form that shows the data of the user who opened the page and that it has some pre-filled fields.

Please note that the user account must be registered in the DAC.

**Step 1 - Create new Page**

![](<../../.gitbook/assets/image (1231).png>)

Create a new page that contains TextFields that will be pre selected with the data of the connected user. Each TextField has been assigned a name by the "param base name" property of each widget.

To display the correct value in the textfields, the pre-selection-values must be configured.

![](<../../.gitbook/assets/image (345).png>)

The relative variable has been selected for each parameter. The parameters that are not associated with any variables will be input by the user.

The Execute button is configured to save in the database the data of the input form.

**Step 2 - Access on RunTime**

![](<../../.gitbook/assets/image (760).png>)

Log in at RunTime. The debug-mode has been activated on the page to show which parameters are passed to the page for the connected user.

Through the passing of the parameters, the TextFields are pre populated with user parameters. The only information missing is the telephone because it was not configured to have a pre-selection value.

It’s now possible to input the phone number and click on the execute button to save the data.

### EXAMPLE - How to use the functions %REPORT\_LEVELS%, %SELECT\_LEVELS%, %PAGE\_BY\_LEVELS%, %PAGE\_BY\_FILTER\_LEVELS%

**STEP1:** **Using LEVELS parameters in Composite Metrics**

![](<../../.gitbook/assets/image (1285).png>)

Create a composite metric that contains the %REPORT\_LEVELS% parameter. The parameter is entered manually in input are to define the formula. Another three metrics with the parameters will be defined in the same way: %SELECT\_LEVELS%, %PAGE\_BY\_LEVELS%, %PAGE\_BY\_FILTER\_LEVELS%.

Then the four Metrics are added in a report (picture below).

**STEP2: Using LEVELS parameters in Composite Metrics**

![](<../../.gitbook/assets/image (1520).png>)

In the report the following levels have been entered:

* Product on rows, Business Unit and Month for the page-bys.
* The composite metrics created previously will show the following information:
* Select Level: \[Product] information relating to the Dimension entered on the rows
* Page by Filter Levels: \[Business\_Unit]\[Month] The report was filtered in the page by for the business levels
* Page-by Level: \[Business\_Unit]\[Month] levels in the page-by
* Report Levels: \[Product] \[Business\_Unit]\[Month] total levels in the report.

### EXAMPLE - How to use %SELECT\_IS\_AGGREGATE%

The parameter %SELECT\_IS\_AGGREGATE%, which can be used exclusively in the formulas of the metrics, is 0 or 1 depending on whether the crossing of the metric corresponds to an aggregate value of the information present in the report or not.

Given for example a report with levels:

MONTH, PRODUCT, AREA

The value of %SELECT\_IS\_AGGREGATE%, set in the metric, will be 0 for the combination

* January, P1, Lazio

The value of the TAG, set in the metric, will be 1 for the combinations

* January, P1, \[Total]
* January, \[Total], Lazio
* January, \[Total], \[Total]

I.e. on each aggregation of the levels present in the report.
