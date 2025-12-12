# Migration Notes

## Content Secure Policy

In version 2024.1.0, the CSP configuration for both Pages and App Composer services has been modified. Update the previous version's CSP to the new CSP as shown below.

{% tabs %}
{% tab title="Last version" %}
{% code overflow="wrap" %}
```yaml
csp:
  script-src: "'unsafe-inline' 'unsafe-eval' 'self' ;"
  img-src: "blob: data: https://*.openstreetmap.org 'unsafe-inline' 'unsafe-eval' 'self' ;"
  font-src: "data: https://fonts.gstatic.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"
  style-src: "https://fonts.googleapis.com/ https://maxcdn.bootstrapcdn.com https://getbootstrap.com/ 'self' 'unsafe-inline' ;"
  default-src: "https://widgethub.decisyon.com/ 'self';"
  frame-ancestors: "'self' ;"
  worker-src: "blob: 'self' ;"
  form-action: "'self' ;"
```
{% endcode %}
{% endtab %}

{% tab title="2024.1.0 " %}
```yaml
pages:
  application:
    security:
      csp:
        img_src: "blob: data: https://*.openstreetmap.org https://test.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"
        script_src: "'unsafe-inline' 'unsafe-eval' 'self' ;"
        font_src: "data: https://fonts.gstatic.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"
        style_src: "https://fonts.googleapis.com/ https://maxcdn.bootstrapcdn.com https://getbootstrap.com/ 'self' 'unsafe-inline' ;"
        frame_ancestors: "'self' ;"
        worker_src: "blob: 'self' ;"
        form_action: "'self' ;"
        default_src: "https://widgethub.decisyon.com/ 'self';"
        
appcomposer:
  application:
    security:
      csp:
        img_src: "blob: data: https://*.openstreetmap.org https://test.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"
        script_src: "'unsafe-inline' 'unsafe-eval' 'self' ;"
        font_src: "data: https://fonts.gstatic.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"
        style_src: "https://fonts.googleapis.com/ https://maxcdn.bootstrapcdn.com https://getbootstrap.com/ 'self' 'unsafe-inline' ;"
        frame_ancestors: "'self' ;"
        worker_src: "blob: 'self' ;"
        form_action: "'self' ;"
        default_src: "https://widgethub.decisyon.com/ 'self';"
```
{% endtab %}
{% endtabs %}

