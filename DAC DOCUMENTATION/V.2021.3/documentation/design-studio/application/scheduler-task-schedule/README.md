# Scheduler (Task Schedule)

Use the **Scheduler** module to plan the updating and executing of certain logical objects based on a schedule, which was previously defined with the Schedules Designer module.

Open _Scheduler_ from the _Application_ menu item.

![](<../../../../.gitbook/assets/image (131).png>)



The planning of a task, or updating rule, takes place by selecting the objects to be performed and by associating a schedule in the _**schedule**_ property: at the top right the date and time of the next execution is indicated.

The _**execution of the refresh rule**_ will be launched by DAC according to the definitions in the time schedule (e.g. every morning at 11:36).

The refresh rules may be also be performed through SQL commands, through the creation of a JOB, with the _**activateRefresh**_ property which enables (as default) or disables the planned execution of the refresh activity. Objects affected by a Refresh Rule are described in the image below.

![](<../../../../.gitbook/assets/image (139).png>)

A Refresh Rule can be defined for the following objects:

* Absolute cache reports
* Alarms
* Notifications
* Dsearch Server update
* DLR execution
* Job Talend execution

The objects selected are indicated automatically in the middle pane with the object name, date and time of the last execution (_**Execution date**_), (_**Execution time**_) and (_**Average time**_), the number of executions performed (_**En**_), the number of executions completed with errors (_**Er**_) and the **total** for each field in the bottom row. The objects are sorted inside the list by using drag & drop.

![](<../../../../.gitbook/assets/13 (5).png>)

If the execution ends successfully, a green check is displayed, otherwise a red X is displayed.

In case of error the schedule does not block: select the row of the object performed with error to view the date and the details of the error in the bottom section.

If an error occurs, the reason for the failures is registered and displayed by the _**log**_ folder, while the validation process continues on the remaining objects. In addition, you can interrupt the execution of the validation (_**Abort**_ button) and export the log of the validations up to that point (_**Export**_ button).

A progress bar shows the process execution in real time.
