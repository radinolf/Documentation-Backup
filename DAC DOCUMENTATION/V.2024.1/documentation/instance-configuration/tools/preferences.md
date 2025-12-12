---
description: The list of the system properties are on the Preferences item
---

# Preferences

## Main

The system properties relating to Data Model are grouped in the **Main** section in **Tools Propertie**s window and are subdivided into the sub-groups:

* **Alert logging**
  * _**Max number of alert execution logs:**_ Allows to set the max number of logs for an alert that can be kept.
  * _**Days to keep alert execution logs :**_ Allows to set how many days logs for an alert must be kept.
* **Cache** The configuration of the cache at system level is on the property of the Cache group:
  * _**minHoldTimeDatamart (min):**_ is the minimum duration (in minutes) of the temporary tables used by the datamart and accessible to the user for displaying reports. Before this time, the tables will not be deleted, even if the system has rendered the cache invalid (default value set at 20 minutes).
* **Data logging –** For the times to clean the tables containing log information. You set how many days different content must be kept before it is deleted automatically. The default is 90 days for all log information tables, meaning that only the information relating to a historical period of 3 months will be kept:
  * _**Cleanup object execution log (days) :**_ for the table relating to the execution of the objects.
  * _**Cleanup user connections log (days) :**_ for the table relating to user connections.
* **Export**
  * **pdf-max-rows:** sets max row limit beyond which the report cannot be exported to Pdf.
  * **excel-max-rows:** sets max row limit beyond which the report cannot be exported to Excel.
  * **xls-Formula-Injection-Mitigation:** Enable this option to mitigate the risk of XLS Formula Injection in exported files. When enabled, cells beginning with characters such as '=', '+', '-', '@', Tab, or Carriage Return will be automatically escaped to prevent potential formula execution Microsoft Excel.
  * **csv-max-rows :** sets max row limit beyond which the report cannot be exported to CSV.
  * **xls-Injection-Mitigation:** Enable this option to mitigate the risk of CSV Injection in exported files. When enabled, cells beginning with characters such as '=', '+', '-', '@', Tab, or Carriage Return will be automatically escaped to prevent potential formula execution in spreadsheet software like Excel
* **External Editors**&#x20;
  * _**eclipse-path:**_ set the path of the Eclipse executed file to use as Snippet Code Editor.
* **Internationalization**
  * _**TimeZone:**_ select the user’s time zone. AUTO identifies the time zone automatically.
  * _**enableMultiLanguage:**_ enabe and disable the multilanguage system.
  * _**default-language:**_ set the default language used by the DAC to display content in case of missing labels in the user’s preferred language.
* **Report temp tables:** In order to operate on the system’s stress levels, by limiting the number of instances of the temporary tables created during execution of the reports:
  * _**intermediateMaxRows:**_ for those of the intermediate temporary tables.
  *   _**finalMaxRows**_: for the final temporary table, i.e. the table created by the system to populate the report.

      If the number of rows in the table exceeds the limit set, report running will be terminated immediately and the report will not be generated. The default value is **-1** which indicates an unlimited number of instances.
  * _**index-temp-tables:**_ &#x74;_&#x61;bles_ to activate temporary table indexing on the join key for the last integration step of the partial results.
* **Storage tables schema**
  * _**report-final-tables:**_ tables containing the DataMart of the reports (“FX” prefix).
  * _**report-interm-tables:**_ tables created in the intermediate stages of running reports (“DX”,”TX”,”UX” prefix).
  * _**excel-integration-tables:**_  the screen where the integration table will be saved when the associated data source is Executive Object-
* **System**
  * **system-parameters:** allows you to set the system parameters useful for debugging the application. The property value must be a valid JSON object written in Key/Value pairs (e.g. {“paramKey”:”paramValue”})
* **Users**
  * **Subject-fullname:** set the sort order to display the user lists

### &#xD;Caching Document Repository

The repository images or documents are managed using a cache of the Application server, which allows immediate loading for accesses following the first, without having to wait the loading times from the repository document to the application server each time.

In case it is necessary to delete this cache, in order to access the repository files again, a command is available from the **General Information console** on DAC.

![](<../../../.gitbook/assets/image (537).png>)

## Web

The configuration properties which impact DAC are in the **Web** item and affect:

* **Appearance**
  * **html-contents-allowed:** Allows you to enable direct interpretation of HTML content in the modules that support.
