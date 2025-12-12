# Discussion

DAC provides a Collaboration solution to associate comments, production notes or other information to the data available in the reports. The users are given the ability to reply and initiate a discussion.

<figure><img src="../../../.gitbook/assets/2442035280.png" alt=""><figcaption></figcaption></figure>

To enable report discussion, select the **Collaboration** property group from the **Properties** tab.

<figure><img src="../../../.gitbook/assets/2442231879.png" alt=""><figcaption></figcaption></figure>

* **activateCellsDiscussion** enables the Attach Discussion item in the pop-up menu of DAC report cells. This property enables the following:
  * **shared-context** enables context sharing with other reports, so that discussions in it can be useful not only on the report itself, but also on other reports.
  * **context-id** is the shared context identifier if, for example, two reports have the same context-id when a discussion is submitted on a certain level (such as product), this will also be visible on the second report. Please see **Share the context**

**Note:** Users can comment on or change Discussions on all the reports that share the context, if they have the permissions on at least one of the reports.

### Content Menu <a href="#discussion-contentmenu" id="discussion-contentmenu"></a>

For each message there is a menu on the right with the following items:

* **Edit**: to edit the message
* **Remove**: permanently removes the message
* **I’m not interested** / **I’m interested** : you can decide whether or not to receive notifications for a discussion

### Edit Message <a href="#discussion-editmessage" id="discussion-editmessage"></a>

To edit a message, select Edit from the menu. You can edit both the text of the message and remove any attached documents.

<figure><img src="../../../.gitbook/assets/2442231871.png" alt=""><figcaption></figcaption></figure>

### **Remove message** <a href="#discussion-removemessage" id="discussion-removemessage"></a>

To remove a message, select **Remove** from the side menu.

<figure><img src="../../../.gitbook/assets/image (922).png" alt=""><figcaption></figcaption></figure>

Both the message and any attachments will be permanently removed. The message will be removed from the discussion but there is still a trace of it.

<figure><img src="../../../.gitbook/assets/image (310).png" alt=""><figcaption></figcaption></figure>

### How to follow or not a discussion <a href="#discussion-howtofollowornotadiscussion" id="discussion-howtofollowornotadiscussion"></a>

When you are interested in following a discussion opened by another user you can activate from the side menu of the discussion the option **I’m interested.**

<figure><img src="../../../.gitbook/assets/image (1140).png" alt=""><figcaption></figcaption></figure>

The DAC will send a notification ([**Notification section**](../../app-functionality/untitled.md)) every time new messages are inserted for the discussion you are interested in.

<figure><img src="../../../.gitbook/assets/image (948).png" alt=""><figcaption></figcaption></figure>

If you are not interested in the discussion you can select the option **I’m not interested**

<figure><img src="../../../.gitbook/assets/2442264658.png" alt=""><figcaption></figcaption></figure>

### How to reply to a message <a href="#discussion-howtoreplytoamessage" id="discussion-howtoreplytoamessage"></a>

To reply to a message, select the replay item at the bottom right and enter a new message and any attachments.

<figure><img src="../../../.gitbook/assets/2442166374.png" alt=""><figcaption></figcaption></figure>

#### Enabling Page widget  <a href="#discussion-enablingpagecomponents" id="discussion-enablingpagecomponents"></a>

The Page widget on which discussions can be used are:

* Table
* Crosstabs
* Graph

You can enable the use of discussions on these components in DAC by enabling the **activateDiscussions** property in the **Title** group.

This will allow DAC users to enter discussions. The icon identifying the discussions appears on the title of the component, and from this users can enter their messages.

**Step 1: Enabling Discussion Page component**

<figure><img src="../../../.gitbook/assets/2442559489.png" alt=""><figcaption></figcaption></figure>

Enable a graph component to use annotations. Create a Page with a graph component.

* Enable annotations: activateDiscussion property of the Title group

**Step 2: Using Discussions on DAC**

<figure><img src="../../../.gitbook/assets/image (366).png" alt=""><figcaption></figcaption></figure>

Access the Page created in step 1. The Discussion icon will be on the graph title. Move to the icon and click it to open the callout and insert a message.

### Share the context <a href="#discussion-sharethecontext" id="discussion-sharethecontext"></a>

Open discussions on one level of a report can be shared on all reports that have that level. To do this, it will be enough to activate the **shared-context** property for all the reports that will share the context and associate the same context identifier in the **Constex-id property**.

In the example below we have the Report A and the Report B. Both have selected the **shared-context** property and inserted the same context identifier Context-id.

* **shared-context** is active
  * **context-id** : ID01

<figure><img src="../../../.gitbook/assets/image (1025).png" alt=""><figcaption></figcaption></figure>

When we go from Web to create a discussion for example on a Plant, after updating the page, the same discussion will be displayed on the same plant of the report B.

