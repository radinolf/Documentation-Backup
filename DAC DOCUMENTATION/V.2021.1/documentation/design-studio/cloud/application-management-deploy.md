# Application Management- Deploy

### Starting the Deployment Process

You can execute the deployment of the existing application from the menu item:

**Application Management >> Deploy**

Or, select the **Deploy** function from the shortcut. Either method launches the Application Deploy wizard.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/1.jpg)

**DAC URL:** enter the URL target DAC where the application will be deployed.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/2.jpg)

**Authorization Tocken :** enter a valid Tocken

The two options allow:

* **Deploy all application objects:** Use this option to deploy all of the application objects that have been modified since the last deployment. Design Studio automatically identifies all of those objects that have been modified.
* **Deploy only selected application objects:** Use this option to select only the specific application objects you want to deploy. You will be prompted, in a separate step, to select the object to deploy.

### Deploy Only Selected Application Objects

The second step after selecting the **Deploy only selected application objects** option is the selection of the component to be deployed.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/3.jpg)

When you select an individual object, a summary of the features will appear in the section on the right. These relate to the source Data Model and target Data Model (if the object is also present in the latter). The last pane shows the type of operation to be performed on it.

Note that each operation is marked by a different color, which is used by the system to highlight the names of the objects involved.

On the first occasion, they can only be copied, while other operations will also be possible on subsequent occurrences:

* _**Creation**_ of the object in the target Data Model (name highlighted in green), when a new object has been created in the source Data Model
* _**Deletion**_ of the object from the target Data Model (name highlighted in purple), when an object still present in the target Data Model has been deleted in the source Data Model
* _**Update**_ of the object in the target Data Model (name highlighted in blue), when the object has been modified in the source Data Model, while it has not underwent any changes in the destination Data Model
* _**Conflicts Between**_ the characteristics of the object in the source and target Data Model (name highlighted in red), when the object has been modified in both the source and target Data Model. The conflict is resolved by applying the changes made to the source object to the target object
* _**Restoring**_ the object in the target Data Model (name highlighted in orange), when an object still in the source Data Model has been deleted in the target Data Model

When you select the items you want and click on the _Next_ button, you display a summary **window with the objects selected previously.**

**In some** case&#x73;**, the&#x20;**_**advanced**_**&#x20;operations column** shows certain advanced operations for a specific object. The next step (_Next_ button) launches the deploy activity.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/4.jpg)

The deploy tool can perform the following operations:

* **Add** (green): create the object in the target environment.
* **Delete** (brown): delete the object in the target environment, since the same object has been deleted in the source environment.
* **Modify** (blue): update the object in the target environment, since the same object has been modified in the source environment.
* **Conflict** (red): the same object has been modified in both source and target environments. The conflict is resolved by modifying the object in the target environment.
* **Restore Add** (orange): restore the object that has been deleted in the target environment but still exists in the source environment.

### Deployment of a Page Catalog

When you deploy a Page Catalog, you overwrite the publication in the target environment of common Pages with the source environment by indicating the catalog branches (groups and sub-groups) of the source Pages Catalog, in the target environment.

When you deploy, the system checks whether or not a Page has been moved to another group, so the same changes are made in the target.

Any images the administrator associates with groups, sub-groups and Page Catalog objects, are deployed simultaneously with it.

**Note:** To indicate the Page catalog, the Pages must already be in the target. You can bring a Page to the Pages Catalog at the same time.

### Deploy User, Groups and Report Catalog Privileges

When you Deploy, you replicate groups or user in the source environment and keep their properties deploy in the target environment.

This step requires the developer to align:

* permissions on Cubes, Dimensions and Metrics of the application (set in the _Permission_ folder)
* privileges on DAC functions (set in the _Events_ folder)

It is mandatory for groups to be versioned so the existing privileges and associations between the groups and objects (such as Pages, alerts, notifications, etc.) can be indicated in the target.

* The object-group association is in fact only indicated if the group is in the object when the object is aligned in the target environment.

However, **privileges on reports** are deployed together with those of the catalog, to prevent inconsistencies between permissions on reports and permissions on folders.

The list of versioning objects includes

* _**Report and folder permissionsà Report Catalog**_

### Deploy Data Sources

There are two steps involved in versioning data sources:

* The create phase, when the data source is not in the target.

The object is indicated internally in the target, properties and pointers.

* The update phase, when they are present in both environments.

Only the properties are updated, while the pointers of the target data source remain unchanged.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/5.jpg)

### Share New Application

If you select the option to deploy the application in an export file there are some mandatory activities to be performed if you are deploying a new application:

* Generate a metadata file for a new application in the App Composer available in the DevBox where you want to deploy your new application.
* In the source App Composer DevBox, use the metadata file to create an Export file that includes the deployment instructions.
* In the App Composer of the destination DevBox you need to import the Export file. At this point the system creates the application.

Below you find a schema describing this action.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/6.jpg)

For example, if you want to bring the application created in the devbox a into the devbox b (step1) &#x20;

It is necessary to create a metadata filein the App Composer available in the devbox b.

The Metadata File to import a new application is a file where all the information is stored about the objects shared between all the workspaces available.

In order to execute this action go to **Application >> Share** and select **Share Metadata File:**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/7.jpg)

* Select the option “Generate the Metadata file for importing a new application”. At the end of the procedure the system will generate the Metadata File. The file must be saved (metadata\_app\_file.ctr).
* At this point you send the Metadata File to the Devbox a (Step 2) and you can start the deployment.
* Go to **Application** >>**Share** and select
* From the wizard, select the Deploy on File and enter the Metadata file (metadata\_app\_file.ctr). The system will perform a control procedure on both the objects and the metadata versioning because they need to be the same on both applications.![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/8.jpg)

Now you are ready to perform the export of all objects or of the selected ones.

In the last step the system will require you to save the Export File(Step 4).

The Export File contains the operations to be executed when the application is exported in the destination.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/9.jpg)

Get the Export File and send it to the Devbox b (Step 4) and execute the import using a File.

Access **Application>> Share** and select **Import.**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/10.jpg)

&#x20;Once the importing process has finished the new application will be available in the application catalog list **File>> Application Management**.

### Updating an Application From File

In order to update an existing application from a file you need to:

* Generate a control file, in the app composer of the destination DevBox, of the application that you need to update (devbox b)
* Generate an Export file in the App Composer of the source devbox using the control file in order to update the application in devbox a
* In the destination devbox (devbox b) you can import the Export file. The system now will update the application.

Below you can see the logical flow of this process.&#x20;

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/11.jpg)

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/12.jpg)

To execute this action go to **Application** and **select** **Metadata File:**

* Select “Create the metadata File for updating the current application”. Save file (metadata\_app\_file.crt).
* Send the Metadata File to Devbox a (Step 2) and run the Deployment using a File.
* Go on **Application>> Share** and select
* From the wizard select “Export” and enter the metadata\_app\_file.crt. The system will perform an automatic control on both objects to be deployed and, the metadata versioning.

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/13.jpg)

At this stage you can decide to proceed to the app deployment using all objects or a selection of them.

In the last step the wizard requires you to save the Export File (Step 4).

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/14.jpg)

Now you can send the Export File to Devbox b (Step 4) and you can run the import using a file.

Go to **Application** and select **Import .**

![](https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/Deploy/15.jpg)

Once the import ends the application will be updated with the changes performed in the source application.

### Remove Deleted Application

To delete an Application, you need to access in the Design Studio of the target application
