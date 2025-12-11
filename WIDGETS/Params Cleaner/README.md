# Params Cleaner

This object serves to restore the parameters of the page to the initial conditions.

![](.gitbook/assets/image.png)

The configuration of this component takes place through the properties of the _Main_ group:

* _**clean-type**_ type allows you to select whether to apply the reset operation to all parameters of the page (_\<all-params>_) or to a subset of them (_\<selection>_), which enables the property:
  * _**param-selection**_ for the selection of the parameters to be reset.
* _**reinit-page-By**_ to restore initial conditions, also of the values of the page-bys on the Page
* _**Custom-JS-code-after-params-clean**_ JavaScript code to be executed when the component is selected.

Restore the initial values of the parameters at the page level can also be enabled, rather than from the _Params Cleaner component._

For the text properties:

* _**button-text**_ (Group _Main_(Text) for the button (DEFAULT “_Settings cleaner_”).

**Note:** _The HTML code is not supported in the button text._

* _**formFontSize**_ (_ObjectStyle_ ) Size of the character to be used as text, for the button.
