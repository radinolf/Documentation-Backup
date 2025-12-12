---
description: >-
  This guide walks you through setting up an interactive Pie Chart widget to
  visualize data. The widget enables users to click on chart slices and navigate
  to a predefined page for further analysis.
---

# E.1 Configuring an Interactive Pie Chart Widget

{% hint style="warning" %}
Before beginning, ensure that the target page for navigation already exists.
{% endhint %}

## 🔧Prerequisites

To complete this configuration, ensure you have access to a database where you can create a table to store KPI data. You will need to execute SQL scripts to:

1. Create the required table structure.
2. Populate the table with sample data.

### Create the Database Table and Insert Data

**SQL Script for Table Creation**

Replace `"schema_name"` with your actual schema name.

```sql
CREATE TABLE IF NOT EXISTS "schema_name".pie_chart_ex1 (
    defect_id INTEGER PRIMARY KEY, -- ID
    defect_type CHARACTER VARYING, -- Type of defect
    defect_count INTEGER, -- Number of defects 
    defect_color CHARACTER VARYING, -- HEX color code 
    tooltip_info TEXT -- Detailed info for tooltips
) TABLESPACE pg_default;
```

**SQL Script for Data Insertion**

Insert data into the table using the following script:

```sql
-- Insert data into the pie_chart_ex1 table 
INSERT INTO "schema_name".pie_chart_ex1 (defect_id, defect_type, defect_count, defect_color, tooltip_info) 
VALUES
    (1, 'Surface Scratches', 120, '#5DCFCA', 'Surface Scratches: 120 occurrences detected in final inspection.'),
    (2, 'Paint Defects', 85, '#C1E2BC', 'Paint Defects: 85 occurrences due to uneven coating.'),
    (3, 'Welding Issues', 60, '#F6DB5F', 'Welding Issues: 60 parts failed due to weak joints.'),
    (4, 'Component Misalignment', 45, '#F0576B', 'Component Misalignment: 45 occurrences, mostly in assembly.'),
    (5, 'Electrical Faults', 30, '#7E83C2', 'Electrical Faults: 30 issues found in the wiring system.');

```

## Tutorial Steps <a href="#tutorial-steps" id="tutorial-steps"></a>

{% stepper %}
{% step %}
## 🛠 Step 1: Create the Data Source (SQL Report)

### 1. Create a New SQL Report:&#x20;

* Open the **Report Design** tool <img src="../../../.gitbook/assets/image (136).png" alt="" data-size="line">&#x20;
* Create a new SQL report.

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### 2. Write the SQL Query:&#x20;

* Paste the following in the SQL tab:

```sql
select
defect_id as defect_id,
defect_type as defect_type,
defect_count as defect_count,
defect_color as defect_color,
tooltip_info as tooltip_info
from
"schema_name".pie_chart_ex1
```

### 3. Configure the OLAP View:

* In the **OLAP tab**, drag relevant fields into the layout to define your data view.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### 4. Preview the Report:

* Execute the report to verify the data is returned and visualized correctly.

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

### 5. Enable Drill-Through Functionality&#x20;

1. Open the Report Editor <img src="../../../.gitbook/assets/image (33).png" alt="" data-size="line"> and navigate to the **Drill-Through** tab to enable navigation from the widget:
2. **`activate drill-through 1`**: Enable this property.
3. **`show-on`**: Select a`contextual rendering type`.
4. **`drill-through-position`**: Use `DEFECT_ID` column from the report to identify the clickable area.

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

1. **`OpenActionType`**: Select `Page` to open a new page upon interaction.
2. **`page`**: Choose your pre-created target page.

### 6. Save the Report:

* Save with a clear name, e.g., "_Pie\_Chart\_ex1_".
{% endstep %}

{% step %}
## 📊Step 2: Create a New Page in Page Design

### 1. Create a New Page:

* Open the Page Design <img src="../../../.gitbook/assets/image (128).png" alt="" data-size="line"> and create a new page and give it a name (e.g., "Pie Chart E.1").

### 2. Add the Widgets:

* Drag the **Pie Chart** and **Plain Text** widgets onto the page.

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ⚙️Step 3. Configure the Widgets Properties

Once the widgets are placed on the page, you need to configure their properties.

### 1. Configure the Pie Chart properties: <a href="#configure-the-text-field-properties" id="configure-the-text-field-properties"></a>

**Main**

* `report datasource`: Associate the "Pie\_Char&#x74;_\_ex1_" report created in the first step.

**ObjectStyle**

**ObjectStyle → Fields Association**

| Widget Field     | Report Column  |
| ---------------- | -------------- |
| `R01_data_id`    | `defect_id`    |
| `R01_data_x`     | `defect_type`  |
| `R01_data_y`     | `defect_count` |
| `R01_tooltip`    | `tooltip_info` |
| `R01_data_color` | `defect_color` |

**Paramaters**

* `base name`: `Pie` (or any unique value).

**Widget settings (settings)**

* `chart title`:  **Analysis of Product Defects by Type**

**Container Size**

* `height`: Set the height of the widget container to "**100%**".

<figure><img src="../../../.gitbook/assets/image (244).png" alt=""><figcaption></figcaption></figure>

### 2. Configure the Plain Text properties: <a href="#configure-the-text-field-properties" id="configure-the-text-field-properties"></a>

**Main**

* `text:` Use the parameter exported by the Pie Chart widget when a slice is clicked.

{% hint style="success" %}
The parameter name must respect the syntax **{baseName}\_selected**, according to the value set in the [`base name` property](e.1-configuring-an-interactive-pie-chart-widget.md#id-3.-paramaters) of the Donut widget (e.g., `Pie_selected`).
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (15).png" alt="" width="537"><figcaption></figcaption></figure>

### 3. Save the Page:

* Save your configured page with a descriptive name (e.g., "Pie Chart E.1").
{% endstep %}

{% step %}
## ✅Step 4: Test the Widgets

Test the widget to ensure everything is working as expected.

### 1.  Access the Page:

* Open the page "_Pie Chart E.1"_ in the web application.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

### 2.  **Test Interactions**:

* Click a slice to ensure drill-through navigation works and the target page loads.
* Confirm that the exported parameter corresponds to the `defect_id` field.

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

