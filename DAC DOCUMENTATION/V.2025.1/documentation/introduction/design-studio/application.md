---
description: >-
  An Application is the means to create a specific IIoT solution. It is possible
  to create one or more applications.
---

# Overview of UI

### Opening Decisyon App Composer <a href="#opening-decisyon-app-composer" id="opening-decisyon-app-composer"></a>

The Welcome Screen is the first and central part of DAC-DS where the developer has instantaneous access to the main and most frequent functions used to create an application. A DAC application is a set of different objects and functions that you bring together to create the functionality you need, such as pages and a configurable rules schedule.



![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeU3b6V6WFmrtpbJZoC%2F-MeU4YrY5sdnGDdNoK3h%2Fimage.png?alt=media\&token=966f4900-ca57-4763-85ca-a2f8c6b653f7)

The **Recently used** table shows the latest edited objects, in chronological order. Select one of these to directly open its edit window. The detailed information below is available for each object.

* **Name:** component name.
* **Type:** Component type (e.g. Report, Metric, Page…).
* **Last Edit:** date and time of the last edit.
* **User:** User that made the last edit.

The **Shortcuts** section contains direct links for access to:

* **Page designer:** for the creation of a new Page.
* &#x20;Rule Setup: for the creation of new rules.
* User management: for the creation and management of the users.
* Group management: for the creation and management of the groups.
* Deploy Application: access to the wizard to execute the deployment.

In the **Help Quick Links** section links are available to access DAC documentation:

· **Getting Started:** tutorials that explain how to create a new application.

· **Design Studio User Manual:** access to the Developer manual (this one)

· **DAC User Manual:** access to the end user manual.

When DAC is opened, information about the connection is shown at the bottom:

* **User:** Connected User.
* &#x20;**Connection:** Data Model, in terms of Hostname and Database.
* **Application:** Application loaded.

**​**

![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeU3b6V6WFmrtpbJZoC%2F-MeU7E_xvQ1T_R4UWyE-%2Fimage.png?alt=media\&token=f83497ab-a459-4d3b-b19c-15f42e2259c3)

​

### The Toolbar <a href="#the-toolbar" id="the-toolbar"></a>

The DAC-DS toolbar is shown in the following figure:

![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeU3b6V6WFmrtpbJZoC%2F-MeU80Y74FK9mGbJqheQ%2Fimage.png?alt=media\&token=6ab7b96b-6382-4659-a518-38d5bdf3ba56)

Once the application is loaded, a first line toolbar is enabled. Once a report is opened, two more toolbar lines are enabled, which show the functions that can be applied to the report.

As the mouse moves over a button, the tooltip is enabled, providing a short description of the associated function as described below:

| ​     | ​                                                     | ​ |
| ----- | ----------------------------------------------------- | - |
| **1** | Reports Catalog                                       | ​ |
| 2     | Report Editor                                         | ​ |
| 3     | Dimension management (see Dimensions)                 | ​ |
| 4     | Cube management (see Cubes and measures section)      | ​ |
| 5     | Metric Management (see Metrics)                       | ​ |
| 6     | Direct filters management (see Direct Filters)        | ​ |
| 7     | Range filters management (see Range filters)          | ​ |
| 8     | User filters (see User filters)                       | ​ |
| 9     | Indicator Designer (see Indicator Designer)           | ​ |
| 10    | Page Designer (see DAC Design page)                   | ​ |
| 11    | Opens widget designer on DAC (see DAC Design Page)    | ​ |
| 12    | Scheduler, (see Scheduler)                            | ​ |
| 13    | Rule setup (see Ruke)                                 | ​ |
| 14    | Data Load via Report (Data load via Repor**t** (DLR)) | ​ |
| 15    | Object Explorer (see Managing Application Objects)    | ​ |
| 16    | Online Help Search Box **(**&#x73;ee Online Help)     | ​ |

### Object Dependencies <a href="#object-dependencies" id="object-dependencies"></a>

You can see the dependencies of DAC\_DS objects through the **Dependencies** menu item, enabled by right-clicking the mouse in the management windows.

![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeUCd75zKdl4-Jq3iZ6%2F-MeUCtKwgQYt9QkRqvYO%2Fimage.png?alt=media\&token=37f8bdfd-2937-424d-8bdc-a2305c597c2f)

Selecting the **Dependencies** item enables the window displayed at the bottom.

You can request two types of dependency:

* **Object That use ‘…’:** list of objects that use the selected object (in the figure above, where, for the "Act Vs Bdg" indicator, all the Pages that use it are listed)

![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeUCz930bnXV_0pLUMb%2F-MeUD1EM0WVxehvvbj23%2Fimage.png?alt=media\&token=86d316d2-c771-4724-8b6e-8ed1cfcc2484)

* **Object used by ‘…’:** list of objects used by the selected object (see figure below). For each selected object, the right side of the dependencies window shows summary information for the selected object.

![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeUCz930bnXV_0pLUMb%2F-MeUD4VKNd0UNfXPA4gb%2Fimage.png?alt=media\&token=d8605c0e-924f-4d2a-bfb9-f750180be141)
