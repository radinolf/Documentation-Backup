# Example

In this section we show you some examples of configuration of the most used javascript functions.

* [Example 1 - How to use the DECISYON.page.subscribeEvent function](example.md#example-1-how-to-use-the-decisyon.page.subscribeevent-function)
* [Example 2 - How to use the DECISYON.page.addPageParamsChangedListener(event,(payload)=>{}) function](example.md#example-3-how-to-use-the-decisyon.page.addpageparamschangedlistener-event-payload-greater-than-funct)
* [Example 3 -How to use the DECISYON.page.execute Button (custom sID) function](example.md#example-3-how-to-use-the-decisyon.page.execute-button-custom-sid-function)
* [Example 4 - Difference between DECISYON.page.refreshPage() and DECISYON.page.reloadPage() functions](example.md#example-5-difference-between-decisyon.page.refreshpage-and-decisyon.page.reloadpage-functions)
* [Example 5 - How to use the DECISYON.utils.createTask(saveCallback, params) and DECISYON.utils.editTask(saveCallback, taskId, application) functions](example.md#example-6-how-to-use-the-decisyon.utils.createtask-savecallback-params-and-decisyon.utils.edittask-s)

## Example 1 - How to use the DECISYON.page.subscribeEvent function

The _DECISYON.page.subscribeEvent(event,(payload)=>{})_ function can be used when an external system has to execute an event on a DAC page invoking it through a REST request.

In this example we will see how to send to a DAC page the values of a JSON through a REST request. The JSON fields will be transformed in parameters and used in widgets.

&#x20;

<figure><img src="../../../.gitbook/assets/image (596).png" alt=""><figcaption></figcaption></figure>

An external system will send data via API to a DAC page. When the user accesses the page the DAC page activate the listener to capture events from external systems. In this example, when an event is sent to the DAC, the logged-in user will see a popup in the page and the JSON data sent in the request REST call will be parsed and displayed within 3 textfield widgets in the page.

&#x20;

**Step 1 Configure the page**

<figure><img src="../../../.gitbook/assets/image (1085).png" alt=""><figcaption></figcaption></figure>

**Widget Textfield**

The form that will receive the data from the API consists of three textfield widgets.

For each Textfield we will define the name of the parameters (base name):

* **machine\_ textfield** : displays the name of the machine sent by the API
* **operation\_textfield:** displays the name of the operation sent by the API
* **operation\_status\_textfield :** displays the status sent by the API

&#x20;

**Widget Javascript**

Let’s review the code in the **Javascript** widget (property **javascript-code**)

```javascript
DECISYON.page.subscribeEvent('SEND_DATA', (payload) => {

//Show the payload in console log
console.log('payload:');
console.log(payload);

//Assign values to the variable
let v_machine = payload.machine;
let v_operation= payload.operation;
let v_operation_status = payload.operation_status;

//Show a message dialog
DECISYON.utils.openMessageDialog( 'The "'+v_operation+'" operation on the "'+ v_machine + '" machine had the following result: "'+ v_operation_status +'"', 'parsed json data',1,700,350,1);

//Set parameters value
DECISYON.page.sendParamChanged('machine_textfield',v_machine);
DECISYON.page.sendParamChanged('operation_textfield',v_operation);
DECISYON.page.sendParamChanged('operation_status_textfield',v_operation_status);
});

```

* With function `DECISYON.page.subscribeEvent(event,(payload)=>{})` we define the event name, in this example "SEND\_DATA". It is possible to define any string as the event name, but it is important that in the REST request exactly the same event name is used to run the function. The event will be processed by the page only if the name matches.
  * `DECISYON.page.subscribeEvent('SEND_DATA', (payload)`
* We define 3 variables and associate the corresponding field in the JSON that is passed as payload in the call REST.
  * `let v_machine = payload.machine;`
  * `let v_operation= payload.operation;`
  * `let v_operation_status = payload.operation_status;`
* The `DECISYON.utils.openMessageDialog` function allows us to display a dialog box in which we will display the values received by the API. In the message we can see how the text has been concatenated to the variable.
  * `DECISYON.utils.openMessageDialog( 'The "'+v_operation+'" operation on the "'+ v_machine + '" machine had the following result: "'+ v_operation_status +'"', 'parsed json data',1,700,350,1);`
* The funtion `sendParamChanged` exports the value of the parameter, assigning a the parameter name and parameter value. Example:
  * `DECISYON.page.sendParamChanged('machine_textfield',v_machine);`
  * `DECISYON.page.sendParamChanged('operation_textfield',v_operation);`
  * `DECISYON.page.sendParamChanged('operation_status_textfield',v_operation_status);`

**Step 2 : Configure the REST requst**

An external system (i.e. Postman for testing purpose) must configure the following REST request to send the evento to the page.

```markup
curl --location --request POST 'https://<host:port>/api/rest/application/<application_owner>/page/<page_id>/event/<event_name>' 
--header 'Authorization: Bearer <token>' 
--header 'Content-Type: application/json' 
--data-raw '{
    "machine": "Filler",
    "operation": "Apply recepit",
    "operation_status": "Success"
}'
```

In the request you need to pass the following information:

* The URL of the webapp, the application owner, the page ID and the event name to send the data
  * `--request POST 'https://<host:port>/api/rest/application/<application_owner>/page/<page_id>/event/<event_name>'`
* The authorization Token of the user
  * `--header 'Authorization: Bearer <token>'`
* The data (in this case a JSON string) to send in the request
  * `--data-raw` In this example we passed a JSON string.

**Step 3: Viewing from the Web**

When the external system execute the REST request and the user has the page opened, the popup dialog shows up and the textfield are popoulated with the values recevied in the JSON file.

<figure><img src="../../../.gitbook/assets/image (570).png" alt=""><figcaption></figcaption></figure>

## **Example 2 - How to use the DECISYON.page.addPageParamsChangedListener(event,(payload)=>{}) function** <a href="#example-3-how-to-use-the-decisyon.page.addpageparamschangedlistener-event-payload-greater-than-funct" id="example-3-how-to-use-the-decisyon.page.addpageparamschangedlistener-event-payload-greater-than-funct"></a>

In the example that we show you we see how to use the function `DECISYON.page.addPageParamsChangedListener(event,(payload)=>{}) .`

This function allows to know which parameters have been changed in the page and thus it could be possible to define custom logics on parameters value using Javascript code.

We will build an example in which every time you select a plant from a dropdown widget a popup will shows up displaying the selection made and an error messagge will be displayed if a numeric value is used in the textfield widget.

<figure><img src="../../../.gitbook/assets/image (704).png" alt=""><figcaption></figcaption></figure>

**Step 1 Configure the page**

<figure><img src="../../../.gitbook/assets/image (1097).png" alt=""><figcaption></figcaption></figure>

The widgets in the page are

* **Dropdown**: allows us to select the Plant.
* **TextField:** allows us to manually enter the value of the machine state
* **Plant Text:** is used to show the list of selected plants

**Widget Javascript**

The code used in the **Javascript** widget (property **javascript-code**) is the following:

```javascript
DECISYON.page.addPageParamsChangedListener(function(params, eventDetails){

//Create two functions to support this example
function ViewPlantList(item) {
    text += item + "</br>";
} 
function ContainsNumber(n) { return/\d/.test(n); } 

//Show the parameters and the eventDetails in the console
console.log('Parameters in the page');
console.log(params);
console.log('eventDetails in the page');
console.log(eventDetails);

//Get the number of plants selected in the dropdown and the array
let  plantLen = params.plant_descriptions.value.length;
let  arrPlant = params.plant_descriptions.value;
//Get the machine status value
let machineStatusValue = params.machine_status.value[0];

//Build the string to display in the HTML and in the dialog
let text = "";
arrPlant.forEach(ViewPlantList);
document.getElementById("demo").innerHTML = text;

//Show the dialog only when there is at least one plant selected in the dropdown
if (plantLen != 0)
{
    DECISYON.utils.openMessageDialog(text, 'Parameters have changed', 1, 200, 150, 1);	
}

//Show a dialog if the machine status contains a numeric
if (ContainsNumber(machineStatusValue))
{
    DECISYON.utils.openMessageDialog('The status of the machine is incorrect, numbers are not allowed! Please change it! ', 'machine status', 1, 200, 150, 1);	
}

});
```

When triggering the events declared in the function, the system, through a popup, shows to the user that parameters changed.

**Step 2 How it works in the webapp**

&#x20;

**Selezione del Plant**

<figure><img src="../../../.gitbook/assets/image (1275).png" alt=""><figcaption></figcaption></figure>

From the Plant List we select a plant. After the selection the system displays the dialog that shows which parameter has been changed. After the selection of the Plant we can see that the list of selected plants is also modified.

Javascript code that shows the dialog when at least one palnt is selected in the drop-down menu is the following:

```javascript
//Show the dialog only when there is at least one plant selected in the dropdown
if (plantLen != 0)
{
    DECISYON.utils.openMessageDialog(text, 'Parameters have changed', 1, 200, 150, 1);	
} 
```

If we try to enter a numeric value in the Machine Status widget, the system shows a popup warning the user that an incorrect value has been input.

<figure><img src="../../../.gitbook/assets/image (490).png" alt=""><figcaption></figcaption></figure>

&#x20;

Javascript code that shows the dialog when a numeric value is used is the following:

```javascript
//Show a dialog if the machine status contains a numeric
if (ContainsNumber(machineStatusValue))java
{
    DECISYON.utils.openMessageDialog('The status of the machine is incorrect, numbers are not allowed! Please change it! ', 'machine status', 1, 200, 150, 1);	
}
```

## Example 3 -How to use the DECISYON.page.execute Button (custom sID) function



The `executeButton` function executes the action associated to an existing Execute Button widget. With the function `DECISYON.page.executeButton(customJsID)` you can execute, through a javascript, all the types of execution that are configured in the widget. The types supported by the widget are shown in the figure:

<figure><img src="../../../.gitbook/assets/image (404).png" alt=""><figcaption></figcaption></figure>

In this example we see how to:

* configure a javascript that execute the function `DECISYON.page.executeButton(customJsID)`
* configure the action of the button widget that is passed in the JavaScript API.

<figure><img src="../../../.gitbook/assets/image (254).png" alt=""><figcaption></figcaption></figure>

**Step 1 How to build the page**

Below is a summary of the widgets used on the page and the properties configured.

<figure><img src="../../../.gitbook/assets/image (1301).png" alt=""><figcaption></figcaption></figure>

As we can see in the diagram above the page consists of only two widgets an Execution button and a javascript. Let’s see in detail the configuration of the properties.

1. Execute button: in this widget has been implemented the `OpenConfirmDialog` function that allows you to display the dialog box when you access the page.
   1. In the Execution property group, select :
      1. execution-type= JAVASCRIPT\_ONLY
      2. javascript-code-after: copy the following Javascript code

```javascript
        let message = 'Dialog message content';
        let title = 'Dialog title';
        let onConfirm = () => {
            alert('openConfirmDialog confirm callback');
        };
        let onCancel = () => {
            alert('openConfirmDialog cancel callback');
        };
        let icon = '2';
        let labelYes = 'YES';
        let labelNo = 'NO';
        let width = 600;
        let height = 400;
        let idDialog = '1234567890';
        
        DECISYON.utils.openConfirmDialog(message, title, onConfirm, onCancel, icon, labelYes, labelNo, width, height, idDialog);
```

1. Copy the Custom-JS-Id of the widget is 118651.
2. Javascript
   1. By the property javascript-code select the function sql and insert the CustomJsID of the button object (118651).

## **Example 4 - Difference between DECISYON.page.refreshPage() and DECISYON.page.reloadPage() functions**  <a href="#example-5-difference-between-decisyon.page.refreshpage-and-decisyon.page.reloadpage-functions" id="example-5-difference-between-decisyon.page.refreshpage-and-decisyon.page.reloadpage-functions"></a>

The next example explains what the difference is between DECISYON.page.refreshPage() and DECISYON.page.reloadPage().

In the page have been inserted several widgets that show the result of the same query but displayed different widgets.

1. The first component show the local timestamp.
2. The second component shows the result of the same query in an SQL report on Data Grid.
3. The third component shows the result of the same query in an SQL report on Crosstab.
4. The fourth component shows the result of the same query in an SQL formula of a textfield.

<figure><img src="../../../.gitbook/assets/image (1139).png" alt=""><figcaption></figcaption></figure>

&#x20;

It is configured such in a way that

* The first textfield has a pre-selection value with the following query:

<figure><img src="../../../.gitbook/assets/image (1336).png" alt=""><figcaption></figcaption></figure>

* Both the data grid and the crosstab are associated to a SQL report that contains the same query used in the pre-selection of the first parameter.
* The textfield widget is configured to use the same query in the SQL-formula of the widget.&#x20;

<figure><img src="../../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

&#x20;

The JS function **DECISYON.page.refreshPage()** executes the SQL query associated with widgets that contain a query, like crosstab, data presentation widgets, textfield etc but do not execute queries configured as pre-selection for the page parameters.  See the figure below.

<figure><img src="../../../.gitbook/assets/image (996).png" alt=""><figcaption></figcaption></figure>

&#x20;

The JS function **DECISYON.page.reloadPage()**&#x65;xecutes the page like if it was a first access. All the preselection query are executed again and also all the SQL query associated with reports or widgets are executed again.&#x20;

{% hint style="info" %}
Be aware that if the page is opened from a drill through and imports parameters from a DT or in a tab panel, the relaunch of the page will lose all the imported parameters, possibly causing problems in the page.&#x20;


{% endhint %}



## **Example 5 - How to use the DECISYON.utils.createTask(saveCallback, params) and DECISYON.utils.editTask(saveCallback, taskId, application) functions**  <a href="#example-6-how-to-use-the-decisyon.utils.createtask-savecallback-params-and-decisyon.utils.edittask-s" id="example-6-how-to-use-the-decisyon.utils.createtask-savecallback-params-and-decisyon.utils.edittask-s"></a>

<br>

In the example that we propose we will see how to use the functions to create and edit tasks using execute button widgets.

A crosstab widget has the list of process order and each order will be associated to one or more task. Task will be created leveraging the UI of task creation, but using pre-populated fields in the form. The association between the process order and the task will be saved in a table and then the task will be opened for edit using the function `DECISYON.utils.editTask`

<figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

**Prerequisites**.

In this example we need to create a table on our database in order to save the Process Order/ Task associations selected by the report.

The table must have the following structure:

| **PO\_TASK\_ASSOCIATION** |          |                                          |
| ------------------------- | -------- | ---------------------------------------- |
| **Column Name**           | **Type** | **Description**                          |
| process\_order\_id        | Varchar  | The ID of the process order              |
| task\_id                  | Varchar  | The ID of the created task               |
| owner                     | Varchar  | Application owner associated to the task |

**Step 0 Create the PO\_TASK\_ASSOCIATION Report**

Now let’s see how to build the report to view data while maintaining the Process Order and Task association.

<br>

<figure><img src="../../../.gitbook/assets/image (814).png" alt=""><figcaption></figcaption></figure>

To create this type of association we have built a SQL report. Below we show the Query .

```sql
select
	lk_line17.line_ds as LINE,
	lk_process_order18.process_order_ds as PROCESS_ORDER,
	lk_material19.material_ds as MATERIAL_DS,
	lk_process_order_type16.process_order_type_ds as TYPE,
	lk_process_order_status21.process_order_status_ds as STATUS,
   	lk_process_order18.plan_start_timestamp as PLAN_START_DATE,
	lk_process_order18.plan_end_timestamp as PLAN_END_DATE,
	lk_process_order18.planned_qty as PLANNED_QTY,
	lk_process_order18.closed_flag as CLOSED_FLAG,
	lk_process_order18.active_flag as PO_ACTIVE_FLAG,
	pta.task_id as TASK_ID,
	case when pta.title is null then '-' else pta.title end||'('||pta.task_id||')' as TASK_TITLE
from
	multi_site_data.lk_process_order lk_process_order18
	inner join 
	multi_site_data.lk_line lk_line17 on lk_line17.line_id = lk_process_order18.line_id
	inner join
	multi_site_data.lk_material lk_material19 on  lk_material19.material_id = lk_process_order18.material_id
    inner join 
	multi_site_data.lk_process_order_status lk_process_order_status21 on lk_process_order_status21.process_order_status_id = lk_process_order18.process_order_status_id
	inner join 
	multi_site_data.lk_process_order_type lk_process_order_type16 on lk_process_order_type16.process_order_type_id = lk_process_order18.process_order_type_id
	left outer join
	multi_site_data.po_task_association pta on lk_process_order18.process_order_ds = pta.process_order_ds 

```

This SQL query is used to get data about the lines, process order, materials and is joining tables already available in the database.

There is a left outer join between the process order and task table to that we can dispay in the report also process order that do not have a task associated yet.

```
multi_site_data.po_task_association pta on lk_process_order18.process_order_ds = pta.process_order_ds 
```

After the query definition we will create a SQL report and save it. In this example the report was named **PO\_TASK\_ASSOCIATION.**

<figure><img src="../../../.gitbook/assets/image (1259).png" alt=""><figcaption></figcaption></figure>

**Step 1 Create Page**

<figure><img src="../../../.gitbook/assets/image (304).png" alt=""><figcaption></figcaption></figure>



**Widget Crosstab:**

For this widget we will configure the following properties:

* We associate the report PO\_TASK\_ASSOCIATION (property **reportAssociated**) report to the crosstab widget.
* Enable the **activate-params-export** property and from the **exp-levels** property select the report levels that will be exported as parameters in the page. In this example the export levels are _PROCESS\_ORDER$au1T8_ and _TASK\_ID$au1T8_ which contain the Process Order ID and the Task ID respectively.
* **custom-js-id** (Tab Advanced): insert a custom-Js-id (PO\_TASK\_LIST) in order to recall the widget in the Javascript API on the page.

&#x20;

**Widget Button (Create New Task)**

This widget will use and input a process order selected in the crosstab: after the task is created, the task id will be saved in the database to create the association between the process order and the task just created.

Insert a **Execute Button** widget and set the following properties:

* **execution-type :** the button execution type is JAVASCRIPT\_ONLY
* **mandatory-params:** from this property we select \<selection> .
* **Parameters:** we select the parameters we want to be mandators. This means that the button is only executed if all the parameters in it are selected. Select the Process Order parameter (PROCESS\_ORDER$au1T8).
* **javascript-code-after:** Let’s define the Javascript to be executed.

{% code lineNumbers="true" %}
```
function insertAssTab(t)
{
    //Show in console log
    console.log("TASK CREATED!");
    console.log(t);
    
    //Set parameters value
    DECISYON.page.sendParamChanged("taskId",t.id);
    DECISYON.page.sendParamChanged("taskTitle",t.title);
    
    //Execute the button to insert data in the database
    DECISYON.page.executeButton('Insert');
}

//Create Task 
DECISYON.utils.createTask((task)=>
     {
      insertAssTab(task);
     },
    {
     "title" : "Task of PO "+"?PROCESS_ORDER$au1T8?",
     "priority" : 2,
     "description" : "Task of "+"?PROCESS_ORDER$au1T8?",
     "dueDate" : new Date().getTime()+(7200*1000),
     "solution" : "This is the solution of the task"
    }
);
```
{% endcode %}



Let’s see in detail the javascript code to create the task.

The `DECISYON.utils.createTask((task)` function creates a task and saves it in a dedicated table using a callback function. When the new Task is created it is associated with the selected Process Order using the parameter `?PROCESS_ORDER$au1T8?.`

The task creation function also contains a JSON with all the task attributes . In the specific example in the title and the description of the task are retriveded from the process order id, while the two dates are calculated dynamically adding 2 hours to the current time (the two dates requires an epoch in millisecond format).

**Widget Button (Edit Task)**

This button is used to edit an existing Task by passing the task ID as a function argument.

Insert a **Execute Button** widget and set the following properties:

* **execution-type** : the button execution type is JAVASCRIPT\_ONLY
* **mandatory-params:** from this property we select \<selection> .
* **Parameters**: we select the parameters we want to be mandators. This means that the button is only executed if all the parameters in it are selected. Select the Task\_ID parameter (TASK\_ID$au1T8)
* **javascript-code-after:** Let’s define the Javascript to be executed.

{% code lineNumbers="true" %}
```
DECISYON.utils.editTask((task) => {
  // Do something after the edit with saved task object
},
'?taskId?',
'SOCIALM');
```
{% endcode %}

* When the Report selects the Task to edit , the variable TASK\_ID$au1T8 contains the ID of the task, that is passed to the function and the task editor dialog opens with all the fields prepopulated. It is also possible to define a callback function to run when saving the modified task, but in this example it has not been defined.

**Widget Button (Insert)**

Now in the page we will insert a Execute button that through a SQL query will save in the table `PO_TASK_ASSOCIATION` the association between the selected process order and the ID of the newly created task.

<figure><img src="../../../.gitbook/assets/image (201).png" alt=""><figcaption></figcaption></figure>

Insert a **Execute Button** widget and set the following properties:

* **custom-js-id (Tab Advanced):** insert a custom-Js\_id (Insert) in order to recall the widget in the Javascript API on the page. (See line 12 of code JS DECISYON.page.executeButton('Insert')
* **sql-formula:** We define the query to insert in the table `PO_TASK_ASSOCIATION` the values selected by the report. The values are stored in the variable ('??PROCESS\_ORDER$au1T8?','?taskid?','?taskTitle?')

```
insert into multi_site_data.po_task_association (process_order_ds,task_id,title,owner)
values
('?PROCESS_ORDER$au1T8?','?taskId?','?taskTitle?','SOCIALM')javaScript-code-after: Let’s define the Javascript that should be executed after the query



```

* **javaScript-code-after:** Let’s define the Javascript that should be executed after the quer&#x79;**.**

```
DECISYON.report.refreshReport('PO_TASK_LIST')
```

Passing the custom-js-id defined in the crosstab widget (PO\_TASK\_LIST) into the `refreshReport` function will update the report data.

**Step 2 Viewing from WEB**

**Creation of a new Task**

<figure><img src="../../../.gitbook/assets/image (842).png" alt=""><figcaption></figcaption></figure>

When you select a Process Order and press the Create New Task button, a new Task Creation window opens. The Title and Description fields are already prefilled with the Process Order id. When you click the SAVE button, the report is refreshed and the task id column show the information of the associated Task `"Task of PO "+"? PROCESS_ORDER$au1T8?".`

**Editing a Task**

<figure><img src="../../../.gitbook/assets/image (1180).png" alt=""><figcaption></figcaption></figure>

Select the Task to edit and press the **Edit Task** button. The Task edit window opens and after making the changes you click the Save button.

{% hint style="info" %}
Tasks created by DECISYON.utils.editTask(((task) are also visible in the Task Board.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (836).png" alt=""><figcaption></figcaption></figure>

&#x20;
