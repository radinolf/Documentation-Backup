# Discussion

DAC provides a Collaboration solution to associate comments, production notes or other information to the data available in the reports. The users are given the ability to reply and initiate a discussion.

The components in the **Collaboration** group let you start the discussions among different user groups.

The components available are:

* ![](<../../../.gitbook/assets/100 (2).png>) **Discussions**

Allows discussions to be opened, possibly on a specific topic.

* ![](<../../../.gitbook/assets/101 (2).png>) **Discussions stream**

Collector of open discussions in various sections of the system and belonging to the same subjects.

The discussions can also be enabled for some of the Page components.

### Discussions

The _**Discussion**_ object allows users to publish one or more discussions.

These can also be linked to one specific subject; the subject to link the discussion to is defined by one or more dimensional levels, chosen from those exported to the Page page.

When you select a level value, you can display or create discussions relating to the selected value.

For example if _Discussions_ are defined with respect to the ‘Business Unit’ level, discussions may begin concerning one of the Business Units (in the example a discussion was opened concerning ‘Fridges and Freezers’).

This way, when selecting a level, only discussions opened for that specific value will be visible.

However, you do not need to set a level as a subject of the discussion.

In the event the **permissions are deleted** on the Page containing the discussions, the discussions will remain visible as long as no one enters comments in the discussion.

![](<../../../.gitbook/assets/102 (3).png>)

The discussions are displayed in a “social network like” mode, i.e. from top to bottom, with replies _indented_ compared to the main subject.

Other users can reply by posting comments and attaching files, and thus have a real conversation on the subject.

The properties for configuring the object are (_Discussions_ group):

* **context-parameters**

It will be possible to select one or more dimensional levels exported by the page objects.

These levels identify the topic of the discussion, something that is not required.

* **context-root-ID**

ID generated automatically by the system, initially corresponding to the actual ID of the page in which it is included.

The ID can be changed manually. This makes the discussion easy to identify, so that it can be used by another _Discussion_ objec&#x74;_._

In fact, if two _Discussion_ objects have the _same context-root-ID_, they will display the same discussions.

This configuration is useful for displaying the same discussions on different Page pages.

**Note**: The discussions open on the object are linked to _the context-root-ID_. When this is renamed, all discussions linked to the modified name will be lost. You can restore them if _the context-root-id_ is assigned the previous value.

* **allow-discussion-remove**

This deletes the discussion. If this property is enabled, you can delete the entire discussion. Otherwise, it isn’t possible to remove the discussion, even if it is possible to remove individual messages.

![](<../../../.gitbook/assets/103 (1).png>)

* **groups-post-enabled**

This sets the user groups authorized to post messages in the discussion. Unless otherwise specified, all groups are authorized to enter messages.

* **post-creation-execution-button**

This sets an action that will be executed after the _Discussion_ is created. You can choose an _Execute button_ object within the page. This will be executed after a new discussion is created.

**Note:** Once the execution of the Execute button is completed, a parameter is given a value that identifies the discussion just created.

The parameter is “?**lastCreatedDiscussionID?**“ and is available in the Page page. This is useful if you want to save the ID of the discussion together with the date or the user that generated it.

* **single-discussion**

This enables the creation of a single discussion. If this is activated, you cannot create multiple discussions associated with the same context.

* **activate-message-reply**

This allows you to reply to the discussion, by entering reply messages within the discussions.

* **enable-post-discussions-on-total:**

This enables a discussion to be created on a context parameter which has no value.

Step 1: Example:‘enable-post-discussions-on-total’

![](<../../../.gitbook/assets/104 (3).png>)

_Page 1 has a Discussion object where the context is related to the values of the Business Unit._

_Pages BU-Shoes, BU-Clothing and BU-Accessories have the Discussion object with the same context-root-ID and context-parameters of Page 1. When a message is entered in Page1, on the \[Total] element, this message is displayed in all the other Pages, even if a user filter was applied in these for a specific context parameter (e.g.: Business Unit=Clothing)._

Step 1: Creating Pages

![](<../../../.gitbook/assets/105 (4).png>)

_This example shows how to set properties so that objects can communicate between themselves. Let’s assume you want to start a discussion to analyze the Business Units included in a report._

1. _You export the Business Unit level from the ‘Business Unit’ report._
2. _For the Discussion object we set:_

* _as context-parameter the Business\_Unit level exported from the previous report_
* _in the groups-post-enabled property, you associate the user group enabled to enter messages_
* _you enable the show-title-field property so that users are able to enter a title for the discussion._

