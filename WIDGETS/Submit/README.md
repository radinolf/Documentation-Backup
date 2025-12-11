# Submit

The action of the **Submit** component consists of making the page parameter changes effective on the data presentation objects.

In the Analysis by pane _of this_ Page, we select the values, which are filter parameters for the two graph and table objects.

Selecting the parameters has no effect on the two presentation objects. Whereas, if you click the _Send_ button (**Submit** component), the values of the parameters are applied to the graph and table, which will show the result of this filtering.

Also the **Submit** action is only enabled for data presentation components with the **refreshMethod** property set to _OnSubmit_.

For the text properties:

* _**button-text**_ (Group _Main_(Text) for the button (DEFAULT “_Submit_”)

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button

Finally, the properties:

**disabled** Enable/Disables the component

This property **may also be assigned a parameter** so that the visibility of the object is governed by it, rather than by a fixed value.

The button to the right of the property opens a pop-up, where the name of the parameter is entered.
