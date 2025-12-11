# User Attributes

DAC allows user attributes to be used not only in the formulas for metrics and levels, but also in the following objects:

* Security filters
* View Filter of the reports
* Default values or filter conditions in the Pages

At the workspace level it is possible to define the attributes that will then be applied for each user. The attributes are configurable only by administrator users. To create a new attribute, select User Attribute item from the Vertical Toolbar.![](blob:https://decisyon.atlassian.net/390e743b-73cc-4a97-a36e-5cd8775609a2#media-blob-url=true\&id=288e2fdb-bed4-4048-ac91-a6c3a3111572\&collection=contentId-2025652251\&contextId=2025652251\&mimeType=image%2Fpng\&name=image-20210525-090723.png\&size=59201\&width=1004\&height=639)

The User Attributes configuration page has 5 attributes ready to be configured. Selecting an attribute on the right the panel opens up for defining the attribute.

* **Tag**: set unique attribute tag
* **Name**: set attribute name
* **Type**: set attribute type:
  * Text
  * Numeric
  * Boolean
  * Dropdown
* **Required:** define if the attribute is requires.
* **Default Value:** define a default value.

For the Dropdown type it’s possible to define:

* **Enable multiple selection :** allows to enable the multiple selection values
* **Application:** select the application that contains the associate report.
* **Report:** select the report
* **Dependencies :** select a set of attributes the attribute depend on. For example MONTH attribute, it depends on the selection made on the YEAR attribute .

See the video to learn how to configure a new attribute



{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/UserAttribute/UserAttribute.mp4" %}



