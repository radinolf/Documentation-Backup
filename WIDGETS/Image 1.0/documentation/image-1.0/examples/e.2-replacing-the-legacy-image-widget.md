---
description: >-
  This example illustrates the process of replacing the legacy Image widget with
  the newer Image widget.
---

# E.2 Replacing the legacy Image widget

This guide will help you smoothly transition from the legacy Image widget to the new Image widget.

{% hint style="warning" %}
Note that the legacy Image widget allows images to be associated from the Resource Catalog rather than just specifying a URL, as the new Image widget provides. To complete the procedure, you must obtain the URL from the old widget.
{% endhint %}

## 1. **Retrieve the Image URL from the Legacy Widget**

### **Open the Page with the Legacy Image Widget**

* In the App Composer Web Application, navigate to the page that uses the legacy Image widget.

<figure><img src="../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

### **Retrieve the Image URL**

* Open the browser console.
* Use the Inspect tool to click on the legacy Image widget.
* In the Elements panel, find and copy the URL from the `<img src>` attribute. Example: `/content/resources/T0T/RXQZZ7X/184620037801165/graph-increase-png.png`.

<figure><img src="../../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

## 2. Replace the Legacy widget with the New Image widget

### &#x20;Open the page in Page Design&#x20;

* In Page Design, select the page currently using the legacy Image widget.

### Remove the Legacy Widget <a href="#replace-the-legacy-widget" id="replace-the-legacy-widget"></a>

* Edit the page to remove the legacy widget.
* Right-click on the legacy Image widget and select "Remove".

### Add the new widget

* Search for the Image widget in the Widgets folder.
* Drag and drop the new Image widget into the page, replacing the old widget.

<figure><img src="../../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

### Configure the New Image widget

* **image fit:** Set the property to "none" to prevent any resizing of the image.
* **image URL:** Enter the URL retrieved from the browser console. Example: /content/resources/T0T/RXQZZ7X/184620037801165/graph-increase-png.png
* **width (Container/Container Size group):** Set the width of the new widget to match the legacy widget. Example: 392 pixels.
* **height (Container/Container Size group):** Set the height of the new widget to match the legacy widget. Example: 322 pixels.

<figure><img src="../../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

## 3. Verify the result in the App Composer Web App

* Open the page in your App Composer web application.
* Ensure that the new Image widget is displayed correctly on the page.

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
By following these steps, you can effectively transition from the legacy Image widget to the new Image widget, ensuring a seamless update to your application's user interface.
{% endhint %}
