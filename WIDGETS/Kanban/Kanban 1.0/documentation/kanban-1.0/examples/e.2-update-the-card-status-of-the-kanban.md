---
description: >-
  This guide provides a step-by-step tutorial on configuring the Kanban widget
  to update the status of a card in the database when it is dragged into a
  different column.
---

# E.2 Update the Card Status of the Kanban

The Kanban widget allows business users to update card statuses dynamically by dragging them across columns. Before proceeding, ensure that you have successfully completed the previous tutorial: **E.1 Configuring an Interactive Kanban Widget**

## 🔧Prerequisites

* Completion of[ **E.1 Configuring an Interactive Kanban Widget**](e.1-configuring-an-interactive-kanban-widget.md)
* A properly configured **Kanban widget**

## Tutorial Steps <a href="#tutorial-steps" id="tutorial-steps"></a>

{% stepper %}
{% step %}
## 📊Step 1: Create a New Page in Page Design

### 1. Create a New Page:

* Open the **Page Design** and create a new page by duplicating the page "Kanban E.1" from the first tutorial.
* Rename the new page (e.g., "Kanban E.2").

### 2. Add the Required Widgets:

* Drag a **Smart Grid** and an **Execute button** widget onto the page.

<figure><img src="../../../.gitbook/assets/image (285).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ⚙️Step 2. Configure the Widget Properties

Once the widgets are placed on the page, configure their properties as follows:

### 1. Configure the Smart Grid Properties: <a href="#configure-the-text-field-properties" id="configure-the-text-field-properties"></a>

**Main**

* `report datasource (1)`: Associate the "_Kanban\_cards\_ex1_" created in the firts tutorial.&#x20;

{% hint style="info" %}
This setup ensures that card status updates are reflected in the database and displayed in the smart grid when a card is moved.
{% endhint %}

### 2. Configure the Execute button Properties: <a href="#configure-the-text-field-properties" id="configure-the-text-field-properties"></a>

**Object Tab / Execution**

* `execution-type:` Select **QUERY** from the dropdown list to define the button’s execution type.
* `sql-formula`: Enter and save the following SQL query, which updates the card's status in the database when moved:

```sql
UPDATE "schema_name".kanban_cards_ex1
SET r02_status_id =?Kanban_status_id?
WHERE r02_card_id =?Kanban_card_id?
```

{% hint style="info" %}
This query ensures that when a card is dragged to a new column, its `r02_status_id` is updated in the database. The `Kanban_status_id` and `Kanban_card_id` parameters must be configured in the page.
{% endhint %}

**Container Tab / ContainerStyle**

* `visibility`: Set to **hidden** to ensure the button is not visible. The execution will be triggered automatically when a card is dragged.

**Advanced Tab / Advanced**

* `custom-js-id`: Set the id of the button (e.g. "update"). This ID will be necessary to link the excution of the button with the Kanban.&#x20;

### 3. Configure the Kanban Properties: <a href="#configure-the-text-field-properties" id="configure-the-text-field-properties"></a>

* `drag card button id`: Set the same ID configured in the `custom-js-id` of the Execute button widget  (e.g., "update"). This ID will be link the execution of the button with the Kanban widget.

### &#x20;4. Save the Page:

* Save your newly configured page as "Kanban E.2".
{% endstep %}

{% step %}
## ✅Step 3: Test the Configuration

To ensure that the configuration works correctly, follow these steps:

### 1.  Access the Page:

* Open the page "**Kanban E.2**_"_ in the web application.
* Select a card (e.g., Card ID "107" with Status ID "1").

<figure><img src="../../../.gitbook/assets/image (290).png" alt=""><figcaption></figcaption></figure>

### 2.  **Drag a Card and Verify the Update:**

* Move the card to a different column to change its status.

<figure><img src="../../../.gitbook/assets/image (288).png" alt=""><figcaption></figcaption></figure>

* Refresh the page by double-clicking it.
* Confirm that the dragged card (Card ID = "107") has successfully updated its `Kanban_status_id`.
* Verify that the status field of the card in the Smart Grid displays the new value correctly.

<figure><img src="../../../.gitbook/assets/image (292).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
By following this guide, you have successfully configured the Kanban widget to update card statuses dynamically when dragged across columns.
{% endhint %}
{% endstep %}
{% endstepper %}
