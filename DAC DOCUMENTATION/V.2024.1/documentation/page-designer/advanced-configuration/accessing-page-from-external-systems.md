---
icon: repeat
---

# Accessing Page from External Systems

## Introduction

DAC allows direct access to pages defined within the application through a customizable link with specific parameters. This functionality enables dynamic integration of DAC pages with external web applications, providing quick and structured access to data. For example, a page can be displayed pre-filtered based on the parameters sent by the source application, ensuring a smooth and contextualized navigation experience.

<figure><img src="../../../.gitbook/assets/image (2310).png" alt=""><figcaption></figcaption></figure>

Two ptions are available for viewing the generated links, including:

* **Direct link to page**: Directly opens a specific page in DAC.
* **Page embedding link**: Displays only the page in embedded mode, allowing it to be integrated into another application.

### Where to get the access link

The access link is available by clicking on the three-dot menu in the top-left corner of the page. In the menu, selecting the "Share Page" option opens a pop-up displaying two links, as shown in the figure.

<figure><img src="../../../.gitbook/assets/image (2311).png" alt=""><figcaption></figcaption></figure>

Both the direct link to the page and the embedding link follow this structure:

`http://<HOST>:<PORT>/<CONTEXT>/content/Page/<OWNER>_<PAGE_ID>/[View|embedView]?<Organization>=<ORGANIZATION_ID>`

* `<HOST>`: The server address.
* `<PORT>:` The port used by the server (e.g., 8080).
* `<CONTEXT>`: The application context.
* `<OWNER>:` The owner identifier of the page.
* `<PAGE_ID>:` The page identifier.
* `View/embedView:` Choose View to open the entire page or embedView to embed it within another application:

The difference between the two URLs lies in the way the page is displayed:

#### **Direct Link to page**

The URL with `</view>` displays the page in standard mode, complete with the navigation menu and Decisyon platform options. This mode is ideal for direct access to the page with all available navigation features.

`<https://<PORT>>/<CONTEXT>/content/Page/<OWNER>_<PAGE ID>/view/<ORGANIZATION>=<ORGANIZATION ID>`

<figure><img src="../../../.gitbook/assets/image (2312).png" alt=""><figcaption><p>Page opened with direct link</p></figcaption></figure>

#### **Page embedding link**

The URL with \</embedView> opens the page in embedded mode, a simplified view without the menu and other navigation elements of the platform. This mode is useful for integrating the page into other applications or websites, providing a content-focused experience.

`<https://<PORT>>/<CONTEXT>/content/Page/<OWNER>_<PAGE ID>/embedView/<ORGANIZATION>=<ORGANIZATION ID>`

<figure><img src="../../../.gitbook/assets/image (2313).png" alt=""><figcaption><p>Page opened with embedding view</p></figcaption></figure>

### How to include any eventual organization

The `<Organization_id>` parameter represents the ID of the organization selected on the page. When the organization ID is passed in the URL, the page opens, and the specified organization is automatically selected, provided that the user is associated with that organization.

It is possible to pass the \<Organization\_id> parameters in both the **Direct Link** to page URL and the P**age embedding link,** using the query string. In this way, the system automatically selects the specified organization when the page is loaded, provided the user is authorized to access it. If the organization ID is invalid or the user does not have the necessary access rights, the system automatically applies error handling rules.

The format for passing the organization ID is:

`https://<PORT>/<CONTEXT>/content/Page/<OWNER>_<PAGE_ID>/view?organization=<ORGANIZATION_ID>`

For example:

`https://example.com/app/content/Page/ADMIN_DASHBOARD/view?organization=1234`

Where `organization=1234` automatically selects the organization with `ID 1234`.

#### **System Behavior Based on Organization ID**

* **Valid Organization**: If the provided organization ID is correct and the user is associated with it, the page opens with the organization automatically selected.
* **Non-Existent Organization**: If the specified ID does not match any existing organization, the system displays an error message to the user and automatically selects the last organization the user has access to.
* **Unauthorized Access**: If the organization ID is valid but the user is not associated with it, an error message appears indicating that the user is not authorized for the organization, and the last available organization is automatically selected.

### How to include the access token in the query string

The user's token can be included in the URL using the `<Token>` variable. In this case, the page will be opened with the permissions and access specific to the user associated with the token. Using a token allows bypassing the login process, directly authenticating the user. If the token is invalid or missing, access will follow the standard authentication methods.

`https:// <PORTA>/<CONTESTO>/content/Pagina/<OWNER>_<ID PAGINA>View?token=<TOKEN_ID>&Organization=<Organization_id>`

{% hint style="info" %}
When generating the token, it is necessary to generate it with the "Login into DAC" scope selected. For more details, see **Generate Token**.[ User Profile in AppComposer ](../../user-management/user-profile-and-change-password.md).
{% endhint %}

### How to include one parameter in query string

If you want to include default parameters in a link to customize a page or content, follow this structure:

**Base link structure**

* `http://<HOST>:<PORT>/<CONTEXT>/content/Page/<OWNER>_<PAGE_ID>/[View/embedView]?pNames=<PARAMETER>&pValues=<VALUE>`

Add the following parameters to the base Link:

