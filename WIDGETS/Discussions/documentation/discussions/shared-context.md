# Shared-Context

## Introduction

The **Shared-Context** feature allows Page Developers to Share the same Discussion about a report cell or level with other reports.

<figure><img src="../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

Using the **shared-context** property available in the **Report Properties** ![](<../../.gitbook/assets/image (26).png>) , the Page Developer may configure this functionality.

<figure><img src="../../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure>

## How to configure the Discussion Shared-Context

### Step 1 - Create the Reports

Create two different reports that share at least one same level. In this explanation the two report share the same level "Line".&#x20;

<figure><img src="../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Page Developers may configure the **shared-context** functionality in two reports and more.
{% endhint %}

### Step 2 - Configure the share-context property&#x20;

Configure the following properties for both reports in the **Collaboration** group of the **Report Properties** ![](<../../.gitbook/assets/image (26).png>)

* **activateCellsDiscussions:** activate the property for enabling the visualization of the Discussions in the reports' cells.
* **shared-context:** activate the property for enabling the shared-context feature and share the same Discussion in the two reports.
* **context-ID:** set an identifier value. It should be the same value for both reports. In this example, we used the ID "1".

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

### Step 3 - Create the Page

* Create a Page and drag two Smart Grid widgets into it.
* Associate one report to each widget.

<figure><img src="../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

* Save and Publish the Page.

### Step 4- Create the Discussion

* Open the Page previously created in the Web Application
* Create a Discussion in the report's cell 'Line1' of the first report 'Stop Duration': Right-click on 'Line 1'--> select **Attach Discussion**
* Type a text in the Discussion field. For example, 'Check this Line, Please.'
* Press **Enter** to publish the Discussion.

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

### Step 5- Display the Discussion Shared-Context

Refresh the page

Now, you can display the same Discussion shared between the two reports.

<figure><img src="../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>