For more details, please consult the [Installation Guide](https://dac-documentation-1.gitbook.io/installation-guides/advanced-topics/content-secure-policy)



## Keycloak

Until version 2023.2.6, Keycloak was included in the HELM Chart of App Composer and was distributed by Decisyon INC. Starting from version 2024.1.0, Keycloak is no longer included in the HELM Chart of App Composer and will need to be deployed and managed externally and independently from App Composer, becoming a pre-requisites.

#### New installations:

* **Without an OIDC-compliant authentication system**: If you do not have an OIDC-compliant authentication service and you needs to use Keycloak, you need to deployed and configure it before installing App Composer, thus becoming a prerequisite.
* **With an OIDC-compliant identity provider**: If you already have an OIDC-compliant identity provider (such as Ping Identity, Auth0, Google, Okta, etc.), the HELM Chart of App Composer can be configured to use it.

#### Existing installations:

* **Without using Keycloak**: If your instance is not using Keycloak, there are no significant impacts. The HELM Chart parameters will need to be slightly modified.
* **With Keycloak**: If your instance is using Keycloak, the deployment needs to be modified following this procedure:
  1. Uninstall the HELM Chart of App Composer.
  2. Prepare the HELM Chart for Keycloak only, configuring it to point to the same database already used from the previous App Composer deployment.
  3. Deploy Keycloak with its HELM Chart.
  4. Deploy App Composer 2024.1.x with its helm.
  5. Execute non-regression test to ensure users are able to login and logout.

## Grant access to app developer on AppComposer

With the removal of the "User Administrator" page from the AppComposer service, you can now **whitelist** developers for login access to both **AppComposer** and **Cockpit**.&#x20;

Developers not on the whitelist will be unable to log in. For those whitelisted, user accounts are automatically created upon login if they do not already exist. Existing users with the "Administrator" scope are migrated automatically but starting from 2024.1.0 they must also be included in the whitelist

The whitelist is a new property that must be specified in the HELM chart for deploying AppComposer and Pages:

```yaml
global:
    authorization:
      whitelist:
        identifierClaim: preferred_username
        users: mrossi;ebianchi;jsmith
```

In the `identifierClaim` property, specify the identity provider claim used by AppComposer and Cockpit for authorization checks. For example, for Keycloak, the claim is `preferred_username`; for Google, it's `sub`, etc.

In the `users` property, list the claim values separated by `;`. For instance, if you authorize users based on their email, list the email addresses in this property, separated by `;`.&#x20;

{% hint style="warning" %}
Ensure there are no spaces between the values.
{% endhint %}

## From “Tenant” to “Organization”

To enhance App Composer multitenant architecture, we are renaming the current feature from "**tenant**" to "**organization**." This change eliminates confusion and more accurately describes the feature's true purpose: segregating data within each tenant.

The migration impact will affect the following functions:

* Tenants API exposed by DAC
* User API exposed by DAC
* System Parameters
* JavaScript API

### **Tenant API**

In version 2024.1.0, the "Tenants" management APIs endpoints have been renamed as "Organization".&#x20;

| Before 2024.1.0                   | Description                                 | After 2024.1.0                                 | Description                                      |
| --------------------------------- | ------------------------------------------- | ---------------------------------------------- | ------------------------------------------------ |
| `/api/v2/rest/tenants`            | Return all Tenants managed                  | /`api/v2/rest/organizations`                   | Return all Organization managed                  |
| `/api/v2/rest/tenants`            | Create a Tenants with the given information | `/api/v2/rest/organizations`                   | Create a Organization with the given information |
| `/api/v2/rest/tenant/{id}/rename` | Rename the Tenant with the given name       | `/api/v2/rest/organizations/{id}/rename`       | Rename the Organization with the given name      |
| `/api/v2/rest/tenant/default`     | Set a default Tenant                        | This API is no longer exposed in this version. |                                                  |
| `/api/v2/rest/tenant/{id}`        | Delete Tenant                               | `/api/v2/rest/organizations/{id}`              | Delete Organization                              |

{% hint style="warning" %}
When migrating from "tenants" to "organizations," developers need to pay close attention to the Swagger documentation. The Swagger contains APIs named "tenant" that are now specific to the multi-tenancy architecture.

One such API is:

**GET /api/v2/rest/tenants/{tenant}/users**

This API is now used in the multi-tenant architecture to return the list of all users within a specific tenant.
{% endhint %}

Below you can see an example of an HTTP request that returns the **Tenants** from the previous version and the corresponding **Organization** in the current version of the DAC.

Before 2024.1.0: `/api/v2/rest/tenants`

```http
GET /api/v2/rest/tenants HTTP/1.1
Host: <Host Name>
Authorization: bearer <token>
Accept: application/json
Content-Type: application/json
```

After 2024.1.0: /`api/v2/rest/organizations`

```http
GET /api/v2/rest/organizations HTTP/1.1
Host: <Host Name>
Authorization: bearer <token>
Accept: application/json
Content-Type: application/json
```

### User API - Request and response body

Due to the transition from "tenants" to "organizations," there have been updates to the JSON schema used by the User Management API, in example for creating a new user, for retrieving user information or for updating user information.&#x20;

Here are the key changes:

<table><thead><tr><th width="229">Before 2024.1.0</th><th width="215">After 2024.1.0</th><th>Description</th></tr></thead><tbody><tr><td><code>tenant</code></td><td><code>organization</code></td><td>This field has been renamed</td></tr><tr><td><code>scope</code></td><td><code>userScope</code></td><td>The original field that defines the user permissions and roles has now been renamed in "<code>userScope</code>". Its content has not been modified.</td></tr><tr><td><code>scope</code></td><td><code>scope</code> (Logo &#x26; Colors)</td><td>The field "scope" that was previously used to defined user permission and roles is now used to assign administrative about the "Logo&#x26;Colors"</td></tr></tbody></table>

The **tenant** group variable as been renamed to **Organization**.

| Before 2024.1.0                                                                                | After 2024.1.0                                                                   |
| ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| <p></p><p><img src="../../../.gitbook/assets/image (140).png" alt="" data-size="original"></p> | <img src="../../../.gitbook/assets/image (141).png" alt="" data-size="original"> |

The variables dedicated to assigning user scopes have undergone changes.&#x20;

* The **scope** has been renamed to **UserScope**.&#x20;
* The s**cope** variable is now used to assign administrative **grants for Logo & Colors.**&#x20;

The table below shows the association between the previous versions and version 2024.1.0.

| Before 2024.1.0                                                                                                                                                                                       | After 2024.1.0                                                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p></p><p><img src="../../../.gitbook/assets/image (2046).png" alt="" data-size="original"></p><p>In the previous versions you can configure the <strong>Scope</strong> associated with the user.</p> | <p></p><p><img src="../../../.gitbook/assets/image (2045).png" alt="" data-size="original"></p><p>In version 2024.1.0, you can configure the <strong>Scoope and UserScope</strong> associated with the user.</p> |

The values you can assigne in the `userScope` have not been modified. The field `scope` requires a new specific value.&#x20;

<table><thead><tr><th>Before 2024.1.0</th><th width="197">After 2024.1.0</th><th>Supported Values</th></tr></thead><tbody><tr><td>Scope</td><td>User Scope </td><td><p>U_ADMIN</p><p>T_ADMIN</p><p>ALL_T_ADMIN</p></td></tr><tr><td>--</td><td>Scope</td><td>TH_ADMIN</td></tr></tbody></table>

### **System Parameters**

System parameters for "Tenant" are now renamed to "Organization". Legacy variables remain available to minimize breaking changes for DAC 2024.1.0, but they are now deprecated and will be removed in a future version.

{% hint style="info" %}
It is strongly recommended to modify the variables immediately after deploying version 2024.1.0 to your development environment.
{% endhint %}

| Before 2024.1.0    | After 2024.1.0           |
| ------------------ | ------------------------ |
| `%CURRENT_TENANT%` | `%CURRENT_ORGANIZATION%` |
| `%TENANTS%`        | `%ORGANIZATIONS%`        |

### Javascript API

The Javascript object exposed by App Composer `DECISYON.userInfo` has been modified renaming "Tenants" in "Organization".

| Before 2024.1.0                     | After 2024.1.0                            |
| ----------------------------------- | ----------------------------------------- |
| `DECISYON.userInfo.currentTenantId` | `DECISYON.userInfo.currentOrganizationId` |

## **Document Repository data source settings**

The settings for specifying the Document Repository data source in Design Studio have been removed, and can now only be configured within the HELM chart.&#x20;

{% hint style="warning" %}
Failure to configure this property correctly may prevent the application from accessing static resources already uploaded to the document repository.
{% endhint %}

To successfully migrate the document repository settings, you must transfer the database connection parameters from the data source associated with the `storage-datasource` property into the corresponding fields now available in the HELM chart. For example, if your document repository is stored in the following database and schema:

<figure><img src="../../../.gitbook/assets/image (2043).png" alt=""><figcaption></figcaption></figure>

```yaml
Database Host: 10.0.40.211
Database Port: 5432
Database Name: appcomposer_db
Database Username: appcomposer_user
Database Password: U4wbEY9y@qxERs6M!
Database Schema: appcomposer_repo
```

You need now to configure the corresponding properties in the HELM chart, in example:&#x20;

```yaml
pages:
  application:
    tenantDocumentRepository: 
      datasource:
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_repo"
        schema: "appcomposer_repo"
        host: "10.0.40.211"
        port: "5432"
        database: "appcomposer_db"
        type: "POSTGRESQL"
    documentRepository:
      datasource:
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_repo"
        schema: "appcomposer_repo"
        host: "10.0.40.211"
        port: "5432"
        database: "appcomposer_db"
        type: "POSTGRESQL"
        
appcomposer:
  application:
    datasource:
      username: "appcomposer_user"
      password: "U4wbEY9y@qxERs6M!"
      url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_md"
    tenantDocumentRepository: 
      datasource:
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_repo"
        schema: "appcomposer_repo"
        host: "10.0.40.211"
        port: "5432"
        database: "appcomposer_db"
        type: "POSTGRESQL"
    documentRepository:
      datasource:
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_repo"
        schema: "appcomposer_repo"
        host: "10.0.40.211"
        port: "5432"
        database: "appcomposer_db"
        type: "POSTGRESQL"

tenant-md-installer:
  application:
    tenantDocumentRepository:
      datasource:
        schema: "appcomposer_repo"
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_repo"
```

The `tenant-md-installer` settings are necessary to create the appropriate schemas and tables; since these already exist, creation steps will be skipped. The configurations for "Pages" and "AppComposer" replace the previously configured properties in Design Studio.&#x20;

{% hint style="info" %}
Existing files in the document repository remain unchanged during this migration; only how App Composer and Pages retrieve files is being altered.
{% endhint %}

If your document repository is stored in the metadata schema, follow the same procedure, specifying the metadata schema name in the relevant property. To verify the success of migration, simply navigate through application pages; correct rendering indicates successful migration. Review the logs of both AppComposer and Pages services upon container start to ensure no exceptions are raised.

## Collaboration data source settings

The settings for specifying the collaboration data source in Design Studio have been removed, and can now only be configured within the HELM chart.&#x20;

{% hint style="warning" %}
Failure to configure this property correctly may prevent the application from loading discussion, tasks etc
{% endhint %}

To successfully migrate the collaboration data source you must transfer the database connection parameters from the data source associated with the `storage-datasource` property into the corresponding fields now available in the HELM chart. For example, if your collaboration data source is stored in the following database and schema:

<figure><img src="../../../.gitbook/assets/image (2044).png" alt=""><figcaption></figcaption></figure>

```yaml
Database Host: 10.0.40.211
Database Port: 5432
Database Name: appcomposer_db
Database Username: appcomposer_user
Database Password: U4wbEY9y@qxERs6M!
Database Schema: appcomposer_collab
```

You need now to configure the corresponding properties in the HELM chart, in example:&#x20;

```yaml
pages:
  application:
    collaboration:
      datasource:
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_collab"
        schema: "appcomposer_collab"
        host: "10.0.40.211"
        port: "5432"
        database: "appcomposer_db"
        type: "POSTGRESQL"
        
appcomposer:
  application:
    collaboration:
      datasource:
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_collab"
        schema: "appcomposer_collab"
        host: "10.0.40.211"
        port: "5432"
        database: "appcomposer_db"
        type: "POSTGRESQL"

tenant-md-installer:
  application:
    collaboration:
      datasource:
        schema: "appcomposer_collab"
        username: "appcomposer_user"
        password: "U4wbEY9y@qxERs6M!"
        url: "jdbc:postgresql://10.0.40.211:5432/appcomposer_db?currentSchema=appcomposer_collab"
```

The `tenant-md-installer` settings are necessary to create the appropriate schemas and tables; since these already exist, creation steps will be skipped. The configurations for "Pages" and "AppComposer" replace the previously configured properties in Design Studio.&#x20;

{% hint style="info" %}
Existing dicussion, tasks etc in the collaboration schema remain unchanged during this migration; only how App Composer and Pages retrieve them is being altered.
{% endhint %}

If your collaboration data source is stored in the metadata schema, follow the same procedure, specifying the metadata schema name in the relevant property. To verify the success of migration, simply open on a Page service a page that contains a "Discussion" widget; the visuaization of existing discussion and comments indicates successful migration. Review the logs of both AppComposer and Pages services upon container start to ensure no exceptions are raised.

## **Migrating from** Schedules Designer and Scheduler to **Action List and Schedule Action List**

The functionalities of the **Schedules Designer** and **Scheduler** in App Composer have been replaced by the new [**Action List**](../../../documentation/app-functionality/action-list/) feature which integrates scheduling and action management, allowing you to schedule and execute a series of actions together​. Follow the Migration Steps to ensure a smooth transition:

**Migration Steps for Replacing Schedules Designer and Scheduler with Action List and Schedule Action List**

<details>

<summary>Step 1. Identify the Configuration and Tasks implemented in the Scheduler and Schedules Designer functionalities</summary>

### 1. Locate Scheduler configuration <a href="#id-1.-locate-scheduler-configuration" id="id-1.-locate-scheduler-configuration"></a>

Open Design Studio, and navigate the **Scheduler** feature in the Application menu to identify the current tasks implemented. A scheduler can be associated with the following objects:

* Reports
* Rule
* Notifications
* DLR
* Code Snippet

In the following example, we have a Scheduler named “**Task Scheduler**”. This Scheduler is associated with:

* The object **Notification** “Check Materials” to send a Notification e-mail, created with the **Notification Designer** feature.
* The **Schedule** named “Every Day” is created with the **Schedules Designer** feature.

<img src="../../../.gitbook/assets/image (127).png" alt="" data-size="original">

### **2. Locate Schedules configuration**

Open the **Schedules Designer** in the Application menu and check the configuration for the scheduler applied in the **Scheduler** functionality.

In this example, the “Every Day” schedule configuration:

![](<../../../.gitbook/assets/image (129).png>)



</details>

<details>

<summary>Step 2. Replace Scheduler and Schedules with Action List and Schedule Action List</summary>

### 1. Create an Equivalent Scheduler using the new [Action List](../../../documentation/app-functionality/action-list/) feature <a href="#id-1.-create-an-equivalent-scheduler-using-the-new-action-list-feature" id="id-1.-create-an-equivalent-scheduler-using-the-new-action-list-feature"></a>

* Open the App Composer web application, and navigate the **Action list** feature in the **Administration** menu of the main sidebar.
* In the **Action list** page, select from the Action list menu the **Application** where your Scheduler configurations are located.

![](<../../../.gitbook/assets/image (130).png>)

* Click the **New** button to create a new Action list (equivalent to the older scheduler).
* In the **Create action list** dialog, enter the same name as the scheduler you are migrating. In this example“Task Scheduler”. Select the position in the Action list catalog to save the new Action list.
* Click **Create**.

![](<../../../.gitbook/assets/image (131).png>)

* Optionally, add a description to the Action List.

![](<../../../.gitbook/assets/image (132).png>)

* Add one or more **Actions** by selecting “**Click here to add a new action**”

![](<../../../.gitbook/assets/image (133).png>)

* In the **Create Action** dialog, select the type of object from the **Type** menu. For example, select **Notification** because the Scheduler being migrated is associated with a notification.
* In the **Actions** menu, select the object. For this example, select the notification object “Check Materials”.
* Click **Create** to associate the object.

![](<../../../.gitbook/assets/image (134).png>)

<img src="../../../.gitbook/assets/image (135).png" alt="" data-size="original">

### 2. Create Equivalent Schedules using the new [Schedule Action List](https://documentation.decisyon.com/documentation/app-functionality/action-list#schedule-action-list) feature <a href="#id-2.-create-equivalent-schedules-using-the-new-schedule-action-list-feature" id="id-2.-create-equivalent-schedules-using-the-new-schedule-action-list-feature"></a>

* Open the contextual menu from the kebab menu of the Action List.
* Click **Create Schedule**.

![](<../../../.gitbook/assets/image (136).png>)

* Copy the configuration of the schedules to be migrated (configured in the Schedules Designer), in this example “Every Day”:&#x20;

**Name:** Insert the name for the schedule. “Every Day”                                                                                                       **Description**: Optionally add a description (eg., “Schedule every day of the week”).                            **Start Date:** Select the start date and time when the schedule starts. “14/06/2024 15:30 Timezone Etc/UTC”                                                                                                                                                                   **End Date:** Set the end date and time when the schedule ends. “18/06/2025 15:30 Timezone Etc/UTC”                                                                                                                                                 **Every:** Define each time the schedule is repeated. The value is a numeric. In this example, we set “1” because the execution to migrate is repeated once.                                                             **Period:** Set the period of the execution. In this example, we set “Day” because the schedule is performed each day of the week.

* Click **Create** to create the schedule.

![](<../../../.gitbook/assets/image (137).png>)

* Enable the newly created schedule. By default, a schedule is disabled, and you need to manually enable it using the highlighted button in the figure.

![](<../../../.gitbook/assets/image (138).png>)

By following these steps, you will successfully migrate your existing Scheduler and Schedules configurations to the new **Action List** and Schedule **Action List** features.

![](<../../../.gitbook/assets/image (139).png>)

</details>

<details>

<summary>Step3. Test the Migration</summary>

Test that you successfully migrate your existing Scheduler and Schedules configurations to the new **Action List** and Schedule **Action List** features.

![](<../../../.gitbook/assets/image (139).png>)

</details>

## Migrating Widgets <a href="#id-1.-locate-scheduler-configuration" id="id-1.-locate-scheduler-configuration"></a>

The File Selector, Inner Container, and Image widgets have been removed. Their functionalities have been replaced by new, updated widgets:

* **File Selector:** Now handled by the File Upload.
* **Inner Container:** Replaced by the IFrame.
* **Image:** Work in Progress

## **From File Selector to File Upload Widget**

A new **File Upload** widget has been introduced, replacing the old **File Selector** widget. Since there is no automatic migration, please follow these steps to ensure a smooth transition:

\
**Step1.** **Locate and Replace**: Identify all pages using the old File Selector widget and replace it with the new File Upload widget.\
**Step2**. **Update Execution Buttons:** If you are using the `Excel Integration` feature, ensure the Execute Button widget is associated with the new File Upload widget.

{% hint style="info" %}
For detailed instructions, refer to the [File Upload](https://app.gitbook.com/s/oXkINxMLmQhdocA02ja1/documentation/file-upload-1.0/examples/e.2-replacing-the-file-selector-widget) documentation.
{% endhint %}

## **From** **Inner Container to the IFrame Widget**&#x20;

A new **IFrame** widget has been introduced, replacing the old **Inner Container** widget. Since there is no automatic migration, please follow these steps to ensure a smooth transition:&#x20;

**Locate and Replace**: Identify all pages using the old Inner Container widget and replace it with the new IFrame widget.

{% hint style="info" %}
For detailed instructions, refer to the [IFrame](https://app.gitbook.com/s/0yNonedRvjTDShHG025K/documentation/iframe-1.0/examples/e.2-replacing-the-inner-container-widget) documentation.
{% endhint %}

## **Ugrade widget version**

The following widgets must be updated to their latest versions from the [**Widget Hub**](https://widgethub.decisyon.com/):

* File Manager
* Button
* Checklist
* Hierarchical Checkbox
* Smart Grid

Please ensure these updates are applied to maintain compatibility and access new features.

