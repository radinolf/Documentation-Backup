# User Attribute

DAC allows user attributes to be used not only in the formulas for metrics and levels, but also in the following objects:

* Security filters
* View Filter of the reports
* Default values or filter conditions in the Pages

At the workspace level it is possible to define the attributes that will then be applied for each user. The attributes are configurable only by administrator users. To create a new attribute, select User Attribute item from the Vertical Toolbar.

![](<../../.gitbook/assets/image (353).png>)

The User Attributes configuration page has 5 attributes ready to be configured. Selecting an attribute on the right the panel opens up for defining the attribute.

* **Tag**: set unique attribute tag
* **Name**: set attribute name
* **Type**: set attribute type:
  * Text
  * Numeric
  * Boolean
  * Dropdown
* **Required:** define if the attribute is requires. When an attribute is set as mandatory, it is mandatory to define a default value.
* **Default Value:** define a default value.

For the Dropdown type it’s possible to define:

* **Enable multiple selection :** allows to enable the multiple selection values
* **Application:** select the application that contains the associate report.
* **Report:** select the report
* **Dependencies :** select a set of attributes the attribute depend on. For example MONTH attribute, it depends on the selection made on the YEAR attribute .

See the video to learn how to configure a new attribute



{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/UserAttribute/UserAttribute.mp4" %}

