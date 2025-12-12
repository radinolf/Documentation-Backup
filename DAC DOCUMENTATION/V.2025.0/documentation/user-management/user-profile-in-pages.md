# User Profile in Pages

## Introduction

The **Profile** page within Pages provides easy access to essential user account features and options that experience and usability when navigating the application. By clicking the profile picture in the Main toolbar, you can access the following sections:

<figure><img src="../../.gitbook/assets/image (2234).png" alt=""><figcaption></figcaption></figure>

* [**User Profile**](user-profile-in-pages.md#user-profile)**:** To view and edit your personal information and preferences.
* [Application settings](user-profile-in-pages.md#application-settings)**:** to customize the application theme.
* [**Terms of use/Privacy Policy**](user-profile-in-pages.md#terms-of-use-privacy-policy)**:** To review the terms of use and privacy policy&#x20;
* [**Logout**](user-profile-in-pages.md#logout)**:**  to logout and disconnect from the application.&#x20;

## User Profile

On the **User** **Profile** page, any user can modify some of their personal information and settings.

{% hint style="info" %}
Please note that this is a built-in page and can not be modified by administrators or application developers.
{% endhint %}

To access your profile, click the profile picture in the Main Sidebar and choose **User Profile**.

<figure><img src="../../.gitbook/assets/image (68).png" alt="" width="277"><figcaption></figcaption></figure>

The page has the following sections:

* [**General information**](user-profile-in-pages.md#general-information)**:** View personal information and profile picture management.
* [**Settings**](user-profile-in-pages.md#settings)**:** Customize account settings related to location and default preferences.
* [**Scopes and Groups**](user-profile-in-pages.md#scopes-and-groups): Display scopes and groups associated with your user account.
* [**Security**](user-profile-in-pages.md#security): Manage security settings, including token management for authorized actions.

### General Information

In this section, you can view personal information and edit your profile picture:

<figure><img src="../../.gitbook/assets/image (2179).png" alt=""><figcaption></figcaption></figure>

User information such as **First Name**, **Last Name**, **Username**, and **Email** cannot be modified by the user as they are automatically inherited from the identify provider associated to App Composer. I.e., if App Composer is associated to "Google" as identity provider, this information are copied from Google.

It is possible to customize your profile by uploading a new picture, or changing or removing the existing one. The profile picture can be configured independently, allowing you to personalize your visual representation within the application, in example in widgets or other pages.

<figure><img src="../../.gitbook/assets/image (2181).png" alt=""><figcaption></figcaption></figure>

### Settings

In this section, you can customize account settings related to location and default preferences:

<figure><img src="../../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure>

### **Location**

* **Language:** Select from a list of configured languages.&#x20;

The language can be chosen only from those configured by the application developer for the instance. Language selection affects built-in labels in the user interface and any multilanguage labels defined by the application developer.

* **Locate me:** Enable to detect your time zone automatically.&#x20;

When enabled, pages will use your browser information to automatically determine your timezone. This allows timestamps to be adjusted to your timezone. App developers can also use this information to adjust application data to match your defined timezone.

* **Timezone:** Manully select your time zone.&#x20;

If you don't use the "Locate me" option, you can manually select your time zone. The selected time zone will apply to all time-sensitive information within the application, including event times, message timestamps, and scheduled notifications.

{% hint style="warning" %}
Changes to the time zone will take effect after you log out and log in again
{% endhint %}

{% hint style="info" %}
For more details, refer to [Multilanguage and localization](../instance-configuration/multilanguage-and-localization/)&#x20;
{% endhint %}

### **Default**

In this section you can select some "defaults" that will be applied to your account.

* **Default application:** Set the default application to access upon login.
* **Default organization:** Set the default organization to access upon login.
* **E-mail notification:** Enable email notifications for task mentions, discussions, and configured alerts. When disabled, you will not receive any email from the application.

### Scopes and Groups

In this section, you can display the **scopes** and **groups** associated with your user account, which control access and permissions within the applications. This information is read-only, and you cannot modify it from here. Only a user with the appropriate scope can change this information about another user from the [User Management](user-administration/) section, maintaining strict control over access permissions and ensuring application security.

<figure><img src="../../.gitbook/assets/image (2199).png" alt=""><figcaption></figcaption></figure>

### Security

In this section, you can generate and manage the Bearer Token created from your account. The bearer token are useful in case you need to consume APIs exposed by the App Composer services.&#x20;

<figure><img src="../../.gitbook/assets/image (2202).png" alt=""><figcaption></figcaption></figure>

Each token includes a description, creation date, optional expiration date, selected scopes, and status. You can delete the token using the dedicated icon.

The **"Generate Token"** button creates a new token. You must enter a mandatory description and an optional expiration date. Once expired, the token becomes invalid, and any request using it will receive an HTTP 401 response status code.

<figure><img src="../../.gitbook/assets/image (2170).png" alt="" width="563"><figcaption></figcaption></figure>

In the **Scopes**, you can select the scope of the token:

* **Login into DAC:** Generate a token that authorizes access to Pages and App Composer user interface. This scope must be selected for actions such as accessing pages via external links, embedding a DAC page in another application, or deploying or deleting an application.
*   **Manage token:** Generate a token that can be used to verify the validity of another token.  For example, using this token, you can invoke the REST API endpoint `.../api/v2/rest/check_token` to determine if another token is active and to whom it&#x20;

    belongs.

    <figure><img src="../../.gitbook/assets/image (2173).png" alt=""><figcaption></figcaption></figure>

    <div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>Refer to <a href="../sdk-and-api/app-composer-rest-api/authentication.md">Authorization Tokens</a> for more details.</p></div>

## Application settings

In the Application Settings page, you can customize your application's theme. By default, the application comes with preset colors, but these can be customized to suit your specific style preferences.

{% hint style="info" %}
Application Settings are enabled only if the connected user has the 'Theme Administrator' role. For more details, see [User Scope](user-administration/users-scope-and-scope.md)
{% endhint %}

<figure><img src="../../.gitbook/assets/image (2235).png" alt=""><figcaption></figcaption></figure>

The customization of the application allows to:

* **Logo**: Upload your application's primary logo for brand representation.
* **Compact Logo:** Upload a condensed version of your logo for smaller screens.
* &#x20;**Primary Color/Secondary Color**:
  * **Primary Color**: Applied to toolbars and areas where the section title is displayed. It serves as the dominant color in the user interface.
  * **Secondary Color**: Used to highlight selected items, such as menu highlights and active components. It helps draw attention to specific elements in the interface.

After making changes to the settings, you can use the **live preview** feature to see how the modifications will appear in real-time, allowing you to review the application's look before confirming and saving the changes.

<figure><img src="../../.gitbook/assets/image (2238).png" alt=""><figcaption></figcaption></figure>

The **'Reset Default**' button allows for resetting the chosen theme and appears only when the settings have been changed. This feature enables reverting to the initial theme configuration.

<figure><img src="../../.gitbook/assets/image (2239).png" alt=""><figcaption></figcaption></figure>

## Terms of use/Privacy Policy

The **Terms of Use/Privacy Policy** page lets you review the conditions you initially agreed to when you first logged in. This page is read-only, so you cannot revoke or modify your acceptance of the terms.

The file is managed by the application developer or system administrator. If the Terms of Use are updated after your initial acceptance, you will be prompted to accept the new terms at your next login.&#x20;

<figure><img src="../../.gitbook/assets/image (2163).png" alt=""><figcaption></figcaption></figure>

To access this section, click on the profile picture and select **Terms of use**.

<figure><img src="../../.gitbook/assets/image (2176).png" alt=""><figcaption></figcaption></figure>

## Logout

The **Logout** section lets you correctly exit and disconnect from the Pages application, clearing the sessions. The logout button will hit the endpoint logout of the identity provider that has been configured when App Composer was installed.

To access this section, click on the profile picture and select **Logout**.

<figure><img src="../../.gitbook/assets/image (2177).png" alt=""><figcaption></figcaption></figure>
