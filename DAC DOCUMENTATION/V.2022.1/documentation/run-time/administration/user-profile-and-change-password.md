# User Profile, Change Password​ & Generate Token

## Introduction

DAC has an area dedicated to the user's personal profile.

![](<../../../.gitbook/assets/image (307).png>)

To access your profile, click on the profile image.

The page consists of two separate areas:

* Profile, which includes all the data of your user profile. If you log in as a non-administrator user the username field will not be editable
* Settings, which includes a set of options to customize your account.

**Language**

You  can choose the language for DAC’s UI. This does not affect the reporting language or language of the social environments’ content.

**Time zone**

A list of available time zones. _**Auto**_ is the first element. When this element is selected, DAC uses the PC’s time zone.

Because time zone changes are applied from the next access, you must log out and log in again.

Generally, the administrator will directly set the users' time zone. This feature allows you to change it.

**Enable Notifications:** if enabled, you can receive email notifications.

In addition, you can attach an image to your profile and view who you are following and who you are being followed by.

To change the password, select the item in the top right.

After changing the password you will be redirected to the login page.

### Generate Token

It is also possible to generate the DAC Authorization Token by selecting Generate Token button.

![](<../../../.gitbook/assets/image (33).png>)



The generated token will be used to get authorization to perform actions on DAC, such as deploying and deleting an application in a target environment, viewing pages using an external link, or for the execution of API rest.

The Token will have an unlimited duration, unless an expiration date is specified.

In the Scope, you can select the the scope of the token:

* If you select Login into the DAC, you can generate a token that authorizes you to access the DAC system. You can use this token, for example, to access pages via external links or to deploy or delete  an application.
* The token with the "Manage token" scope is used to manage the tokens. For example, provided a Token you can invoke the Rest API / check\_token which allows you to determine if the token is active and to whom it belongs.

### Change your password

To change your password select Change Password button.

![](<../../../.gitbook/assets/image (310).png>)

In the "Current Password" enter the password you want to change. Enter the new password in "New password" and confirm in the next field "Confirm Password". After changing your password you will be redirected to the login page.

&#x20;

## Video

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/2.1AccountPassword/UserProfileChangePassword.mp4" %}

