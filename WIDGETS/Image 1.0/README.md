# Image 1.0

## Overview <a href="#toc57294676" id="toc57294676"></a>

The **Image** widget is designed to display specific images within an App Composer page, which is useful for logos or static pictures. The widget enables application developers to configure easily and include specific images in App Composer pages using its properties.

<figure><img src=".gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

The most common use cases for this widget are:&#x20;

* **Embedding External Content:** The Image widget is commonly used to embed pictures from external sources, such as other websites, web applications, or documents. Page Developer specifies the URL of the content he wants to embed, and the Image widget displays it within the page.
* **Parametric URL**: Page Developers can configure the image URL dynamically by providing parameters. Using parametric URLs in the Image widget provides a way to make the embedded content more dynamic and responsive to specific requirements or Business User interactions.&#x20;

{% hint style="warning" %}
The content will be displayed only when all parameters are valued.
{% endhint %}

<figure><img src=".gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

It is possible to customize its functionality and behavior using the specific configuration properties available in the Page Design. Page Developers can, for example, configure:

* Associate an action to be executed when the image is clicked

<div align="left"><figure><img src=".gitbook/assets/image (70).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Parametric URL

<div align="left"><figure><img src=".gitbook/assets/image (71).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Image fit

<figure><img src=".gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>



* Tooltip

<div align="left"><figure><img src=".gitbook/assets/image (74).png" alt="" width="231"><figcaption></figcaption></figure></div>

All applicable configurations may be found in the **Properties** section.&#x20;

### Image security configuration

**CORS** ([Cross-Origin Resource Sharing](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS))  is a security feature implemented by web browsers to control how web pages from one origin can request and interact with resources from a different origin.

When a browser makes a cross-origin request, it includes an Origin header indicating the origin of the requesting site. The server then responds with appropriate CORS headers, such as `Access-Control-Allow-Origin`, to grant or deny access.

When embedding content from a different origin in the Image widget, the embedded content's server must include the appropriate CORS headers to allow the hosting page's domain to make requests to it.

To securely use an Image widget within an App Composer page, it's crucial to properly configure also the **Content Security Policy** (CSP). [CSP](https://content-security-policy.com/) helps mitigate the risk of content injection attacks, such as XSS, by defining which resources the browser is allowed to load for a given page.

For the Image widget, the CSP directive `image-src` is particularly important as it dictates which origins are permitted to be embedded as images within a page. If the `image-src` directive isn't correctly set to include the domain of the content you wish to embed, the browser will block it from loading in the widget.

Additionally, if the embedded content requires scripts, styles, images, or other resources from different sources, the CSP directives `script-src`, `style-src`, `img-src`, and others must include those sources as well.

Here is an example of setting the CSP header for an IFrame widget:

```html
Content-Security-Policy: image-src 'self' https://allowed-embed.example.com; script-src 'self' https://scripts.example.com;
```

In this example, only content from `https://allowed-embed.example.com` is allowed to be embedded as an Image, and scripts can only be executed from the hosting page's origin (`self`) and `https://scripts.example.com`.

You can inspect the configured CSP policies using the developers' tools of your browser and verify the value of the `image-src` policy: if it doesn't include the URL to embed, the widget will not work as expected.

<figure><img src=".gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

