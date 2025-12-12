# How to use Dumbella service

## Introduction: What is Dumbella



Dumbella is a service in the stack of "App Composer" and its role is to execute ETL / Data Integration jobs built with Talend. It exposes REST API to execute and manage the jobs. Jobs are executed assigning values to context and context variables of the job in the body of the request. Thanks to the integration of Talend Studio Data Integration services with the AppComposer, you have the possibility to manage Talend Jobs resources in terms of updating, deleting and publishing.

### Architecture <a href="#architecture" id="architecture"></a>

Dumbella is a service specific to the Decisyon Inc. and is built and maintained by the Decisyon Inc. team. It requires its own database/schema to do its job. Communication between App Composer  and Dumbella takes place using the REST API. A job exported from Talend can be uploaded, published, executed, upgraded and deleted from App Composer user interface.&#x20;

Dumbella requires a **persistent storage volume** and the guarantee is granted by the token seed. The Dumbella service does not have a user interface and the requests can be executed by external applications or users directly on Dumella or via App Composer. Within the K8S service, Dumbella must be exposed to be accessible from outside the cluster. Process execution can be activated via REST API and Job execution can be triggered via **synchronous** mode.&#x20;

<figure><img src="../../../../.gitbook/assets/image (590).png" alt=""><figcaption></figcaption></figure>

The Swagger is available on \<DAC URL>/swagger-ui/index.html.  Dumbella has its own service log and has a native health check.

Dumbella’s schema has few tables. The Job execution are logged in a table.

<figure><img src="../../../../.gitbook/assets/image (570).png" alt=""><figcaption></figcaption></figure>

Dumbella's audit table IS NOT THE SAME of Talend.

<figure><img src="../../../../.gitbook/assets/image (714).png" alt=""><figcaption></figcaption></figure>

&#x20;The App Composer manage Dumbella operation using a Dedicated UI.&#x20;

&#x20;

<figure><img src="../../../../.gitbook/assets/image (540).png" alt=""><figcaption></figcaption></figure>

The .zip file of the job exported from Talend Studio must be uploaded in the resource catalog of DAC.When the job is published from the UI, the .zip file is copied from the resource to the persistent volume and expanded. Dumbella executes the .sh file of the job.Dumbella “wraps” the execution in a REST API.&#x20;

{% hint style="danger" %}
Do not change the name of the .zip file before uploading in the App Composer.&#x20;
{% endhint %}

{% hint style="danger" %}
App Composer manage Dumbella operation using a Dedicated UI. The link to UI ( **Administrations>> Jobs** ) is available only if services configuration in the stack is correct.&#x20;

Please see the [Dumbella Installation Guide. ](/broken/pages/-MfX1AzFu9mGKdBq5FLp)


{% endhint %}

## Managing JOBS

Now let's see how to manage Dumbella's Jods inside the App Composer .

### Uploading

All available jobs built with Talend are visible in the **APP COMPOSER** **Administration >>Jobs section**.

<figure><img src="../../../../.gitbook/assets/image (726).png" alt=""><figcaption></figcaption></figure>

Jobs must be previously uploaded in the Resource catalogue.

<figure><img src="../../../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

### Publishing

All Jobs available in the Jobs section must be published before using them.To publish a job, click on three dots icon and run the “Publish” command.Published job is displayed with the icon  ![](<../../../../.gitbook/assets/image (66).png>)in the “Status” column.

<figure><img src="../../../../.gitbook/assets/image (716).png" alt=""><figcaption></figcaption></figure>

### Unpublishing

All published Jobs can be unpublished.To unpublish a job, click on three dots icon and run the “Unpublish” command.Unpublished are not delete from App Composer resource catalog.

<figure><img src="../../../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Unpublished jobs cannot be run
{% endhint %}

### Deleting

When a job is deleted, the JOB id is lost and thus all the requests on that job will raise and error.

