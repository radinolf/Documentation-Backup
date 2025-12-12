---
description: >-
  In this page are listed a small number of the most important updates and share
  them with you via What's New. For more details you can consult the Changelog
---

# What's New

## Version 2023.0.0

In this page are listed a small number of the most important updates and share them with you via What's New. For more details you can consult the Changelog.

### Action List and Schedule Action List <a href="#action-list-and-schedule-action-list" id="action-list-and-schedule-action-list"></a>

The modules **Schedules Designer** and **Scheduler** are moved on the DAC and renamed to **Action List** and **Schedules**.

Using the **Action List** module of the Composer App, you can create a list of actions, schedule their update and execution using **Schedules** .

The Action Lists can be executed through a schedule or through **Execute Button**.

The App Composer objects that can be scheduled within an **Action List** are :

* Report
* Notification
* Rest Api Client
* Rule
* Job



<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

For more details see&#x20;

{% content-ref url="../documentation/app-functionality/action-list/" %}
[action-list](../documentation/app-functionality/action-list/)
{% endcontent-ref %}

## Dumbella Job <a href="#dumbella-job" id="dumbella-job"></a>

Now the Dumbella Jobs can also run in Asynchronus mode.

<figure><img src="../.gitbook/assets/image (277).png" alt=""><figcaption></figcaption></figure>

Now you can know which Jobs are running on Dumbella select the button on the top right of the Jobs Section to open the **Job manager.**

<figure><img src="../.gitbook/assets/image (525).png" alt=""><figcaption></figcaption></figure>

