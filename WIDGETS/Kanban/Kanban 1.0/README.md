# Kanban 1.0

## Overview <a href="#toc57294676" id="toc57294676"></a>

The **Kanban Widget** is a **versatile work management tool** designed to optimize processes across multiple stages. With its intuitive **drag-and-drop interface**, it provides a **clear and structured** way to track, organize, and manage work progress efficiently.

<figure><img src=".gitbook/assets/image (279).png" alt=""><figcaption></figcaption></figure>

#### **Key Use Cases**

The widget can be applied in various scenarios and business needs, including:

* **Manufacturing & Production** – Tracking work orders and monitoring process completion.
* **Project Management** – Organizing tasks, deadlines, and team activities.
* **Software Development** – Tracking feature development, bug fixes, and sprint progress.
* **Customer Support & Helpdesk** – Managing support tickets and service requests.

{% embed url="https://app.arcade.software/share/px2EPCOE6oG7W7bBZHAt" %}

#### **How It Works**

The Kanban board is composed of:

* **Columns:** Represent different stages, such as "To Do," "In Progress," and "Completed."
* **Cards:** Represent individual work items within each stage, containing key details like title, description, assignee, and status.

**Easy Configuration & Interaction**

Page developers can easily configure the widget using simple reports. When a user interacts with a card, the widget exports the corresponding **ID** value of the card and its status, as defined in the report. These parameters can then be used for further interactions and data processing within the page.

<figure><img src=".gitbook/assets/image (269).png" alt=""><figcaption></figcaption></figure>

### Customization Options

### Widget Settings (Configuration Panel)

These settings allow developers to **fine-tune the widget’s behavior** to match their use case:

* **Show item count:** This feature enables a card counter on the Kanban columns.

<figure><img src=".gitbook/assets/image (278).png" alt=""><figcaption></figcaption></figure>

* **Collapse Columns**: Enable users to collapse and expand Kanban stages for better space management.

<figure><img src=".gitbook/assets/image (277).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (275).png" alt=""><figcaption></figcaption></figure>

* **Read-Only Mode**: Disables user interaction, making the Kanban board a **view-only** tool.
* **Search Filter**: Enables a **search box** to filter cards based on keywords.

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption><p>Search cards based on Title keywords</p></figcaption></figure>

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption><p>Search cards based on Summary keywords</p></figcaption></figure>

