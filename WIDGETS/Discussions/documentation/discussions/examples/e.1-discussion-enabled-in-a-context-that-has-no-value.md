# E.1 Discussion enabled in a context that has no value

This explanation demonstrates how to post a Discussion even if a page's parameter, such as a page-by set to \[Total], is not defined. The example additionally shows how to repeat a Discussion across many pages.

{% hint style="info" %}
For this example, we are going to use the following widget's properties:

* **context-parameters**
* **context-root-ID**
* **enable-post-discussion-on-total**
{% endhint %}

### Step 1 - Create the Report

Create a simple report. We created a report with two levels, the level "Line" located in rows and the level "Plant" located in page-by.

<figure><img src="../../../.gitbook/assets/image (89).png" alt="" width="456"><figcaption></figcaption></figure>

### Step 1 - Create the Page

Create a page that contains the widgets **Smart Grid, PageBy Selector,** and **Discussion:**

* Create a new page.
* Drag to the page the widgets Smart Grid, PageBy Selector, and Discussion.
* Associate the report created in the Step 1 with the Smart Grid.
* Associate the level Plant in the PageBy Selector.

<figure><img src="../../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

### Step 3 - Configure the Discussion widget

Configure the following properties in the Discussion widget:

* **context-parameters:** Select the "Plant" level to define the parameter that identify the context of your Discussion.
* **context-root-ID:** Set the ID context of the Discussion. This will allow you to show your Discussion on other pages. In this example "Plant".
* **enable-post-discussion-on-total:** enable the property to post the Discussion on the Total elemet.

<figure><img src="../../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>





* Save and publish the page.

### Step 4 - Post the Discussion on the Page

* Open the page in the Web Application.
* Select \[Total] in the PageBy Selector and post a message in the Discussion widget.

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

* Select a different Plant from the PageBy Selector (e.g. Brussels) and note that the posted message is displayed even if a filter is applied.&#x20;

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### Step 5 - Create a new page and use the Discussion widget

* Create a new page in the Page Design. In this example, we are going to use an existing page.
* Drag to the page the Discussion widget.
* Configure the property **context-root-ID** in the Discussion widget using the same ID context ("Plant") set in the Discussion configured in Step 3.
* Save the page.
* When you open the page in the Web application, you will display the same Discussion posted in Step 4.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

