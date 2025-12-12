# Synchronization

## **What is the synchronization**

**Synchronization** (also know as Deploy) is an operation reserved for admin users and it is used to copy an App Composer object (i.e. pages, reports, dimensions etc) from one instance to another. Usually in any project there are different instanced (or environments) such as development, testing, production etc. **Synchronization** is used to deploy the entire application or also single specific objects in other **DAC** instances.

App Composer will automatically detect new objects or objects that has been modified between the source environment and the target environment(s) (i.e. between development environment and production environment).

In a **production environment**, application synchronization is crucial for keeping data up-to-date and consistent across different instances. Since _App Composer is not available_ in a _production environment_, users must rely on Cockpit to manage the synchronization process. **Cockpit** provides an intuitive interface and the necessary tools to facilitate application synchronization, thus allowing for effective data management and ensuring that all instances are aligned.

It’s possible to use the **Synchronization tool** only between metadata installed on the same RDBMS. You can copy App Composer objects between two instanced both on PostgreSQL used for the metadata, but you can NOT copy objects from a metadata hosted on PostgreSQL to a metadata hosted in SQL Server (or viceversa).

<figure><img src="../../.gitbook/assets/image (514).png" alt=""><figcaption></figcaption></figure>

There are two approaches to **synchronize an Ap Composer application**:

A single ADP file can be produced and imported to any DAC instance.

## Export or Deploy <a href="#type-of-export-or-deploy" id="type-of-export-or-deploy"></a>

There are two approaches to synchronize an App Composer application:

* **Deploy**: the synchronization is done with a direct connection to the target environment web application. It is the quickest and easiest way, but it implied that the target environment is reachable
* **Export**: the application and instance objects are exported on a file created in the source environment that will be later imported in the target when application.

| Application Deployment                       | Application Export                           |
| -------------------------------------------- | -------------------------------------------- |
| ![](<../../.gitbook/assets/image (843).png>) | ![](<../../.gitbook/assets/image (748).png>) |

During the application deployment process or during export, it is possible to select whether to deploy all application objects or manually select each single objects to deploy.

* **Deploy all application objects:** Use this option to deploy/export all of the application objects that have been modified since the last deployment. Design Studio automatically identifies all objects that are different between source and target environment. Objects modified in source instance will override the same objects available in the target instance have been modified.
* **Deploy only selected application objects:** Use this option to select only the specific application objects you want to deploy. You will be prompted, in a separate step, to select the object to deploy.

<figure><img src="../../.gitbook/assets/image (569).png" alt=""><figcaption></figcaption></figure>

When you select an individual object, a summary of the main properties is displayed in the section on the right. The bottom pane shows the type of operation to be performed on the object.

### Dependencies calculation

When you select the box **Automatically calculate the dependencies,** Design Studio will evaluate all the objects on which the selected item depends on and automatically include them in the list of objects to synchronize. I.e., if you select a page that contains a report, when this property is enabled then Design Studio will automatically select both the page and the report when the page is selected for synchronization.&#x20;

The automatic selection of dependent objects minimize the error for which you can deploy/export an object without including additional objects on which it depends on, causing issues in the target environment.

{% hint style="warning" %}
This operation is time consuming and could take several minutes to be completed in case the application has many objects and dependencies to calculate.&#x20;
{% endhint %}

### Object ID

The **Object ID** of any App Composer object is never modified in the synchronization process: the ID assigned to the object in the sources environment will be used also to create the same object in the target environment. When an object is modifed from source to target, the match is based on the object ID.

In case the object is also exposed in the REST API, such as the Snippets, when deploying in the target environment the original object ID will be used.&#x20;

I.e. you have the following REST API to execute a Snippet in the source environment:

```url
https://<dev-app>/api/rest/application/AAAAA/program/123456789/body?key1={{par1}}&key2
```

After the synchronization of the snippet "123456789" in production, the production URL will be:&#x20;

```
https://<prod-app>/api/rest/application/AAAAA/program/123456789/body?key1={{par1}}&key2
```

As you notice, it maintain the same ID.

## **Type of Operations** <a href="#type-of-operations" id="type-of-operations"></a>

When you select the items you want and click on the _Next_ button, you display a summary **window with the objects selected previously.**

Note that each operation is marked with a different color, to distinguish the type of operation that will be applied.

