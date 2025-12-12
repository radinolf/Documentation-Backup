# Execute Button

## Overview

The **Execute button** is a widget that allows users to trigger an action or perform operations that interact with other App Composer widgets or with external application.

This widget is used in many scenarios where the user performs an on-click action such as opening a new page, executing code such as JavaScript or Java, executing a query to update specific values ​​in the database, assign value to parameters etc.

![](<.gitbook/assets/image (48).png>)

The execute button can be configure to execute the following actions: &#x20;

1. **QUERY:** execute a SQL query
2. **JAVASCRIPT ONLY:** execute JavaScript code
3. **DRILL THROUGH:** open a drill through (page, report or external link)
4. **REST API:** execute a REST API Client
5. **ACTION LIST:** execute an action list.
6. **TALEND INTEGRATION:** execute a job
7. **NOTIFICATION:** send an email message
8. **CODE SNIPPET:** execute Java code
9. **EXCEL INTEGRATION:** copy data from an Excel file to a table
10. &#x20;**REFRESH RULE:** execute a scheduler
11. **DLR:** execute a Data Load Report
12. **APPLY SELECTION OPENER PAGE:** send parameters defined in the target page to the source page.

Regardless of all of these configurations, the Execute button's user interface on the web application always remains the same.

{% hint style="info" %}
For more details on each operation, go to the [Execution type](documentation/execute-button/execution-type/) section.
{% endhint %}

## Properties

Each execution type may have its own dedicated properties to configure the action to execute. The following properties are available for any execution type of the **Execute button** widget. Per properties that are specific for each execution type are reported below.

<table><thead><tr><th width="197">Group</th><th width="148">Name</th><th width="240">Description</th><th width="182" align="center">Type</th><th width="126" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td><strong>button-text</strong></td><td>Text displayed on the button.</td><td align="center">TEXTFIELD</td><td align="center">Execute</td><td>false</td></tr><tr><td><strong>Main</strong></td><td><strong>tooltip</strong></td><td>Tooltip visible on mouse over.</td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td></tr><tr><td><strong>Form</strong></td><td><strong>Disabled</strong></td><td>Disable the button, making it unclickable. It support parameters. </td><td align="center">SWITCH</td><td align="center">0</td><td>false</td></tr><tr><td><strong>ObjectStyle</strong></td><td><strong>FormFontSize</strong></td><td>Sets the font size for the displayed text.</td><td align="center">NUMERIC</td><td align="center">10</td><td>false</td></tr><tr><td><strong>Drill-through</strong></td><td><strong>Refresh-opener-report</strong></td><td>If the widget is in a page that has been opened by a drill-through, it specifies whether the source report of the drill-through should be refreshed.</td><td align="center">SWITCH</td><td align="center">0</td><td>false</td></tr><tr><td><strong>Drill-through</strong></td><td><strong>Close-on-execution-success</strong></td><td>If the widget is in a page that has been opened by a drill-through, the dialog will be close if the action executed is successful.</td><td align="center">SWITCH</td><td align="center">0</td><td>false</td></tr><tr><td><strong>Execution</strong></td><td><p></p><p><a href="documentation/execute-button/execution-type/"><strong>Execution-type</strong></a></p><p></p></td><td>Sets the type of execution associated on button click.</td><td align="center">SELECT</td><td align="center">QUERY</td><td>false</td></tr><tr><td><strong>Execution</strong></td><td><strong>Mandatory-params</strong></td><td><p>Widget is not displayed untill other parameters in the page have a value defined.</p><ul><li> <strong>&#x3C; all parameters></strong>:  all the parameters used in the widget are considered mandatory. The button may be run only after all the parameters have been valued.</li><li><strong>&#x3C;selection>:</strong> only the selected parameters are considered mandatory. This type activates the <strong>parameters</strong> property where you can set which parameters.</li><li><strong>&#x3C;none></strong>: no parameter is considered mandatory. The button will be executed regardless the value of any parameter.                                         </li></ul></td><td align="center">SELECT</td><td align="center">&#x3C;all parameters></td><td>false</td></tr><tr><td><strong>Execution</strong></td><td><strong>Post-execution-button</strong></td><td>Select another "Execute button" widget on the page executed to execute just after the executed action. This allows to configure a chain of executions. Only the action is executed, any other option will be ignored.</td><td align="center">SELECT</td><td align="center">&#x3C;none></td><td>false</td></tr><tr><td><strong>Execution</strong></td><td><strong>JavaScript-code-before</strong></td><td>JavaScript code to execute before the execution of the button. This property is not available when the "<strong>Javascript only"</strong> execution type is selected.</td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td></tr><tr><td><strong>Execution</strong></td><td><strong>JavaScript-code-after</strong></td><td>JavaScript code to execute after the execution of the button</td><td align="center">TEXTFIELD</td><td align="center"></td><td>false</td></tr></tbody></table>

## **Widget Parameters**

### **Imported Parameters**

This widget is able to import and read any parameter available in the page.

### **Exported Parameters**

The following parameters are exported by the Execute button widget:

<table><thead><tr><th width="281.3333333333333">Name</th><th>Description</th><th>Note</th></tr></thead><tbody><tr><td>&#x3C;rest_api_alias><strong>_Response_Body</strong></td><td>Contains the response body of the executed request. The name of the parameter include the "Alias" defined in the Client REST API.</td><td>This is applicable only for execution-type = Rest API</td></tr><tr><td>&#x3C;rest_api_alias>_ <strong>Response_Status</strong></td><td>Contains the response status of the executed request. The name of the parameter include the "Alias" defined in the Client REST API.</td><td>This is applicable only for execution-type = Rest API</td></tr></tbody></table>
