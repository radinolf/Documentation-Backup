# E.1 How to configure the Execute button to perform a QUERY

## How to configure the Execute button to perform a QUERY

This example will show how to create a new plant line using a simple input form. You may insert data into the database by setting the execute button **execution type** to **QUERY**.

## **Step 1**

Create a Report using the dimensional levels Plant, Line Id, and Line Description:

<div align="left"><figure><img src="../../../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure></div>

## **Step 2**

Create a new Page in the Page Design and use the following widgets:

1. **Dropdown**
2. **2 TextField**
3. **Execute Button**
4. **Crosstab**

![](<../../../../../.gitbook/assets/image (40).png>)

## **Step 4**

Configure the widgets:

In the Dropdown widget set the following properties:

* **report datasource** (**Main** group)**:** associate the report created in the first step.
* **fields association** (**ObjectStyle** group)**:** bind the fields Plant and Line Id respectively.

<figure><img src="../../../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

* **base name** (**Parameters** group)**:** input "Plant"
* **label** (**Content (Layout/Form)** group)**:** input "Plant"

In the first TextField widget set the following properties:

* **base name** (**Parameters** group)**:** input "line\_description"
* **label** (**Content (Layout/Form)** group)**:** input "Line Description"

In the second TextField widget set the following properties:

* **base name** (**Parameters** group)**:** input "line\_code"
* **label** (**Content (Layout/Form)** group)**:** input "Line Code"

In the Execute button widget configure the following properties:

* **button-text** (**Main** group)**:** enter "Add Line"
* **execution-type** (**Execution** group)**:** select QUERY
* **sql-formula\*** (**Execution** group): Open the dialog and define the query:

```sql
INSERT INTO %MODEL_SCHEMA%.lk_line (plant_ds, line_id, line_ds)
VALUES ('?Plant?', '?line_code?', '?line_description?')
```

In the Crosstab widget set the following property:

* **reportAssociated** (**Main** group)**:** associate the report created in the first step.

## **Step 5**

When a new line is created, the cross must be automatically refresh. On the Execute button widget set the property **JavaScript-code-after** with the following [Javascript API](https://documentation.decisyon.com/documentation/page-designer/api-javascript):

```javascript
DECISYON.page.refreshPage()
```

## **Step 6**

Open the Web Application and try to add a new Line filling the form.

<figure><img src="../../../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>
