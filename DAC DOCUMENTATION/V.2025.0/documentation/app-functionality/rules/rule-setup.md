# Rule

The alert and rules service in DAC is an advanced tool designed to monitor data and information, and issue real-time alerts when tolerance thresholds are reached and/or exceeded.

Alerts can provide information to the decision makers when preventive actions are needed. The alert system is based on a set of rules that describe which **data needs monitoring** and what actions need to be performed when the alert conditions are met. Alert conditions are tested according to **a preset time schedule**.

The **possible actions in an alert** are:

1. sending a notification
2. run Refresh rules, defined with the _**Scheduler**_
3. execute a SQL statement

You can create an alert with the **Rule Setup** module, opened from the **Application** menu item.

![](<../../../.gitbook/assets/0 (24).png>)

The procedure for creating an alert is as follows:

* Choose object type on which to define the alert condition in the _**alertType**_ property:
* a report (_**Report**_), that enables the _**reportAssociated**_ property to select the report (previously created)
* an indicator (_**KPI**_), that enables the _**indicatorAssociated property**_ to select the indicator previously created
* custom (_**Custom**_)
* time series (_**TimeSeries**_) configure the property:
* **Time series Property:**
* **End:** sets the last time stamp used to get data from time series. It can be either absolute or relative value. If no value is configured, the default value is “current time”.
  * **Start:** start time to get measurement from time series. It can be either absolute or relative value.
    * **Absolute** start time is expressed as the starting day and time used to retrieve data from the Time Series service.
    * **Relative** start time is calculated backward from the current time and has the format “\<value>\<time-unit>-ago”.
* **Queries** input the number of query used to display data. It possible to configure one or more query, each one with its own property.
  * **query-1**
    * **Tags** read the tags available in the time series service configured in the widget. List of tags is obtained when opening the multiple selection window. It is possible to configure one or more tags in the chart. Tags must have been already created from external sources.
    * **Order** configure the order of the series (ascending or descending)
    * **Aggregations**: input the aggregation functions used to merge different time series into one single time series. Aggregation is defined based on API. E.g. \[{"type" : "interpolate","sampling":{"datapoints":500\}}]
    * **Filters:** input the filter for the time series using the comparison operations \[gt|ge|lt|le|eq|ne]. Filters are defined based on API. E.g. {"measurements": {"condition": "ge","values": "46"\}}
    * **Limit:** use an integer number to set the limit of the data points retrieved from Time Series
* define one or more alert conditions
* set one or more **actions to carry out** for each alert condition

Alerts can be _**issued immediately**_ with the “Play” button, which verifies the preset conditions and carries out the associated actions. During the execution, the system displays a window with the different stages from verification of the conditions to the individual steps in the execution of the actions. This is useful to monitor all steps of the alert process, from defining the object on which the alert condition is verified to executing the action correctly (e.g. presence of a server to send an e-mail notification).

The alerts can be also carried out by:

* a schedule defined with the _**Scheduler**_ _module (see Scheduler section)_
* SQL commands, when a JOB is created (see _JOB Management_ section)

## Rule Conditions

The rule conditions are defined in the top right section.

It is possible to configure:

