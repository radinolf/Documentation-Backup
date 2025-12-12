# Removals

## User Administration in App Composer <a href="#id-8.-web-alert-editor" id="id-8.-web-alert-editor"></a>

The User Administration page previously available in App Composer has been removed. Administrators will no longer be able to manage or view users directly from App Composer since user management is now delegated only to "Pages". Administrators who need access to App Composer must be added to the whitelist. Please refer to the corresponding [migration note](migration-notes.md#grant-access-to-app-developer-on-appcomposer).

## Web Alert Editor <a href="#id-8.-web-alert-editor" id="id-8.-web-alert-editor"></a>

The Web Alert feature and all associated references will no longer be usable. Web alerts will not be available anymore for business users. No alternative configuration is provided. Consider other methods for alerting users.

## Scheduler Object and Schedules <a href="#id-3.-scheduler-object-and-schedules" id="id-3.-scheduler-object-and-schedules"></a>

It will no longer be possible to use the Schedules Designer and Scheduler. Existing schedules will be removed and cease to function. Migrate to Action List and Schedule Action. Please view the[ Migration Notes](migration-notes.md#migrating-from-schedules-designer-and-scheduler-to-action-list-and-schedule-action-list) for details.

## Platform Deploy Wizard <a href="#id-4.-removal-of-platform-deploy-wizard" id="id-4.-removal-of-platform-deploy-wizard"></a>

It will no longer be possible to use the wizard to create the YAML file to deploy on Docker Compose. Docker Compose deployment are no longer supported. You need to use a Kubernetes cluster and you can leverage the HELM chart to deploy App Composer. Please view the [installation guide](https://dac-documentation-1.gitbook.io/installation-guides).&#x20;

## &#x20;Server & Services Editor <a href="#id-5.-removal-of-server-and-services-editor" id="id-5.-removal-of-server-and-services-editor"></a>

It will no longer be possible to use the “Server & Services” editor to define the services available in the cluster. Use the HELM chart to deploy App Composer. Please view the [installation guide](https://dac-documentation-1.gitbook.io/installation-guides).&#x20;

## Properties of Widget Execute Button <a href="#id-6.-properties-of-widget-execute-button" id="id-6.-properties-of-widget-execute-button"></a>

It will no longer be possible to use the properties `show-on` and `drill-through-grants` in the widget "Execute Button". These two properties never worked as expected and thus no migration impact is expected.

## Widget File Selector <a href="#id-7.-widget-file-selector" id="id-7.-widget-file-selector"></a>

The "File Selector" widget will no longer be available in the page designer. Pages that use the widget will display an error box. Migrate to the "[File Upload](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/oXkINxMLmQhdocA02ja1/)" widget.

## Widget Image <a href="#id-1.-widget-image" id="id-1.-widget-image"></a>

The "Image" widget will no longer be available in the page designer. Pages that use the widget will display an error box. Remove references to the "Image" widget in your pages and consider using alternative methods to display images.

## Widget Inner Container <a href="#id-2.-widget-inner-container" id="id-2.-widget-inner-container"></a>

The "Inner Container" widget will no longer be available in the page designer. Pages that use the widget will display an error box. Migrate to the "[IFrame](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/0yNonedRvjTDShHG025K/)" widget..

## REST API to set a Tenant as Default <a href="#id-8.-web-alert-editor" id="id-8.-web-alert-editor"></a>

The API to set a Tenant will no longer be available. No alternative configuration is provided. The business user can set its own default organization from the [User Profile page.](../../../documentation/user-management/user-profile-in-pages.md)

```
/api/v2/rest/tenant/default
```

## **Reset Users Passwords**

The "Reset Password" feature for users and administrator has been removed from the User Administration section in the "Pages" service. Password management is now delegated to the authentication provider. Users should follow the password reset procedures provided by their OIDC authentication provider.
