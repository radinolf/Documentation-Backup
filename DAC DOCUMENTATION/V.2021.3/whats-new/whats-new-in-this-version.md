---
description: >-
  In this page are listed a small number of the most important updates and share
  them with you via What's New. For more details you can consult the Changelog
---

# What's New in this version

## Version 2021.3



### User Creation  <a href="#user-creation" id="user-creation"></a>

* In the dialog used to create a new user, a search field has been added to the tenant drop-down menu.
* In the user creation dialog, if the user already selected a tenant from the list on the left, the tenant menu be pre-selected on the same tenant, especially if the user only has 1 tenant associated. (See Users Administration for details)
* In the User Administration section, the edit of a user from Dx-Sidenav has been moved to the dialog box. See the figure.. (See [Users Administration](../documentation/run-time/administration/users-administration.md#create-new-user) for details)

![](<../.gitbook/assets/image (9).png>)

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

![](<../.gitbook/assets/image (88).png>)

A new column has been added to the widget catalog which shows the status of the published / unpublished widgets

![](<../.gitbook/assets/image (46).png>)

### Param sorting on Api-params-mapping <a href="#param-sorting-on-api-params-mapping" id="param-sorting-on-api-params-mapping"></a>

Now the list of parameter has be sorted ascending and case sensitive so that can easily find parameters by name.

### Refactoring and Simplification of Timezone settings <a href="#refactoring-and-simplification-of-timezone-settings" id="refactoring-and-simplification-of-timezone-settings"></a>

Creating a user (even by API) the timezone must be set.

Plese see the [Migration Notes](../migration-notes/untitled/version-2021.3/changes-and-migration-notes-of-version-2021.3.0.md#refactoring-and-simplification-of-timezone-settings)

&#x20;

### Tasks <a href="#tasks" id="tasks"></a>

In the Task Board and Task List, has been moved the Edit of task from Sidenav to Dialog.

![](<../.gitbook/assets/image (27).png>)

### **Langing Page** <a href="#langing-page" id="langing-page"></a>

In the landing page, move the edit of page and application from Sidenav to Dialog. The dialog is opened from the modify icon in the Page and Application card.

![](<../.gitbook/assets/image (39).png>)

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

![](<../.gitbook/assets/image (60).png>)

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

![](<../.gitbook/assets/image (172).png>)

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