If a job is published, you have to delete the job from the Resource catalog and then click on three dots icon and run the “**Remove**” command. If a job is not published, you have to delete the job from the Resource catalogue but no action is required on the App Composer, refreshing the Jobs section will automatically remove all deleted jobs.

For more details please see this page:

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}



## Executing jobs

Now let's see how to do execute the Jobs in App Composer.

"Dumbella" service exposes APIs to manage jobs. You can test API using App Composer REST API Client, Postman, cURL or any other HTTP Client.

<figure><img src="../../../../.gitbook/assets/image (107).png" alt=""><figcaption></figcaption></figure>

In the **body** of the request you can select the job’s context and assign values to the context using JSON.The “**jobContext**” and “**jobParams**” keys must be used to pass values when executing the job.You can use only the "jobContext" key or only the jobParams key or both, it depends on the use cases.

<figure><img src="../../../../.gitbook/assets/image (556).png" alt=""><figcaption></figcaption></figure>

### Execute the jobs passing context and context params

It’s possible to execute a job by sending the execution Context and Context Params in the body of the Rest API Request. Context and Context Params can be:

* Static
* Dynamic

<figure><img src="../../../../.gitbook/assets/image (721).png" alt=""><figcaption></figcaption></figure>

Variable values use the \{{ **mustache** \}} notation.

Those \{{params\}} elements can be associated with the parameters defined in the App Composer  page.

<figure><img src="../../../../.gitbook/assets/image (542).png" alt=""><figcaption></figcaption></figure>

### Execute the jobs in App Composer REST API Client <a href="#execute-the-jobs-in-dac-rest-api-client" id="execute-the-jobs-in-dac-rest-api-client"></a>

In the **Jobs** page, the “**Url**” button shows the **relative** path used to run the selected job.

<figure><img src="../../../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

You can configure your request coping the relative path and using POST method. Then you can configure the Headers and the Body of the request.In the header you need to configure the Authorization using the bearer token.&#x20;

For more datails please see the document

{% content-ref url="../rest-api-client.md" %}
[rest-api-client.md](../rest-api-client.md)
{% endcontent-ref %}

### Execute the jobs in App Composer - Widget Execute button with Talend Integration

Execute button widget can be configured to execute Talend Integration.

The Input-params-context property allows you to set the context that will be used during execution. You can choose between page parameters or job contexts (list of available contexts name defined in the job)

<figure><img src="../../../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

The Input-params-mapping property shows you the list of available context variable defined in the Talend job. You can bind page parameters to job's context variable.

<figure><img src="../../../../.gitbook/assets/image (568).png" alt=""><figcaption></figcaption></figure>

### Execute button widget can be configured to execute REST\_API.

The api-params-mapping property allows you to map variables defined in the rest api client request with pre-selection parameters or parameter defined in the page itself.

<figure><img src="../../../../.gitbook/assets/image (580).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (593).png" alt=""><figcaption></figcaption></figure>

### Logs and output&#x20;

Execution logs can be analyzed using the Dumbella service logs from the hosting environment.

<figure><img src="../../../../.gitbook/assets/image (578).png" alt=""><figcaption></figcaption></figure>

Adding query string parameter “output=true” the console output of the log will be displayed both in the response body and in the service log.

<figure><img src="../../../../.gitbook/assets/image (100).png" alt=""><figcaption></figcaption></figure>

Adding query string parameter “output=true” the console output of the log will be displayed both in the response bod and in the service log.

<figure><img src="../../../../.gitbook/assets/image (574).png" alt=""><figcaption></figcaption></figure>

##

### Sequential vs parallel execution

By default, the job is configured as sequential execution it means that if another instance of the same job is already running, the next instance must wait the previous one before starting.&#x20;

<figure><img src="../../../../.gitbook/assets/image (334).png" alt=""><figcaption></figcaption></figure>

You can configure job for parallel execution: more than one job instance can be execute.

<figure><img src="../../../../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>



{% hint style="danger" %}
&#x20;Parallel execution could be resource consuming if not well designed
{% endhint %}

