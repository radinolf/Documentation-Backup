# User Attribute

## Introduction

User Attributes provide a structured way to collect additional data during user creation in App Composer, enabling customization of the user experience based on specific application requirements.



User Attributes allow application developers to create custom fields that they can fill in during the account creation process. This feature is especially useful when you need to collect additional information beyond basic user account details. With user attributes, you can gather data that is relevant to your application, such as user preferences, profile information, association to plant, departmetns or any other details that must be associated to a user.



User Attributes can be used as system parameters, associated with the logged-in user's session. This allows for dynamic customization of various features within the App Composer, such as [User Filters](../data-mapping/users.md). For example, you can personalize user experiences, dynamically adjust page content, or implement conditional logic based on user input.



When user attributes are defined, they will be displayed in a dedicated tab of the user creation dialog.

<figure><img src="../../.gitbook/assets/image (1979).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
[Synchronization](../application-synchronization-wip/) of user attributes is not supported.
{% endhint %}

## Create New Attribute <a href="#how-to-create-new-attribute" id="how-to-create-new-attribute"></a>

To create a new attribute, select **Administration>>User Attribute** item from the Main Menu.

<figure><img src="../../.gitbook/assets/image (2026).png" alt=""><figcaption></figcaption></figure>

The attributes are configurable only by administrator users.&#x20;

Five attributes are available by default. To start we can use one of the default attribute. There isn't a limitation to the number of attributes it's possible to create

A new attribute can be created using the "Plus" icon in the top left of the page.

<figure><img src="../../.gitbook/assets/image (2027).png" alt=""><figcaption></figcaption></figure>

App Composer offers several configuration options for each user attribute to adapt to your requirements:

* **Tag**: it's a unique identifier of the user attribute and it will be the same identifier that can be re-use in other App Composer feature, such as [parameter pre-selection](../page-designer/) value in Page Designer.
* **Name**: it's the label that is displayed in the user creation dialog
* **Type**: define how the attribute will be rendeder in the user creation or user edit dialog. Select the type of attributes:
  * Text: it's the default, allows any text to be inputted.
  * Numeric: only numeric value are allowed
  * Boolean: it will be rendered as checkbox
  * Dropdown: select the items from a pre-defined list

In the image below we can see how to visualize the attributes in the User Administration interface.

<figure><img src="../../.gitbook/assets/image (1975).png" alt=""><figcaption></figcaption></figure>

* **Required:** define if the attribute is required. When an attribute is set as mandatory, it is mandatory to define a default value on user creation.

<figure><img src="../../.gitbook/assets/image (1973).png" alt=""><figcaption></figcaption></figure>

* **Default Value:** define a default value that will be used in case on user creation the attribute will not be configured..

{% hint style="warning" %}
Please note that when a custom attribute is defined as required, the automatic user creation from an external OIDC provider (i.e. Microsoft Active Directory or Schneider IDMS) will fails because the OIDC will not be able to provide any value for the mandatory custom attribute.
{% endhint %}

## Dropdown attribute configuration <a href="#dropdwon-attribute-configuration" id="dropdwon-attribute-configuration"></a>

The "Dropdown" type within the User Attributes configuration offers valuable flexibility for collecting user data in a structured and user-friendly manner.&#x20;

The dropdown options can be dynamically populated from application's [reports](../report/), ensuring that users have access to the records available in the report.



It's possible to configure the following properties:&#x20;

* **Enable multiple selection :** enable multiple selections within the dropdown. This can be particularly useful when users need to choose from a list of options that are not mutually exclusive. The items selected will be exported as a comma separated string.
* **Application:** select the application that contains the report you want to associated
* **Report:** select the report that contains the options to be displayed in the dropdown
* **Dependencies :** You can create cascading dropdowns, where the selection in one user attribute dropdown dynamically change the available options in another dropdown. For example, _Department_ attribute may depends on the selection of the _Plant_ attribute .

<figure><img src="../../.gitbook/assets/image (2028).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
When using attribute of type "Dropdown", make sure you have already created the report
{% endhint %}

When a report is associated to the dropdown, the list of items used in the dropdown will comes from the first level positioned on the rows of the report. Please note that if you have duplicated values, they will create two options in the dropdown: in case you need a value with distinct option, you need to modify the report accordingly. The report has no structural constraints and may have even more than one level or pageby, but the list of values displayed in the dropdown refers to the values contained in the first column to the left of the report.

<figure><img src="../../.gitbook/assets/image (2031).png" alt=""><figcaption><p>Example of report associated to a dropdown attribute. Please note this report doesn't have distinct plant values.</p></figcaption></figure>



The value assigned to the user attributes is the value of the **ID column** configured in the level

The label displayed in the dropdown options is the value of the **Description column** configured in the level.

#### Reports with multiple columns Associated with a Dropdown User Attribute

In the example below we have a report containing several columns.

<figure><img src="../../.gitbook/assets/image (1977).png" alt=""><figcaption></figcaption></figure>

&#x20;When a report has multiple columns and is used as a report for a dropdown attribute, the lost values taken into account are only those of the first column on the left.U

<figure><img src="../../.gitbook/assets/image (1976).png" alt=""><figcaption><p>Example of report multi columns  associated to a dropdown attribute. Please note attribute use the Values in the first Left Column of the report</p></figcaption></figure>



## How to use the attribute into the User Filters <a href="#how-to-use-the-attribute-into-the-user-filters" id="how-to-use-the-attribute-into-the-user-filters"></a>

When creating a User Filter that intends to use an attribute, you must include the tag defined during the attribute creation within the filter.

In the example below, the Plant attribute is tagged as `U_attribute_1`.

<figure><img src="../../.gitbook/assets/image (2032).png" alt=""><figcaption></figcaption></figure>

When defining the User Filter, you can include in the formula the tag, so that it will be replaced at runtime with the value associated to the connected user.&#x20;

```sql
Plant_Cd@ID = '%U_attribute_1%'
```

<figure><img src="../../.gitbook/assets/image (1978).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Typing the % character activates the tag selection menu.
{% endhint %}

## How to use the attribute into the View Filters <a href="#how-to-use-the-attribute-into-the-view-filters" id="how-to-use-the-attribute-into-the-view-filters"></a>

In the image below, an example of a View Filter is displayed, where the formula includes the tag defined for the user attribute.



<figure><img src="../../.gitbook/assets/image (2034).png" alt=""><figcaption></figcaption></figure>

## How to use the attribute in the default values or filter conditions in the Pages.

In the image we can see how the user attribute is associated with the pre-selection parameters of a page.

Select the property **pre-selection-values** and select the tag for the attribute in the list of values.

<figure><img src="../../.gitbook/assets/image (2035).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Please refer to [Page Propert](../page-designer/page-properties/)[ies ](../page-designer/page-properties/)fro more information
{% endhint %}



##

