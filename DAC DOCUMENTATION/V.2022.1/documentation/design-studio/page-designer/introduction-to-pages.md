# Introduction to Pages

The Application can contain one or more **pages** where the business user can analyze data, collaborate with colleagues, perform analysis and take actions. DAC pages are designed using the "Design Studio" and consumed in "DAC". Pages are composed using one or more widgets.

Widgets can be entered on the Page, making the applications and data analyses particularly efficient. In addition the layout was designed so that you can have the most complete picture possible on a single page.

The page structure and layout are defined in **Decisyon App Composer** and distributed to the final users using the **DAC** module, which is an intuitive interface, even for inexperienced users.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/1.PagePresentation/PagePresentation.mp4" %}



To access the Page management window, select **Application >> Page Designer** from the menu bar.

![](<../../../.gitbook/assets/0 (10).png>)

The _**Group**_ folder (bottom left) lists the user groups or users with Page display privileges, which is a prerogative of Page publishing. By default the page is associated with the “everyone” group.

The module consists of an area for designing the Page (_Design_ folder on the right) and a preview (_Preview_ folder on the right).

The **design area** consists of a series of cells, grouped by row, where the components (_Components_ folder, on the left) available on DAC are inserted, which are grouped by type:

* data visualization, relating to publication of reports in the modes supported by DAC, such as tables (_Crosstab_), chart, indicators, and maps provided by Google Maps (_Map_).
* _FORM_ type components, used to:
  * the selection of data by the user, such as drop-down menus, lists or text fields
  * execute actions, both towards external systems (_Execute button_), and within the same page (_Submit_ and Params Cleaner)
* components for Collaboration
* **containers**, such as tables, used for alignment
* generic components, to customize your Page:
  * An image
  * Some text, to enter free format text and especially useful to **enter HTML code** in the Page page, other than the one managed by the system
  * An object dedicated to JavaScript code to be used in the page

Customizing the Page page can be enhanced by importing JavaScript or CSS style files to be assigned to the same page.

The page default background color is light gray.

Components are published on the Page by simply dragging them into one of the cells available.

They can then be customized by accessing the object-specific properties from the _**Properties**_ folder (bottom left). The _**Properties**_ are divided into three main groups:

* _**Object**_ contains all the properties for the elements of the Page
* _**Container**_ contains all the properties for the element “containers” of the Page
* _**Advanced**_ contains all the properties of the most advanced level.

This is the method used to customize any Page element, whether it is a component inserted in a cell, or a page or row of cells (section): each time one of these elements is selected in the design area, the properties are enabled in the _Properties_ folder.

The properties of a component/element are divided into groups, some of which are common to all objects, such as the title, description and border.

When multiple objects are entered, they require alignment in the modes available in the module.

Container components can be customized to background (by associating a uniform color or an image, or making them transparent).

A pop-up menu (right button of the mouse) is enabled on the components, where the following operations can be performed:

* _**copy, paste, and delete the selected element**;_
* _**copy and paste individual groups of properties**_ or all properties of the element; this function is particularly useful because after having defined a graphic aspect for a component, such as the title, the properties of the title can be copied and pasted on the other components.

The specific properties of the page allow the user to configure the behavior and enable export Excel formats.

Also available is a shared management of the datamarts for the Page data presentation objects, in a way that optimizes the number of temporary tables necessary for the Page.

DAC allows you to execute Page connections from other systems.

**Preview: allows you to visualize** the preview of the Page
