# Activities Task

## Task

DAC offers a solution to manage activities and to assign tasks to users.

You can manage tasks in DAC through reports or Page components enabled for this purpose. You can assign tasks:

* on the report cells
* on some Page components (Graph, Indicator, Table)

Tasks can be notified to recipients through e-mails which give direct access to the task. Therefore, in order to access the task, the mail server and DAC server must be configured (see next paragraph).

### **Configuring Task Notifications for E-mail**

The mail server for sending notification e-mails must be defined in the _Server Designer_ module and then associated in the system properties _**associated–SMTP-server**_ (_Tools preference_, _E-mail_ sectio&#x6E;_, System Emails_ group)_._

The e-mails contain a link for directly accessing the assigned Tasks; the reference to DAC must therefore be defined in the system properties:

_**decisyonWebURL**_ (_Tools properties_, _Web section,_ _Connection group_) enter the DAC link.

### **Enabling Task on the Report**

You will need to set the properties in the _Body_ section for reports that have to be used in the task assignment process:

_**activateCellsTask**_ allows you to enable the insertion of the new task on the report cells

![](../../../.gitbook/assets/152.png)

_**viewCellinfoTask**_ to display, on the metric cells, information about the percentage deviation between the metric and set target

![](<../../../.gitbook/assets/153 (1).png>)

### **Enabling Tasks on Page Components**

The Page components used during the task assignment process are:

* Tables
* Crosstabs
* Graphs
* Indicators

You can enable components for the assignment of tasks in the following way:

* enable the component title with the _**show-Title**_ property of the **Title** group
* enable the _**activate-Task**_ property, always in the **Title** group.

Example: Displaying Tasks on a Component - GRAPH

![](<../../../.gitbook/assets/image (1356).png>)

_From Page Designer, we enter the graph-type component and in the TITLE section we enable the property activate-task. The graph in DAC will display the task button_ ![](<../../../.gitbook/assets/155 (1).png>) _next to the title. Clicking the button opens the window for inserting the new task._
