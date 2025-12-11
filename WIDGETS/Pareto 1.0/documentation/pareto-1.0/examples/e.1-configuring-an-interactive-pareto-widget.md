---
description: >-
  This guide provides a step-by-step tutorial for configuring a simple
  interacrive Pareto widget.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/aYHQvgJiShX4tMBRzZ83/documentation/andon-line-1.0/examples/e.1-configuring-an-interactive-andon-line-widget
---

# E.1 Configuring an Interactive Pareto Widget

The widget enables business users to click on data columns and navigate to a specific page. Before beginning, ensure the target page has been created.

## 🔧Prerequisites

To complete this configuration, ensure you have access to a database where you can create a table to store KPI data. You will need to execute SQL scripts to:

1. Create the required table structure.
2. Populate the table with sample data.

#### Create the Database Table and Insert Data

```sql
-- Create table for storing Pareto data
CREATE TABLE IF NOT EXISTS "schema_name".pareto_ex1 (
    item character varying COLLATE pg_catalog."default" NOT NULL,
    value character varying COLLATE pg_catalog."default",
    color character varying COLLATE pg_catalog."default",
    seq integer,
    CONSTRAINT pareto_ex1_pkey PRIMARY KEY (item)
);
```

**SQL Script for Data Insertion**

Insert data into the table using the following script:

```sql
-- Insert data into the pareto_ex1 table
INSERT INTO "schema_name".pareto_ex1 (item, value, color, seq) VALUES

-- Machine A: Highest downtime with 200 minutes recorded
    ('Machine A', 200, '#F89C74', 1), -- Orange, indicating high impact

-- Machine B: Significant downtime of 180 minutes
    ('Machine B', 180, '#F76C5E', 2), -- Red-orange, signaling an issue

-- Machine C: 150 minutes of downtime, medium impact
    ('Machine C', 150, '#F5DD90', 3), -- Yellow, indicating caution

-- Machine D: 120 minutes of downtime, lower than previous entries
    ('Machine D', 120, '#C4D381', 4), -- Light green, suggesting moderate impact

-- Machine E: Least downtime with 90 minutes recorded
    ('Machine E', 90, '#9EDBF9', 5); -- Light blue, possibly a minor issue
```

## Tutorial Steps <a href="#tutorial-steps" id="tutorial-steps"></a>

{% stepper %}
{% step %}
## 🛠Create the Report for the Data

### 1. Create a New SQL Report:&#x20;

* Open the **Report Design** <img src="../../../.gitbook/assets/image (194).png" alt="" data-size="line"> and create a new SQL report.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

### 2. Enter the SQL Query:&#x20;

* Navigate to the SQL tab and enter the following SQL query to retrieve the data from your newly created table:

```sql
select
item as item,
value as value,
color as color,
seq as seq
from
multi_site_data.pareto_ex1
order by
seq
```

### 3. Configure the OLAP View:

In the OLAP tab, drag and drop the necessary fields to create rows for visualization.

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

### 4. Execute the Report:

* Run the report to verify the data visualization.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

&#x20;For this specific example, ensure the **`create-temp-table`** property is **disabled** in the report settings to maintain correct field sorting and complete the tutorial successfully:

**Report Properties → Main → `create-temp-table`: Disabled**

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

### 5. Configure Drill-Through Functionality&#x20;

1. Open the Report Editor <img src="../../../.gitbook/assets/image (91).png" alt="" data-size="line"> and navigate to the **Drill-Through** tab to enable navigation from the widget:
2. **`activate drill-through 1`**: Enable this property.
3. **`show-on`**: Select the `contextual rendering type`.
4. **`drill-through-position`**: Select the `Item` column from the report to identify the clickable area.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

5. **`openActionType`**: Select `Page` to open a new page upon interaction.
6. **`page`**: Select a pre-created target page.

### 6. Save the Report:

* Save your report and name it something relevant (e.g., "_Pareto\_ex1_").
{% endstep %}

{% step %}
## 📊Create a New Page in Page Design

### 1. Create a New Page:

* Open the Page Design, create a new page, and give it a name (e.g., "Pareto E.1").

### 2. Add the Widgets:

* Drag the **Pareto** and **Plain Text** widgets onto the page.

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ⚙️Configure the Widgets' Properties

#### 1. Configure the Pareto properties: <a href="#user-content-configure-the-text-field-properties" id="user-content-configure-the-text-field-properties"></a>

Once the widgets are placed on the page, you need to configure their properties.

**Main**

* `report datasource`: Associate the "_Pareto\_ex1_" created in the first step.

**ObjectStyle**

* `fields association:` Map the following report columns to their respective fields in the widget:
  * `R01_data_id` → ITEM (In this example, the `data_id` and `data_x` are the same report column).
  * `R01_data_x` → ITEM (Loss Reason/Machine).
  * `R01_data_y` → VALUE (Loss Duration/Minutes).
  * `R01_data_color`→ COLOR (column for custom bar colors).

**Appearance (Settings)**

* `dash array:` Select the option "**Dotted Line**" from the drop-down.
* `line color`: Set a custom color for the Pareto line. In this example, "**#607D8B**".

**Paramaters**

* `base name`: Specify a unique identifier to compose the widget parameters. In this example, the default value "**Pareto**" is kept.

**X axis title (Settings/ Axes title)**

* `x axis title`: Type **"Machine"**.

**Y axis title (Settings/ Axes title)**

* `y axis title`: Type **"Loss Duration (Minutes)"**.

**Container Size**

* `height`: Set the height of the widget container to "**100%**".

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

### 2. Configure the Plain Tex widgets properties: <a href="#configure-the-text-field-properties" id="configure-the-text-field-properties"></a>

**Main**

* `text:` Configure the parameter exported by the Pareto widget when the business user clicks a column.

{% hint style="success" %}
The parameter name must respect the syntax **{baseName}\_selected**, according to the value set in the [`base name` property](e.1-configuring-an-interactive-pareto-widget.md#configure-the-widgets-properties) of the Pareto widget (e.g., `Pareto_selected`).
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (26).png" alt="" width="470"><figcaption></figcaption></figure>

### 3. Save the Page:

* Save your newly configured page (e.g., "Pareto E.1").
{% endstep %}

{% step %}
## ✅Test the Widgets

Test the widget to ensure everything is working as expected.

### 1.  Access the Page:

* Open the page "_Pareto E.1"_ in the web application.

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

### 2.  **Test Interactions**:

* Click a column to ensure drill-through navigation works and the target page loads.
* Confirm that the exported parameter corresponds to the `R01_data_id` field.

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>




{% endstep %}
{% endstepper %}



