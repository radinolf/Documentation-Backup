# Tab Control

The _Tab Control_ is a Page container. It is inserted in a main Page and shows various Pages by simply selecting the TABs associated with them.

The parameters of the main Page may be used as a filter in the Pages contained in the Tab Control. Developers may define whether the filters are applied instantly (i.e. when choosing each value) or only when selecting the Pages of the Tab Control so there isn’t a refresh when selecting each parameter, but rather a single refresh requested after the selection of all the parameters of interest.

![](<.gitbook/assets/image (1).png>)

You can change from one TAB to another in automatic mode, by respecting a default time-out; the opening of the different TABS can be set in different modes (fade-out, vertical or horizontal scrolling).

The initial TAB opened is also the default selection. In addition, moving from one tab to another can affect other page elements, and vice versa (selecting page elements can position a specific TAB).

If this element is open in drill-through from a report, it can receive the source parameters and filter the Pages associated with the _Tab Control_.

**Tab** **Control** consists of two components (in the _Containers folder_):

* _**Tab Selector**_ defines the TABS and the associated Pages
* _**Tab Panel**_ customizes the container of the Pages associated with the TAB of the _Tab Selector_ object

Below is an example of publishing the _Tab Control object_

_**Note:**_ _When images are associated with the Pages, these will be replaced in the TABs of the object._

### Tab Selector

The specific properties of the **Tab** **Selector** component are (_Object folder_):

* _**Tab-pages**_ _(Tabs_ grou&#x70;_)_ selection of the Pages to be associated with the TABS: open a pop-up with the Pages of the application.

For each Page selected, the following is enabled:

* _**Page(i)**_ reports the name of the Page selected in the previous property; the name of the Page is used as the name of the TAB.
* _**description**_ the description associated with the TAB, shown as tooltip when passing the mouse over.
* _**tab-panel**_ (_Settings_ group) selection of the _panel_ which will count the Pages chosen in the _tab-pages_ property: open a menu with the list of the _Tab Panels_ present in the Page.
* _**auto-select-tab**_ (_Settings_ grou&#x70;_**)**_ select the TAB to be shown at first access

If the property is set to \<none> no TAB is active and selected; as a result the Tab Panel component is not displayed until you select a specific TAB.

* _**parameter-name**_ (_Settings_ group) parameter associated with the Tab Control:

the parameter will be valued with the cardinal number of the selected TAB (1 for the first TAB, 2 for the second, etc.).

This parameter may be used:

* when importing, valued by other components of the page or a source that opens it in drill-through; the value of the parameter pre-selects the TAB being displayed
* when exporting, valued by the _Tab Selector_ with the cardinal number of the TAB being selected and used by other elements; for example each TAB change could change the value selection in a _Select_, when this is conditioned by the value of the parameter of the _Tab selector_.
* **slider height:** _(Settings group)_ sets the height of the object. No percentage values are acepted
* _**auto-select-tab**_ (_Settings_ group) enables/disables automatic sliding.

if _**auto-select-tab**_ is set to _\<none>_; as a consequence it is not possible to set the automatic sliding if a specific TAB is not set upon the first opening.

If the automatic sliding is active, the following property is enabled:

* _**interval-time**_ time interval to show the next TAB (in seconds); the time interval is applied after loading the current Page.
* **associatedImageSet :** Set the type and the size of the image.

### Tab Panel

The specific properties of the **Tab** **Panel** component are (_Object_ folder):

* _**name**_ (_Main_ group) name of the object
* _**transitionEffect**_ (_Settings_ group) transition effect on the TAB change
  * _**none**_ no effect is applied
  * _**fade**_ makes it dissolve
  * _**slide**_ sliding from the top downwards
  * _**slide\_left**_ sliding from right to left

this effect is not available if the _Tab Panel_ has the auto-expand property active (_Container_ folder, _Container Size_ group).

* _**auto-refresh-on-params-change**_ makes the refreshing of the parameters used as filter sync, in the Pages of the Tab Control. If disabled, the Pages of the tab control are refreshed only when selecting the Page.

Example: Tab Control

Step 1: Page Creation

![](<.gitbook/assets/image (2).png>)

_Create a new Page containing the Tab Selector and Tab Panel components. For the Tab Panel the following properties are set:_

* _name the name of the panel;_
* _Template-theme the theme of the container_
* _transitionEffect the type of transition for the TAB change_

_For the Tab Selector the following properties are set:_

* _tab-pages select the Page pages to be associated with the TABs_
* _tab-panel the panel name to be associated with the Tab Selector (defined before)._
* _Template-theme theme for the TABs._

Step 2: Page display

![](.gitbook/assets/image.png)

_The figure shows the Page Preview. Note that:_

* _for each Page page, a specific TAB was created, which takes the same name._
* _the Page pages can be browsed by simply selecting the desired TAB._

_If the auto-sliding property of the Tab Selector object had been enabled, this would have made the sliding of the Pages automatic._