Please refer to the App Composer installation guide to configure the CSP policies for App Composer: [https://dac-documentation-1.gitbook.io/installation-guides/](https://dac-documentation-1.gitbook.io/installation-guides/). By default, App Composer CSP policies do not allow embedding third-party websites, and thus you need to configure the services to enable it.

<figure><img src=".gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

**CORS** and **CSP** have crucial roles in securing websites that use the **Image** widget as they prevent malicious scripts from accessing data across different domains.

## Properties <a href="#toc57294678" id="toc57294678"></a>

The properties that are specific for the configuration of the **IFrame** widget on **Decisyon App Composer** are listed below:

<table data-full-width="true"><thead><tr><th width="221">Group</th><th width="209">Name</th><th width="375">Description</th><th width="173" align="center">Type</th><th width="132">Select Value</th><th width="163" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Appearance (Appearance)</strong></td><td><a href="./#image-fit"><strong>image fit</strong></a></td><td>Sets how the image should be resized to fit its container.</td><td align="center">SELECT</td><td>Fill, Contains, Covers, Scale Down, None</td><td align="center">Contain</td><td>false</td></tr><tr><td><strong>Tooltip (Tooltip)</strong></td><td><strong>tooltip</strong></td><td>Set a tooltip for additional context or information about the image. A parametric URL can be specified.</td><td align="center">TEXTFIELD</td><td></td><td align="center">Empty</td><td>true</td></tr><tr><td><strong>Widget specific (Widget specific)</strong></td><td><strong>execute object ID</strong></td><td>Set the ID (Custom-js-id) of the Execute Object widget to associate an action to execute when the image is clicked.</td><td align="center">TEXTFIELD</td><td></td><td align="center">Empty</td><td>false</td></tr><tr><td><strong>Widget specific (Widget specific)</strong></td><td><strong>image URL</strong></td><td>Allows you to embed the URL (HTTP/HTTPS) as the Image's source. A parametric URL can be specified.</td><td align="center">TEXTFIELD</td><td></td><td align="center">Empty</td><td>true</td></tr></tbody></table>

### Image Fit

The `image fit` property in the Image widget controls how an image is resized to fit within its container. This property allows page developers to manage the display of images effectively, ensuring they appear correctly for various layouts and use cases.&#x20;

{% hint style="warning" %}
It is essential to configure the container dimensions (width and height) to appropriately fit the image.&#x20;
{% endhint %}

<figure><img src=".gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

Below are the options available for the `image fit` property:

<table data-full-width="true"><thead><tr><th width="146">Image Fit </th><th width="279">Description</th><th width="197">Use Case</th><th>Result</th></tr></thead><tbody><tr><td><strong>Contain</strong> (Default)</td><td>The image will be scaled to fit within the container while maintaining its aspect ratio. This means that the entire image will be visible, and there may be empty space around the image if the aspect ratio of the container and the image do not match.</td><td>Best for displaying the whole image without any cropping, such as logos or detailed illustrations where the entire content needs to be seen.</td><td><img src=".gitbook/assets/image (46).png" alt="" data-size="original"></td></tr><tr><td><strong>Fill</strong></td><td>The image will be stretched to fill the entire container. This means that the image may be distorted if its aspect ratio does not match the aspect ratio of the container.</td><td>Useful when the entire container needs to be covered by the image, but distortion is acceptable.</td><td><img src=".gitbook/assets/image (47).png" alt="" data-size="original"></td></tr><tr><td><strong>Cover</strong></td><td>The image will be scaled to cover the entire container while maintaining its aspect ratio. This may result in parts of the image being cropped if the aspect ratios of the image and container do not match.</td><td>Ideal for background images where you want to ensure the container is completely filled, and cropping of the image edges is acceptable.</td><td><img src=".gitbook/assets/image (48).png" alt="" data-size="original"></td></tr><tr><td><strong>Scale-Down</strong></td><td>The image will be scaled down to the smallest possible size that fits within the container while maintaining its aspect ratio.</td><td>Useful when you want to display an image at its natural size or smaller, ensuring it fits within the container without scaling up</td><td><img src=".gitbook/assets/image (49).png" alt="" data-size="original"></td></tr><tr><td><strong>None</strong></td><td>The image will not be resized. It will retain its original dimensions, which might cause it to overflow the container if it is larger than the container’s dimensions.</td><td>uitable for situations where the original size of the image is essential, and any resizing would be undesirable.</td><td><img src=".gitbook/assets/image (50).png" alt="" data-size="original"></td></tr></tbody></table>
