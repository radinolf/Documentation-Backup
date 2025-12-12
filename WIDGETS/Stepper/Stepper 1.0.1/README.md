# Stepper 1.0.1

## Overview

The **Stepper** widget enables you to create a sequence of steps starting from a simple report. Use it to walk users through all the steps required to complete an action that requires several distinct actions.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/WidgetHub/Stepper/Stepper.mp4" %}

![](<.gitbook/assets/image (1).png>)

The picture shows an example to represent purchase order tracking. **Stepper** has icons and status colors that can be used to indicate whether the step is active or completed. The step ID will be exported as a parameter on the page when the user selects the step.  You can associate to the widget an action to recall an object (Report, Page, and Web page) and view detailed data inside a new window.

## Report Mapping

The **Stepper** is a Data Presentation type widget. It requires the association of a single data source report where each row represents a step. The data source must contain two mandatory fields (ID and Name), whereas the other fields determine the appearance of the widget:

1. **R01\_step\_id:** Unique identification of the step. It is mandatory.
2. **R01\_step\_name:** Name of the step, visible to the user. It is mandatory.
3. **R01\_step\_icon:** Icon element to represent each step. Enter the name of the angular material icon by referring to the website [https://material.io/icons/](https://material.io/icons/)
4. **R01\_primary\_color:** HEX code to be used as the background color of the step. If this field is not specified in the report, the widget will inherit the Primary color set on the Web Application (Logo and Colors settings).
5. **R01\_secondary\_color:** HEX code to be used for the border and the icon color. If this field is not specified in the report, the widget will inherit the Secondary color set on the Web Application (Logo and Colors settings).

![](<.gitbook/assets/image (4).png>)

The user can interact with the widget by clicking the step. It is possible to associate an action to recall an object (Report, Page, and Web page) and view detailed data inside a new window. See the picture below.

![](<.gitbook/assets/image (3).png>)

The Administrator can configure this feature directly on the data source report from the **Report Editor**<img src=".gitbook/assets/image (6).png" alt="" data-size="line">:&#x20;

**Report Properties tab > Drill-Through**&#x20;

* **You can only use one drill-through for this widget**

If you configure multiple drill-through in the report, only the first activated drill-through will be rendered by the widget.

* **The drill-through must be enabled on the Step ID or Step name column of the report**

If the drill-through is enabled on both the Step ID and Step name levels, only the one on the Step ID will be taken into by the widget.

* **The widget only supports the Contextual renderings drill-through**&#x20;

Not Contextual renderings drill-through will not be taken into by the widget.

* **When you set the following properties of the drill-through:**&#x20;

- [ ] **drill-through-grants:** the widget will inherit grants from the report.
- [ ] **drillThroughImage:** the image set in this property not will be taken into by the widget. The widget will only render icons defined in the report fields.&#x20;
- [ ] **drillThroughDesc:** the description will be used by the widget as the dialog title of the drill through.&#x20;

## Widget Parameters

**Exported Parameters**

The following parameter is exported by the **Stepper** widget on the click event of the Step:

| Name                  | Description                                                             | Note                                                                                |
| --------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| \<baseName>\_selected | Exports the identification code of the Step when the user clicks on it. | The Step ID code is defined in the data source report (see Report Mapping section). |

## Example <a href="#toc69201843" id="toc69201843"></a>

**Description:** The example shows how to configure an interactive **Stepper** that opens a page when the user clicks on the step. We are assuming the page opened by the step has already been created.

* Create the data source report. The report must have two mandatory fields, the identification code and the name of the step.&#x20;

![](<.gitbook/assets/image (10).png>)

For more details about creating your report, see the [Report Mapping](./#report-mapping) section.

* Configure the drill-through feature on the data source report previously created:

Set the following properties in the **Drill-Through tab** of the **Report Editor**<img src=".gitbook/assets/image (6).png" alt="" data-size="line">

* [ ] **activate drill-through 1:** enable the property;
* [ ] **show-on**: select **Link** in the **Contextual renderings** section;
* [ ] **drill-through-position**: select the ID column of your report;

![](<.gitbook/assets/image (8).png>)

* [ ] **openActionType**: select the **Page** option to set the object that you want to open via the drill\_through;
* [ ] In the **Page** property: select a page previously created.
* [ ] **drillThroughDesc:** set the description that will be used by the widget as the dialog title of the drill through (in this example "Questions").

- Create a new Page in the Page Design and use the **Stepper** widget. Associate the report created in the first step to the widget.
- Map the columns of the report in the **fields association** property of the widget.

![](<.gitbook/assets/image (12).png>)

* Configure the parameter exported by the widget when the user clicks the step:                                  &#x20;

- [ ] In the **Stepper** properties (**Parameters** group) enter the **base name**. In this example “**Stepper**”;
- [ ] Add a **Plain Text** widget to the page. Specify the **\<baseName>** parameter exported by the **Stepper** widget when the user clicks the step. The parameters name must respect the syntax **\<baseName>\_selected** (see the picture below):

![](<.gitbook/assets/image (11).png>)

* Display the **Stepper** widget on the Web Application. Click a Step to open the page and view detailed data.

![](<.gitbook/assets/image (7).png>)