For more details see the documentation [**How to use Dumbella service**](whats-new-in-this-version.md#jobs)

## Drill Through dialog <a href="#drill-through-dialog" id="drill-through-dialog"></a>

It is possible to set the size (width and height) of a drill through dialog in pixel (both in the report and in the execute object widget). Now it is possible to make the dialog works even when the current viewport is smaller than the defined dialog size.

## Flex and Overflow auto property <a href="#flex-and-overflow-auto-property" id="flex-and-overflow-auto-property"></a>

The **Flex** and **Flex-overflow** properties have been moved below the **Container Size** set.

&#x20;

## Version 2022.2.0

## Flex Container  <a href="#definer-execute-button" id="definer-execute-button"></a>

Starting from version 2022.2.0 App Composer adopted the CSS Flexbox module to create responsive and flexible pages adding new set of properties and changing the behaviour of some existing widgets and features.

For more detail See the [Page Layout](../documentation/page-designer/page-layout/)

## Definer <a href="#definer-execute-button" id="definer-execute-button"></a>

Two new definers are now available to selected an Execute Button in the containing page and it's possible to use the REPORT\_LEVEL definer, which allow the selection of one or more levels of one of the reports associated to the widget.

<figure><img src="../.gitbook/assets/image (1053).png" alt=""><figcaption></figcaption></figure>

For more detail see [Widget Designer](whats-new-in-this-version.md#widget-designer) >> Definer in The widget



## Show a loding icon when Drill-Through opens. <a href="#show-a-loding-icon-when-drill-through-opens." id="show-a-loding-icon-when-drill-through-opens."></a>

A loading icon is shown on RunTime pages when opening a drill-through page.

## Page Designer <a href="#page-designer" id="page-designer"></a>

Some enhancements have been made to the Page Designer.

Some of these improvements concern the behavior of objects within the page, some scrollbar bugs have been fixed and the behavior of the min-width and max-width properties has been revised.\
You see:

#### Margin property <a href="#margin-property" id="margin-property"></a>

A new property “margin” is now present in the Container Style properties.\
The new property allows you to define the margins of the container.

#### Flex property <a href="#flex-property" id="flex-property"></a>

A new Flex property is now present in the container style properties. The Flex property is activated when the widget is placed in a Row or Column container

#### Row and Colum Container <a href="#row-and-colum-container" id="row-and-colum-container"></a>

New property have been added that if selected, allows you to manage the widgets inserted inside the container more flexibly and to automatically resize them according to the screen size.

#### Widget default size is changed <a href="#widget-default-size-is-changed" id="widget-default-size-is-changed"></a>

The default width of all custom widget are changed from 98% (old default value) to 100%.

Some widget present in de Widgets catalog are change the size when dragged in the page:

* **pageBy selector :** width and height are emply
* **execute button:** width and height are emply
* **submit:** width and height are emply
* **params cleaner:** width and height are emply
* **plain text:** width and height are emply
* **textfield** : width=300 and height =empty
* **tab selector** width =100% and height = empty
* **tab panel** width = 100% and height =400
* **table** width =100% and Min-height=50

#### Updated the default container height <a href="#updated-the-default-container-height" id="updated-the-default-container-height"></a>

* Is **changed** the default height of the **page** from 50px to 100%
* Are **remove** default **height** 50px add default **min-height** 50px\
  from the panel and row/col container

#### Property removed <a href="#property-removed" id="property-removed"></a>

To consult the list of removed properties see the following document in the Removal Feature section in the Change and migration notes of versione 2022.2.

#### Widgets <a href="#widgets" id="widgets"></a>

Custom widget documentation has been moved to the widget-hub site:

[Widgets](https://widgets.decisyon.com/dac-widget-hub)

#### Widget Discussion <a href="#widget-discussion" id="widget-discussion"></a>

The widget Discussion have been scaled down because the widget required a lot of vertical space and the number of visible message was very low . The improvement has impacted not only the discussion widget but also the discussions on tasks, documents as well as the private discussion.\
Part of the improvement are:

* A font scaling (smaller 12px)
* The size of the portrait on the first message has been reduced
* The reply box is always hidden and can be activated via the "reply" which, in addition to making it visible, will give the focus and scroll the content if it is not in the viewport
* A show / hide message command for messages ( visible only if there is at least a message )
* A show more comment command at the top of the messages if necessary ( visible only if there is other messages )
* The hide / show and reply commands are also present after the last message if the thread contains more than 5 messages

#### Widget Smart Table <a href="#widget-smart-table" id="widget-smart-table"></a>

Now in the smart-table-definition property it is possible to insert a percentage value in the width column.

<figure><img src="../.gitbook/assets/image (224).png" alt=""><figcaption></figcaption></figure>

&#x20;

### **API Version** <a href="#api-version" id="api-version"></a>

With the release of version 2022.2.0 the supported API version is 2.0. All Widgets Hub Widgets have been updated to the current version.

**Please see the Migration Note of API**

### Others  <a href="#others" id="others"></a>

A new example is available that explains how to build a page using the row and column container widgets using the new Flex-Container and Flex property.

## Version 2022.1.0

### Jobs

Now it is possible to decide the type of execution of the job (parallel or sequential).

{% content-ref url="/broken/pages/AyYtlYQV2l3LXnJ6x6U2" %}
[Broken link](/broken/pages/AyYtlYQV2l3LXnJ6x6U2)
{% endcontent-ref %}

### Widget Designer

Now in the widget HUB folder, it's present the Install menu item. Opens the Widget Hub window and shows the list of all DAC widgets that can be installed in the Widget Designer.

![](<../.gitbook/assets/image (762).png>)

{% content-ref url="/broken/pages/Qtn0MlREI33Cd8HDgaIJ" %}
[Broken link](/broken/pages/Qtn0MlREI33Cd8HDgaIJ)
{% endcontent-ref %}



### Users Creation

When system administrator enable the tool property _automatic-user-creation_ then it's possible to configure a new property _user-active-on-creation_ that will set the user as active when the user account is created. Default value: disabled (by default new automatic users will be created as disabled users).&#x20;

{% content-ref url="../documentation/instance-configuration/tools/preferences.md" %}
[preferences.md](../documentation/instance-configuration/tools/preferences.md)
{% endcontent-ref %}

### User Attribute

* When an attribute is set as mandatory, it is mandatory to define a default value.&#x20;
* When defining the value of an attribute for a user, you can choose .
* When the default value is chosen, the value is converted using the default value of the current attribute.
* Also is used as the initial value for attributes when creating a new user and all attributes are marked as default.&#x20;

### Accessing Page from the external systems&#x20;

Now in the direct link and embedded link of the Page, the tenant ID is passed in the query string as well .

View Page Designer >>Activities Task >> [Accessing Page from External Systems](../documentation/page-designer/advanced-configuration/activities-task.md#accessing-page-from-external-systems)

### Mandatory Params&#x20;

Now the mandatory parameter is evaluated even if not used in the widget.

### Page Designer

The DS Page Designer folder "**Social Widget**" has been renamed to "**Activity Stream**". Inside there is the "Activity Stream" widget

{% content-ref url="/broken/pages/vJvhOiL6QokdrOwVdvr7" %}
[Broken link](/broken/pages/vJvhOiL6QokdrOwVdvr7)
{% endcontent-ref %}

### **Parameter sorting on debug info of a page**

Now in the debug info of a page the parameters alphabetically is sorted

## Version 2022.0.0

## Runtime <a href="#runtime" id="runtime"></a>

A new interface for the Widget Catalog has been implemented.

![](<../.gitbook/assets/image (134).png>)

&#x20;See the documentation: [Broken link](/broken/pages/Qtn0MlREI33Cd8HDgaIJ "mention")

### Task <a href="#task-inlinecard" id="task-inlinecard"></a>

1. In the editing section of the Task, pagination has been introduced to view the available users.

### Main Toolbar  <a href="#main-toolbar-inlinecard" id="main-toolbar-inlinecard"></a>

1. The main toolbar has been made responsive. Below are the ways of displaying the icons on the main toolbar.

* **Main Menu** icon , **Inbox icon** , **Task board** icon , **Alert** icon, **User profile icon** are slways visible.

&#x20;

![](<../.gitbook/assets/image (759).png>)

* The **Logo** is visible only if enabled and for width > 960px
* The **Tenant** selection, a select is visible if the window width is> 600px otherwise if the width <= 600 Icon is shown

![](<../.gitbook/assets/image (890).png>)

* **Logout** icon is visible for width > 480
* A new item (Logout) has been added to the main menu , which allows you to log out of the application.



![](<../.gitbook/assets/image (169).png>)

* The panes opened by alerts and tenant selection have been resized to fit resolutions < 480 px and > 360 p

### Main Menu <a href="#main-menu" id="main-menu"></a>

The "Pages" menu item replaces the \<Application Name> item and a subtitle has been inserted for the application name.

![](<../.gitbook/assets/image (229).png>)

### Responsiveness and Performance of DAC UI <a href="#responsiveness-and-performance-of-dac-ui" id="responsiveness-and-performance-of-dac-ui"></a>

Refactoring of DAC user interfaces for responsive visualization and verification of improvements in static resource loading.\
The following components have been improved in this release:

**Navigation Sidenav menu**

![](<../.gitbook/assets/image (784).png>)

The navigation sidenav is opens locked at left of the page contents at screen resolution >=480px and is hidden if the screen resolution is <480px.\
In this case, the sidenav opens fullscreen on demand and closes on the click of item or close icon.  This behavior is also applied to when the section are opened:

* User Administration section&#x20;
* Group Administration&#x20;
* Rest API Client&#x20;
* Alert

&#x20;**Details Sidenav**

![](<../.gitbook/assets/image (613).png>)

The details sidenav shows the selected object details.\
It appears at the right of the screen overlapped on the page content.

The navigation sidenav and the detail sidenav can be opened at the same time with a screen width >960px.

If the screen width is lower than 960px, one sidenave visible at time is allowed, the other is closed.If the screen width <480px the details sidenav is opened al full page.

This behavior is also applied to when the section are opened:

* User Administration&#x20;
* Tasks&#x20;

#### Others dialogs made responsive <a href="#others-dialogs-made-responsive" id="others-dialogs-made-responsive"></a>

* Alert
* User Administration
* User Attribute
* Label Management
* Rest Api Client module
* Application Syncronization
* Group Administration's
* Task module
* Landing Page

### Design Studio Installer <a href="#design-studio-installer" id="design-studio-installer"></a>

Now it’s possibile to download the correct version of the Design Studio directly from RunTime, accessed in the Settings>>General Information >> Application Key section

![](<../.gitbook/assets/image (901).png>)

The installation of the design studio is performed through a wizard. The installer can be executed on Windows and Linux client. The installer automatically deploy the required OpenJDK to run Design Studio, ignoring any other java version already used by the client. When Design Studio is installed, each version will have its own folder in the O.S.



## Design Studio  <a href="#design-studio" id="design-studio"></a>

### Page Designer <a href="#page-designer" id="page-designer"></a>

### New Property in Container Style <a href="#new-property-in-container-style" id="new-property-in-container-style"></a>

A new property "className" has been introduced in the Container Style group of all the Page Designer widgets. Property allows to define css class to apply on the component. It will therefore be possible to manage the customization of CSS of the widget

### Execute object - Opening a page using Drill-Through <a href="#execute-object-opening-a-page-using-drill-through" id="execute-object-opening-a-page-using-drill-through"></a>

Two properties have been removed in the Execute Object widget of type Drill-Through

* **open-in-same-window:** opens the new page in the current page.
* **modal-window:** if enabled the Page will be opened in a modal type window.

The properties listed below have been added

* **enable-esc-to-close:** Allows user to close the dialog by pressing ESC keyboard button" default true
* **allow-user-to-close:** Allows user to close the dialog" default true)
* **click-outside-to-close:** Allows the user to close by clicking outside the dialog" default false
* **allow-full-screen:** Allows user to enlarge the dialog to full screen" default true

&#x20;

## APIs <a href="#apis" id="apis"></a>

### Added the new Decisyon JS APIs to the Page's Javascript object. <a href="#added-the-new-decisyon-js-apis-to-the-pages-javascript-object." id="added-the-new-decisyon-js-apis-to-the-pages-javascript-object."></a>

New JavaScript functions accessible from the Javascript object of the Page have been introduced, which will replace those present in the system. The new functions are available in the Decisyon folder.

Documentation of the new API is available within the documentation of the Widget in the web app.

![](<../.gitbook/assets/image (1021).png>)

### JS API - Include the id of the widget exporting the parameter <a href="#js-api-include-the-id-of-the-widget-exporting-the-parameter" id="js-api-include-the-id-of-the-widget-exporting-the-parameter"></a>

The JS API \{{extSendParamChanged\}} and \{{extSendMultiParamsChanged\}} now optionally also accept the ID of the widget that is currently exporting the parameter so the rendering of the widget itself will be excluded from refresh.

## Version 2021.3

### User Creation  <a href="#user-creation" id="user-creation"></a>

* In the dialog used to create a new user, a search field has been added to the tenant drop-down menu.
* In the user creation dialog, if the user already selected a tenant from the list on the left, the tenant menu be pre-selected on the same tenant, especially if the user only has 1 tenant associated. (See Users Administration for details)
* In the User Administration section, the edit of a user from Dx-Sidenav has been moved to the dialog box. See the figure.. (See [Users Administration](../documentation/user-management/users-administration.md#create-new-user) for details)

![](<../.gitbook/assets/image (848).png>)

### Migrate the Dialogs from Jquery to Angular Material Design <a href="#migrate-the-dialogs-from-jquery-to-angular-material-design" id="migrate-the-dialogs-from-jquery-to-angular-material-design"></a>

In this version, the graphics of some DAC components have been improved, passing from the use of the Jquery library to Angular Material UI component library.

The components that have undergone a restyling are the following:

* Drill-trough from Execute Button and Report Configuration
* Drill trough run from another dialog
* Report > Discussion and task on report cell (show/edit)
* Report > Functions on right click menu
* Edit report > tabs "Main" and "Object Explorer" (try all function buttons)
* Social bar on page > Settings > Share dialog
* Main menu > Create Signal, Task, Send a Message,
* User Administration >Create Tenant and Create/edit user)
* Create Area and Create Initative page > associate image
* My Signal > create/edit/delete
* Custom Total dialog on report contextual menu
* Remove Post dialog
* Remove or delete a discussion
* Remove or delete a reply to a discussion
* REST Datasource error code (i.e. 404) dialog

### Widget Designer <a href="#widget-designer" id="widget-designer"></a>

Now the function to Publish or unpublish the widgets are available in the contextual menu of the widget.

![](<../.gitbook/assets/image (736).png>)

A new column has been added to the widget catalog which shows the status of the published / unpublished widgets

![](<../.gitbook/assets/image (879).png>)

### Param sorting on Api-params-mapping <a href="#param-sorting-on-api-params-mapping" id="param-sorting-on-api-params-mapping"></a>

Now the list of parameter has be sorted ascending and case sensitive so that can easily find parameters by name.

### Refactoring and Simplification of Timezone settings <a href="#refactoring-and-simplification-of-timezone-settings" id="refactoring-and-simplification-of-timezone-settings"></a>

Creating a user (even by API) the timezone must be set.

Plese see the [Migration Notes](untitled/version-2021.3.0/migration-notes-2021.3/changes-and-migration-notes-of-version-2021.3.0.md#refactoring-and-simplification-of-timezone-settings)

&#x20;

### Tasks <a href="#tasks" id="tasks"></a>

In the Task Board and Task List, has been moved the Edit of task from Sidenav to Dialog.

![](<../.gitbook/assets/image (1050).png>)

### **Langing Page** <a href="#langing-page" id="langing-page"></a>

In the landing page, move the edit of page and application from Sidenav to Dialog. The dialog is opened from the modify icon in the Page and Application card.

![](<../.gitbook/assets/image (654).png>)

See [Application](/broken/pages/-MfHl_a4pwfbDb46XWQJ#create-application) section for details

### Metric formatt <a href="#metric-formatt" id="metric-formatt"></a>

Three new priorities have been added in the Layer group of Graph:

* **decimal-separator :** decimal separator applied to all chart series
* **thousand-separator:** thousand separator applied to all chart series
* **additional-chars:** Additional chars applied to all chart series

The addition of these new properties has an impact on migration. See [migration note](untitled/version-2021.3.0/migration-notes-2021.3/changes-and-migration-notes-of-version-2021.3.0.md#metric-format).

### First user logged marked as "administrator" <a href="#first-user-logged-marked-as-administrator" id="first-user-logged-marked-as-administrator"></a>

Now if the property Tool>>Preference>>Web>>automatic-user-creation is enabled, the first user that logs in the web application after the login will be marked as ‘administrator’. All the user that logs after the first one, are not created as an administrator.

See [Server\&Services](../documentation/instance-configuration/server-and-services.md)

### Report Property <a href="#report-property" id="report-property"></a>

Two new properties have been added for reports. Read.only-filter and Read-only-Columns.

![](<../.gitbook/assets/image (128).png>)

If a "read-only-filter" is defined through "read-only-columns" property is possible to select one o more columns of the read only rows as editable. The "readOnly" field is exposed in the report's json at Cell level.

### Configure security headers to embed page

To include a page of a DAC in an iframe it is necessary to configure the Content Security Policy of both DAC and the web application you want to use to include the pages of DAC.

See&#x20;

## Version 2021.2.2

### Deprecate JS API Function extCloseDialog(idDialog)

The JS API Function extCloseDialog(idDialog)&#x20;

### Configure visualization grants on Drill Through

Now it's possible to select wich user groups can view the drill through.

{% content-ref url="../documentation/report/report-1/" %}
[report-1](../documentation/report/report-1/)
{% endcontent-ref %}





{% hint style="info" %}
Please see the [Migration Notes](untitled/version-2021.2/)
{% endhint %}

### Group Interface

Now in the user groups section there is pagination to view users.

### Execute Object

The widget "Execute object" is refactored in order to use the new Dumbbells services.

### Talend integration

Now you can select or insert (using a page parameter) the context name of a Talend Job into a run button widget. This allows you to select which job execution context to use.





## Version 2021.2.1

### New Languages supported by the App Composer

A new list of languages must be supported by App Composer.

{% content-ref url="../documentation/instance-configuration/multilanguage-and-localization/languages-administrations.md" %}
[languages-administrations.md](../documentation/instance-configuration/multilanguage-and-localization/languages-administrations.md)
{% endcontent-ref %}

### Application Synchronization On Web

Web synchronization compared to Design Studio allows you to connect via Run Time to the target application if it is not possible to connect to the Design Studio.

{% content-ref url="../documentation/application-synchronization-wip/" %}
[application-synchronization-wip](../documentation/application-synchronization-wip/)
{% endcontent-ref %}

### Filter User List

Now it’s possible to filter the user list by the Scope

{% content-ref url="../documentation/user-management/users-administration.md" %}
[users-administration.md](../documentation/user-management/users-administration.md)
{% endcontent-ref %}

### Administrator Switch

Users with scope "Users Administration" or "Tenans Administration" or "All Tenant" don't display the switch "Administrator" in the Detail tab of the user creation wizard and in the summary inforations.

{% content-ref url="../documentation/user-management/users-administration.md" %}
[users-administration.md](../documentation/user-management/users-administration.md)
{% endcontent-ref %}

### Dumbella on MSSql Server

Now Dumbella works on MSSQL Server

{% content-ref url="/broken/pages/-MfX1AzFu9mGKdBq5FLp" %}
[Broken link](/broken/pages/-MfX1AzFu9mGKdBq5FLp)
{% endcontent-ref %}

### Column definition on composite metric

Now the Data Type and visibility can be set for a composite metric.

### Tenant section

Improvements have been made to the tenant section of user administration

1. have been rename the button to "New Tenant"
2. Have been a new item called "All Users" which displays both tenant and non-tenant users.
3. The "no tenant" item have been renamed to "Users without tenant"
4. The Icons have been updated

{% content-ref url="../documentation/user-management/tenant.md" %}
[tenant.md](../documentation/user-management/tenant.md)
{% endcontent-ref %}

![](<../.gitbook/assets/image (80).png>)

### Enhancement in the list of user in the administration page

Now in the User Administration :

1. The default sorting of the list have be by name ascending&#x20;
2. The column “type” have removed&#x20;
3. The column “username” now is displayed in this list.&#x20;
4. Disabled users are highlighted in the interfaceUI,&#x20;
5. When the user is associated to many tenants, the user interface show only some Tenant.

{% content-ref url="../documentation/user-management/users-administration.md" %}
[users-administration.md](../documentation/user-management/users-administration.md)
{% endcontent-ref %}

### Refactoring of filters in the user management

{% content-ref url="../documentation/user-management/users-administration.md" %}
[users-administration.md](../documentation/user-management/users-administration.md)
{% endcontent-ref %}



