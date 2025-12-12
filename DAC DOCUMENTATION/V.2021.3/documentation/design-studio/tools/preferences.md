---
description: The list of the system properties are on the Preferences item
---

# Preferences

## Main

The system properties relating to Data Model are grouped in the **Main** section in **\*\*the** Tools Properties\*\* window and are subdivided into the sub-groups:

* **Alert logging**
  * _**Max number of alert execution logs:**_ Allows to set the max number of logs for an alert that can be kept.
  * _**Days to keep alert execution logs :**_ Allows to set how many days logs for an alert must be kept.
* **Cache** The configuration of the cache at system level is on the property of the Cache group:
  * _**minHoldTimeDatamart (min):**_ is the minimum duration (in minutes) of the temporary tables used by the datamart and accessible to the user for displaying reports. Before this time, the tables will not be deleted, even if the system has rendered the cache invalid (default value set at 20 minutes).
* **Collaboration**
  * **storage-datasource:** set the target in which the Collaboration tables will be created.
* **Data logging –** For the times to clean the tables containing log information. You set how many days different content must be kept before it is deleted automatically. The default is 90 days for all log information tables, meaning that only the information relating to a historical period of 3 months will be kept:
  * _**Cleanup object execution log (days) :**_ for the table relating to the execution of the objects.
  * _**Cleanup user connections log (days) :**_ for the table relating to user connections.
