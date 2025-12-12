# 🆕 User Administration

## Introduction

**User Management** allows business users to view and manage the users associated with the selected Organization. Depending on the privileges, users can perform different operations such as editing users and creating new organisations.

{% hint style="info" %}
Refer to  [Users Scope](users-scope-and-scope.md) for details on permissions.
{% endhint %}

To access this section click the Users button <img src="../../../.gitbook/assets/image (91).png" alt="" data-size="line"> located in the **Main Toolbar** of Pages.

<figure><img src="../../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

## **Users Management Panels**

User Management consists of three panels that collectively provide comprehensive tools for managing users and organizations within the Pages application:

<figure><img src="../../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

1. [**User List Content Panel**](./#user-list-content-panel)**:**
   * Displays a list of users from the currently selected organization, including main information such as Name, Username, and Email.
   * Provides options to manage these users.
2. [**Navigation Panel**](./#navigation-panel)**:**
   * Allows you to create and manage organizations.
   * [**Users Sub-Navigation**](./#users-sub-navigation)**:** Includes buttons to filter and view All Users or Users without Organization.
   * [**Organizations Sub-Navigation**](./#organizations-sub-navigation)**:** Contains options to create, rename, and delete organizations.
3. [**Support Panel:**](./#support-panel)
   * Displays details of the selected user.
   * Allows you to edit the user's settings.

## User List Content Panel

In the **User List Content panel**, business users can view and manage the list of users in the selected organization. This panel has two main elements: the [**List of Users** ](./#list-of-users)and the [**Action Toolbar**](./#action-toolbar)**.**

<figure><img src="../../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

### List of Users

For each user, the list displays:

* **Name**
* **Username**
* **Email**
* **Connection (Online/Offline)**
* **User Icon or Profile Picture:** The icon changes based on the connection (Online/Offline), and account status (Enabled/Disabled).

<figure><img src="../../../.gitbook/assets/image (2074).png" alt=""><figcaption></figcaption></figure>

#### Additional features of the List of Users:

* **Sortable Columns:** Users can be sorted by name, username, and email.

<figure><img src="../../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

* **Multiple User Selection:** A column is available for selecting multiple users at once.

<figure><img src="../../../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

* **User Menu:** Located on the right of each user entry, the **user menu** allows managing user accounts providing actions: **Delete**, **Disconnect**, and **Enable/Disable**. Refer to [Edit User](edit-user.md) for more details.

<figure><img src="../../../.gitbook/assets/image (98).png" alt=""><figcaption></figcaption></figure>



{% hint style="warning" %}
To perform actions for managing user accounts (Delete, Disconnect, Enable/Disable) the connected user must have at least the **Users Administration scope.** Refer to [Users Scope](users-scope-and-scope.md) for more details.
{% endhint %}

### Action Toolbar

The **Action Toolbar** provides different functionalities for displaying, filtering and managing the user list.

The Action Toolbar contains the following buttons: &#x20;

* **Navigation Panel Button**: Located on the left, it opens and closes the [Navigation panel](./#navigation-panel).
* **Support Panel Button**: Located on the right, it opens and closes the [Support panel](./#support-panel).

<figure><img src="../../../.gitbook/assets/image (2118).png" alt=""><figcaption></figcaption></figure>

The options available in the Action Toolbar change depending on whether users are selected in the user list or not:

#### **When No Users Are Selected**

1. **Search Field**: Search for a specific user.
2.  **Filter** **Button**![](<../../../.gitbook/assets/image (101).png>): Located in the Search field, it allows you to filter the list based on specific criteria:

    * **Scope**
    * **Status:** All, Enabled, Disabled
    * **Online:** All, Online, Offline
    * **User Attributes**

    <figure><img src="../../../.gitbook/assets/image (2082).png" alt=""><figcaption></figcaption></figure>



#### **When One or More Users Are Selected**

The Action Toolbar displays actions that can be performed simultaneously on the selected users:

* **Delete users** <img src="../../../.gitbook/assets/image (62).png" alt="" data-size="line">:  Remove selected users.
* **Disconnect users** <img src="../../../.gitbook/assets/image (63).png" alt="" data-size="line">: Log out selected users.
* **Enable users** <img src="../../../.gitbook/assets/image (50).png" alt="" data-size="line">:  Activate selected users.
* **Disable users**<img src="../../../.gitbook/assets/image (52).png" alt="" data-size="line">: Deactivate selected users.

<figure><img src="../../../.gitbook/assets/image (2077).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
These features, for managing user accounts, are also available in the **User Menu** located to the right of each user, but the **Action Toolbar** allows you to perform these actions on multiple users at once. Refer to [Edit User](edit-user.md) for more details.
{% endhint %}

## Navigation Panel

The **Navigation** Panel allows business users to search for, create, and manage organizations. It consists of the **Users** and **Organizations** sub-navigations.

<figure><img src="../../../.gitbook/assets/image (108).png" alt=""><figcaption></figcaption></figure>

### Users Sub-Navigation

The **Users** sub-navigation provides options to filter the User List panel based on organization association:

* **All users**: Display all users associated with the selected organization. This option also shows the total number of users.
* **Users without organization:** Display all users who are not associated with any organization. This option also shows the total number of users without an organization.

### Organizations Sub-Navigation

The **Organizations** sub-navigation allows you to search for, create and manage organizations. It includes the following features:

* ![](<../../../.gitbook/assets/image (109).png>)**Search** **Field**: Search for the organization in the list.
* ![](<../../../.gitbook/assets/image (110).png>)**Create Organization Button**: Create a new organization.
* **Organization Menu:** Each organization has a menu to rename and delete it.

<figure><img src="../../../.gitbook/assets/image (2184).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Refer to the [Organization](../organization.md) section for more details on creating and managing organizations.
{% endhint %}

## Support Panel

The **Support panel** allows you to display and edit the selected user's details. To perform editing operations in the Support Panel, the connected user must have at least the **Users Administration** scope. This panel opens on the right when a user is selected and provides comprehensive information configured for that user.

{% hint style="warning" %}
Refer to [Edit User](edit-user.md) and [Users Scope](users-scope-and-scope.md) chapters for more details on editing operations and user permissions.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

The support panel is divided into the following sections:

### Header

Displays the user profile picture and online status with the connection date and time. This section includes the **user menu** with the options to manage user accounts (delete, disconnect, enable, or disable users).

<figure><img src="../../../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>

### Details

It shows the main user information (**Name, Username, Email, and Scope**) and allows you to edit the [**Users Scope**](users-scope-and-scope.md).

<figure><img src="../../../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>

### Organizations

Displays the **organizations** associated with the selected user and allows you to edit these associations, including adding or removing organizations.

<figure><img src="../../../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Refer to [Create and Edit Organization](../organization.md) for more details on managing Organization.&#x20;
{% endhint %}

### Settings

Allows you to view and edit location and notification settings, including:

* **Timezone:** View or change the user’s timezone.
* **Language**: View or change the user’s language from a list of configured languages.
* **Email Notifications**: Enable or disable email notifications for the user.
* **Locate Me:** Enable or disable automatic user location detection.

<figure><img src="../../../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Settings options can also be customized by each user in their account from the [User Profile](/broken/pages/hSsEgtao4sQ3OngBdVxb) page
{% endhint %}

### Groups

The **Groups** section shows the user groups associated with the selected user and allows you to edit this association, including adding or removing groups.\
This customisation enables the management of page and report visibility based on each group's purpose, as well as the restriction of access to sensitive information that isn't pertinent to specific roles. By setting access permissions at the group level, organizations can guarantee sensitive data and ensure certain application functionalities are only available to authorized users.

<figure><img src="../../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

### Attributes

Displays user-assigned attributes and allows for editing. User Attributes are custom fields that collect additional user information. Configuring these fields enables business users to dynamically access relevant content and data reporting within the application. Each dropdown menu in this section includes a search field for finding specific items.

<figure><img src="../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>
