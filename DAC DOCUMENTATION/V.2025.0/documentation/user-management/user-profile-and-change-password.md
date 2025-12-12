# User Profile in AppComposer

## Introduction

App Composer provide a built-in page where any user is able to modify its own personal information and settings.

{% hint style="warning" %}
Please note that this is a built-in page and can not be modified by administrators or application developers.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (1987).png" alt=""><figcaption></figcaption></figure>



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

When enabled, user can receive email notifications from App Composer, in example when mentioned in [tasks](/broken/pages/-MfHgDqO0nKQQ-UqipQ6), in [discussion](https://widgets.decisyon.com/discussion-1/v/discussions/) or when they are configured for a [notification](../app-functionality/untitled.md).

**Profile picture**

It is possible to modify the profile picture. Administrator users doesn't have the grants to modify a profile picture.

## Generate Token

The generated token can be used to authorized actions to be performed on the DAC. The allowed action may be limited scopes associated when the token was generated.&#x20;

All users (administrators and business users) are able to generate an App Composer token.

The token can be used in the following use cases:

* to invoke the [App Composer REST API](../sdk-and-api/app-composer-rest-api/)
* Deploy or delete an application in a target environment during an [application synchronization](../application-synchronization-wip/)
* [To view or embed App Composer pages](../page-designer/advanced-configuration/accessing-page-from-external-systems.md), passing the token in query string to prevent the login screen to show up.

<figure><img src="../../.gitbook/assets/image (443).png" alt=""><figcaption></figcaption></figure>

For more details see [Authorization Tokens](../sdk-and-api/app-composer-rest-api/authentication.md)

