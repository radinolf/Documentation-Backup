# Widget Editor

## Overview&#x20;

The **Widget Editor** is used to create and modify widgets which are later used in Decisyon Design Studio to create application pages. Widget Developers can create any desired functionalities that can be consumed by business users in a widget leveraging client technologies like HTML, JavaScript, CSS, Angular etc.

In the Widget Editor, there are different types of objects Widget Developers can create:

* **Folder**
* **Data Connector**
* **Data Presentation widget (with report association)**
* **Generic widget (without report association)**
* **Shared library**

<figure><img src="../../../.gitbook/assets/image (1576).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="80.33333333333331"> Icon</th><th width="174">Name</th><th>Description</th></tr></thead><tbody><tr><td><img src="../../../.gitbook/assets/image (1770).png" alt=""></td><td><strong>Folder</strong></td><td>Allow Widget Developers to organize widgets by providing a hierarchy of objects that includes widgets and may also contain additional folders.</td></tr><tr><td><img src="../../../.gitbook/assets/image (1064).png" alt=""></td><td><strong>Data Connector</strong></td><td>It is a type of widget that allows  Widget Developers to retrieve and make data available for Generic widgets.</td></tr><tr><td><img src="../../../.gitbook/assets/image (688).png" alt=""></td><td><a href="data-presentation-widgets.md"><strong>Data Presentation</strong></a></td><td>It is a type of widget that needs report association. Its data source consists of one or more reports.</td></tr><tr><td><img src="../../../.gitbook/assets/image (637).png" alt=""></td><td><a href="generic-widgets.md"><strong>Generic</strong></a></td><td>This type of widget can be developed with any type of user interface. Associating reports is not required.</td></tr><tr><td><img src="../../../.gitbook/assets/image (1573).png" alt=""></td><td><a href="shared-library.md"><strong>Shared library</strong></a></td><td>These objects are composed of JavaScript libraries, CSS definitions, HTML templates, and or images that Widget Developers may be to reuse on multiple widgets.</td></tr></tbody></table>

Widget Editor has the following features:

* Editing and upload of JS and CSS resources
* Code editor and content assist
* Multiple perspectives
* Preview
* Resource dependencies settings (JS, CSS)
* Ability to use any browser developer tools
* Multiple resources association

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1854).png" alt=""><figcaption></figcaption></figure></div>

{% hint style="warning" %}
You must have the appropriate privileges to build and edit widgets. The Administrator is the default role to access the Widget Editor.
{% endhint %}

Administrator users access Widget Editor from the Main Menu.



<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1178).png" alt=""><figcaption></figcaption></figure></div>

Once you open the Widget Catalog page, click a widget in your resources list to open the Widget Editor.

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (675).png" alt=""><figcaption></figcaption></figure></div>

Widget Editor elements:

1. **Widget Resources:** Shows the widget's special resources. These resources are organized into special folders automatically. Go to [Widget Resources](/broken/pages/MiCT76B6ZkB1Pa89UHGf) section for more details.
2. **Toolbar:** Contains the actions menu, with commands:
   * <img src="../../../.gitbook/assets/image (1053).png" alt="" data-size="line">to save the resource&#x20;
   * <img src="../../../.gitbook/assets/image (1746).png" alt="" data-size="original">maximaze the editor panel &#x20;
   * <img src="../../../.gitbook/assets/image (690).png" alt="" data-size="line"> open the editor panel in a new tab&#x20;
   * <img src="../../../.gitbook/assets/image (1586).png" alt="" data-size="line"> reload resource  &#x20;
   * <img src="../../../.gitbook/assets/image (692).png" alt="" data-size="line"> open resource menu (Save, Maximaze, Open in new Tab)&#x20;
3. **Code editor:** Enter and edit the code used in the widget you are developing or editing.
4. **Preview button:** Show a preview of the widget as it would be seen when added to the page.
5. **Widget Settings:** Shows the widget's settings properties, which are organized into the categories Main, Mock, Page integration, and Options. Go to [Widget Settings](widget-settings.md) section for more information.
6. **Perspective and Documentation:** By clicking the kebab menu <img src="../../../.gitbook/assets/image (692).png" alt="" data-size="line"> at the top, you display the options to change the layout of the Widget Editor and access the documentation with the API references.

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/image (1792).png" alt=""><figcaption></figcaption></figure></div>
