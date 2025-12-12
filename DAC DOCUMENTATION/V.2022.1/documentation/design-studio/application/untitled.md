---
description: >-
  The notification service is a complete contact management system which lets
  companies optimally manage their communication with user groups or single
  users.
---

# Notification Designer

The notification service is a complete contact management system which lets companies optimally manage their communication with user groups or single users. A management system allows users to create, review and send notification messages, without requiring users to always be connected to the application.

The type of notification is:

* Mai&#x6C;**,** where the notification is sent by e-mail;

From the **Application>> Notification Designer** menu, open the window that manages the notification service.

![](<../../../.gitbook/assets/0 (6).png>)

In the Mail notification we define the send mode, the recipients and the message with the title.

## Notification Transmission

Notifications can be sent instantly, by clicking the ![](<../../../.gitbook/assets/1 (10).png>) button.

During execution, the system displays the dialog window _Execution log_ which displays the different steps, detailing the instructions which are carried out.

The steps are highlighted in red if there are errors such as missing privileges, reports not found, etc. The figure shows an example where a user does not have the license to receive notifications.

![](<../../../.gitbook/assets/2 (25).png>)

Notifications can be also sent through:

* a schedule defined with the _Scheduler_ modul&#x65;_._
* via a command in a Page . In this case, the recipients can be set dynamically: we can select recipients on the Page, in addition to those set in the notification itself.
* SQL commands, when a JOB is created .

## Notification Recipients

You can select **Notification recipients** in the **Groups** section; you can choose them by groups or individually. To send the notification, DAC takes the information from user configuration, shown in the figure, which indicates the data used for each type of notification.

![](<../../../.gitbook/assets/3 (18).png>)

## Notification Message

Notification messages are composed of a title and the actual message. In the message it is possible to enter custom parameters, such as the username:

selecting the ![](<../../../.gitbook/assets/4 (7).png>) button will enter the keyword %SUBJECT%; this will be replaced by the corresponding recipient username, when the notification is sent.

![](<../../../.gitbook/assets/5 (20).png>)

For e-mail notifications, there are functions for the formatting of reports in text \[form].

## E-mail Notifications

With e-mail notifications, you can send reports and/or Pages in different formats, including DAC format.

The message can contain information about one or more reports formatted through Pattern.

For sending notification e-mails, the **mail server** must be defined in the _Server Designer_ module (see _Server connections_ section, parag. _SMTP server_) and then associated in the system properties _**associated–SMTP-server**_ ( _Tools properties_, _E-mail_ section, _System E-mails_ group)_._

To create this type of notification, select the **Create Mail notification** item from the pop-up menu on the _Root._

The sender of the email server may be defined, differently from the system-wide one (through the Server Designer) in the properties (_Main_ group):

* _**the default email-notification-sender**_ is identified, in parentheses, as the sender defined in the _email-sender_ property in the _Server designer_; this may be edited, entering a different email address to be used as the sender.
* _**the default email-sender-name**_ indicates, in parentheses, the name to be associated with the sender defined in the _email-sender-name_ property in the _Server designer_; this may be edited, entering a different name to be used as the sender.

You can associate one or more user groups to an e-mail notification, which must be CC'ed in the e-mail, using the property:

* _**CC**_ opens a window for selecting DAC groups and/or users to be added to the mailing list as CC. These users must also have a _Notification_ license. Users associated with multiple groups will receive only one copy of the email.

### **Report and Page Attachments**

You can choose the reports and Pages to attach to the e-mail using the appropriate buttons, as shown in the figure (_**Attachments**_ panel): the reports/Pages attached are placed in the bottom table. A menu is enabled for each one that allows you to select an export format.

The formats available for the **report** are:

* _PDF_ or _Excel_
* text (_TEXT_) or _CSV_
* or by directly accessing the report in DAC (WEB).

While a **Page** can be sent in the formats:

* PDF or Excel (configured beforehand)
* by directly accessing the Page in DAC (WEB).

the prior configuration of a Page must be completed in the Page Designer module

![](<../../../.gitbook/assets/6 (2).png>)

### **WEB Format**

The **WEB** format sends you a link that will allow you to directly access the report or the Page, without having to be authenticated.

![](../../../.gitbook/assets/7.png)

To use this type of format, you must set the address of DAC for the connection in the system properties:

* _**decisyonWebURL**_ (_Tools properties_, _Web section,_ _Connection_ group) enter the DAC link.

### **Report Pattern (formatting report in the message)**

The e-mail notification message can contain information from one or more reports, which are formatted according to patterns specified by the user instead of being sent in the usual tabular form.

For example, you can list products sold to a certain customer, in a text form such as: _Product X’ was sold to 'Client Y’ with sales for ‘sales value', where the_ product, the client and the sales value are given a value in the report.

The pattern is set in the _**pattern{n}**_ property (_Report Pattern_ group), enabled from the _**patterns-number**_ property (by default set to 0), which indicates the number of patterns you intend to define.

![](<../../../.gitbook/assets/8 (24).png>)

You can open a window from the _**pattern{n}**_ property, shown in the figure above, where you can select the report with the information to be formatted.

After choosing the report, _Column_ lists the references to the columns of the report itself: with the + **+**&#x62;utton (on the right) we input the references in the text area below, under _Pattern_, together with the desired textual form (an example is given by default).

The section to be used for the text (in HTML format) is enclosed between quotation marks and is linked to the report columns with the + command. **+**.

The preview button (shown in the picture) displays the text formatted according to the pattern input in the text area.

_Excel-like functions_ are also supported, selected with the button shown in the figure. The functions to format metric values are particularly useful.

After defining one or more patterns, you can input them in the message title or body, simply by indicating the reference to the chosen pattern: this enables a list for selecting the pattern, which you can input in the message by clicking the + Button.

![](<../../../.gitbook/assets/9 (6).png>)

An example of the application of the _Report Pattern_ method is shown below, where a text string is defined for the list of sales of each product and detail for the customer groups the product was sold to.

Example : Report Pattern

Step 1: Report Pattern

![](<../../../.gitbook/assets/10 (3).png>)

_We define an e-mail notification. In patterns-number we set the value 2: we enable the corresponding pattern{1} and pattern{2} properties._

_You define the e-mail message for the list of products sold with reference to the pattern{1}, and the detail list with reference to the pattern {2}._

Step 2: Report Pattern

![](<../../../.gitbook/assets/11 (7).png>)

_We define the report for the list of products sold: the report has the Product level and the metric Sales Val._

_In the pattern{1}, the window opens for defining the first pattern: the text shown in the figure is inserted._

_You can see the text form in the preview, where references to the corresponding report columns are shown._

Step 3: Report Pattern

![](<../../../.gitbook/assets/12 (22).png>)

_We define the report for the detail list (product sales and corresponding customer groups): the report will contain the Product and Customer Group, with the metric Sales Val._

_The window opens in pattern{2} for defining the second pattern, where we insert the text shown in the figure._

_You can see the text form in the preview, where references to the corresponding report columns are shown_**.**

Step 4: Report Pattern

![](<../../../.gitbook/assets/13 (5).png>)

_In the picture we see the e-mail message received by the user associated with the notification. The two parts of the message, corresponding to the patterns defined in the notification, are pointed out._