* [**Document Repository**](preferences.md#caching-document-repository)
  * _**repository-type:**_ set the medium the Document Repository is saved.
  * _**storage-datasource:**_ data source used to store the files in the Document Repository.
* **Export**
  * **pdf-max-rows:** sets max row limit beyond which the report cannot be exported to Pdf.
  * **excel-max-rows:** sets max row limit beyond which the report cannot be exported to Excel.
  * **csv-max-rows :** sets max row limit beyond which the report cannot be exported to CSV.
* **External Editors**&#x20;
  * _**eclipse-path:**_ set the path of the Eclips executed file to use as Snipped Code Editor.
* **GoogleMap**
  * _**googleMapKey:**_ enter the URL code that contains the _Google Maps_ service activation key.
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

![](<../../../.gitbook/assets/image (118).png>)

## Web

The configuration properties which impact DAC are in the **Web** item and affect:

* **Appearance**
  * **html-contents-allowed:** Allows you to enable direct interpretation of HTML content in the modules that support.
* **Cloud**
  * **kubernetes-endpoint:** it sets the Kubernetes.
  * **kubernetes-token:** it sets the token to authenticated to.
* **Connection**
  * **decisyonWebURL:** which allows you to define the URL to connect to DAC.If the system cannot connect to the URL entered, a warning message is displayed and the address entered is deleted. Whereas for the URL HTTPS, when the properties are validated, the SSL certificates are not considered.

_**Note:** when the App Composer container starts, the system updates the value of the DecisyonWebUrl workspace property using a variable in the dedicated container in yaml. This way if the app is moved to another server or the DNS is changed, there is no need to manually update the property._

* **Login**
  * **automatic-user-creation:** if enabled, users will be autommatically created.
* **Page Navigation**
  * **page-navigation-component:** Select Tab or Breadcrumb navigation mode.&#x20;
* [**Toolbar Settings**](preferences.md#toolbar-settings)
  * **show-menu-items:show-menu-items:** Allow you to select which menu item to make visible on DAC.The default value is ALL. The option are Side Nav Menu and Toolbar Options
* [**User contents**](preferences.md#user-contents)
  *   **maxUploadFileSize (MB):**

      File size is expressed in MB and the default size configured is 20 MB.

      Minimum and maximum file sizes that can be set are 0.25 MB and 5 GB respectively.which sets the maximum size for files attached by users:

      * in collaboration Page components
      * in a discussion or task
* [**WebEvents**](preferences.md#web-events-managing-user-web-events)
  * **customEventManager:** allows you to enable the Custom Events.
* **WebReport**
  * **reinit-report (OnLaunch):** enables the automatic initialization of reports, when they are requested in DAC
  * **showReportToolbarCollapseButton:**&#x64;isplays/hides the button for openin&#x67;**/closing** _the report Toolbar in DAC_
  * **startReportToolbarCollapsed:**&#x64;isplays/hides the Report toolbar in DAC when the report Toolbar in DAC is hidden (**startReportToolbarCollapsed** _enabled_), (you can only open it if the button for opening the toolbar is available **showReportToolbarCollapseButton** _enabled_).



### Connection

The Connection group has the **decisyonWebURL** property which allows you to define the URL to connect to DAC.

If the system cannot connect to the URL entered, a warning message is displayed and the address entered is deleted. Whereas for the URL HTTPS, when the properties are validated, the SSL certificates are not considered

### Login

Authentication in DAC allows the user to automatically log in the next time the system is accessed. The **Stay** **connected** check allows the system to store the user access credentials in DAC.

The Login group includes several properties:

·        **saveLastUserLogin** when selected, this property saves the last user connected to DAC. The next time the user logs in, the username will automatically be completed and he will only have to enter the password.

If this property is not selected, the user will have to enter his user\_id each time he logs into DAC.

·        **activateStayConnected** is enabled by default and enables the property:

§  **expiration-time (days)** this is where you set how many days access via automatic login is valid for

The system generates a token for managing DAC authentication and saves it in a cookie saved in the browser.

You can use the token to log in once, after which it will no longer be valid and authentication will no longer be performed.

The system uses this token to perform authentication and generates a new token which is saved for the next login.

The validity of the cookie is the same as the validity set in the expiration-time (days) property.

DAC will then authenticate the user according to one of the four methods available on the system and defined beforehand for the user.

·        **show-login-message** is disabled by default and lets you insert a message that will be displayed after logging into DAC.

§  **message-text** a window is opened in which you can insert the text of the message.

The message is displayed both if the login took place via standard or custom authentication, or via the stay connected function.

It is not displayed in the event of accessing the system via the direct link with authentication parameters.

**Note:**  If you use a custom login, you can enter in the DAC URL the parameter PAR\~Alm=1 to prevent this message being shown by the system.

###

### Toolbar Settings

·        **show-menu-items:** Allow you to select which menu item to make visible on DAC. The default value is ALL.

The menu item that can be disabled are:

* **Home:** to return to the Home Page; you can also click on the Decisyon logo.
* **Create:** which opens a menu for creating new objects in DAC.
* **Recent Contents:** which opens a list of the last contents viewed by the user, such as reports, pages, documents, spaces etc.
* **Collaboration Spaces:** which opens a list with all available spaces for the user.
* **Contents:** to access the list of content in your environment, such as documents, blog posts and signals.
* **Users:** contains the list of users, from which you can choose who to follow, send a signal, add to Favorites, etc.
* &#x20;**Widget Designer:** to access the Widget Catalog that lists the widgets and libraries created by the user.
* **Settings**: to access on the Administration and Customization settings
* **Online Help:** which opens the online help to consult DAC manuals.&#x20;

### Web Events (Managing User Web Events)

The **Web Events** group presents **the customEventManager** propert&#x79;**:** it enables **eventManagerClass** where it is possible to associate a Java class (external and compiled independently), through which it is possible to perform the customized actions of the administrator in respect to the action of the users of DAC.

The Java class must be inserted:

* in the DAC-DS “EXT” folder
* in the DAC “Lib” folder

The following parameters are those sent by DAC and allow the event to be managed:

* **@param userIdString user-id**, user-ID of the user, in string format, for which execution of the event is requested;
* **@param userName**, username of the user, for which execution of the event is requested;
* **@param eventId**, ID of the event relating to the function (e.g. LW\_RSTATE\_LAUNCH\_REPORT to launch a report);
* **@param eventDesc**, description (if present) relating to the event to be authorized;
* **@param objId**, ID (when present) of the object which is being authorized (e.g. report ID, Page ID, etc.);
* **@param objType**, ID (when present) which allows the type of object to be determined;
* **@param objDesc**, description (when present) of the object for which the user is requesting authorization;
* **@param objName**, name (if present) of the object to be authorized;
* **@param modelName**, name of the application containing the objects;
* **@param owner**, id of the application containing the objects;
* **@param**, reference of the database connection;
* **@param additionalParams**, additional parameters that provide extra support for the calculation of permissions (E.g. HttpServletRequest);
* **@return true**, if the function is to be permitted for the user;
* **@throws Exception**, if it is necessary to stop the operation and prevent it from being executed, or to flag a problem.

The reference Java interface that the event manager must implement is shown below:

package it.decisyon.ext.customEventManager;

import java.sql.Connection;

import java.util.HashMap;

/\*\*

&#x20;\* Interface that defines an event manager object

\*/

public interface **IEventManager** { {

&#x20;              public static final String  PARAM\_HTTP\_REQUEST              = "httpRequest";

&#x20;              /\*\*

&#x20;               \* Returns true if the specified event is permitted

&#x20;               \*

&#x20;               \* @param userIdString

&#x20;               \* @param userName

&#x20;               \* @param eventId

&#x20;               \* @param eventDesc

&#x20;               \* @param objId

&#x20;               \* @param objType

&#x20;               \* @param objDesc

&#x20;               \* @param objName

&#x20;               \* @param modelName

&#x20;               \* @param owner

&#x20;               \* @param with

&#x20;               \*@param additionalParams

&#x20;               \* @return true

&#x20;               \* @throws Exception

&#x20;               \*/

public boolean **isAllowed**(long userIdString,String userName, String eventId,String eventDesc, String objId,int objType, String objDesc, String objName, String modelName,String owner, Connection con, HashMap\<String,Object> additionalParams) throws Exception;

&#x20;              /\*\*

&#x20;               \* Is called when the event is actually executed, after the isAllowed method

&#x20;               \*

&#x20;               \* @param userIdString

&#x20;               \* @param userName

&#x20;               \* @param eventId

&#x20;               \* @param eventDesc

&#x20;               \* @param objId

&#x20;               \* @param objType

&#x20;               \* @param objDesc

&#x20;               \* @param objName

&#x20;               \* @param modelName

&#x20;               \* @param owner

&#x20;               \* @param with

&#x20;               \* @param additionalParams

&#x20;               \* @throws Exception if it is necessary to stop the operation and prevent it from being executed.

&#x20;               \*/

public void **eventExecuted**(long userIdString,String userName, String eventId,String eventDesc, String objId,int objType, String objDesc, String objName, String modelName,String owner, Connection con, HashMap\<String,Object> additionalParams) throws Exception;

}<br>

### User Contents

The **User** contents group presents the property:

·        **maxUploadFileSize (MB)** which sets the maximum size for files attached by users:

–       in collaboration Page components

–       in a discussion or task

File size is expressed in MB and the default size configured is 20 MB.

Minimum and maximum file sizes that can be set are 0.25 MB and 5 GB respectively.

#### **Metrics Selection Method**WebReport

The **WebReport** group has the following properties:

·        **reinit-report (OnLaunch),** enables the automatic initialization of reports, when they are requested in DAC

·        **showReportToolbarCollapseButton,** displays/hides the button for openin&#x67;**/closing** the report Toolbar in DAC

·        **startReportToolbarCollapsed:** displays/hides the Report toolbar in DAC

when the report Toolbar in DAC is hidden (**startReportToolbarCollapsed** enabled), (you can only open it if the button for opening the toolbar is available **showReportToolbarCollapseButton** enabled).

## E-mail&#x20;

Managing the sending of e-mails is configured in the **Email** section of the Tools properties:

·        **associated-SMTP-server** (System Emails group) the server sending e-mails is managed centrally and is associated in this property: open a window to select a **SMTP server**, among those defined in the server management window.

This server will be used to send e-mail notifications.

####

