# User Profile

## Introduction

App Composer provide a built-in page where any user is able to modify its own personal information and settings.

{% hint style="warning" %}
Please note that this is a built-in page and can not be modified by administrators or application developers.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (839).png" alt=""><figcaption></figcaption></figure>

To access your profile, click on the profile image.

The page consists of two separate areas:

* Profile: includes all the data of your user profile. If you log in as a non-administrator user the username field will not be editable
* Settings: which includes a set of options to customize your account.

**Language**

You  can select the language to be use in App Composer. The language can be selected only from a list of languages that an administrator user has configured for the instance. The language selection affects the built-in labels App Composer user interface and any eventual multilanguage label that the application developer has defined when building the application.

{% hint style="info" %}
To configure additional languages, please see [Multilanguage and localization](../instance-configuration/multilanguage-and-localization/).
{% endhint %}

**Time zone**

A list of available time zones. _**Auto**_ is the first element. When this element is selected, App Composer automatically reads the user's timezone based on its browser.

Because time zone changes are applied from the next login, you must log out and log in again to make them effective.

Generally, the administrator is able to set the users' time zone when creating the user: this feature allows business user to select its own time zone.

**Enable Notifications**&#x20;

When enabled, user can receive email notifications from App Composer, in example when mentioned in [tasks](../collaboration/task.md), in [discussion](https://widgets.decisyon.com/discussion-1/v/discussions/) or when they are configured for a [notification](../app-functionality/untitled.md).

**Profile picture**

It is possible to modify the profile picture. Administrator users doesn't have the grants to modify a profile picture.

## Generate Token

The generated token can be used to authorized actions to be performed on the DAC. The allowed action may be limited scopes associated when the token was generated.&#x20;

All users (administrators and business users) are able to generate an App Composer token.

The token can be used in the following use cases:

* to invoke the [App Composer REST API](../sdk-and-api/app-composer-api.md)
* Deploy or delete an application in a target environment during an [application synchronization](../application-synchronization-wip/)
* [To view or embed App Composer pages](../page-designer/advanced-configuration/accessing-page-from-external-systems.md), passing the token in query string to prevent the login screen to show up.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

By default, the token will have an unlimited duration, unless an expiration date is specified. If you set an expiration date for the token, after that date the API requests will return an HTTP 401 “Unauthorized” error.

In the Scopes, you can select the the scope of the token:

* If you select **Login into the DAC,** you can generate a token that authorizes the access to App Composer user interface. This scope must be selected, for example, to access pages via external links, to embed a DAC page in another application or to deploy or delete an application.
* If you select "**Manage token**" you can generate a token that can be used to verify the validity of other tokens. For example, provided a Token you can invoke the Rest API `.../api/v2/rest/check_token` which allows you to determine if the token is active and to whom it belongs to.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
**Use cases**

In DAC applications, it happens that both basic user tokens and administrator tokens are used.

Basic user tokens are used for example, when clients start up and allow automatic access to the DAC, bringing the user directly into a specific application page.

Administrator tokens are used for internal application communications. For example, an administrator token is used because it has the ability to make APIs request to DAC, such as refreshing a page when an event happens outside the App Composer.
{% endhint %}

### Using token in a Rest API <a href="#how-to-use-token-in-the-rest-api" id="how-to-use-token-in-the-rest-api"></a>

To invoke a **DAC REST API**, a bearer token is required to authorize the request. The token to be use is generated from the user profile page.&#x20;

`“Authorization” = “Bearer <DAC Token>".`&#x20;

In the following example, the App Composer [REST API Client](../sdk-and-api/rest-api-client.md) is used to execute a request to an API exposed by DAC. The token to authenticate a request to App Composer API must be generated from the user profile page.&#x20;

{% hint style="info" %}
When you need to consume App Composer API from within the DAC Instance, it's possible to use the variable `%DAC_ACCESS_TOKEN%` that contains the value of the token issued to the user at login.&#x20;

For further details see [How to use authorization tokens](../sdk-and-api/rest-api-client.md#how-to-use-authorization-tokens)
{% endhint %}

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### Using token to deploy or delete an application <a href="#how-to-use-the-token-to-deploy-or-delete-an-application-in-a-target-environment." id="how-to-use-the-token-to-deploy-or-delete-an-application-in-a-target-environment."></a>

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

The token is also used when deploying the application in a target environment: in the source environment you need to set a token from an administrator user of the target environment. In this case, the token doesn’t require any specific scope.

{% hint style="info" %}
You can also see the document: [Synchronization](https://documentation.decisyon.com/documentation/application-synchronization-wip)
{% endhint %}

### **Using token to view or embed pages** <a href="#view-or-embed-pages" id="view-or-embed-pages"></a>

It's possible to open an App Composer page or embed it in another application without insert the user credential adding in the query string of the URL the token: “`?token=<DAC Token>`” .&#x20;

{% hint style="warning" %}
Token used for this purpose must have been generated with the "_Login into DAC_" scope.
{% endhint %}

After the token is generated, you can include it in the URL:

`https://<application URL>/content/Page/<OWNER>_<PAGE ID>/[view or embedView]?token=<token>`

{% hint style="info" %}
You can also see the example:[ How to get the link to embed the page ](https://documentation.decisyon.com/documentation/page-designer/advanced-configuration/embed-a-dac-page-in-a-third-party-application#2.-how-to-get-the-link-to-embed-the-page)>>[ 2.How to generate a user token](https://documentation.decisyon.com/documentation/page-designer/advanced-configuration/embed-a-dac-page-in-a-third-party-application#2.how-to-generate-a-user-token).
{% endhint %}

## Change password

To change the password click "Change Password" button.

![](<../../.gitbook/assets/image (793).png>)

In the "Current Password" enter the password you want to change. Enter the new password in "New password" and confirm in the next field "Confirm Password". After changing your password you will be redirected to the login page.

{% hint style="warning" %}
The "Change Password" button is available only when the authentication provider configured in the App Composer instance is "Keycloak".&#x20;

Instances configured with "Azure Active Directory" or "Schneider IDMS" as authentication provider will not display the button.
{% endhint %}

&#x20;

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/2.1AccountPassword/UserProfileChangePassword.mp4" %}

