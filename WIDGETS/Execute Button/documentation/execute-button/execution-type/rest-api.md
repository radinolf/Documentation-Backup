# REST API

## Overview

This execution type allows you to execute a [REST Client API](https://documentation.decisyon.com/documentation/sdk-and-api/rest-api-client) previously created in App Composer. By choosing **REST\_API**  in the **execution-type** property, the following property is available for the configuration:

The **api-params-mapping** property allows you to map variables defined in the rest API client request with page parameters.

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Consult the following DAC documentation for further details on REST API:

[Widget Execute Button with REST API Client](https://documentation.decisyon.com/documentation/app-functionality/jobs#howtousedumbellaservice-executebuttonwidgetcanbeconfiguredtoexecuterest_api.)
{% endhint %}

### Execution-type Properties

The properties that are specific for the configuration of the **Execution-type REST\_API** are listed below:

<table><thead><tr><th width="275">Specific Properties</th><th width="252">Description</th><th width="133" align="center">Type</th><th width="148" align="center">Default Value</th><th width="358" data-type="checkbox">Allow Page Parameters</th><th data-hidden>Group</th></tr></thead><tbody><tr><td><strong>api-alias</strong></td><td>Select the <strong>API REST</strong> to execute.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>api-params-mapping</strong></td><td>Defines the mapping of the parameters used by the API REST with the parameters of the page.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr></tbody></table>

