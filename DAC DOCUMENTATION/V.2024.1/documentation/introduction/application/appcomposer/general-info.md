# General Info

## General Information

#### Decisyon App Composer <a href="#decisyon-app-composer" id="decisyon-app-composer"></a>

The panel shows some summary information of the installed DAC. In this window you can retrieve the version of the DAC, the host etc.

<figure><img src="https://1992103909-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F3JNq3GxgX3RMIli5oPz8%2Fuploads%2FuN35cBE7mjxFzH8RQs25%2Fimage.png?alt=media&#x26;token=f53a5a06-b18b-4244-bd0a-c17abc85fbcc" alt=""><figcaption></figcaption></figure>

#### App Composer Environment Variable <a href="#app-composer-environment-variable" id="app-composer-environment-variable"></a>

Environment variables defined at the operating system level can be used throughout the DAC.​Some of the Decisyon object that could leverage this features:

<figure><img src="../../../../.gitbook/assets/image (1950).png" alt=""><figcaption></figcaption></figure>

* **Data sources:** to leverage JDBC string created as env variable.
* **REST client:** to leverage bearer token of external services or URL to external services
* **Page editor:** to leverage any environment variable as Decisyon variable
* **SMTP server:** to leverage SMTP parameters as environment variable.(host, user, port, password) of the SMTP server.
* it’s possible to use App Composer Environment Variables in specifying any connection settings (user, host, jdbc url,…) of a database-based data source

Environment variables can be created for all those objects that could change depending on the target environment. The change of target environment could occur during a migration for example from Test to Development or Production. In this way, taking advantage of the environment variables, it will not be necessary to change the values ​​in the destination.The environment variables used by Design Studio will be created in the operating system where the DS is installed the same thing for the RunTime.When creating an environment variable in the operating system, the name must start with the prefix DAC\_ENV. (for example _**%DAC\_ENV\_\<parameter>%**_ ). The Dac will only recognize environment variables with this prefix.It s necessary to add environment variable also on DAC-DS Operative Sytem to use variable on DAC-DS.It is very important to point out that the environment variables have a different syntax depending where are declared:

* as OS system variables (linux export command, for example): DAC\_ENV\_VAR\_ONE=value
* as Docker Compose environment variables: DAC\_ENV\_VAR\_ONE=value
* as Cornelius env properties: dac.env.var.one=value
* as K8S configMap item: dac.env.var.one=value Anyway, such variables will alway been referenced as %DAC\_ENV\_VAR\_ONE% (case insensitive) with the App Com

**Summary schema of variables**

* **SMTP :** the variable must be delimited by the **%** character e.g. %DAC\_ENV\_HOST% to be configured both on the O.S. where the DS is located and on the application server.
* **API rest:** the variable must be delimited by the **\{{ \}}** character e.g.\{{DAC\_ENV\_HOST \}} to be configured both on the O.S. where the DS is located and on the application server.
* **Datasource rest:** the variable must be delimited by the **\{{ \}}** character e.g.\{{DAC\_ENV\_HOST \}} to be configured both on the O.S. where the DS is located and on the application server.

It is possible to consult the list of system variables recognized by the DAC by accessing the "General information" panel "Environment variables of the app composer"

#### Log <a href="#log" id="log"></a>

In the Log panel you can download the RunTime logs.​

<figure><img src="https://1992103909-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F3JNq3GxgX3RMIli5oPz8%2Fuploads%2FJ7GG5BvGrqgdE6Agq5Mp%2Fimage.png?alt=media&#x26;token=f2d9dc12-c616-413f-a0b9-4c88d6c75098" alt=""><figcaption></figcaption></figure>

For more details see  [logs.md](../../../instance-configuration/logs.md "mention")

#### Resources <a href="#resources" id="resources"></a>

The resources made available by the DAC are present in the resources panel. in this section it is possible to reset the Document Reporisory chache, Update the Static Resources and reset the System Labels

<figure><img src="https://1992103909-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F3JNq3GxgX3RMIli5oPz8%2Fuploads%2FX87piGnzrysxRPoXMNOV%2Fimage.png?alt=media&#x26;token=b5de69e1-e3f3-4be4-8052-a8d45222a14d" alt=""><figcaption></figcaption></figure>

#### Activation Key <a href="#activation-key" id="activation-key"></a>

You can download the Design Studio installer from RunTime. You need to have an active user account in DAC with “administrator” grant in order to download the installer. If you don’t have it, please ask to your system administrator.The installation of the design studio is performed through a wizard. The installer can be executed on Windows. The installer automatically deploy the required OpenJDK to run Design Studio, ignoring any other java version already used by the client. When Design Studio is installed, each version will have its own folder in the O.S.Please see the documentation [Design Studio Installer](https://documentation.decisyon.com/v/documentation-version-2022.2/documentation/design-studio/design-studio-installer).

<figure><img src="https://1992103909-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F3JNq3GxgX3RMIli5oPz8%2Fuploads%2F0UZgug6nBmU9DxN0kEYH%2Fimage.png?alt=media&#x26;token=7948c9ad-2f18-412b-af9f-cb4b846fba6a" alt=""><figcaption></figcaption></figure>
