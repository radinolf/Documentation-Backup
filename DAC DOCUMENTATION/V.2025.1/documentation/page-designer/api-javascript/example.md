# Example

In this section we show you some examples of configuration of the most used javascript functions.

* [Example 1 - How to use the DECISYON.page.subscribeEvent function](example.md#example-1-how-to-use-the-decisyon.page.subscribeevent-function)
* [Example 2 - How to use the DECISYON.page.addPageParamsChangedListener(event,(payload)=>{}) function](example.md#example-3-how-to-use-the-decisyon.page.addpageparamschangedlistener-event-payload-greater-than-funct)
* [Example 3 -How to use the DECISYON.page.execute Button (custom sID) function](example.md#example-3-how-to-use-the-decisyon.page.execute-button-custom-sid-function)
* [Example 4 - Difference between DECISYON.page.refreshPage() and DECISYON.page.reloadPage() functions](example.md#example-5-difference-between-decisyon.page.refreshpage-and-decisyon.page.reloadpage-functions)

## Example 1 - How to use the DECISYON.page.subscribeEvent function

The _DECISYON.page.subscribeEvent(event,(payload)=>{})_ function can be used when an external system has to execute an event on a DAC page invoking it through a REST request.

In this example we will see how to send to a DAC page the values of a JSON through a REST request. The JSON fields will be transformed in parameters and used in widgets.

&#x20;

<figure><img src="../../../.gitbook/assets/image (1045).png" alt=""><figcaption></figcaption></figure>

An external system will send data via API to a DAC page. When the user accesses the page the DAC page activate the listener to capture events from external systems. In this example, when an event is sent to the DAC, the logged-in user will see a popup in the page and the JSON data sent in the request REST call will be parsed and displayed within 3 textfield widgets in the page.

&#x20;

**Step 1 Configure the page**

<figure><img src="../../../.gitbook/assets/image (1534).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (1019).png" alt=""><figcaption></figcaption></figure>

## **Example 2 - How to use the DECISYON.page.addPageParamsChangedListener(event,(payload)=>{}) function** <a href="#example-3-how-to-use-the-decisyon.page.addpageparamschangedlistener-event-payload-greater-than-funct" id="example-3-how-to-use-the-decisyon.page.addpageparamschangedlistener-event-payload-greater-than-funct"></a>

In the example that we show you we see how to use the function `DECISYON.page.addPageParamsChangedListener(event,(payload)=>{}) .`

This function allows to know which parameters have been changed in the page and thus it could be possible to define custom logics on parameters value using Javascript code.

We will build an example in which every time you select a plant from a dropdown widget a popup will shows up displaying the selection made and an error messagge will be displayed if a numeric value is used in the textfield widget.

<figure><img src="../../../.gitbook/assets/image (1153).png" alt=""><figcaption></figcaption></figure>

**Step 1 Configure the page**

<figure><img src="../../../.gitbook/assets/image (1546).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (1724).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (939).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (853).png" alt=""><figcaption></figcaption></figure>

In this example we see how to:

* configure a javascript that execute the function `DECISYON.page.executeButton(customJsID)`
* configure the action of the button widget that is passed in the JavaScript API.

<figure><img src="../../../.gitbook/assets/image (703).png" alt=""><figcaption></figcaption></figure>

**Step 1 How to build the page**

Below is a summary of the widgets used on the page and the properties configured.

<figure><img src="../../../.gitbook/assets/image (1750).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (1588).png" alt=""><figcaption></figcaption></figure>

&#x20;

It is configured such in a way that

* The first textfield has a pre-selection value with the following query:

<figure><img src="../../../.gitbook/assets/image (1785).png" alt=""><figcaption></figcaption></figure>

* Both the data grid and the crosstab are associated to a SQL report that contains the same query used in the pre-selection of the first parameter.
* The textfield widget is configured to use the same query in the SQL-formula of the widget.&#x20;

<figure><img src="../../../.gitbook/assets/image (999).png" alt=""><figcaption></figcaption></figure>

&#x20;

The JS function **DECISYON.page.refreshPage()** executes the SQL query associated with widgets that contain a query, like crosstab, data presentation widgets, textfield etc but do not execute queries configured as pre-selection for the page parameters.  See the figure below.

<figure><img src="../../../.gitbook/assets/image (1445).png" alt=""><figcaption></figcaption></figure>

&#x20;

The JS function **DECISYON.page.reloadPage()**&#x65;xecutes the page like if it was a first access. All the preselection query are executed again and also all the SQL query associated with reports or widgets are executed again.&#x20;

{% hint style="info" %}
Be aware that if the page is opened from a drill through and imports parameters from a DT or in a tab panel, the relaunch of the page will lose all the imported parameters, possibly causing problems in the page.&#x20;


{% endhint %}



&#x20;