_The context-parameter and the context-root-id define the context of your discussion._

_Note: If you want to show the same discussions opened on this object in another dashboard, all you have to do is to make sure the other dashboard contains a Discussion object with the same context-root-ID assigned (in this example Sales\_BU)._

### Discussion Stream

The object of the _**Discussion Stream**_ Page allows you to view discussions opened in one or more _Discussion_ objects: it will act as a **collector for the discussions** opened in various sections of the system, and, for example, on the same subjects.

The _Discussions_ displayed in this object have the same features as the Discussion object and will be configured again, in a rather similar way to the _Discussion_ objec&#x74;_._

![](<../../../.gitbook/assets/106 (1).png>)

The properties to configure the _Discussion Stream_ object (_Discussions stream_ group) are:

* **associated-collaboration-objects**

to select the _Discussion_ objects that will contribute to the stream:

Pages containing at least one _Discussion_ object are listed, with the context-root-ID of the Discussion itself in brackets.

* **context-parameters**

to select one or more dimensional levels exported by page objects.

These levels filter the discussion context and display only the discussions open at the chosen level.

Selecting a level is not required; if no level is selected, all open discussions of the Discussion objects associated with the stream will be presented.

* **allow-discussion-remove**

This deletes the discussion. If this property is enabled, you can delete the entire discussion. Otherwise, it will not be possible to remove the discussion, even if it is possible to remove individual messages.

* **groups-post-enabled**

This sets the user groups that are enabled to post messages in the discussion. Unless otherwise specified, all groups are able to post messages.

* **activate-message-reply**

This enables users to reply to the discussion, posting messages in the discussions.

By default, you can only view discussions on the Pages that you can access.

It is possible to allow users to also view dashboards they have no access to through the property (_Filter_ group):

* **filter-viewable-Pages**

This property is selected by default. If it is disabled, all discussions will be visible, even those open on Pages which users do not have access privileges for.

In the event **the permissions are deleted** on one of the Pages containing the discussions and the property **filter-viewable-Pages** is disabled, these will remain visible and active.

In addition, you'll be able to access the discussions associated with the cells of a report even if there are no permissions for accessing that report, but you won't be able to comment on, edit or create new discussions. Furthermore, notifications continue to be received in Incoming mail and in e-mail notifications if enabled.

The following example shows a possible configuration for the _Discussion Stream_ object.

Step 1: View in DAC

![](<../../../.gitbook/assets/image (226).png>)

_Suppose you want to gather all the discussions opened in the Pages displayed in the figure (Discussion 1 and Discussion 2)._

_The Discussion object created in the ‘Discussion 1’ Page was named ‘Discussion1’, using the context-root-ID property. The Discussion object of the ‘Discussion 2’ Page was named ‘Discussion2’._

Step 2: Creating Pages

![](<../../../.gitbook/assets/108 (2).png>)

_You can create a Page that includes the Discussion Stream object. For this to work, the following properties need to be set:_

_context-parameters select the Business unit level exported by the above report._

_associated-collaboration-objects from the menu window select the Discussion objects to be displayed in the Document Stream: Discussion 1 (Discussion1) and Discussion 2 (Discussion2)._

3.Display in DAC

![](<../../../.gitbook/assets/109 (2).png>)

_The Discussion Stream object is displayed as in the picture._

_It will show the list of discussions open within the Discussion object._

_When you select a Business Unit from the report (which exports this level), it will act as a Filter. The Document Stream will display only the discussions linked to the selected Business Unit, but open on both the Discussion objects of the other Pages._

### Enabling Page Components

The Page components on which discussions can be used are:

* Table
* Crosstabs
* Graph
* Flag Setup
* Indicator

You can enable the use of discussions on these components in DAC by enabling the **activateDiscussions** property in the **Title** group.

This will allow DAC users to enter discussions. The icon identifying the discussions appears on the title of the component, and from this users can enter their messages.

Step 1: Enabling Discussion Page component

![](<../../../.gitbook/assets/110 (1).png>)

_Enable a graph component to use annotations. Create a Page with a graph component._

* _Enable annotations: activateDiscussion property of the Title group_

Step 2: Using Discussions on DAC

![](<../../../.gitbook/assets/111 (3).png>)

_Access the Page created in step 1. The Discussion icon will be on the graph title. Move to the icon and click it to open the callout and insert a message._
