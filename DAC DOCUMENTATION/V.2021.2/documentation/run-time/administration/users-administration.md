# Users Administration

## Introduction

Users to access DAC web applications must be registered within the application. There are five types of users in the DAC, each of which has concessions that allow them to perform certain operations or not (see [Users scope](users-administration.md#users-scope)).Only the users with Administrator **scope** can create a new user. To create a new user in DAC select the menu item **Administration >>User Administration** of the main men&#x75;**.**





![](<../../../.gitbook/assets/image (124).png>)

The User Administrator interface is it is made up of several sections.

On the left is the list of tenants created in the application, and the respective creation button (for more details see [Tenant ](tenant.md)documentation).

In the center is the list of users created in the application with the most relevant information highlighted.

At the top left is the user search menu. it is also possible to apply search criteria by activating the panel from the side icon. The search will be applied to the users of the selected tenant

![](<../../../.gitbook/assets/image (122).png>)

The search criteria can be applied for the following information:

* **Role:** Filter the list with the users that are Administrator or a simple User.
* **Scope**: Filter the list with the users by the selecting Scope.
* **Status**: Filter the list with the users that are Anable or not.
* **Online**: Filter the list with the user are online.
* **Attribute**:Filter the list with the user attribute.

### Create New User

To create a new user in DAC select the menu item **Administration >>User Administration** of the main men&#x75;**.**

Select the "Plus" button on the top to create new user, and follow the wizard.

{% tabs %}
{% tab title="Details" %}
![](<../../../.gitbook/assets/image (141).png>)

In the **DETAILS** panel insert the user information

* **Username:** insert the user name that the user use when acces on the DAC Web.
* **First Name:** Name of user.
* **Last Name:** surname of the user.
* **Password**: insert the password that the user use when acces on the DAC Web.
* **Confirm Password:** repeat the password to confirm.
* **Email**: Insert a vail Email.&#x20;
* **Tenant**: associate a Tenant to the user ( this inforamation is optional).
* **Scope**: Associate a scope to the user (this information is optional. If don't select any scope the system create a user with NONE  [scope](users-administration.md#users-scope)).
{% endtab %}

{% tab title="Settings" %}
![](<../../../.gitbook/assets/image (112).png>)

In the **SETTING** panel set the information about:

* **Timezone**: select a specific timezone or select AUTI to associate automatically  the TimeZone set by the Administrator at the application level.
* **Language**: Select the language to be used for displaying application labels
* **Email Notification**: Select if the user is enabled or not to receive emails from the system.
{% endtab %}

{% tab title="Groups" %}
![](<../../../.gitbook/assets/image (123).png>)

In the **GROUPS** panel are available all the groups created into the application. it's possible to associate the user to one, more or no groups.
{% endtab %}

{% tab title="Attribute" %}
![](<../../../.gitbook/assets/image (132).png>)

In the **ATTRIBUTE** panel are available all the user [attribute ](/broken/pages/-Mfgj4wzCjKd7cch6xDV)create into the application.
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Users with scope "Users Administration" or "Tenans Administration" or "All Tenant" don't display the switch "Administrator" in the Detail tab of the user creation wizard and in the summary inforations.
{% endhint %}

![](<../../../.gitbook/assets/image (80).png>)

In the Details section are availabe other most importat information:&#x20;

* **Enable**: temporarily enables or disables the user to access the application&#x20;
* **Open Connetion Identifier**: identity code of the OAuth 2.0 protocol. It allows to verify the identity of the End-User based on the authentication performed by an Authorization Server, as well as to obtain basic profile information about the End-User in an interoperable and REST-like manner.&#x20;
* **Id:** user identification code.

### **Users Scope**

The users created within DAC can be associated at different scopes:

* **All Tenants Administration**
  * Scope “All Tenants Administration” enable a user to manage users belonging to any tenants;
  * Scope shall be assigned to not-administrator users;
  * Scope "All Tenants Administration" do enable a user to manage users's groups;
  * Scope "All Tenants Administration" enable a user to assign/revoke scopes "Users Administrator", “Tenant Administration” and "All Tenants Administration" of a user.
  * Scope “Tenants Administration” do not enable a user to manage (delete, promote, disable...) other users having "All Tenants" scopes or Administrators;
  * Scope “All Tenants Administration” do not enable a user to manage (delete, promote, disable...) Administrators;
  * Scope "All Tenants Administration" do enable user to create Tenant and modify all existing Tenants.
  * The User Administration section shall show modifiable users only.
* **Tenants Administration:**
  * Scope “All Tenants Administration” enable a user to manage users belonging to any tenants;
  * Scope shall be assigned to not-administrator users;
  * Scope "All Tenants Administration" do enable a user to manage users's groups;
  * Scope "All Tenants Administration" enable a user to assign/revoke scopes "Users Administrator", “Tenant Administration” and "All Tenants Administration" of a user.
  * Scope “Tenants Administration” do not enable a user to manage (delete, promote, disable...) other users having "All Tenants" scopes or Administrators;
  * Scope “All Tenants Administration” do not enable a user to manage (delete, promote, disable...) Administrators;
  * Scope "All Tenants Administration" do enable user to create Tenant and modify all existing Tenants.
  * The User Administration section shall show modifiable users only.
* **User Administration** (NO Administrator)**:**&#x20;
  * Scope shall be assigned to not-administrator users;
  * Scope "User Administration" enable a user to manage users belonging to the same tenants and those belonging to no tenants.
  * Scope "Users Administration" do not enable a user to manage other users having "Tenants" or "All Tenants" scopes or Administators (delete, promote, disable...)
  * Scope "User Administration"enables users to modify others users' scopes, assigning/revoking “User Administration” scopes.
  * The User Administration section shall show modifiable users only.
* **None** This is the basic user that does not have administration capabilities.
* **Administrators** act like they have “All Tenants Administration” scope assigned even though they do not have this scope assigned. Furthermore they can create an Administration user or promote to Administration an existing user.

### Delete User

To delete a user just select and press the trash icon

![](<../../../.gitbook/assets/image (97).png>)

### Video Tutorial

For a brief overview of how to create a new user, please see the video below.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/10.Users/CreateUser.mp4" %}

###