* **Connection**&#x20;
*   The Connection group has the **decisyonWebURL** property which allows you to define the URL to connect to DAC.

    If the system cannot connect to the URL entered, a warning message is displayed and the address entered is deleted. Whereas for the URL HTTPS, when the properties are validated, the SSL certificates are not considered

    * ⛔ **decisyonWebURL:** which allows you to define the URL to connect to DAC.If the system cannot connect to the URL entered, a warning message is displayed and the address entered is deleted. Whereas for the URL HTTPS, when the properties are validated, the SSL certificates are not considered.

{% hint style="danger" %}
&#x20;**decisyonWebURL.** This feature has been deprecated and it will be removed in a later version.
{% endhint %}

_**Note:** when the App Composer container starts, the system updates the value of the DecisyonWebUrl workspace property using a variable in the dedicated container in yaml. This way if the app is moved to another server or the DNS is changed, there is no need to manually update the property._

* **Login**
  * **automatic-user-creation:** if enabled, users will be automatically created in the system after being authenticated.
    * **user-active-on-creation:** define if the user created automatically is active or not after the authentication. Default new automatic users will be created as disabled users. &#x20;
  * **enable-group-sync-on-login:** system automatically updates the user's groups by comparing those found in the token with those associated with the internal account
    * **deny-access-if-no-groups:** is also available to block access for users who end up with no groups after login.  &#x20;

{% hint style="warning" %}
The **enable-group-sync-on-login** and **deny-access-if-no-groups** properties are available starting with version 2024.1.7
{% endhint %}

* **Page Navigation**
  * **⛔page-navigation-component:** Select Tab or Breadcrumb navigation mode.&#x20;

{% hint style="danger" %}
&#x20;**age-navigation-component:**&#x54;his feature has been deprecated and it will be removed in a later version.
{% endhint %}

*   [**Toolbar Settings**](preferences.md#toolbar-settings)

    * **show-menu-items:** Allow you to select which menu item to make visible on DAC.The default value is ALL. The option are Side Nav Menu and Toolbar Options.

    **Side Nave Menu:**

    * **Home:** to return to the Home Page; you can also click on the Decisyon logo.
    * **Pages**: Lists of pages created in the application
    * **Create:** which opens a menu for creating new objects in DAC.
    * **Recent Contents:** which opens a list of the last contents viewed by the user.
    * **People:** contains the list of users create in the application.
    * **Action List:** opens the window for creating an Action List
    * **Contents:** to access the list of content in your environment, such as documents, blog posts and signals.
    * **Alerts:** opens the window for creating an alert
    * **My Documents:** opens the list of documents created by the logged in user.
    * **Online Help:** which opens the online help to consult DAC manuals.&#x20;
    * **Widget Designer:**&#x74;o access the Widget Catalog that lists the widgets and libraries created by the user.
    * **Administration:** access to administrator functions (visible only for users with the administrator role)
    * **Settings:** Access to application customization tools and general information
    * **Logout:** shows the logout button on the Side nav Menu

    **Toolbar Options**:&#x20;

    * Notification: Show the Notification icon&#x20;
    * Tasks: Show the Task icon&#x20;
    * Alert: Show the Alert icon&#x20;

![](<../../../.gitbook/assets/image (1321).png>)

* [**User contents**](preferences.md#user-contents)
  *   **maxUploadFileSize (MB):**

      File size is expressed in MB and the default size configured is 20 MB.

      Minimum and maximum file sizes that can be set are 0.25 MB and 5 GB respectively.which sets the maximum size for files attached by users:

      * in collaboration Page components
      * in a discussion or task
* **WebReport**
  * **reinit-report (OnLaunch):** enables the automatic initialization of reports, when they are requested in DAC
  * **showReportToolbarCollapseButton:**&#x64;isplays/hides the button for openin&#x67;**/closing** _the report Toolbar in DAC_
  * **startReportToolbarCollapsed:**&#x64;isplays/hides the Report toolbar in DAC when the report Toolbar in DAC is hidden (**startReportToolbarCollapsed** _enabled_), (you can only open it if the button for opening the toolbar is available **showReportToolbarCollapseButton** _enabled_).



## E-mail&#x20;

Managing the sending of e-mails is configured in the **Email** section of the Tools properties:

·        **associated-SMTP-server** (System Emails group) the server sending e-mails is managed centrally and is associated in this property: open a window to select a **SMTP server**, among those defined in the server management window.

This server will be used to send e-mail notifications.

