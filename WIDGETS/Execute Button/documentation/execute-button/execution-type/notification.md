# NOTIFICATION

## Overview

With this option it is possible to send a notification that has been previously defined using the **Notification designer** (**Application --> Notification designer**).&#x20;

Select the **NOTIFICATION** item in the **execution-type** property to enable the **notifications\*** property and associate one or more previously created notifications with the Execute button widget.

When notifications are executed, the parameters currently selected on the page can be used within the e-mail notifications to customize the content.&#x20;

It is possible to set dynamic mail recipients to the notification. If you define in the page a parameter called `%NOTIFICATION_RECEIVERS%` that contains the unique identifier of the user (also know as `subject_id` ) they will receive the mail notification.&#x20;

### Execution-type Properties

The properties that are specific for the configuration of the **Execution-type NOTIFCATION** are listed below:

<table><thead><tr><th width="275">Specific Properties</th><th width="252">Description</th><th width="133" align="center">Type</th><th width="148" align="center">Default Value</th><th width="358" data-type="checkbox">Allow Page Parameters</th><th data-hidden>Group</th></tr></thead><tbody><tr><td><strong>notifications*</strong></td><td>Select a notifications previously defined using the <strong>Notification designer</strong>.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr></tbody></table>

