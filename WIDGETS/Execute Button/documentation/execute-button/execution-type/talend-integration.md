# TALEND INTEGRATION

## Overview

This execution type execute a job created on Talend, loaded as a resource in the **Resource catalog** (**Application --> Resource Catalog**) and later published as [**Job**](https://documentation.decisyon.com/documentation/app-functionality/jobs) in App Composer.&#x20;

Talend allows you to define a series of context variable that could be used during the execution of the job. These variables, which can be assigned a default value, define a "context". It is possible to select one of the context available in the job and to assign page parameters value to any context variable of the job.

Select **TALEND\_INTEGRATION** in the **execution-type** property and the following  properties are available for the configuration:

The **Input-params-context** property allows you to select the job's context that will be used during execution. You can select between the list of context extracted from the job or you can use a page variable, i.e. when you want to dynamically change the name of the job's context.&#x20;

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

The **Input-params-mapping** property shows you the list of available context variable defined in the job. You can bind page parameters to the job's context variable.

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Read the following DAC documentation for further details on Talend Job:

* [Jobs](https://documentation.decisyon.com/documentation/app-functionality/jobs)
* [Widget Execute button with Talend Integration](https://documentation.decisyon.com/documentation/app-functionality/jobs#howtousedumbellaservice-executethejobsinappcomposer-widgetexecutebuttonwithtalendintegration)
{% endhint %}

### Execution-type Properties

The properties that are specific for the configuration of the **Execution-type TALEND INTEGRATION** are listed below:

<table><thead><tr><th width="275">Specific Properties</th><th width="252">Description</th><th width="133" align="center">Type</th><th width="148" align="center">Default Value</th><th width="358" data-type="checkbox">Allow Page Parameters</th><th data-hidden>Group</th></tr></thead><tbody><tr><td><strong>job*</strong></td><td>Select a <strong>job</strong> previously published in the Job page.</td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>input-params-mapping</strong></td><td><p>Defines the value to assign to each context variable. The value could be</p><ul><li> <strong>&#x3C; Default></strong>:  to use the default value as defined in the job. </li><li><strong>One of the Page parameters:</strong> the context parameter will get the value of the selected page parameter</li></ul></td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr><tr><td><strong>input-params-context</strong></td><td>Allows you to select the context that will be used during the Job execution. </td><td align="center">SELECT</td><td align="center"></td><td>false</td><td></td></tr></tbody></table>

