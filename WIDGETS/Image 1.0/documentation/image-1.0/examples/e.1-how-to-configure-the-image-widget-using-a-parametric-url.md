---
description: This tutorial shows how to configure the IFrame widget using a parametric URL
---

# E.1 How to configure the Image widget using a parametric URL

{% hint style="info" %}
**Configuration:** This tutorial has been implemented using the interaction between the widgets:

* **Image**
* **Text Field**
* **Execute Button**
* **Flex Row Container and Column Container**
{% endhint %}

## Prerequisites

**Content Security Policy (CSP) Configuration**

* If you are using an external image, you need to configure the  **Content Security Policy** ([CSP](https://content-security-policy.com/))

Here is an example of setting the CSP header for an Image widget:

```html
Content-Security-Policy: frame-src 'self' https://allowed-embed.example.com; script-src 'self' https://scripts.example.com;
```

* In this example, only content from `https://allowed-embed.example.com` is allowed to be embedded as an image, and scripts can only be executed from the hosting page's origin (`self`) and `https://scripts.example.com`.

{% hint style="info" %}
For more details, refer to the Image Security Configuration chapter.
{% endhint %}

**Example Image Configuration**

It is possible to use the following Image without setting any security configuration:

<figure><img src="../../../.gitbook/assets/sotm_2024-f20c5735185d043231a28fc89b16d93ceac49f5c377b310c30be9c64610ddf6e.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Image URL:** [https://www.openstreetmap.org/assets/banners/sotm\_2024-f20c5735185d043231a28fc89b16d93ceac49f5c377b310c30be9c64610ddf6e.png](https://www.openstreetmap.org/assets/banners/sotm_2024-f20c5735185d043231a28fc89b16d93ceac49f5c377b310c30be9c64610ddf6e.png)

**Image dimensions:**&#x20;

* **width:** 350 pixels
* **height:** 350 pixels
{% endhint %}

## 1. Create a page on Design Studio

Create a new Page in the Page Design <img src="../../../.gitbook/assets/image (26).png" alt="" data-size="line"> and add the following widgets:

* **TextField**&#x20;
* **Flex Row Container**
* **Image Widget**
* **Execute Button**

## 2. Configure the Widget's Properties

### Configure the TextField properties:

* **base name:** Set the name of the widget to be used as a page parameter. We set it to "_imageUrl_".
* **placeholder:** Set a placeholder. We set it to "_Enter URL_".
* **show-title:** Enable the property.
* **title-text:** Set it to "_URL_"

<figure><img src="../../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

### Configure the Page properties:

* **pre-selection-values:** In the **Value** field of the "_imageUrl_" parameter, set a valid URL for the external resource you want to embed within the **Image** widget. Example UR&#x4C;**:** &#x20;

[https://www.openstreetmap.org/assets/banners/sotm\_2024-f20c5735185d043231a28fc89b16d93ceac49f5c377b310c30be9c64610ddf6e.png](https://www.openstreetmap.org/assets/banners/sotm_2024-f20c5735185d043231a28fc89b16d93ceac49f5c377b310c30be9c64610ddf6e.png)

<figure><img src="../../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

### Configure the Execute Button properties

* **execution-type:** Select `JAVASCRIPT_ONLY` option.
* **javascript-code-after**: Define the JavaScript code to be executed when the image is clicked

```javascript
Example code:
alert('widget Image')
```

* **visibility:** Set the widget to be hidden.
* **custom-js-id:** Define the ID of the Execute Button. This ID will be used in the **Execute Object ID** image property so that the button action is associated. We set it to "Button".

<figure><img src="../../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

### Configure the Container properties size:

* **margin**: Set the margin size of the FlexRow Container on the page (i.e., 20,20,20,20)
* **width:** Set the width of the FlexRow container that holds the Image widget. In this example, we configure the container width of 250 px to be less than the width of the image that will be associated with the widget.
* **height:** Set the height of the FlexRow container that holds the Image widget. In this example, we configure the container width of 300 px to be less than the height of the image that will be associated with the widget.

<figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

### Configure the Image widget properties:

* **image fit:** Sets how the image should be resized to fit its container. We use the default value "contain" because the dimensions of the container are less than the picture, and this setting allows the image to be scaled to fit within the container maintaining its aspect ratio.
* **tooltip:** Specify the text to be shown when the business user hovers over the picture. We set "_Click_"
* **execute object ID:** Enter the ID value defined in the **custom-js-id** Execute Button property ("_Button_").
* **image URL:** Select the _'imageUrl_' TextField parameter from the dropdown menu, as previously configured in the **pre-selection-values** page property.

<figure><img src="../../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

## 4. Save and Publish your page.

Save and publish your page to apply the configuration.

## 3. Display the Image widget in the Web Application

* Open your **Image** page and display it in the App Composer Web Application. The image should now be configurable via the parametric URL entered in the Text Field.

<figure><img src="../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
By following these steps, you can configure the **Image** widget to display images based on user-input URLs, ensuring flexibility and dynamic content display in your application.
{% endhint %}
