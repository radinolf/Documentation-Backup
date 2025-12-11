# Job Management

The system allows the user to define the execution of:

* A **Rule setup**
* A **notification**

This function is particularly useful, for example, at the end of an ETL process to monitor and promptly communicate any changes to data and to assess them for strategic and operational marketing.

During the installation of DAC the table EVENT\_MANAGER\_JOBS was created in the Data Model scheme, on which the **JOBS** that the user wishes to perform can be inserted. In fact, each INSERT instruction on the table EVENT\_MANAGER\_JOBS automatically activates the execution of the jobs concerned.

When you go to the Property pane of the **Rule Setup**, **Notification designer** and **Scheduler** modules for the definition of alerts, notifications and Refresh Rules respectively, you can extract information from the **metadataInfo** property regarding the following: **OWNER**, **OBJECT\_ID** and **TYPE** of job that the user wishes to perform.

![](<../../.gitbook/assets/image (6).png>)

The field value TYPE indicates the type of object, as indicated in the following table:

| **Subject**         | **TYPE** |
| ------------------- | -------- |
| E-mail notification | 311      |
| Refresh rule        | 400      |
| Alert               | 401      |

With that information the INSERT command is set up on the **EVENT\_MANAGER\_JOBS** table, so that the system activates the execution of the desired job, solely for the columns:

* EVENT\_JOB\_ID, where a number is inserted
* OWNER, where the **OWNER** field of the **metadataInfo** property is **inserted**
* ELEMENT\_ID, where the **OBJECT\_ID** field of the **metadataInfo** property  is inserted
* ELEMENT\_TYPE , where the **TYPE** field of the **metadataInfo** property is entered

The remaining columns in the EVENT\_MANAGER\_JOBS table are populated by the system automatically.

An example of an INSERT instruction on the EVENT\_MANAGER\_JOBS table is shown below:

INSERT INTO EVENT\_MANAGER\_JOBS

(EVENT\_JOB\_ID , OWNER, ELEMENT\_ID, ELEMENT\_TYPE) VALUES

(‘1’, ‘WGTA4YC’, ‘8827829332381’, ‘400’);

COMMIT;

The layout of the EVENT\_MANAGER\_JOBS table is shown below.

| Field Name        | Description                                                     | Format       | Notes                                                                            |
| ----------------- | --------------------------------------------------------------- | ------------ | -------------------------------------------------------------------------------- |
| EVENT\_JOB\_ID    | Unique job ID.                                                  | VARCHAR(50)  | Primary key                                                                      |
| OWNER             | Application owner.                                              | VARCHAR(100) | Information extracted from the metadataInfo property of the application element. |
| ELEMENT\_ID       | ID of the element to be executed.                               | VARCHAR(100) |                                                                                  |
| ELEMENT\_TYPE     | Type of element to be executed.                                 | NUMBER(3)    |                                                                                  |
| EXECUTION\_STATUS | Execution status. Domain: STARTED, EXECUTING, CONCLUDED, ERROR. | VARCHAR(20)  | Populated by the system.                                                         |
| EXECUTION\_DETAIL | Execution detail.                                               | VARCHAR(100) |                                                                                  |
| START\_DATE       | Execution start date.                                           | DATE         |                                                                                  |
| KEEP\_ALIVE\_DATE | Service date.                                                   | DATE         |                                                                                  |
| END\_DATE         | Execution end date.                                             | DATE         |                                                                                  |
| SERVER\_NAME      | **Server name.**                                                | VARCHAR(50)  |                                                                                  |

