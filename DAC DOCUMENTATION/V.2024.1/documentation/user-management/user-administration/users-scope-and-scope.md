# Users Scope & Scope

## Introduction

Users can be assigned both 'User Scopes' and 'Scopes'. 'User Scopes' define permissions related to managing users and organizations, while 'Scopes' grant specific privileges, such as the ability to customize the application's theme through the 'Theme Administration' scope. These levels of authorization allow for granular control over the actions a user can perform within the application.

## User Scope

Users registered in Pages can be assigned with different scopes (permissions):

* **None:** The user has no permissions.
* **User administration:** The user can manage and edit other user accounts within their associated organizations.
* **Organizations administration:** The user can create and edit organizations within their associated organizations.
* **All organizations administration:** The user has full administrative permissions over all organizations within the application.

{% hint style="info" %}
For detailed information on the permissions associated with each scope, refer to the [Users Scope](users-scope-and-scope.md#users-scope) table.
{% endhint %}

By default, users are assigned the **None** User Scope. User Scopes can be assigned from the **Details** section of the **Support** panel.

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

### User Scope Authorization Levels

Here are the details of editing operations related to the different user scopes:

<table data-full-width="true"><thead><tr><th width="166"> Category</th><th width="177">Operations Scopes</th><th width="74" align="center">None</th><th width="193" align="center">Users administration</th><th width="246" align="center">Organizations administration</th><th align="center">All organizations administration</th></tr></thead><tbody><tr><td><strong>User Administration</strong></td><td>Read, Edit and Delete users only in associated organizations</td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr><tr><td></td><td>Associate users to Groups</td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr><tr><td></td><td>Read, Edit, and Delete users in any organizations (even not associated)</td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr><tr><td><strong>Organization Administration</strong></td><td>Read, Edit and Delete only  in associated Organizations</td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr><tr><td></td><td>Read, Edit and Delete any Organizations</td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr><tr><td></td><td>Create New Organizations</td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2062).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr></tbody></table>

## Scope

Users can be assigned the scope for application customization. The 'Theme Administration' scope, available in the Scope dropdown menu, enables these privileges. By default, users' scope is set to 'none'.

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

When a user has the 'Theme Administrator' scope, the 'Application Settings' menu item will be enabled in their profile.

<figure><img src="../../../.gitbook/assets/image (30).png" alt="" width="248"><figcaption></figcaption></figure>

For information on how to customize your application, see [Application Settings](../user-profile-in-pages.md#application-settings):

### &#x20;Scope Authorization Levels

All users with any assigned **User Scope** can have the **'Theme Administrator'** scope. However, only users with the '**Organization Administrator**' or '**All Organization Administrator**' roles have the ability to assign the '**Theme Administrator**' scope to other users.

Here are the details of editing operations related to the different user scopes:

<table data-full-width="true"><thead><tr><th width="166"> Category</th><th width="177">Operations Scopes</th><th width="74" align="center">None</th><th width="193" align="center">Users administration</th><th width="246" align="center">Organizations administration</th><th align="center">All organizations administration</th></tr></thead><tbody><tr><td><strong>Theme Administration</strong></td><td>Customize the Appliction Layout</td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td><td align="center"><img src="../../../.gitbook/assets/image (2061).png" alt="" data-size="line"></td></tr></tbody></table>
