# Users Administration

## Introduction

Users to access DAC web applications must be registered within the application. There are five types of users in the DAC, each of which has concessions that allow them to perform certain operations or not (see [Users scope](users-administration.md#users-scope)).Only the users with Administrator **scope** can create a new user. To create a new user in DAC select the menu item **Administration >>User Administration** of the main men&#x75;**.**





![](<../../.gitbook/assets/image (854).png>)

The User Administrator interface is it is made up of several sections.

In the user administration interface, the logged in user will only see users with a role equal to or less than that of the logged in user of their tenant or who do not have tenants.

On the left is the list of tenants created in the application, and the respective creation button (for more details see [Tenant ](tenant.md)documentation).

**All users** group shows the list of all the users registered in the DEC while the **User without tenant** show the list of users without an associated tenant.

In the center is the list of users with the most relevant information highlighted.

The icon associated with the user can change according to:

![](<../../.gitbook/assets/image (663).png>)



At the top left is the user search menu. it is also possible to apply search criteria by activating the panel from the side icon. The search will be applied to the users of the selected tenant

![](<../../.gitbook/assets/image (41).png>)

The search criteria can be applied for the following information:

* **Role:** Filter the list with the users that are Administrator or a simple User.
* **Scope**: Filter the list with the users by the selecting Scope.
* **Status**: Filter the list with the users that are Anable or not.
* **Online**: Filter the list with the user are online.
* **Plant**: Filter by plant.
* **Department**: Filter by department
* **Manager**: Filter by manager
* **Name**: Filter by name of user
* **Attribute**:Filter the list with the user attribute.

### Create New User

To create a new user in DAC select the menu item **Administration >>User Administration** of the main men&#x75;**.**

Select the "Plus" button on the top to create new user, and follow the wizard.

{% tabs %}
{% tab title="Details" %}
![](<../../.gitbook/assets/image (426).png>)

In the **DETAILS** panel insert the user information

* **Username:** insert the user name that the user use when acces on the DAC Web.
* **First Name:** Name of user.
* **Last Name:** surname of the user.
* **Password**: insert the password that the user use when acces on the DAC Web.
* **Confirm Password:** repeat the password to confirm.
* **Email**: Insert a vail Email.&#x20;
* **Tenant**: associate a Tenant to the user ( If the user already selected a tenant from the list on the tents, the value will be pre-selected on the same tenant, even when if the user only has 1 tenant associated. If the selection is on "All users" or "Users without tenant", the item is empty ).
* **Scope**: Associate a scope to the user (this information is optional. If don't select any scope the system create a user with NONE  [scope](users-administration.md#users-scope)).
{% endtab %}

{% tab title="Settings" %}
![](<../../.gitbook/assets/image (427).png>)

In the **SETTING** panel set the information about:

* **Timezone**: select a specific timezone or select AUTI to associate automatically  the TimeZone set by the Administrator at the application level.
* **Language**: Select the language to be used for displaying application labels
* **Email Notification**: Select if the user is enabled or not to receive emails from the system.
* **Local me:** The timezone will be set automatically according to your location.
{% endtab %}

{% tab title="Groups" %}
![](<../../.gitbook/assets/image (351).png>)

In the **GROUPS** panel are available all the groups created into the application. it's possible to associate the user to one, more or no groups.
{% endtab %}

{% tab title="Attributes" %}
![](<../../.gitbook/assets/image (110).png>)



In the **ATTRIBUTE** panel are available all the user [attribute ](/broken/pages/-Mfgj4wzCjKd7cch6xDV)create into the application.

When defining the value of an attribute for a user, you can choose . When the default value is chosen, the value is converted using the default value of the current attribute.

also is used as the initial value for attributes when creating a new user and all attributes are marked as default.&#x20;

**Default Flag:**

* If you create a user in the administration section, all attributes have the "Default" flag inactive.
* If a user is automatically created as inactive, all attributes have the "Default" flag inactive.i If there is an attribute required, the system, both in the modification phase and in the creation of the user, does not allow the saving.
* If a user is automatically created as active, only the mandatory attributes have the "Default" flag active.
* If you activate a user in the administration section via the context menu, the configuration of the attributes is validated.

{% hint style="info" %}
In the user administration only the attributes with a set default value and those of the BOOLEAN type will have the default flag present.
{% endhint %}


{% endtab %}
{% endtabs %}



{% hint style="info" %}
Users with scope "Users Administration" or "Tenans Administration" or "All Tenant" don't display the switch "Administrator" in the Detail tab of the user creation wizard and in the summary inforations.
{% endhint %}

![](<../../.gitbook/assets/image (769).png>)

In the Details section are availabe other most importat information:&#x20;

* **Enable**: temporarily enables or disables the user to access the application&#x20;
* **Open Connetion Identifier**: identity code of the OAuth 2.0 protocol. It allows to verify the identity of the End-User based on the authentication performed by an Authorization Server, as well as to obtain basic profile information about the End-User in an interoperable and REST-like manner.&#x20;
* **Id:** user identification code.

### **Users Scope**

The users created within DAC can be associated at different scopes:

![](<../../.gitbook/assets/image (326).png>)

### Delete User

To delete a user just select and press the trash ico&#x6E;**.**&#x20;

**All Tenant Administrator , Administrator and Tenant Administrator** they can delete users who belong to their tenants **or associated to no tenant.**

![](<../../.gitbook/assets/image (36).png>)

### Video Tutorial

For a brief overview of how to create a new user, please see the video below.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/10.Users/CreateUser.mp4" %}

###
