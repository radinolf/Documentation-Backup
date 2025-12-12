# DAC Environment Variable

## **What are DAC Environment Variables (DAC ENV):** <a href="#what-are-dac-environment-variables-dac-env" id="what-are-dac-environment-variables-dac-env"></a>

DAC Environment Variables, commonly referred to as **DAC ENV**, are user-defined key-value pairs designed to store values that could be consumed by features and objects within an App Composer application.

Each DAC ENV is an environment variable uniquely identified by a name prefixed with "`DAC_ENV`." These variables are defined during the deployment of App Composer and can be referenced within the application using their assigned name. The actual value associated with a DAC ENV is dynamically retrieved from App Composer whenever it is referenced within the application logic.

DAC ENV significantly streamline the management of environment-specific configurations, such as transitioning between development and production environments. Instead of hard-coding environment-dependent values directly into the application, DAC ENV enables application developers to utilize placeholders within the application logic, which can be dynamically adjusted based on the deployment environment. The DAC ENV is configured at the DAC instance level. Once configured, they will be available and applicable to any application.

DAC ENV are supported in various components of App Composer:

* [Data Source](./#data-source)
* [Pages](./#pages)
* [REST API Client](./#rest-api-client)
* [Jobs](./#jobs)
* [SMTP](./#smtp-server)

## **Use Cases for DAC Environment Variables:**

Environment variables are particularly utilized in data sources, where they offer an efficient way to store connection parameters.

This approach proves especially useful when managing different environments such as testing, production, and development, allowing dynamically adapting connection settings based on the specific needs of each context.

For example, you could define an environment variable called `{{DAC_ENV_URL}}` containing the connection URL to your database. During the development phase, the URL might point to a local database, while in production, it might be configured to connect to a remote database. This makes the synchronization process between environments smoother and more manageable, allowing greater flexibility in managing data sources.

DAC ENVs are extensively used within the REST API Client, particularly for managing tokens within authorization headers and URL. This approach offers notable benefits for configuring APIs during synchronization across different environments. Consider a scenario where an application needs to migrate between three environments - Development, Test, and Production. By leveraging DAC ENV, URLs and Bearer tokens in API calls can dynamically adjust according to the environment without modifying the configuration of the REST API Client itself. The actual values used in the request are stored in DAC ENVs rather than within the REST API Client, ensuring seamless adaptability across various deployment environments.

<figure><img src="../../../.gitbook/assets/image (274).png" alt=""><figcaption></figcaption></figure>

Let’s see the example above:

* Environment variables are defined for each environment (DEV, TEST and PROD).
* The environment variables will all have the same name, in the example DAC\_ENV\_URL.
* Each environment variable will be set with the URL value of each environment in which it was created.
* The REST API Client will not change depending on the environment, but by using the environment variable \{{DAC\_ENV\_URL\}} the request will be executed with the value assigned in each environment to the variable DAC\_ENV\_URL.

Even within **page parameters**, environment variables can play a fundamental role. A use case is storing the name of a plant in a DAC ENV and using the variable as the pre-selection value for a page parameter. This way, if there are multiple environments, there will be no need for manual intervention to modify values after synchronization, making data management dynamic.

## **Creating DAC Environment Variables:**

The value of a DAC ENV variable is defined in the deployment HELM chart of App Composer. DevOps can easily view, modify or delete a DAC ENV without previous knowledge about App Composer or Design Studio.

Once the DAC ENV has been defined, App Developer can see the list of the available DAC ENV from the web page “Settings → General Info”:

<figure><img src="../../../.gitbook/assets/image (275).png" alt=""><figcaption></figcaption></figure>

App Developer are able to see the names of the DAC ENV and use them in the business logic of the application, but they are not able to create or to see the values of a DAC ENV.

### Helm Chart

In the HELM chart used to deploy App Composer, you can add DAC ENV in the group application.properties

Please note that they must be defined using the syntax DAC.ENV.\<name>

DAC ENV are always defined in the App Composer container.

```
application:
  properties:
    DAC.ENV.mail_smtp_server: smtp.example.com
    DAC.ENV.mail_port: 587
    DAC.ENV.mail_username:  user@example.com
    DAC.ENV.mail_password: 123abc
    DAC.ENV.mail_from: application@example.com
    DAC.ENV.mail_use_auth: 1
    DAC.ENV.parallel_job: 6
    DAC.ENV.dcy_url: http://appcomposer:8080
    DAC.ENV.dcy_token: AAAAAAAAAA
```

### Container Manager

Assuming you are using Rancher on K8S as container manager, you can modify the deployment to create a DAC ENV.

The first step is to stop the appcomposer container. Set the scale to 0

Now edit the deployment.

<figure><img src="../../../.gitbook/assets/image (276).png" alt=""><figcaption></figcaption></figure>

Now edit the deployment

<figure><img src="../../../.gitbook/assets/image (277).png" alt=""><figcaption></figcaption></figure>

Open the “Environment Variable” section and select “Add variable” to add a new variable.&#x20;

<figure><img src="../../../.gitbook/assets/image (278).png" alt=""><figcaption></figcaption></figure>

Select “Key/Value Pair” as type of environment variable and set the variable name. Remember that is must start with DAC\_ENV in upper case. Set also the value of the variable.



<figure><img src="../../../.gitbook/assets/image (280).png" alt=""><figcaption></figcaption></figure>

**Save** the configuration and set again the scale to 1. Wait the container to start and verify if the DAC ENV has been successfully created.



<figure><img src="../../../.gitbook/assets/image (281).png" alt=""><figcaption></figcaption></figure>

### **Design Studio**

DAC ENV can be used also in Design Studio and they need to be defined as environment variable of the operating system where it is executed. In example, any Microsoft Windows environment variables start starts with DAC\_ENV is recognized as a DAC ENV and could consumed in Design Studio.

In you used a DAC ENV in an App Composer object and the variable is not defined, an exception could be raised. In example, if you used a DAC ENV as hostname of the database in a Data Source but the DAC ENV is not defined in the operating system, an error is raised by Design Studio.



<figure><img src="../../../.gitbook/assets/image (282).png" alt=""><figcaption></figcaption></figure>

The name of environment variables must always start with **DAC\_ENV:** in example DAC\_ENV\_dac\_db\_usernam&#x65;**.**

Here some example on how to create DAC ENV in a Windows operating System.

{% tabs %}
{% tab title="Windows Batch" %}
Example for windows CMD

```
//Set environment variables with specified values
setx DAC_ENV_dac_db_username "appcomposer_user"
setx DAC_ENV_dac_db_password "P@ssw0rd!"
setx DAC_ENV_dac_db_host "localhost"
setx DAC_ENV_dac_db_name "appcomposer_db"
```
{% endtab %}

{% tab title="Power Shell" %}
```
# Set environment variables with specified values for the current Windows user
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_username", "appcomposer_user", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_password", "P@ssw0rd!", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_host", "localhost", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_dac_db_name", "appcomposer_db", [System.EnvironmentVariableTarget]::User)
```
{% endtab %}
{% endtabs %}

To ensure the variables are correctly set, open the Windows Environment Variable dialog:

Batch / Power Shell

```
rundll32.exe sysdm.cpl,EditEnvironmentVariables
```

<figure><img src="../../../.gitbook/assets/image (283).png" alt=""><figcaption></figcaption></figure>

When using the same Design Studio to connect to multiple environments like development and production, it's crucial to manage DAC ENV variables carefully. Ensure that when switching between environments, the corresponding DAC ENV values are updated to reflect the new connection. Failing to do so could lead to discrepancies, where Design Studio is logged into the development metadata, but queries are executed on the production environment due to outdated DAC ENV values.

## **Using DAC ENVs**

In the previous paragraph, we explored the DAC components that can utilize DAC ENV and the process of creating them. Now, let's explore how to leverage DAC ENV within these objects.

### SMTP Server

In the SMTP server configuration, it's possible to utilize DAC ENV to dynamically configure server properties, which is helpful in cases of synchronization between different environments and when the properties changes accordingly to the environment, i.e. when the username and/or password are different between a dev environment and a prod environment.

In the image below, the DAC ENVs has been passed to the host\_name but also other properties accept DAC ENVs, included username and password.

<figure><img src="../../../.gitbook/assets/image (284).png" alt=""><figcaption></figcaption></figure>

#### Data Source <a href="#data-source" id="data-source"></a>

In the Data Source is possible to use DAC ENVs to pass the value in the database connection parameters. This configuration allow a smarter managing of the connection when the application is synchronized with other environments, for example Test vs Prod.





<figure><img src="../../../.gitbook/assets/image (285).png" alt=""><figcaption></figcaption></figure>

### Rest API Client <a href="#rest-api-client" id="rest-api-client"></a>

The DAC ENVs can also be used to configure the REST API Client. In this case, you need to use DAC ENVs referring to them using the double brackets. They can be uses as part of the URL, in the header or in the request body.

`https://{{DAC_ENV_URL}}/application/<application_owner>/page/<page_id>/event/<event_name>`

<figure><img src="../../../.gitbook/assets/image (286).png" alt=""><figcaption></figcaption></figure>

### **Pages** <a href="#pages" id="pages"></a>

In the page designer is possible to use the DAC ENVs as pre-selection-values of the page parameters.

{% hint style="info" %}
Make sure you have created the corresponding DAC ENV also in your operating system, otherwise they will not be displayed in the dropdown list.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (287).png" alt=""><figcaption></figcaption></figure>



### JOBS <a href="#jobs" id="jobs"></a>

In Jobs page, when the job is configures as a services, it is possible to associate a DAC ENV as context parameters.

For more details please see the [documentation](https://documentation.decisyon.com/documentation/app-functionality/jobs).

<figure><img src="../../../.gitbook/assets/image (288).png" alt=""><figcaption></figcaption></figure>