<figure><img src="../../.gitbook/assets/image (1858).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="218">Operation Type</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:green;">Add (green)</mark></td><td>The object exist in the source environment but not in the target environment. It will be created in the target environment.</td></tr><tr><td><mark style="color:orange;">Delete (brown)</mark></td><td>The object has been deleted in the source environment but it still exists in the target environment. It will be deleted also in the target environment.</td></tr><tr><td><mark style="color:blue;">Modify (blue)</mark></td><td>The object exists both in the source and the target environment, in the source environment has been later modified. It will modified in the target environment.</td></tr><tr><td><mark style="color:red;">Conflict (red)</mark></td><td>The object exists both in the source and the target environment, but it has been modified in both. The conflict will be resolved copied the object of the source environment in the target environment</td></tr><tr><td><mark style="color:orange;">Restore Add (orange)</mark></td><td>The object exists in the source environment but it has been deleted in the target environment. It will be copied again the target environment.</td></tr><tr><td>None (grey)</td><td>The object is the same in both source and target environment. No operation will be executed.</td></tr></tbody></table>

## Difference Between Deploy or Synchronization with FILE <a href="#difference-between-deploy-or-synchronization-with-file" id="difference-between-deploy-or-synchronization-with-file"></a>

We can use different approaches to synchronize the objects of the application, depending on the scenario you present yourself:

* **Deploy of Application:** In order for the Deploy application to run correctly, the web app of the target environment must always be active and accessible from  the Design Studio of the source environment.
* **Synchronization** **From File:** Synchronization from File allows for exporting and importing application metadata from a source environment to a target environment. In this scenario, both the export and import of metadata are performed using the Design Studio in both environments. However, if access to the Design Studio in the target environment is not available, it is possible to import the metadata file by connecting to the Run Time environment.

### **Deploy of Application** <a href="#deploy-of-application" id="deploy-of-application"></a>

Deploy or On-line synchronization is recommended when the target environment is reachable from the source environment via the Composer Web App URL.

<figure><img src="../../.gitbook/assets/image (910).png" alt=""><figcaption></figcaption></figure>

If you select the option to deploy the application there are some mandatory activities to be performed if you are deploying a new application:

* Access on Design Studio of Source Environment and select the menu item **Cloud >>Application Management >> Deploy**
* Insert:
  * **DAC URL:** enter the URL target DAC where the application will be deployed.
  * **Authorization Token :** enter a valid Token. The Authorization Token must be generated by the User Admin from the target environment.