* [Complex Condition](rule-setup.md#complex-condition)**:** using specific code to create a complex condition.
* [Simple Condition (Time Series only):](rule-setup.md#simple-condition) using a formula to create a simple condition.

![](<../../../.gitbook/assets/1 (17).png>)

### Complex Condition

The Complex conditions are defined in the top right section, using the **Condition** button, which inserts a Complex _Condition_ row in the list below.

![](<../../../.gitbook/assets/2 (4).png>)

To define the condition you need to click the ![](<../../../.gitbook/assets/3 (17).png>) button which opens a different window, according to the type of object selected in the _alertType_ property:

* For the _**Report**_ type, the window shows report levels and metrics, of the same type as those used for View Filter.

![](<../../../.gitbook/assets/4 (27).png>)

* For the _**KPI**_ type the window is as shown in the following figure.

![Descrizione: SNAGHTML692740](<../../../.gitbook/assets/5 (11).png>)

Using the **Value** button you insert the TAG? VALU&#x45;_?_ which indicates the value of the metric associated with the indicator

### Simple Condition

The Simple condition alert is defined in the top right section, using the **Simple** **Condition** button, which inserts a simple _Condition_ row in the list below. This condition is available only for the Time Series alert type.

![](<../../../.gitbook/assets/6 (8).png>)

To define the condition you need to click the ![](<../../../.gitbook/assets/7 (1).png>) button which opens a window to insert a single condition.

You can configure a trigger condition of the Alert by selecting a single tag and setting a threshold value.

![](<../../../.gitbook/assets/8 (5).png>)

## Rule Action

Each alert condition is associated with one or more actions that are carried out when the condition is met. You need to select the condition to which the action is associated and, in the bottom right section, the buttons of the action list are enabled:

![](<../../../.gitbook/assets/9 (5).png>)

* The **Notification** button opens a window to select a previously created notification.
* The **Refresh Rule** action button opens a window containing the rules created in the Scheduler module.
* The **Code Snippet** button opens a window with the Java classes, added to the system libraries, which implement the _**IUserAction**_ interface:

The selected class must extend the _**IUserAction**_ class in the **cassiopea.jar** file of the **lib** folder.

The source code of a **custom action** that extends the _**IUserCondition**_ class is shown below.

_package userPackage;_

_import it.unyversys.cassiopea.designers.alertDesigner.model.action.IUserAction;_

_// The class implements a custom condition._

_public class CustomAction implements IUserAction{_

&#x20;_public void perform() throws Exception{_

&#x20;_// Custom Action to be performed_

&#x20;_}_

* The **SQL Action** to execute a SQL statement. To define the query you need to click the ![](<../../../.gitbook/assets/10 (12).png>) button which opens the query editor window.

![](<../../../.gitbook/assets/11 (5).png>)

By default, DAC provides parameters of the applied rules that you can use in the query to store information in a database table.

* ?alarm\_id?: identification code of the alarm
* ?tag\_name?: name associated with the tag
* ?tag\_value?: tag measurement of the fired rule
* ?time\_stamp?: date and time of the fired rule
* ?attributes?: attribute associated with the tag

When the rule is deployed in order to use the Postgre database present on the space where DAC is pushed, you need to set the table name the of the Postgre data source alias, created on Design Studio.

The script to create the table with alarms information to execute on Postgre database is:

CREATE TABLE rule\_alarms (

&#x20;alarm\_id NUMERIC(20) NOT NULL,

&#x20;tag\_name VARCHAR(300) NOT NULL,

&#x20;tag\_value NUMERIC(30,10) NULL,

&#x20;attributes json NULL,

&#x20;timestamp NUMERIC(20) NOT NULL

);

CREATE UNIQUE INDEX pk\_rule\_alarms\_idx ON rule\_alarms (alarm\_id ASC);

ALTER TABLE rule\_alarms ADD CONSTRAINT pk\_rule\_alarms PRIMARY KEY (alarm\_id);

An example to create a condition alert for time series type

This example demonstrates the steps to create a simple alert using query-type action for placement in the event table.

Step1: Configure time series properties

![](<../../../.gitbook/assets/12 (20).png>)

_Select the Time Series in alert type property. Define the Time series property:_

* _Start: sets the start time to retrieve data from time series. It can be either absolute or relative._
* _Queries: input the number of query used to display data. One query_
  * _Select tags where the rules apply. In this case SENSOR\_03 and SENSOR\_02_
  * _Ordering: Ascending_

Step2: Define a Simple Condition

![](<../../../.gitbook/assets/13 (4).png>)

_Select the Simple Condition button, which inserts a Simple Condition row in the list below._

* _To define the condition you need to click the_ ![](<../../../.gitbook/assets/14 (17).png>) _button to open the Simple Condition Editor. Define a condition for TAG SENSOR\_02 >100_

Step 3: Define a Simple Action

![](<../../../.gitbook/assets/15 (3).png>)

_To define the SQL Action, click the button SQL ACTION to open a SQL-action Editor._

* _Define the SQL statement executed once the rule condition is fired. For instance, in the above example, the information about the fired alert is stored in a table._

## Rule Execution

After creating the new Rule, its execution can be tested, based on data coming from the Time Series service or from a test Excel file.

The ![](<../../../.gitbook/assets/16 (1).png>) button starts the wizard to test the rule.

![SNAGHTML6bdd0ab8](<../../../.gitbook/assets/17 (14).png>)

In the first step you select the data source onto which the rule validation will be carried out.

There are two methods:

* **Time series services:** the system queries in real time the data coming from the Time series service and runs the rule created on this data.
* **Simple Data:** the system validates the rule based on the data coming from an Excel file.

In this case you select the Excel file that contains the test data through a second panel.

![](<../../../.gitbook/assets/18 (15).png>)

*
  * **File:** choose the Excel file that contains the data.
  * **Sheet**: select a specific worksheet if the Excel file includes more than one sheet.

![](<../../../.gitbook/assets/19 (2).png>)

After defining one or more rules, on the alert conditions, and having started the execution, the system gives the result of the rule application in the last step of the wizard.

![](<../../../.gitbook/assets/20 (15).png>)

The data given by the execution of the rule is displayed in a table, where each column reports the information below:

* **Name**: name of the rule triggered for the test data
* **Sensor Data:** list of the tags and value for which the rule was triggered
* **Timestamp:** date and time when the rule was triggered
* **Attributes :** if present in the service or in the Excel file, the attributes associated with the Time Series event are listed
