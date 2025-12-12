# Migration notes

## Migration of new File Upload when the execute button is configured as Excel Integration

A new **File Upload** widget has been released, replacing the old **File Selector** widget. Since there is no automatic migration from the old widget to the new one, proceed as follows:

1. Access the pages where the old **File Selector** widget is used and replace it with the new **File Upload** widget.
2. If you use an **Execution Button widget**  as **file integration,** you will need to associate the new **File Upload** widget with the **Execution Button**.

Please refer to the[ ](../../../documentation/widgets/widget-catalog.md#widgets-contextual-menu)[File Upload](https://widgets.decisyon.com/file-upload-1.0/documentation/file-upload-1.0) documentation for more details.

## Add Data Type of type HTML to the columns-definition of the Report Properties

From the **Column-definition** property of the **Report** properties you can now select the "**HTML**" datatype. This allows you to define a column that interprets any HTML, JavaScript or CSS available in the content.

<figure><img src="../../../.gitbook/assets/image (373).png" alt=""><figcaption></figcaption></figure>

If the cells of the Smart Grid (or any other widget) contains HTML, JavaScript or CSS codes, as in the figure, after migrating to version 2023.2.2 the code will not be interpreted anymore. App Developer must manually change the column-definition in the report's property to allow the widget to interpret again the code.

In the image below, you can see how the column that originally contained HTML code appears after the migration, without modifying the data type. It's important to note that, unlike the previous scenario, the HTML code is no longer interpreted as HTML but rather as plain text.

<figure><img src="../../../.gitbook/assets/image (385).png" alt=""><figcaption></figcaption></figure>

## Impossible to logout if user is disabled or exception is raised on user creation

In the scenario for which there is an issue preventing the user from logging in e.g., when their account is disabled or when there is an exception during user creation, the user is unable to disconnect their account because the disconnect button is available only after a successful login.

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

During the migration process, it is necessary to modify the content of the `logoutEndpoint` variable in the [**Values.yaml.**](https://dac-documentation-1.gitbook.io/installation-guides/helm-chart/decisyon-appcomposer#values.yaml) file of Helm Chart.  The `redirect_uri` must be removed from the property otherwise logout will not work.

Before:

`logoutEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/logout?redirect_uri=%LOGOUT_REDIRECT_URI%"`

After:

`logoutEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/logout"`

The string `?redirect_uri=%LOGOUT_REDIRECT_URI%` has been removed

## Remove Keycloak's properties from its Helm Chart

The following properties can be removed from Keycloak Helm Chart’s value.yaml because are now obsolete:

* `CACHE_OWNERS_AUTH_SESSIONS_COUNT`
* `CACHE_OWNERS_COUNT`
* `JGROUPS_DISCOVERY_PROPERTIES`
* `JGROUPS_DISCOVERY_PROTOCOL`

###

