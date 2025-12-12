# Discussions Stream

The object of the _**Discussions Stream**_ Page allows you to view discussions opened in one or more _Discussions_ objects: it will act as a **collector for the discussions** opened in various sections of the system, and, for example, on the same subjects.

The _Discussions_ displayed in this object have the same features as the Discussion object and will be configured again, in a rather similar way to the _Discussion_ objec&#x74;_._

![](<.gitbook/assets/image (5).png>)

The properties to configure the _Discussions Stream_ object (_Discussions stream_ group) are:

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

![](<.gitbook/assets/image (4).png>)

_Suppose you want to gather all the discussions opened in the Pages displayed in the figure (Discussion 1 and Discussion 2)._

_The Discussion object created in the ‘Discussion 1’ Page was named ‘Discussion1’, using the context-root-ID property. The Discussion object of the ‘Discussion 2’ Page was named ‘Discussion2’._

Step 2: Creating Pages

![](.gitbook/assets/image.png)

_You can create a Page that includes the Discussions Stream object. For this to work, the following properties need to be set:_

_context-parameters select the Business unit level exported by the above report._

_associated-collaboration-objects from the menu window select the Discussion objects to be displayed in the Document Stream: Discussion 1 (Discussion1) and Discussion 2 (Discussion2)._

3.Display in DAC

![](<.gitbook/assets/image (1).png>)

_The Discussions Stream object is displayed as in the picture._

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

![](<.gitbook/assets/image (2).png>)

_Enable a graph component to use annotations. Create a Page with a graph component._

* _Enable annotations: activateDiscussion property of the Title group_

Step 2: Using Discussions on DAC

![](<.gitbook/assets/image (3).png>)

_Access the Page created in step 1. The Discussion icon will be on the graph title. Move to the icon and click it to open the callout and insert a message._
