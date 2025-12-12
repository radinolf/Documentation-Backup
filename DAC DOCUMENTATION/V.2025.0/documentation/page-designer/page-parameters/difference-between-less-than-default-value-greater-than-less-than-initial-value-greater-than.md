# Difference between \<default-value> \<initial-value>

In this document we will try to understand the difference between \<default-value> \<initial-value> for the pre-selection-values properties in the Page.

### &#x20;\<initial-value>

When the preselection is set to “initial-value”,the parameter value configured is set when the page is loaded and then it’s not evaluated again when using the page.The value of the parameters could be modified by other widgets or Javascript API in the page, but the “initial-value” is evaluated only during the page loading.

&#x20;In case of a pre-selection parameter configured to use a SQL query that contains a DAC parameter, the SQL is executed only once, when the page is loaded.

&#x20;e.g. select plant\_name from lk\_plant where plant\_id=?plant\_id?

#### Example - Initial-value

![](<../../../.gitbook/assets/image (1096).png>)

In the Page the textfield exports a parameter called "dropdown" that is used in the SQL query of the preselection. .

&#x20;Now we see the page from the web.

If insert the value "202201" as we can see in the page, the preselection value did not change its value because the query is executed only when the page is rendered and at that time the textfield didn't have any value.

![](<../../../.gitbook/assets/image (564).png>)

Only in case the page is opened as a target of a drill-through or in a **tab panel**, is the parameter is exported from the source page then the query is properly executed. This because when the DT is executed, the parameter is exported and thus it’s available during the loading of the target page.

#### Example - Same page is used as a target of the DT.

Look at this example where the same page is used as a target of the DT.

![](<../../../.gitbook/assets/image (1572).png>)

When this same page is opened from a DT and the parameter "dropdown" has a value, the query is correctly executed; if you change the value after the page is rendered then the value doesn't change.

When the same page is opened in a tab panel widget, it works in the same way a DT but you need to make sure the following tab panel property “**Auto-refresh-on-params-change”** is enabled because it specifies that whenever a parameter is changed the page is the tab panel will be executed again.



![](<../../../.gitbook/assets/image (1558).png>)

&#x20;

### \<default-value>

When the preselection is set to “default-value”, the parameter value is evaluated **every time** an event in the page affects the parameter itself. I.e. Every time there is a change in the parameter value, there is a new evaluation of the value itself: if null then the “default value” is set. Every time a parameter used in the SQL query used to define the default value changes its value, the SQL statement is executed again because the new value must be evaluated to verify if it’s null.

This is the reason why the **\<default-value>** used in the parameter can trigger multiple report execution in case the same parameter is used as a filter in other widgets.

&#x20;

#### Example - default-value

It’s the same page as the above example but the preselection params are now on \<default-value>.

![](<../../../.gitbook/assets/image (1347).png>)

When the page is rendered, the preselection parameter is empty, but when you assign a value to the dropdown widget the SQL query is evaluated again and the parameter has now a value.

![](<../../../.gitbook/assets/image (1253).png>)

It works in the same way when the page is opened as a target of a DT or in a tab panel.

![](<../../../.gitbook/assets/image (1502).png>)

{% hint style="info" %}
It is possible to define a parameter in the pre-selection query even without having a widget in the page, as `query` and the SQL statement contains a parameter of the page,

**i.e.** select min (id\_day) from %MODEL\_SCHEMA%.lk\_date where id\_month=?dropdown?
{% endhint %}

