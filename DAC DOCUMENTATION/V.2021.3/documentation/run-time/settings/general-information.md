# General Information

### Decisyon App Composer

The panel shows some summary information of the installed DAC. In this window you can retrieve the version of the DAC, the host etc.

![](<../../../.gitbook/assets/image (33).png>)

### App Composer Environment Variable

Environment variables defined at the operating system level can be used throughout the DAC.



![](<../../../.gitbook/assets/image (65).png>)

Some of the Decisyon object that could leverage this features:

* **Data sources:** to leverage JDBC string created as env variable.
* **REST client:** to leverage bearer token of external services or URL to external services
* **Page editor:** to leverage any environment variable as Decisyon variable
* **SMTP server:** to leverage SMTP parameters as environment variable.(host, user, port, password) of the SMTP server.
* it’s possible to use App Composer Environment Variables in specifying any connection settings (user, host, jdbc url,…) of a database-based data source

Environment variables can be created for all those objects that could change depending on the target environment. The change of target environment could occur during a migration for example from Test to Development or Production. In this way, taking advantage of the environment variables, it will not be necessary to change the values ​​in the destination.

The environment variables used by Design Studio will be created in the operating system where the DS is installed the same thing for the RunTime.

When creating an environment variable in the operating system, the name must start with the prefix DAC\_ENV. (for example _**%DAC\_ENV\_\<parameter>%**_ ). The Dac will only recognize environment variables with this prefix.

#### Summary schema of variables <a href="#summary-schema-of-variables" id="summary-schema-of-variables"></a>

* **SMTP :** the variable must be delimited by the **%** character e.g. %DAC\_ENV\_HOST% to be configured both on the O.S. where the DS is located and on the application server.
* **API rest:** the variable must be delimited by the **\{{ \}}** character e.g.\{{DAC\_ENV\_HOST \}} to be configured both on the O.S. where the DS is located and on the application server.
* **Datasource rest:** the variable must be delimited by the **\{{ \}}** character e.g.\{{DAC\_ENV\_HOST \}} to be configured both on the O.S. where the DS is located and on the application server.

It is possible to consult the list of system variables recognized by the DAC by accessing the "General information" panel "Environment variables of the app composer"

### Log

In the Log panel you can download the DSC logs.



![](<../../../.gitbook/assets/image (77).png>)

### Resources

The resources made available by the DAC are present in the resources panel. in this section it is possible to reset the Document Reporisory chache, Update the Static Resources and reset the System Labels

![](<../../../.gitbook/assets/image (11).png>)

