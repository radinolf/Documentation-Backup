# Loading Talend Jobs

Thanks to the integration of Talend’s services with the AppComposer, you have the possibility to manage Talend Jobs resources in terms of updating, deleting and publishing.

To manage the Jobs within the AppComposer you need to import them as a resource through the Resource Catalog.

For the Talend Job to be correctly recognized within DAC, it must be generated through the export of a **.zip** file, containing folders and files, as described below:

* **lib**
  * _\[JOB Name]_
    * _\[PROJECT Name]_
      * ….
* **jobInfo.properties**

If the file of the Talend Job has this structure when it is loaded as a resource in the catalog, it is recognized as a **Job Talend** type resource, as shown in the figure below.

In the summary information, the type and the name of the Job's main class are specifie&#x64;**.**

![](<../../../.gitbook/assets/8 (16).png>)

{% hint style="info" %}
It is not recommended to manually change the name of the job, as this could make the structure of

the job folders inconsistent, making impossible to execute it through the executable file that is inside the job folders.
{% endhint %}

The list of Jobs imported into the DAC is available in the [_**Administration>> Jobs**_](/broken/pages/-Mi0SPs4oskUYkDyLWIY) _**section of Run Time.**_
