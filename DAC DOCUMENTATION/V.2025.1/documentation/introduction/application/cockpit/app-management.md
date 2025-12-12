# App Management

The **App Management** section allows for the synchronization of applications across different environments. It is possible to import a new application based on an existing one from another environment or update existing applications through synchronization. Additionally, each application offers functionalities such as application removal and log consultation, providing a centralized and comprehensive management experience.

<figure><img src="../../../../.gitbook/assets/image (2284).png" alt=""><figcaption></figcaption></figure>

The pagenshows the list of available applications, and for each of them, the following details are provided:

* **Application**: Displays the application ID (owner) associated with each application. The owner is automatically assigned when the application is created, it is unique and it is visible also in Design Studio and App Composer
* **Name**: Indicates the name of the application to facilitate its identification (e.g., "Digital Lean Meeting Assistant").
* **Description**: If set during the[ application creation](../../../application/application.md), it shows the description associated with the application.&#x20;

{% hint style="success" %}
The application name and description are managed by the multilingual system if multilingual tags were used during the application's creation.
{% endhint %}

### New Application

In the top right corner, there is a **New Application** button, which allows users to import new applications into the system.

<figure><img src="../../../../.gitbook/assets/image (2285).png" alt=""><figcaption></figcaption></figure>

From the **"New Application"** button, the necessary options are available to start the synchronization and import process for a new application:

* **Download application configuration**: Includes all the metadata information in the [control file](../../../application-synchronization-wip/).
* **Import application**: Imports the **.adp** file downloaded from the source environment.

### Contextual Menu

<figure><img src="../../../../.gitbook/assets/image (2286).png" alt=""><figcaption></figcaption></figure>

For each application, there is a contextual menu that activates by selecting the three dots on the right:

* **Download application configuration**: Includes all the metadata information in the [control file](../../../application-synchronization-wip/).
* **Update**: Allows you to select the .adp file containing the export of the application to be imported.
* **Delete**: Permanently deletes the application from DAC. Once deleted, it cannot be restored.
* **Show Log**: Opens a window displaying the details related to the application's synchronization logs. Log items are sorted in descending order by execution date.

<figure><img src="../../../../.gitbook/assets/image (2288).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
The examples related to synchronization from Cockpit are provided in the dedicated [synchronization ](../../../application-synchronization-wip/)module.
{% endhint %}



