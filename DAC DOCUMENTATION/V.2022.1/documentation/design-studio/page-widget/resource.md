# Resource

Other components can be inserted in a dashboard:

* An image
* Some text, to enter free format text and especially useful for entering HTML code in the Page page, other than the one managed by the system
* An object dedicated to JavaScript code to be used in the page

### Image (Deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

The **Image** object lets you insert an image in any format (JPEG, GIF, BITMAP, etc.).

The specific configuration properties are as follows

* _**Image**_ (_Image_ group) to select the resource relating to the image;

The image file needs to be inserted ahead of time in the resource catalog.

* _**wiDSh**_ and _**height**_ (_Image_ group): wiDSh and height of the image.
* _**tooltip**_ (_Image_ group) tooltip to be associated with the image
* _**javascript-code-onClick**_ (_Events_ group) opens the window to enter the JavaScript code, which will be run by clicking on the image

### Plain text

The **Text** object enters the free text, particularly useful to enter HTML code in the Page page, unlike the one managed by the system.

The specific property is the following

* _**text**_: sets the text contained in the element

The following example shows an advanced use of the Text component, together with the publication of an image.

Step 1: Using Text and Image components

![](<../../../.gitbook/assets/112 (2).png>)

_The example shows a Page page that contains a bubble graph. In addition to the Graph component, Image and Text components were also inserted. The first displays the Decisyon logo while the Text object was associated with an image that will serve as a button. Clicking on it will open another page (this is also an image) that displays detailed information about the type of graph. These operations are linked with each other through the HTML code._

Step 2: Using the Image component

![](<../../../.gitbook/assets/113 (3).png>)

_A Page page is created that contains:_

_A Graph object, in this example a bubble graph is displayed._

_An Image object that will display the Decisyon logo._

_In the resource property, the name of the file ‘logoDcy.jpg’ was entered. This file is located in the DAC_

_customization/IMG folder._

Step 3: Using the Text component

![](<../../../.gitbook/assets/114 (3).png>)

_The Text object will display the_ ![](<../../../.gitbook/assets/115 (4).png>)_icon from which a second image can be accessed, that will display the detailed information on the bubble graph._

_Two images are inserted in the DAC customization/IMG folder, one relating to the icon named "1297265268\_info.png" and one relating to the detailed information on the graph, named "Info Bubble.jpg"_

_The HTML code for creating the link is inserted in the window that is enabled from the text property._

_The code is as follows:_

**\<a href="#images" onclick="window.open('../../customizations/img/Info Bubble.JPG','','wiDSh=1024,height=480')">**

**\<img src="../../customizations/img/1297265268\_info.png" border="0" alt="Info Bubble Graph">**

**\</a>**

_The first link opens the detailed image ‘Info Bubble.JPG'. The dimensions of the window will be 1024x480._

_The second link displays the icon_ ![](../../../.gitbook/assets/116.png)_((\<img src="../../customizations/img/1297265268\_info.png" border="0" alt="Info Bubble Graph">)_

### JavaScript

Use the JavaScript object to define the JavaScript code to be used in the same page, such as the Execute button.

The specific properties of this object are:

* _**javascript-code**_ which enables opening the window to enter the JavaScript code.

If some parameters of the Page are used in the JavaScript code, each time these parameters are valued the system runs the code in the component again.

An **example** of using this component is below.

The Page in the example is a mask to enter orders; when data is entered in _a mask_ in a suitable table via the _Execute button_ component, a report will show the data that was just entered (_Crosstab_ object).

For the report to be updated, the new data will be associated with a _JavaScript_ to select the function predefined to update the Page. The JavaScript will be performed after updating the data in the table. The WAIT icon is published while you wait for the updated report, as defined via the predefined JavaScript function.

Another JS code is added for printing the date including the time (top right).

![](<../../../.gitbook/assets/117 (3).png>)

Step 1: Creating the Page

![](<../../../.gitbook/assets/118 (3).png>)

_The figure shows the components which the Page consists of._

_JavaScript and Execute button are the components of interest._

_The first JAVASCRIPT (#1) serves as a container to declare the two functions:_

* _exec function():which recalls the updating function of the current Page:_

_extERefreshCurrentDashbaord()_

* _Wait() Function: which recalls the display function of the wait image:_

&#x20;_extShowWait()_

_EXECUTE BUTTON (#2) runs the query to update the data entered in the mask._

_In the JavaScript the Execute button has two functions associated:_

* _JavaScript-code-before: before the update, but after clicking the button, it runs the function to display the wait icon: “Wait()”_
* _JavaScript-code-after: after updating the data, it runs the Page update function “exec()”_

_The second JAVASCRIPT (#3) occupies a specific position inside the Page page, since a printing function for the current date and time is declared inside it._

Step 2: Viewing in DAC

![](<../../../.gitbook/assets/119 (4).png>)

_Viewing in DAC_

_Step 1: the user enters the data in a mask and presses the Add to Order ( Execute button) button)_

_In a completely transparent manner for the user, the system runs the update query showing the wait icon._

_Step 2: At the end of the query the icon disappears and the Page is updated:_

_Note that the report shows an additional row with the last data entered._

_In the top right the current date and time are displayed._