* `pNames`: Name of the parameter
* `pValues`: Value of the parameter

#### Passing a Single Parameter

To add the parameter LINE\_ID with the value 1:

`http://example.com:8080/app/content/Page/OWNER/View?pNames=LINE_ID&pValues=1`

#### Passing Multiple Parameters

To add multiple parameters, for instance, `LINE_ID=1` and `day_filter=20241118`, the link will look like this:

`http://example.com:8080/app/content/Page/OWNER/View?pNames=LINE_ID%23_%23_%23day_filter&pValues=1%23_%23_%2320241118`

Suppose you need to filter the page by production line `(LINE_ID=4`) and date (`day_filter=2024-11-20):`

`http://example.com:8080/app/content/Page/OWNER/View?pNames=LINE_ID%23_%23_%23day_filter&pValues=4%23_%23_%2320241120`

This will display data only for line 4 and the date 2024-11-20.

### **How to include more than one parameters in query string**

If one or more parameters need to be assigned multiple values, the separator between multi-values is as follows: **%23\_%23\_%23.**

The link structure is as follows:

`http://<HOST>:<PORT>/<CONTEXT>/content/Page/<OWNER>_<PAGE_ID>/[View/embedView]?&Organization=<Organization_id>?pNames=<PARAMETER>&pValues=<VALUE>`

If you have multiple parameters:

1. `pNames`: List of parameters separated by `%23_%23_%23` (e.g. Parameter1%23\_%23\_%23Parameter2).
2. `pValues`: Corresponding values, separated by the same separator `%23_%23_%23` (e.g. `Value1%23_%23_%23Value2`).

{% hint style="warning" %}
**Important note**

The separator `%23_%23_%23` is required to separate multiple parameters and values.

Make sure each parameter corresponds to its respective value.
{% endhint %}



### **Example: Accessing a Page via External Link with Parameter Passing**

In this example, we show how to build a link that accesses an external page, passing both a **single parameter** and **multiple parameters.**

**Step 1: Page access in debug mode**

<figure><img src="../../../.gitbook/assets/image (2314).png" alt=""><figcaption></figcaption></figure>

Access a page where Debug Mode has been activated through Design Studio. This will allow you to view all the parameters accepted by the page and that can be used to filter the data.

**Passaggio 2: Shere page**

<figure><img src="../../../.gitbook/assets/image (2315).png" alt=""><figcaption></figcaption></figure>

From the top-right menu, select the option "Share Page."

A window will open displaying two link.

Select the first link, which will have the following structure:

`http://<HOST>:<PORT>/<CONTEXT>/content/Page/<OWNER>_<PAGE_ID>/[View/embedView]?Organization=<Organization_id>`

#### Passing a Single Parameter

To add a parameter, for example, LINE\_ID with the value 3, the link will look like this:

`http://<HOST>:<PORT>/<CONTEXT>/content/Page/<OWNER>_<PAGE_ID>/View?Organization=<Organization_id>&pNames=LINE_ID&pValues=3`

<figure><img src="../../../.gitbook/assets/image (2316).png" alt=""><figcaption></figcaption></figure>

In this example, if the page is accessed using the link with the parameter, the data will be filtered for line 3.

#### Passing Multiple Parameters

To add multiple parameters, for instance, LINE\_ID=4 and day\_filter=20241120, the link will look like this:

`<http://<HOST>>:<PORT>/<CONTEXT>/content/Page/<OWNER><PAGE_ID>/View?Organization=<Organization_id>&pNames=LINE_ID%23%23_%23day_filter&pValues=2%23_%23_%2320241120`

<figure><img src="../../../.gitbook/assets/image (2317).png" alt=""><figcaption></figcaption></figure>

In this example, if the page is accessed using the link with multiple parameters, the data will be filtered for line 3 and the date 20241120.

### Handling Page Access and Availability Issues

This section addresses scenarios where access to a page is no longer available due to permission changes, page deletion, or removal. It provides guidance on system behavior and the messages displayed to inform users, helping them navigate these situations effectively.

**What happens if the specified organization ID does not match an existing organization in DAC?**

If the organization Idoes not match any existing organization in DAC, an error message will be displayed stating that the specified organization does not exist. In this case, the user's last selected organization will be automatically applied.

<figure><img src="../../../.gitbook/assets/image (2321).png" alt=""><figcaption></figcaption></figure>

_"Errore Message: Required organization does not exist. You have been redirected to your default_ organization."

**What happens if the user is not associated with the specified organization?**

If the user is not associated with the indicated organization, an error message will appear stating that the user is not authorized. In this case, the user's last organization will be automatically selected.

<figure><img src="../../../.gitbook/assets/image (2322).png" alt=""><figcaption></figcaption></figure>

_"Error Message: Access to organization is denied. You may not have the appropriate permissions"_

**What happens if a user no longer has access to a page, or if the page has been deleted or removed?**

If a user loses access to a page or the page has been removed, they will receive a notification informing them that the page is no longer available within the application or that they no longer have permission to access it.

<figure><img src="../../../.gitbook/assets/image (2320).png" alt=""><figcaption><p>Example of a Error Message</p></figcaption></figure>