{% hint style="info" %}
In the examples section, you’ll find a step-by-step guide on[ how to sync your application via Deploy](application-management-deploy.md#how-to-deploy-application).
{% endhint %}

## **Synchronization from File** <a href="#synchronization-from-file" id="synchronization-from-file"></a>

The second approach is to use object synchronization via File. In this mode, there are two options to sync objects.

* [**Synchronization with files from Design Studio**](./#snchronization-with-files-from-design-studio). Synchronization from File allows to export and import application metadata from a source environment to a destination environment. In this scenario, both export and import of metadata is done using the Design Studio in both environments.
* [**Synchronization with files from WEB.**](./#snchronization-with-files-from-web) Used when the Design Studio of the target environment is not reachable. This way, you can still sync objects via the web module.
* [**Synchronization with file fron Cockpit**](./#snchronization-with-files-from-design-studio-1)**:** Used in a production environment where AppComposer is not available.

### From Design Studio <a href="#snchronization-with-files-from-design-studio" id="snchronization-with-files-from-design-studio"></a>

{% hint style="danger" %}
The possible to use synchronizing an application through .adp files, using the Design Studio of the source and destination environment, has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

Below is a diagram that illustrates the process of synchronizing an application through files, using the Design Studio of the source and destination environment.

<figure><img src="../../.gitbook/assets/image (844).png" alt=""><figcaption></figcaption></figure>

If you select the option to deploy the application in an export file there are some mandatory activities to be performed if you are deploying a new application:

1. Generate a metadata Control file for a new application in the Design Studio available in the Destination Environment where you want to deploy your new application ( Export Metadata File.**ctr**)
2. In the Design Studio of Source environment, use the metadata Control file to create an Export file that includes the deployment instructions. ( Export\_Ap&#x70;**.adp**)
3. In the Design Studio of the Destination environment you need to **Import** the Export file **.adp**. At this point the system creates the application.  \
   **This feature has been deprecated  we recommend that import the file from** [**Web** ](./#snchronization-with-files-from-web)

{% hint style="info" %}
In the examples section, you will find a step-by-step guide on [how to sync the application via file using the Design Studio](application-management-deploy.md#how-to-sync-via-file-from-design-studio).
{% endhint %}

### **From App Composer**  <a href="#snchronization-with-files-from-web" id="snchronization-with-files-from-web"></a>

Web synchronization is useful when you don’t have the ability to reach the Design Studio of the target environment.

<figure><img src="../../.gitbook/assets/image (1832).png" alt=""><figcaption></figcaption></figure>

Go to the runtime and from the Main Menu toolbar select Administration >> Sync Applications.

1. Connect at the Run Time of the target application. From the Main Menu toolbar select **Administration** >> **Application Synchronization**.
2. Share Metadata File. Save into the file all the metadata information.
3. Choose the type of Metadata File to be generated. Different Metadata Files are created if you want to update an existing application or you want to import a brand new application.
4. The control file must be imported into the source application.
5. Connect to the design studio of the source application.
6. Generate the File of export (`ExportFile. Adp`) that contains the metadata information of the object to be synchronized.
7. Connect at the Run Time of the target application and import `ExportFile.adp` to synchronize the application.

{% hint style="info" %}
In the examples section, you will find a step-by-step guide on [how to synchronize the application using the WEB module.](application-management-deploy.md#how-to-synchronize-two-applications-using-the-web-module.)
{% endhint %}

### From Cockpit <a href="#snchronization-with-files-from-design-studio" id="snchronization-with-files-from-design-studio"></a>

If synchronization must occur in a production environment, it will be necessary to perform it through Cockpit, as AppComposer is not available in production.

<figure><img src="../../.gitbook/assets/image (2284).png" alt=""><figcaption></figcaption></figure>

1. Connect to the Cockpit of destination environment. Select by the Main Toolbar the item App management. On the application menu select the item _Download application configuration._
2. Share Metadata File (Control file). Save into the file all the metadata information.
3. The control file must be imported into the source application.
4. Connect to the design studio of the source application.
5. Generate the File of export (`ExportFile. Adp`) that contains the metadata information of the object to be synchronized.
6. Connect at the Cockpit of the target application and import `ExportFile.adp` to synchronize the application.

{% hint style="info" %}
&#x20;The examples section, you will find a step-by-step guide on [how to synchronize the application using the C](application-management-deploy.md#how-to-synchronize-two-applications-using-the-web-module.)[ockpit](application-management-deploy.md#syncronization-in-cockpit)
{% endhint %}



## Post-synchronization management in the target environment <a href="#post-synchronization-management-in-the-target-environment." id="post-synchronization-management-in-the-target-environment."></a>

After the synchronization is completed, some manual activities has to be anyway manually executed in the target environment. In this chapter you will find which objects may require such manual task and how to deal with these scenarios.

### Action Lists and Scheduled Action Lists <a href="#action-lists-and-scheduled-action-lists" id="action-lists-and-scheduled-action-lists"></a>

All the objects used as actions in the Action List will be synchronized as dependencies of the Action List, assuming the dependency calculation is selected in the synchronization dialog in Design Studio.

In the target environment, the Actions list is imported in the same catalog path as the source environment, overwriting any different folder tree available in the catalog of Action List of the target environment.

Any page containing **Execute Buttons** configured to use an Action List will have the associated action list as a dependency in the synchronization.

Schedule Action Lists can be synchronized between App Composer instances, in example between a development and a production environment.

When executing the synchronization of the Schedule Action List:

* will have as dependency the Action List to which it is associated
* will keep the state Enabled/Disabled that has in the source environment.

### Jobs Associated to Action List

When you sync a Dumbella job associated to an Action List, then in the target environment the jobs resource version in Dumbella will be the same as the synchronized one.

{% hint style="danger" %}
When the job is synchronized because associated to an Action List, only the zip file of the job available in the resource catalog is copied from the source environment to the target environment. In the target environment, you need to refresh the version of the job from the Jobs user interface. Please refer to "[Job](https://decisyon.atlassian.net/documentation/app-functionality/jobs)" for more details.
{% endhint %}

### Jobs <a href="#page-management-to-web" id="page-management-to-web"></a>

Jobs are synchronized as a resource between the application resources. In the target environment they must be published as Jobs

### Page management to web <a href="#page-management-to-web" id="page-management-to-web"></a>

In this section, we will address some considerations regarding synchronization of edited pages through the web interface.

* When a page is deleted, it will be marked as "to be deleted" in the target environment during synchronization.
* In case the group association is modified, the page will be recognized as modified during the synchronization process.
* When changes are made to the page's properties or its name, the page will be identified as "modified" during the synchronization process.

### Terms of Use <a href="#terms-of-use" id="terms-of-use"></a>

The terms of use are not supported in the synchronization. It is required to manually (or via API) reconfigure this setting in the target environment.

### Page Catalog <a href="#page-catalog" id="page-catalog"></a>

When you deploy a Page Catalog, you overwrite the publication in the target environment of common Pages with the source environment by indicating the catalog branches (groups and sub-groups) of the source Pages Catalog, in the target environment.

When you deploy, the system checks whether or not a Page has been moved to another group, so the same changes are made in the target.

Any images the administrator associates with groups, sub-groups and Page Catalog objects, are deployed simultaneously with it.

**Note:** To indicate the Page catalog, the Pages must already be in the target. You can bring a Page to the Pages Catalog at the same time.

### User, Groups and Report Catalog Privileges <a href="#user-groups-and-report-catalog-privileges" id="user-groups-and-report-catalog-privileges"></a>

When you Deploy, you replicate groups or user in the source environment and keep their properties deploy in the target environment.

This step requires the developer to align:

* permissions on Cubes, Dimensions and Metrics of the application (set in the _Permission_ folder)
* privileges on DAC functions (set in the _Events_ folder)

It is mandatory for groups to be versioned so the existing privileges and associations between the groups and objects (such as Pages, alerts, notifications, etc.) can be indicated in the target.

The object-group association is in fact only indicated if the group is in the object when the object is aligned in the target environment.

However, **privileges on reports** are deployed together with those of the catalog, to prevent inconsistencies between permissions on reports and permissions on folders.

The list of versioning objects includes the _**Report and folder permissions Report Catalog**_

### Data Sources <a href="#deploy-data-sources" id="deploy-data-sources"></a>

There are two steps involved in versioning data sources:

* The create phase, when the data source is not in the target. The object is indicated internally in the target, properties and pointers.
* The update phase, when they are present in both environments. Only the properties are updated, while the pointers of the target data source remain unchanged.

<figure><img src="../../.gitbook/assets/image (513).png" alt=""><figcaption></figcaption></figure>

### Languages, Labels & Custom Error Messages <a href="#terms-of-use" id="terms-of-use"></a>

When synchronizing **languages**, the system replaces all languages in the destination environment with the languages from the source environment. This means that if the target environment has an extra language compared to the source, it will be lost during the synchronization process.

**Labels** and **Custom Error Messages** are also synchronized during the language synchronization process. The system replaces all the custom error messages available in the target environment with those available in the source environment. As a result, if there is an extra label or custom error message in the target environment compared to the source environment, it will be deleted during synchronization.

### Application Properties

During synchronization, Application Properties are overwritten in the target environment.

### Tool Preferences

During synchronization, the Tool Preferences properties are overwritten in the target environment.

### Widgets

Both widget from Widget Hub or created in the App Composer instance can be synchronized.

If there are two distinct widgets (i.e. _Widget V1_ and _Widget V2_) with the same logical name, when  _Widget V2_ is published in the source environment, after the synchronization in the target environment the _Widget V1_ will be unpublished and the _Widget V2_ will be published.

If the two versions of widgets are available only in the source environment, then they will be synchronized in the target environment

If in the target environment there is only the _Widget V1_, after the synchronization in the target environment _Widget V1_ will be unpublished and _Widget V2_ will be created and published.



## Constraint and limits

### Constraints

The synchronization of an application between two App Composer instanced works only in the following scenarios:

* App Composer version is the same between source and target (i.e. you can synchronize between two DAC instance with version 2023.1.0 but you can NOT synchronize if source is on 2023.1.0 and target on 2022.2.1
* The metadata database must be of the same vendor. I.e. you can synchronize between two DAC version both on PostgreSQL but you can NOT synchronize if you have source in PostgreSQL and target in SQL Server
* The object comparison to calculate the differences is executed only when the application has the same owner code.&#x20;
* When exporting the application using CTR file and ADP file, the ADP can be imported only in the same environment that exported the CTR because the unique environment ID is compared before importing the ADP file. It is possible to overcome this limitation with a specific property: see the chapter below.
*   When selecting a large number of objects (in the range of hundreds or thousands) for the same .adp file, it is crucial to be aware of potential memory exceptions, notably the "`Java Heap Space`" error. Similarly, selecting objects with larger file sizes, such as resources uploaded in the Resource Catalog (e.g., zip files for Jobs), may also trigger this exception.

    To prevent the "Java Heap Space" exception and ensure smooth processing, it is strongly recommended to limit the selection to no more than 100 to 200 objects for the same .adp file. This precautionary measure helps maintain optimal Design Studio performance and prevents potential memory-related issues. You can also evaluate to [increase the memory](../introduction/design-studio/other-information.md#increase-the-memory-allocated-to-design-studio) allocated to Design Studio to prevent the issue from happening.

**Importing ADP on several different instances**

It is possible to import the **Metadata Dump File** (.adp) in an **different environment** from the one that created the Control file (.ctr).&#x20;

In this way it is possible to use the same adp file to import the same changes in multiple environments.

<figure><img src="../../.gitbook/assets/image (689).png" alt=""><figcaption></figcaption></figure>

When synchronizing on DAC WEB using a . adp file from a different environment than the one that created the Control (.ctr) file. you can disable id checking by selecting the **Ignore environment id check.**

<figure><img src="../../.gitbook/assets/image (1552).png" alt=""><figcaption></figcaption></figure>

### Objects compatibility

The table displays a list of all DAC objects and shows whether each object is supported, has limitations, or is not supported during synchronization. In case an object is not supported for the synchronization, it has to be manually modified or created in the target environment.

**Instance objects and properties**

<table><thead><tr><th>Object Name</th><th width="157.33333333333331">Supported</th><th>Notes</th></tr></thead><tbody><tr><td>Tool preferences</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td>All properties are overwritten in the target environment</td></tr><tr><td>Server</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Widgets</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>REST API Client</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Data Source</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span></td><td>From the second synchronization, only some properties are copied. See <a href="./#deploy-data-sources">Details </a></td></tr><tr><td>Languages</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span></td><td>Languages and labels are overwritten in the target environment. See <a href="./#terms-of-use-1">Details</a></td></tr><tr><td>Documents</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr><tr><td>Task</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr><tr><td>Recent contents</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr><tr><td>Users</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr><tr><td>Users Custom Attributes</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr><tr><td>Terms of use</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr><tr><td>Logo &#x26; Colors</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span></td><td></td></tr></tbody></table>

**Application objects and properties**

<table><thead><tr><th>Object Name</th><th width="154">Supported</th><th>Notes</th></tr></thead><tbody><tr><td>Report</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Report And Folder Permission</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Cube</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Dimension</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span></td><td>For the <a href="../data-mapping/dimensions/time-dimension.md">"TIME" dimensions</a>, tables and records are not included</td></tr><tr><td>Metric</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Direct Filter</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Range Filter</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Code Snippet</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Page</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Page Catalog</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td>The object will be always displayed as "in conflict".</td></tr><tr><td>DLR</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Application Properties</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td>All properties are overwritten in the target environment. See <a href="./#application-properties">Details</a></td></tr><tr><td>Application resource</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Group</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td>Association user/groups is not included (since users synchronization is not supported</td></tr><tr><td>User filter</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Notification</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Rule</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Action List</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td>See <a href="./#action-lists-and-scheduled-action-lists">Details </a></td></tr><tr><td>Scheduled Action List</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Scheduler (deprecated)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Schedule (deprecated)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span></td><td>The scheduling must be re-defined in the target environment.</td></tr><tr><td>Alert</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span> </td><td></td></tr><tr><td>Jobs</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26d4">⛔</span> </td><td>See<a href="./#page-management-to-web"> </a><a href="./#page-management-to-web">Details</a></td></tr></tbody></table>
