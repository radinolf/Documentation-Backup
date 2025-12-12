# How to use the Environment Variable in the Data Source.

## Introduction

The example shows how to pass environment variables (DAC\_ENV) as configuration parameters of a data source.

### **Step 0 . Define DAC\_ENV in the  operating system where the Design Studio is installed.**

Open the system operating prompt where the Design Studio is installed, and execute the following commands to define the DAC\_ENV used in this example:

{% tabs %}
{% tab title="Windows Batch" %}
{% code title="Example for windows CMD" lineNumbers="true" fullWidth="true" %}
```batch
rem Set environment variables with specified values
setx DAC_ENV_DAC_DB_USERNAME "appcomposer_user"
setx DAC_ENV_DAC_DB_PASSWORD "P@ssw0rd!"
setx DAC_ENV_DAC_DB_HOST "localhost"
setx DAC_ENV_DAC_DB_NAME "appcomposer_db"
```
{% endcode %}
{% endtab %}

{% tab title="Power Shell" %}
{% code title="Powershell" lineNumbers="true" fullWidth="true" %}
```powershell
 # Set environment variables with specified values for the current Windows user
[Environment]::SetEnvironmentVariable("DAC_ENV_DAC_DB_USERNAME", "appcomposer_user", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_DAC_DB_PASSWORD", "P@ssw0rd!", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_DAC_DB_HOST", "localhost", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_DAC_DB_NAME", "appcomposer_db", [System.EnvironmentVariableTarget]::User)
```
{% endcode %}
{% endtab %}
{% endtabs %}

To ensure the variables are correctly set, open the Windows Environment Variable dialog:

{% code title="Batch / Power Shell" lineNumbers="true" %}
```batch
rundll32.exe sysdm.cpl,EditEnvironmentVariables
```
{% endcode %}

For more information please see the documentation:

{% embed url="https://documentation.decisyon.com/~/changes/4wz9mvgtaJqyX0kpwj3O/documentation/application/data-source/advanced-configurations-and-properties#using-dac-env-in-a-data-source" %}

{% hint style="warning" %}
The DAC\_ENV variable should also be defined on the **Helm Chart** of App Composer. Please see the documentation  of i[nstallation guide ](https://dac-documentation-1.gitbook.io/installation-guides/helm-chart/decisyon-appcomposer).
{% endhint %}

### **Step 1: App Composer environment variables**

Access DAC to view the environment variables configured on your DAC. In this example, we used environment variables to store the credentials for accessing the database.

<figure><img src="../../../../.gitbook/assets/image (1900).png" alt=""><figcaption></figcaption></figure>

The following values are stored in the variables configured for this example:

```
%DAC_ENV_DAC_DB_USERNAME%: "appcomposer_user"
%DAC_ENV_DAC_DB_PASSWORD%: "P@ssw0rd!"
%DAC_ENV_DAC_DB_HOST%:"localhost"
%DAC_ENV_DAC_DB_NAME%:"appcomposer_db"
```

{% hint style="danger" %}
In case the value of a DAC ENV has been modified when the Data Source editor is opend, to use the new value it is required to close and open again the editor.
{% endhint %}

### **Step 2: Creating Data Source**

Access your Design Studio, from the toolbar, select "Tools" >> "Data Source".

<figure><img src="../../../../.gitbook/assets/image (1933).png" alt=""><figcaption></figcaption></figure>

1. Select "New" to create new Data Source.
2. Select "PostgreSQL" as Database Type.
3. In the Database Connection, you can copy and paste the environment variable from the General Information Panel in the web application:
   1. The `%DAC_ENV_DAC_DB_USERNAME%` variable is used in the "Login" field
   2. The `%DAC_ENV_DAC_DB_PASSWORD%` variable is used in the "Password" field
   3. The `%DAC_ENV_DAC_DB_HOST%` variable is used in the "Server" field
   4. The `%DAC_ENV_DAC_DB_NAME%` variable is used in the "Database" field

{% hint style="info" %}
Remember that the names of the environment variables are case-sensitive. Therefore, it's necessary to write them exactly as listed in the 'General Information' panel. We recommend using the copy button next to each variable to avoid typing errors."
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (1934).png" alt=""><figcaption></figcaption></figure>

### **Step 3. Test Data Source Connection**

<figure><img src="../../../../.gitbook/assets/image (1903).png" alt=""><figcaption></figcaption></figure>

As the last step, execute the test connection by using the 'Test Connection' button. If the environment variables are configured correctly, the test connection is successful.
