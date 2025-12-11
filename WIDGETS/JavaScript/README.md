# JavaScript

Use the JavaScript object to define the JavaScript code to be used in the same page, such as the Execute button.

The specific properties of this object are:

* _**javascript-code**_ which enables opening the window to enter the JavaScript code.

If some parameters of the Page are used in the JavaScript code, each time these parameters are valued the system runs the code in the component again.

An **example** of using this component is below.

The Page in the example is a mask to enter orders; when data is entered in _a mask_ in a suitable table via the _Execute button_ component, a report will show the data that was just entered (_Crosstab_ object).

For the report to be updated, the new data will be associated with a _JavaScript_ to select the function predefined to update the Page. The JavaScript will be performed after updating the data in the table. The WAIT icon is published while you wait for the updated report, as defined via the predefined JavaScript function.

Another JS code is added for printing the date including the time (top right).

![](<.gitbook/assets/image (1).png>)

Step 1: Creating the Page

![](<.gitbook/assets/image (2).png>)

_The figure shows the components which the Page consists of._

_JavaScript and Execute buttons are the components of interest._

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

![](.gitbook/assets/image.png)

_Viewing in DAC_

_Step 1: the user enters the data in a mask and presses the Add to Order ( Execute button) button)_

_In a completely transparent manner for the user, the system runs the update query showing the wait icon._

_Step 2: At the end of the query the icon disappears and the Page is updated:_

_Note that the report shows an additional row with the last data entered._

_In the top right, the current date and time are displayed._