When working with parallel executions, be careful about files that could be locked from the jobs (i.e. excel files or other): the first execution could lock the file and the second execution could be affected by this lock. Make sure to design the jobs such in a way that they can really work in parallel.

<figure><img src="../../../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

### Organizing contexts to leverage App Composer and Dumbella

There are several ways to manage contexts leveraging App Composer and Dumbella capabilities, each of which with advantages and disadvantages.

* [One context per environment using App Composer environment variable](how-to-use-dumbella-service.md#one-context-per-environment-using-dac-environment-variable)
* [Single context passing App Composer environment variable](how-to-use-dumbella-service.md#single-context-passing-dac-environment-variable)
* [Single context passing Dumbella environment variable](how-to-use-dumbella-service.md#single-context-passing-dumbella-environment-variable)
* [Context variables loaded from database table](how-to-use-dumbella-service.md#context-variables-loaded-from-database-table)

#### One context per environment using App Composer environment variable

In the Talend job, you define one context per environment, will all its context variables.

<figure><img src="../../../../.gitbook/assets/image (547).png" alt=""><figcaption></figcaption></figure>

In App Composer  you define and environment variable with the name of the context to be applied in that environment.

<figure><img src="../../../../.gitbook/assets/image (559).png" alt=""><figcaption></figcaption></figure>

When creating the JOB request using App Composer  REST Client, use theApp Composer Env variable to pass the context name.

<figure><img src="../../../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

For more details on environment variables see:

{% content-ref url="../../settings/general-information.md" %}
[general-information.md](../../settings/general-information.md)
{% endcontent-ref %}

When using the job from a page, capture the App Composer  Env variable in a parameter and pass it to the “Execute object” widget.



| Advantages                                         |                    Disadvantages                   |
| -------------------------------------------------- | :------------------------------------------------: |
| ![](<../../../../.gitbook/assets/image (345).png>) | ![](<../../../../.gitbook/assets/image (554).png>) |

####

#### Single context passing App Composer environment variable

In the Talend job, you define only one context, the “default” one, with all its context variables

In App Composer you define an environment variable for each context variables you need to pass accordingly to the environment.

<figure><img src="../../../../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

When creating the JOB request using App Composer REST Client, use the App Composer Env variable to pass the value to each context variables.

<figure><img src="../../../../.gitbook/assets/image (577).png" alt=""><figcaption></figcaption></figure>

When using the job from a page, capture each App Composer Env variable corresponding to a context variable in a parameter and pass it to the “Execute object” widget.When using the job from a page, capture each App Composer  Env variable corresponding to a context variable in a parameter and pass it to the “Execute object” widget.



| Advantages                                         |                    Disadvantages                   |
| -------------------------------------------------- | :------------------------------------------------: |
| ![](<../../../../.gitbook/assets/image (584).png>) | ![](<../../../../.gitbook/assets/image (562).png>) |

#### Single context passing Dumbella environment variable

When creating the JOB request using App Composer REST Client, you don't need to assign context variable.

When using the job from a page you don’t need to assign context variables.

The job will read them from the environment variables of Dumbella.

Talend Java components allows you to capture env variables during execution.

<figure><img src="../../../../.gitbook/assets/image (544).png" alt=""><figcaption></figcaption></figure>



| Advantages                                         |                    Disadvantages                   |
| -------------------------------------------------- | :------------------------------------------------: |
| ![](<../../../../.gitbook/assets/image (566).png>) | ![](<../../../../.gitbook/assets/image (576).png>) |

#### Context variables loaded from database table

In the database, you can create a table that has all the context variables and their name. In the Talend job, you define only one context, the “default” one.The job is designed to load variables from the table. In App Composer Dumbella you need to configure only the connection string to the database since it changes by environment.



| Advantages                                         |                    Disadvantages                   |
| -------------------------------------------------- | :------------------------------------------------: |
| ![](<../../../../.gitbook/assets/image (543).png>) | ![](<../../../../.gitbook/assets/image (565).png>) |

###

