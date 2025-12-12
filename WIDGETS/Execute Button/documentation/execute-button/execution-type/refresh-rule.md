# REFRESH RULE

## Overview

{% hint style="warning" %}
Refresh rules have been deprecated in DAC 2023.0.0 in favor of "Action List". This action type will be removed in future version.&#x20;
{% endhint %}

With this execution type it is possible to execute a **Scheduler** object previously defined using the **Scheduler** designer (**Application --> Scheduler**). Then by selecting **REFRESH\_RULE** in the **execution-type** property, the **refresh\_rules\*** property is available for associating the scheduler defined using the **Scheduler** (**Application --> Scheduler**). The objects in the scheduler may use the parameters exported from the page.

### Execution-type Properties

The properties that are specific for the configuration of the **Execution-type REFRESH\_RULE** are listed below:

<table><thead><tr><th width="275">Specific Properties</th><th width="252">Description</th><th width="133" align="center">Type</th><th width="148" align="center">Default Value</th><th width="358" data-type="checkbox">Allow Page Parameters</th><th data-hidden>Group</th></tr></thead><tbody><tr><td><strong>refresh-rules*</strong></td><td>Select a scheduler previously defined using the <strong>Scheduler</strong> designer.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr></tbody></table>

