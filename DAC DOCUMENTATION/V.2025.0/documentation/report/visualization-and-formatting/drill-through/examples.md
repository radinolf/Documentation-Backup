# ✏️ Examples

In this section, we will provide you with practical examples that demonstrate how to apply the concepts and techniques discussed in the previous sections.

We have carefully curated a variety of examples that will help you to deepen your understanding of the Drill-through function and its features. Each example includes step-by-step instructions.

### **Drill-Through to a Page**

The example below shows the page opening via a DT. At the same time the parameters are also passed.

By selecting a "PO TYPE", for example "Cooking", the values of the report on the page opened by the DT is automatically filtered for this value.

<figure><img src="../../../../.gitbook/assets/image (1374).png" alt=""><figcaption></figcaption></figure>

**How to confiure DT to a Page and passing params**

<figure><img src="../../../../.gitbook/assets/image (1373).png" alt=""><figcaption></figcaption></figure>

On the main report we define the properties highlighted in the image above.

Through the property **Show-on** we define that the type of DT will be a contextual Link and will be enabled on the level **Process\_Order\_type** (property **dtill-through-position**). Through the property **openActionType** we select the type Page and from the property Page select the page that we want to open through DT.

With these simple steps we have defined a DT that opens a filtered page for the selected value

### **Drill-Through** to a URL

In the image below we can see how through DT can open an external URL.

<figure><img src="../../../../.gitbook/assets/image (790).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
To include an external page in a DAC dialog it is necessary to configure the [Content Security Policy](https://content-security-policy.com/) of both DAC and the web application you want to use to include the pages of DAC.&#x20;
{% endhint %}



**How to configure DT to URL**

<figure><img src="../../../../.gitbook/assets/image (1205).png" alt=""><figcaption></figcaption></figure>

On the main report we define the properties highlighted in the image above.

Through the property **Show-on** we define that the type of DT will be a contextual Link and will be enabled on the level **Process\_Order\_type** (property **drill-through-position**). Through the property **openActionType** we select the Open URL type and in the URL property insert the URL that you want to open.

{% hint style="info" %}
Parameters passing is also possible for the Open URL. In this case you can pass the parameter directly into the link that you define in the URL property.&#x20;

E.g. "`https://www.google.it/search?q=?plant_name?`" where `?plant_name?` is the parameter and that is passed before opening the URL.
{% endhint %}

### **Drill-Through** to a Report

In the image below we can see the opening of a report via DT.

<figure><img src="../../../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

**How to configure the DT to report**

<figure><img src="../../../../.gitbook/assets/image (798).png" alt=""><figcaption></figcaption></figure>

On the main report we define the properties highlighted in the image above.

Through the Show-on property we define that the DT type will be a Contextual Link and will be enabled on the "Process\_Order\_type" level (dtill-through-position property). Through the openActionType property we select the Report and in the report property you can select the report you want to open from the DT.

{% hint style="info" %}
Parameters passing is also possible when opening a report.
{% endhint %}

### **Smart Grid - Drill-Through Report Configuration**

**Step 1 - Activate Drill-Through 1 on Report**

<figure><img src="../../../../.gitbook/assets/image (1597).png" alt=""><figcaption></figcaption></figure>

In this example we enable the **Drill-Through 1** and we go to define through the property **Show-on** the type of DT to display. In this case it will be type Kebab menu icon only and positioned at the top

**Step 2- Visualization on Web**

<figure><img src="../../../../.gitbook/assets/image (1274).png" alt=""><figcaption></figcaption></figure>



### **Smart Grid - Drill-Through 2 Report Configuration**

**Step 1 - Activate Drill-Through 2 on Report**

<figure><img src="../../../../.gitbook/assets/image (1801).png" alt=""><figcaption></figcaption></figure>

In this example we enable the **Drill-Through 2** and we go to define through the property **Show-on** the type of DT to display. In this case it will be type Link, Kebab menu Icon and Text and Contextual menu and Command column

**Step 2- Visualization on Web**

<figure><img src="../../../../.gitbook/assets/image (1339).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
If you want to have more details on the configuration of the Smart Grid widget see

the [SMART GRIG](https://widgets.decisyon.com/widgets/#smart-grid) documentation.
{% endhint %}



