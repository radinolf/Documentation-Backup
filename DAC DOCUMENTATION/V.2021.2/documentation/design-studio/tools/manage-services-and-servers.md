# Manage Services & Servers

Some DAC-DS services require a connection to external servers to be able to be executed, for example, sending notifications (see [Notification Designer](../application/untitled.md))

The parameters for the connection to these servers are configured in the window opened from the menu item:

**Tools >> Servers & Server**

The servers that can be configured are of the type:

* [SMTP ](manage-services-and-servers.md#smtp-server)Server for the SMTP type e-mail services



#### SMTP Server

The definition of a reference to a **SMTP Server** includes specifying the following properties:

* **host-name**, reference to the machine that manages the SMTP service
* **port-number**, port for accessing the service (default 25)
* **smtp-security-protocol** allows the user to select whether the type of protocol used is SMTP (default) or SMTPS (for the SSL protocol).
* **Smtp-authentication-protocol** lets you select whether the type of authentication protocol used is not encrypted or if it is SSL or TLS.
* **mail-sender**, e-mail address to be used as sender, for the e-mails sent from this e-mail server
* **mail-sender-name**, name to be associated with the sender

If the server requires authentication credentials, select the **useCredential** property (Access credential group), which enables:

* **smtp-**/**username/smtp-password**, for entering the name and password of a user authorized to access the SMTP server

**Connection Test** button allow you if the configuration is correct.
