# Connect on Metadata

## Introduction&#x20;

**The Super Administrator** is the user that is used at the first access of the Design Studio after installation and is not enabled to access the runtime. Its task is to create a new application and configure the Server for authentication if necessary.

The first user who authenticates from runtime will be created with the role of Administrator **and will be** enabled by default. The user must be registered and valid in the authentication system (keycloak, google etc.).

![](<../../../.gitbook/assets/10 (4)>)

All other users who authenticate via runtime are created as Basic users and are disabled.

![](<../../../.gitbook/assets/11 (6)>)

The DAC offers the possibility to automatically create users already enabled after authentication. Please see the section [**How to set "enabled" user automatically created**](connect-on-metadata.md#how-to-set-enabled-user-automatically-created.)**.**

When the administrator user accesses the **Users Administration** section of the runtime, disabled users have the status of "Disabled". They must then be enabled ( see User Administration)

![](<../../../.gitbook/assets/13 (6)>)

## First Connection in Design Studio&#x20;

After the installation we start the Design Studio and go to create the first connection.

If this is a **first login** after installatio&#x6E;**, the user configuring the connection will be the Super Administrator user.**

Below is the step by step guide to create a new connection.

### 1.Create New Connection&#x20;

A new connection is created by selecting the New Connection button present in the Connection wizard.

![](<../../../.gitbook/assets/16 (1)>)

### 2. Insert Credential&#x20;

In the credential section you enter the login credentials Username and Password of the Super Administrator (if it is a first access to the Design Studio)

In **Connection Name**, enter the name of the new connection.

**Credential**

* **Select Login with Open Connect** . The authentication of Design Studio leverage the IDMS
* **Select Login As Administrator** if is the first Installation. Usually when you build the first installation you not have the installation about the IDMS. And so in this case you have to connect with the administrator.

{% hint style="info" %}
For this installation we can use the Connect as Open Connect because the configuration on the IDMS it’s already pre-configured
{% endhint %}

* **Password**: Administrator

{% hint style="danger" %}
The first administrator user who accesses the runtime must reset the Password to the Super **Administrator user**
{% endhint %}



* **Remember Password** : save the user password

### 3.Connect To Metadata Database&#x20;

The Decisyon Connection panel allow to you to create a new Metadata Database Connection.

<figure><img src="../../../.gitbook/assets/image (1003).png" alt=""><figcaption></figcaption></figure>

**Metadata Database:**

In Metadata Database we insert all the information that will be required to connect to de Metadata Database.

To establish the connection between the Design Studio and the metadata database.

Login credentials must be provided by the system administrator

Enter the following parameters:

* **Database Type:** Select the Database Type
  * **Username:** Username for the connection to the DB
  * **Password:** Password for the connection to the DB
  * **Host:** Database Host
  * **Port:** Database Port
  * **Schema:** Database scheme
  * **Test Connection:** the button runs a test of the configured connection.

After insert the connection parameters select or Save & Connect or Connect (this second options don’t save the connection).

### 4.Use a previously saved connection.&#x20;

To use a previously saved connection, double click on the connection name. This will be run automatically if the credentials have been previously saved, it will be possible to access DAC-DS. Otherwise, you will need to enter the credentials. In this way it will be possible to access the metadata.

<figure><img src="../../../.gitbook/assets/image (382).png" alt=""><figcaption></figcaption></figure>

### 5.Edit or Clone Connection&#x20;

After selecting the connection to be edited, the panel displays a summary of the data for this connection.

<figure><img src="../../../.gitbook/assets/image (1009).png" alt=""><figcaption></figcaption></figure>

## How to set “enabled” user automatically created.&#x20;

By enabling the User-activate-on-creation property between the Web properties of the Preferences group (by default it is disabled), you have the option to automatically create all users who access the runtime without having to enable them individually.

<figure><img src="../../../.gitbook/assets/image (746).png" alt=""><figcaption></figcaption></figure>

## How to define a specific Administrator&#x20;

To register a user as an administrator, after logging into the Design Studio with the Super Administrator user you can associate the first user who will be the administrator of the application with the Administrator.

Dalla toolbar selezionare **Cloud>>Server & Services.**

<figure><img src="../../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

After selecting the system of authentication by OpenID Connect and define the type of authentication in Design Studio (For more detail se[ Server & Services](../../instance-configuration/server-and-services.md) ) let's go to define who will be the System Administrator.

In the **Tab Authentication** section **"Authentication on DAC**" we go to define the user who will be appointed administrator on the first access.

**Authentication on DAC:** Define the type of authentication in DAC

* **Admin User id Claim value:** Enter the ID of the user who will be appointed administrator at the first login. The user IDs are registered within the Openconnect server that has been selected in the Open Id Connect property)
* **Details:** Insert any detailed comments.
