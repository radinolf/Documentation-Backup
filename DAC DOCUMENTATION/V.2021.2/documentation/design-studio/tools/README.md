---
description: Application administration tools
---

# Tools

### DAC Settings <a href="#dac-settings" id="dac-settings"></a>

Administrators can customize the language and graphic style of the DAC interface.

To change the language used in the application, choose the menu item:

**Tools >> DAC Settings >> Language,** and then select the language to use.

Close the DAC and login again in order to apply the language change. When you change the language, all the interface elements are affected, such as menu bars, tooltips, links, and buttons.

The language set on DAC-DS will be the same one displayed on DAC. If a new language is set on DAC, this will also be inherited from DAC-DS.

### Reminders for Administrators <a href="#reminders-for-administrators" id="reminders-for-administrators"></a>

Reminders are available to help administrators to correctly configure all the different DAC modules. These messages will appear as pop-ups when the administrator creates or configures an object. For example, when the addressees of a notice are chosen, a message appears to remind the administrator to give a special license to these users so that they can receive the notice.

The administrator can disable each of these messages with a flag, indicating that the display of the message is no longer wanted. Disabling messages is reserved to users with administrator privileges.

You can restore the reminder by selecting the menu item:

**Tools>> App Composer Settings Reset all reminders**

### **Administrator password** <a href="#administrator-password" id="administrator-password"></a>

Administrator user, after the first access to the DAC can change his password. To change the password used in the application, choose the menu item:

**Tools >> Administrtor Password**

![](https://gblobscdn.gitbook.com/assets%2F-MdzyD4-QFXT0gq0bnEU%2F-MeU3b6V6WFmrtpbJZoC%2F-MeU7E_xvQ1T_R4UWyE-%2Fimage.png?alt=media\&token=f83497ab-a459-4d3b-b19c-15f42e2259c3)



### Connecting to Servers

Some DAC-DS services require a connection to external servers to be able to be executed, for example, sending notifications (see Notification Designer)

The parameters for the connection to these servers are configured in the window opened from the menu item:

**Tools >> Servers & Server**

#### SMTP Server

The definition of a reference to a **SMTP Server** includes specifying the following properties:

·        **host-name**, reference to the machine that manages the SMTP service

·        **port-number**, port for accessing the service (default 25)

·        **smtp-security-protocol** allows the user to select whether the type of protocol used is SMTP (default) or SMTPS (for the SSL protocol).

·        **Smtp-authentication-protocol** lets you select whether the type of authentication protocol used is not encrypted or if it is SSL or TLS.

·        **mail-sender**, e-mail address to be used as sender, for the e-mails sent from this e-mail server

·        **mail-sender-name**, name to be associated with the sender

If the server requires authentication credentials, select the **useCredential** property (Access credential group), which enables:

·        **smtp-**/**username/smtp-password**, for entering the name and password of a user authorized to access the SMTP server

####