{% hint style="success" %}
For a full list of configurable options, refer to the [Properties](./#toc57294678).&#x20;
{% endhint %}

### Report-Based Customization (Dynamic Adjustments)

Beyond the standard widget settings, the **Report Properties** enable the developers to customize the widget dynamically, including:

* **Column Status Icons:** Add distinctive icons to **Kanban board columns** for better identification.

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

* **Card Border Color Customization**: Assign **unique colors** to the left borders of each card using the `R02_card_color` field, helping visually differentiate card types.
* **Card Thumbnails**: Add **user avatars, icons, or small images** to visually represent cards.

<figure><img src=".gitbook/assets/image (5).png" alt="" width="162"><figcaption></figcaption></figure>

* [**Interactive Data Exploration**](documentation/kanban-1.0/interactive-kanban-drill-through-configuration.md): Enable **drill-through functionality** to allow users to open detailed reports or additional insights by clicking on a card.&#x20;

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Refer to the [Report Mapping](./#report-mapping) section for detailed configuration.
{% endhint %}

## Report Mapping

The **Kanban** widget is classified as a **Data Presentation** widget that requires two **data sources (reports):**

**Report 1: Kanban Columns (Board Statuses) \[REQUIRED]**

Defines the **stages of the kanban**, which will be displayed as columns.

**Mandatory Fields**

* `R01_status_id`**:** Unique identifier of the board column. It must match `R02_status_id` in Report 2.
* `R01_status`**:** The title of the board column (e.g., "To Do", "In Progress"). It is displayed as the column header.

**Optional Field**

* `R01_status_icon`**:** Icon is shown before the title of the board column. Used for quick visual identification.

**Report 2: Kanban Cards \[REQUIRED]**

**Mandatory Fields**

* `R02_status_id`**:** Unique identifier of the associated board column (from Report 1).
* `R02_card_id`**:** Unique identifier of the card.
* `R02_title`: The title of the card. Displayed as the main label of the card.

**Optional Field**

* `R02_summary`: Description or additional details of the card.
* `R02_assignee`: The entity (user, team, production line, department, etc) responsible for the card.
* `R02_thumbnail`**:** The URL to a small icon or picture that represents the cards. If the URL is external, the CSP must be properly configured.&#x20;

{% hint style="warning" %}
Please refer to the App Composer installation guide to configure the CSP policies for App Composer: [https://dac-documentation-1.gitbook.io/installation-guides/](https://dac-documentation-1.gitbook.io/installation-guides/). By default, App Composer CSP policies do not allow embedding third-party websites, and thus you need to configure the services to enable it.
{% endhint %}

* `R02_card_color`: Hex, RGB, or color name for the left border of the card helps differentiate card types visually.

### **Field Mapping Example**

Following the field mapping example for the **Report 1:** **Kanban Columns**

<figure><img src=".gitbook/assets/image (257).png" alt="" width="563"><figcaption></figcaption></figure>

Following the field mapping example for the **Report 2:** **Kanban Cards**

<figure><img src=".gitbook/assets/image (260).png" alt=""><figcaption></figcaption></figure>

Ensure that the fields of **Report 1** and **Report 2** are correctly mapped in the **Fields Association** property of the widget to ensure proper functionality.

<figure><img src=".gitbook/assets/image (281).png" alt=""><figcaption></figcaption></figure>

## Properties <a href="#toc57294678" id="toc57294678"></a>

The properties that are specific for the configuration of the **Kanban** widget on **Decisyon App Composer** are listed below:

<table data-full-width="true"><thead><tr><th width="246">Group</th><th width="167">Name</th><th width="608">Description</th><th width="394" align="center">Type</th><th width="800">Select Value</th><th width="129" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td><code>report data source number</code></td><td>Allows you to define the number of report data sources that provide the dataset to the widget. When defining more than one report, then they should be associated with the <code>report datasource</code> properties.</td><td align="center">TEXTFIELD</td><td></td><td align="center">1</td><td>false</td></tr><tr><td><strong>Main</strong></td><td><code>report data source</code></td><td>Allows you to associate one or more reports to the widget, based on the number of data sources specified in the <code>report datasource number</code> property.</td><td align="center">SELECT</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>ObjectStyle</strong></td><td><code>fields association</code></td><td>Allows you to map the report columns with the specific fields.</td><td align="center">SELECT</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>Widget settings/Setting Preference</strong></td><td><code>allow toggle</code></td><td>If true, it enables column collapse.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Widget settings/Setting Preference</strong></td><td><code>drag card button id</code></td><td>Sets the ID of an Execute Object widget to be triggered when a card is dragged.</td><td align="center">TEXTFIELD</td><td></td><td align="center"></td><td>false</td></tr><tr><td><strong>Widget settings/Setting Preference</strong></td><td><code>enable search filter</code></td><td>If set to <code>true</code>, a search box is displayed to filter cards on the Kanban board. The filter applies to both the card title and summary fields.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">1</td><td>false</td></tr><tr><td><strong>Widget settings/Setting Preference</strong></td><td><code>read only</code></td><td>If set to <code>true</code>, the Kanban widget enables read-only mode. In this mode, derived parameters will still be exported, but users will not be able to drag cards or perform any CRUD operations on them.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">0</td><td>false</td></tr><tr><td><strong>Widget settings/Setting Preference</strong></td><td><code>show item count</code></td><td>If true, it shows a card counter for each Kanban column.</td><td align="center">SWITCH</td><td>1,0</td><td align="center">1</td><td>false</td></tr></tbody></table>

## Widget Parameters

In the `base name` widget's property, it is possible to specify a baseName to identify the widget's parameters and compose them uniquely.

**Exported Parameters**

The following parameter is exported by the **Kanban** widget on the click (or double-click) event of the card:

| Name                   | Description                          |
| ---------------------- | ------------------------------------ |
| `{baseName}_status_id` | Exports the ID values of the status. |
| `{baseName}_card_id`   | Exports the ID values of the card.   |

<figure><img src=".gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>
