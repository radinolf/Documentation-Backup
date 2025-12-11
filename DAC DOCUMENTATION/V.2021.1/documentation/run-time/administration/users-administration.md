# Users Administration

## Introduction&#x20;

Users to access DAC web applications must be registered within the application. There are five types of users in the DAC, each of which has concessions that allow them to perform certain operations or not (see [Users scope](users-administration.md#users-scope)).Only the users with Administrator **scope** can create a new user. To create a new user in DAC select the menu item **Administration >>User Administration** of the main men&#x75;**.**





![](<../../../.gitbook/assets/image (124).png>)

The User Administrator interface is it is made up of several sections.

On the left is the list of tenants created in the application, and the respective creation button (for more details see [Tenant ](tenant.md)documentation).

In the center is the list of users created in the application with the most relevant information highlighted.

At the top left is the user search menu. it is also possible to apply search criteria by activating the panel from the side icon.

![](<../../../.gitbook/assets/image (134).png>)

The search criteria can be applied for the following information:

**Role:** Filter the list with the users that are Administrator or a simple User

**Status**: Filter the list with the users that are Anable or not.

**Online**: Filter the list with the user are online.

**Attribute**:Filter the list with the user attribute.

### Create New User

To create a new user in DAC select the menu item **Administration >>User Administration** of the main men&#x75;**.**

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

In the **ATTRIBUTE** panel are available all the user [attribute ](user-attributes.md)create into the application.
{% endtab %}
{% endtabs %}

### User  Summary Information

After creation, the user list is updated. To access the information of the newly created user, select user and select the right arrow. all user information is available in this panel and can be edited.

![](<../../../.gitbook/assets/image (80).png>)

In the Details section are availabe other most importat information:&#x20;

* **Enable**: temporarily enables or disables the user to access the application&#x20;
* **Open Connetion Identifier**: identity code of the OAuth 2.0 protocol. It allows to verify the identity of the End-User based on the authentication performed by an Authorization Server, as well as to obtain basic profile information about the End-User in an interoperable and REST-like manner.&#x20;
* **Id:** user identification code.

### **Users Scope**

The users created within DAC can be associated at different scopes:

* **All Tenants Administration:** can create/modify/delete users associated to any Tenants or no tenant. He can assign to users he managed “All Tenants Administration” or “Tenants Administration” or “Users Administration” or “None” scope. He can’t create an Administrator user or promote as Administrator an existing user.
* **Tenants Administration:** he is able to modify only Tenants he is associated to. He can create/modify/delete users associated to tenants he is associated to. He can assign to users he managed only “Tenants Administration” or “Users Administration” or “None” scope. He can assign users to Tenants he is associated to. He can’t create an Administrator user or promote as Administrator an existing user.
* **Users Administration** (NO Administrator)**:** but he can create, modify, eliminate users associated to the Tenants he is associated to. He can assign to users he managed “Users Administration” or “None” scope. He can assign users to Tenants he is associated to. He can’t create an Administrator user or promote as Administrator an existing user.
* **None** This is the basic user that does not have administration capabilities.
* **Administrators** act like they have “All Tenants Administration” scope assigned even though they do not have this scope assigned. Furthermore they can create an Administration user or promote to Administration an existing user.

### Delete User

To delete a user just select and press the trash icon

![](<../../../.gitbook/assets/image (97).png>)

### Video Tutorial

For a brief overview of how to create a new user, please see the video below.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/10.Users/CreateUser.mp4" %}

###
