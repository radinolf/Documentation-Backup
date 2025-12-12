# Organization

## Introduction

Pages defines an **Organization** as a structured entity representing a hierarchical group of users. Organization-based user segregation offers a more hierarchical structure than group-based segregation. Users can be associated with none, one, or many organizations. If no organization is selected during user registration or modification, the user will be assigned to none as a default.

Users with the "Organization Admin" or "All Organization Admin" [scope ](user-administration/users-scope-and-scope.md)can associate organizations with users. These users have privileges to manage organizations, assign users, and handle related configurations.

In every page of the application, a dropdown menu allows users to select the organization to which they belong.

<figure><img src="../../.gitbook/assets/image (2247).png" alt=""><figcaption></figcaption></figure>

The data displayed on the pages can be filtered based on the selected organization, allowing users to automatically access only data relevant to their organization. This filtering is implemented through system variables like `%CURRENT_ORGANIZATION%` and `%ORGANIZATION%`.

For more details see:

{% embed url="https://documentation.decisyon.com/documentation/app-functionality/system-parameters" %}

## Creates and Manages Organizations

In Pages, only users with specific scope grants can create and manage organizations:

* **Organizations administration:** Users with this scope can create and edit organizations within their associated organizations.
* **All organizations administration:** Users with this scope have full administrative permissions over all organizations within the application.

{% hint style="info" %}
For more details on permissions, refer to [Users Scope](user-administration/users-scope-and-scope.md) section.
{% endhint %}

## Rename, Delete, and Edit Organization

Organizations are created and managed in the **User Management** section of Pages. Access this section by clicking the **Users** button <img src="../../.gitbook/assets/image (139).png" alt="" data-size="line"> located in the **Main Toolbar** of Pages.

* In the **Navigation Panel,** located on the left, you can create, rename, and delete organizations.
* In the **Support Panel**, located on the right, you can edit organizations by managing the user associations (adding or removing one or more organizations for the selected user).

### &#x20;Create New Organizations

* In the **Organizations Sub-Navigation** section of the **Navigation Panel**, click the ![](<../../.gitbook/assets/image (158).png>)**Create Organization Button**:

<figure><img src="../../.gitbook/assets/image (2135).png" alt=""><figcaption></figcaption></figure>

* In the dialog that opens, enter a title for the new organization (mandatory, max 100 characters).
* Click the **Create** button.

<figure><img src="../../.gitbook/assets/image (2235).png" alt=""><figcaption></figcaption></figure>

### Rename and Delete Organizations

* In the **Organizations Sub-Navigation** section of the **Navigation Panel,** select the organization you want to rename or delete. Use the Search field ![](<../../.gitbook/assets/image (157).png>) to find the organization in the list.
* Each organization has a menu to rename and delete it.
* Click the **Rename** or **Delete** button to confirm the operation.

<figure><img src="../../.gitbook/assets/image (2234).png" alt=""><figcaption></figcaption></figure>

### Edit Organizations

Editing organizations involves associating users with new organizations or modifying their current associations.

* Select a user from the **User List Content Panel** to open the **Support Panel.**
* In the **Organizations** section, click the edit button ![](<../../.gitbook/assets/image (2132).png>)  to associate a new organization with the selected user.
* In the dialog that opens, select the organization from the dropdown list.
* Click the Save button.

<figure><img src="../../.gitbook/assets/image (2133).png" alt=""><figcaption></figcaption></figure>

### Assigning Organizations to Users

Organizations are assigned to users during the configuration phase by a user with the necessary privileges to perform this action. Users can then have their data filtered according to the organization they belong to.&#x20;

For more details see:&#x20;

{% content-ref url="user-administration/" %}
[user-administration](user-administration/)
{% endcontent-ref %}

<figure><img src="../../.gitbook/assets/image (2248).png" alt=""><figcaption></figcaption></figure>

### Setting Default Organization

Upon accessing a page, the selected organization corresponds to the current one. To modify the selected organization, simply choose a different one from the dropdown selector.\
Users can set a default organization so that the application's pages are already filtered to the desired organization upon login.\
To set the default organization, users can access their profile and select **Default Organization** under the **Settings** properties.

<figure><img src="../../.gitbook/assets/image (2249).png" alt=""><figcaption></figcaption></figure>
