---
description: >-
  In this page are listed a small number of the most important updates and share
  them with you via What's New. For more details you can consult the Changelog
---

# What's New in this version

## Version 2022.0.0

## Runtime <a href="#runtime" id="runtime"></a>

A new interface for the Widget Catalog has been implemented.

![](<../.gitbook/assets/image (140).png>)

&#x20;See the documentation: [widget-designer.md](../documentation/run-time/widget-designer.md "mention")

### Task <a href="#task-inlinecard" id="task-inlinecard"></a>

1. In the editing section of the Task, pagination has been introduced to view the available users.

### Main Toolbar  <a href="#main-toolbar-inlinecard" id="main-toolbar-inlinecard"></a>

1. The main toolbar has been made responsive. Below are the ways of displaying the icons on the main toolbar.

* **Main Menu** icon , **Inbox icon** , **Task board** icon , **Alert** icon, **User profile icon** are slways visible.

&#x20;

![](<../.gitbook/assets/image (85).png>)

* The **Logo** is visible only if enabled and for width > 960px
* The **Tenant** selection, a select is visible if the window width is> 600px otherwise if the width <= 600 Icon is shown

![](<../.gitbook/assets/image (177).png>)

* **Logout** icon is visible for width > 480
* A new item (Logout) has been added to the main menu , which allows you to log out of the application.



![](<../.gitbook/assets/image (141).png>)

* The panes opened by alerts and tenant selection have been resized to fit resolutions < 480 px and > 360 p

### Main Menu <a href="#main-menu" id="main-menu"></a>

The "Pages" menu item replaces the \<Application Name> item and a subtitle has been inserted for the application name.

![](<../.gitbook/assets/image (153).png>)

### Responsiveness and Performance of DAC UI <a href="#responsiveness-and-performance-of-dac-ui" id="responsiveness-and-performance-of-dac-ui"></a>

Refactoring of DAC user interfaces for responsive visualization and verification of improvements in static resource loading.\
The following components have been improved in this release:

**Navigation Sidenav menu**

![](<../.gitbook/assets/image (212).png>)

The navigation sidenav is opens locked at left of the page contents at screen resolution >=480px and is hidden if the screen resolution is <480px.\
In this case, the sidenav opens fullscreen on demand and closes on the click of item or close icon.  This behavior is also applied to when the section are opened:

* User Administration section&#x20;
* Group Administration&#x20;
* Rest API Client&#x20;
* Alert

&#x20;**Details Sidenav**

![](<../.gitbook/assets/image (113).png>)

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

![](<../.gitbook/assets/image (136).png>)

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

![](<../.gitbook/assets/image (137).png>)

### JS API - Include the id of the widget exporting the parameter <a href="#js-api-include-the-id-of-the-widget-exporting-the-parameter" id="js-api-include-the-id-of-the-widget-exporting-the-parameter"></a>

The JS API \{{extSendParamChanged\}} and \{{extSendMultiParamsChanged\}} now optionally also accept the ID of the widget that is currently exporting the parameter so the rendering of the widget itself will be excluded from refresh.

## Version 2021.3

### User Creation  <a href="#user-creation" id="user-creation"></a>

