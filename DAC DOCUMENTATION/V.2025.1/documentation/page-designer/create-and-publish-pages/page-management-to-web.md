# Page management to web

Some of the page properties, that can be configured by the Page Designer, can also be configured from the Web.

On the Landing page Administrator User can customize for published applications, pages and folders:

* the image,
* the name
* description

<figure><img src="../../../.gitbook/assets/image (1262).png" alt=""><figcaption></figcaption></figure>

When you select the Pencil icon, the edit dialog opens opens:

<figure><img src="../../../.gitbook/assets/image (836).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Please note that the name of the page and the description supports the [multilanguage tags](https://documentation.decisyon.com/documentation/instance-configuration/multilanguage-and-localization/labels-management). In example, if the users who logs in has configured a language different from English, the page name or description will be translated
{% endhint %}

When you select a page to display the content, on the left is the icon to open the **Page Catalog** that contains the list of published pages in the application.

<figure><img src="../../../.gitbook/assets/image (655).png" alt=""><figcaption></figcaption></figure>

For each page there is a side menu that is enabled by selecting the icon with the contextual menu. Remember that in order to change the page properties the logged-in user must have an administration role.

<figure><img src="../../../.gitbook/assets/image (875).png" alt=""><figcaption></figcaption></figure>

The menu has the following items:

* **Rename**: Rename the Page
* **Delete**: Permanently delete page from the application. A confirmation of the action is required.
* **Settings**: Enable the Section Navigation bar on the right for the settings of the following properties:
  * **Settings**
    * [**Developoment Mode**](../page-properties/#main)**:** Enables the reloading of page's metadata at each opening, applying immediately any changes done in Design Studio. This property should be use only while building the page.
    * [**Debug Mode:**](../page-parameters/#enabling-debug-mode-debug-mode) Enables visualization of information useful to debug the objects contained in the page
    * [**Inizialize Page:**](../page-properties/) Enables full page reset. Any browsing information will be rejected and all the page objects will be presented as if initially accessed.
    * [**Refresh Page:**](../page-properties/#object)If enabled, at every access to the page all the objects will be updated. The objects associated to a report will be updated querying the related data source
  * **Groups :** In the Groups section you can select the user groups that will display the page. Pencil icon opens the panel for group selection

{% hint style="info" %}
Groups can be associated both in this section and on the Page Designer from the [Groups ](page-management-to-web.md#publish-the-page)Tab
{% endhint %}



<figure><img src="../../../.gitbook/assets/image (1450).png" alt=""><figcaption></figcaption></figure>

**Show Info**

<figure><img src="../../../.gitbook/assets/image (790).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The settings group property can also be configured from the Page Designer. Please see [Page Properties](https://documentation.decisyon.com/documentation/page-designer/page-properties#on-enter)
{% endhint %}

The page properties modified in the web application are visible also in Page Designer and vice versa: properties modified in Design Studio are visible also in the web application.

### Synchronization <a href="#synchronization" id="synchronization"></a>

Page properties configured by web can be synchronized between App Composer instances, in example between a development and a production environment.&#x20;

All the properties edited on the page  will be synchronized as dependencies of the Page, if the dependency calculation is selected in the synchronization dialog in Design Studio.&#x20;

Synchronization takes place when:

* Page is deleted, it will be marked "to be deleted" in the target environment when it is synced.
* Association of the groups is modified from web, then the page will be displayed as modified in the synchronization process
* Page properties and the page name is modified from web, then the page will be displayed as modified in the synchronization process