* In the dialog used to create a new user, a search field has been added to the tenant drop-down menu.
* In the user creation dialog, if the user already selected a tenant from the list on the left, the tenant menu be pre-selected on the same tenant, especially if the user only has 1 tenant associated. (See Users Administration for details)
* In the User Administration section, the edit of a user from Dx-Sidenav has been moved to the dialog box. See the figure.. (See [Users Administration](../documentation/run-time/administration/users-administration.md#create-new-user) for details)

![](<../.gitbook/assets/image (124).png>)

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

![](<../.gitbook/assets/image (76).png>)

A new column has been added to the widget catalog which shows the status of the published / unpublished widgets

![](<../.gitbook/assets/image (166).png>)

### Param sorting on Api-params-mapping <a href="#param-sorting-on-api-params-mapping" id="param-sorting-on-api-params-mapping"></a>

Now the list of parameter has be sorted ascending and case sensitive so that can easily find parameters by name.

### Refactoring and Simplification of Timezone settings <a href="#refactoring-and-simplification-of-timezone-settings" id="refactoring-and-simplification-of-timezone-settings"></a>

Creating a user (even by API) the timezone must be set.

Plese see the [Migration Notes](../migration-notes/untitled/version-2021.3/changes-and-migration-notes-of-version-2021.3.0.md#refactoring-and-simplification-of-timezone-settings)

&#x20;

### Tasks <a href="#tasks" id="tasks"></a>

In the Task Board and Task List, has been moved the Edit of task from Sidenav to Dialog.

![](<../.gitbook/assets/image (100).png>)

### **Langing Page** <a href="#langing-page" id="langing-page"></a>

In the landing page, move the edit of page and application from Sidenav to Dialog. The dialog is opened from the modify icon in the Page and Application card.

![](<../.gitbook/assets/image (152).png>)

See [Application](../documentation/design-studio/application/#create-application) section for details

### Metric formatt <a href="#metric-formatt" id="metric-formatt"></a>

Three new priorities have been added in the Layer group of Graph:

* **decimal-separator :** decimal separator applied to all chart series
* **thousand-separator:** thousand separator applied to all chart series
* **additional-chars:** Additional chars applied to all chart series

The addition of these new properties has an impact on migration. See [migration note](../migration-notes/untitled/version-2021.3/changes-and-migration-notes-of-version-2021.3.0.md#metric-format).

### First user logged marked as "administrator" <a href="#first-user-logged-marked-as-administrator" id="first-user-logged-marked-as-administrator"></a>

Now if the property Tool>>Preference>>Web>>automatic-user-creation is enabled, the first user that logs in the web application after the login will be marked as ‘administrator’. All the user that logs after the first one, are not created as an administrator.

See [Server\&Services](../documentation/design-studio/cloud/server-and-services.md)

### Report Property <a href="#report-property" id="report-property"></a>

Two new properties have been added for reports. Read.only-filter and Read-only-Columns.

![](<../.gitbook/assets/image (186).png>)

If a "read-only-filter" is defined through "read-only-columns" property is possible to select one o more columns of the read only rows as editable. The "readOnly" field is exposed in the report's json at Cell level.

### Configure security headers to embed page

To include a page of a DAC in an iframe it is necessary to configure the Content Security Policy of both DAC and the web application you want to use to include the pages of DAC.

See&#x20;

## Version 2021.2.2

### Deprecate JS API Function extCloseDialog(idDialog)

The JS API Function extCloseDialog(idDialog)&#x20;

### Configure visualization grants on Drill Through

Now it's possible to select wich user groups can view the drill through.

{% content-ref url="../documentation/run-time/report/" %}
[report](../documentation/run-time/report/)
{% endcontent-ref %}





{% hint style="info" %}
Please see the [Migration Notes](../change-log/untitled/version-2021.2.md)
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

{% content-ref url="../documentation/run-time/administration/languages-administrations.md" %}
[languages-administrations.md](../documentation/run-time/administration/languages-administrations.md)
{% endcontent-ref %}

### Application Synchronization On Web

Web synchronization compared to Design Studio allows you to connect via Run Time to the target application if it is not possible to connect to the Design Studio.

{% content-ref url="../documentation/run-time/administration/application-synchronization-wip.md" %}
[application-synchronization-wip.md](../documentation/run-time/administration/application-synchronization-wip.md)
{% endcontent-ref %}

### Filter User List

Now it’s possible to filter the user list by the Scope

{% content-ref url="../documentation/run-time/administration/users-administration.md" %}
[users-administration.md](../documentation/run-time/administration/users-administration.md)
{% endcontent-ref %}

### Administrator Switch

Users with scope "Users Administration" or "Tenans Administration" or "All Tenant" don't display the switch "Administrator" in the Detail tab of the user creation wizard and in the summary inforations.

{% content-ref url="../documentation/run-time/administration/users-administration.md" %}
[users-administration.md](../documentation/run-time/administration/users-administration.md)
{% endcontent-ref %}

### Dumbella on MSSql Server

Now Dumbella works on MSSQL Server

{% content-ref url="../installation-guides/dumbella-installation-guide.md" %}
[dumbella-installation-guide.md](../installation-guides/dumbella-installation-guide.md)
{% endcontent-ref %}

### Column definition on composite metric

Now the Data Type and visibility can be set for a composite metric.

### Tenant section

Improvements have been made to the tenant section of user administration

1. have been rename the button to "New Tenant"
2. Have been a new item called "All Users" which displays both tenant and non-tenant users.
3. The "no tenant" item have been renamed to "Users without tenant"
4. The Icons have been updated

{% content-ref url="../documentation/run-time/administration/tenant.md" %}
[tenant.md](../documentation/run-time/administration/tenant.md)
{% endcontent-ref %}

![](<../.gitbook/assets/image (292).png>)

### Enhancement in the list of user in the administration page

Now in the User Administration :

1. The default sorting of the list have be by name ascending&#x20;
2. The column “type” have removed&#x20;
3. The column “username” now is displayed in this list.&#x20;
4. Disabled users are highlighted in the interfaceUI,&#x20;
5. When the user is associated to many tenants, the user interface show only some Tenant.

{% content-ref url="../documentation/run-time/administration/users-administration.md" %}
[users-administration.md](../documentation/run-time/administration/users-administration.md)
{% endcontent-ref %}

### Refactoring of filters in the user management

{% content-ref url="../documentation/run-time/administration/users-administration.md" %}
[users-administration.md](../documentation/run-time/administration/users-administration.md)
{% endcontent-ref %}



