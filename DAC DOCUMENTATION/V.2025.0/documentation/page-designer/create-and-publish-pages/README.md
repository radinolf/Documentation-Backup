# Create and publish pages

## Creating a page

To create a new Page press the **New** button. From the **Insert page name** property, assign the name to the page you are creating, while in the **Select** **Template Style** section the system displays a gallery of templates that may be used as a starting structure for the creation of a new page.

![](<../../../.gitbook/assets/1 (26).png>)

Selecting the **Empty** template lets you create a page without the row and column structure already predefined in the page.



## Using widgets



**Widgets** are the fundamental bricks of a page and provide specific functionalities that you can leverage to build your page. Each widget has its own configuration properties; a page contains one or more widgets and you can also create interactions on them and they can leverage the same data.

In the widgets folder there are all the widget imported into the application, by default the system preinstalled a set of widgets.

![](<../../../.gitbook/assets/image (845).png>)

To insert a widget select the widget in the widgets catalog and drag and drop in the page.

![](<../../../.gitbook/assets/image (1115).png>)

The widget property are available in the panel at bottom left and are divided into three tabs:

* **Object** : Property of the widget
* **Container** : Property for customize the container
* **Advanced**: Advanced property to apply at the widget

## **Page Preview**

When designing a page, a preview can be displayed by selecting the **View Page** button.

The system opens the browser and displays the preview of the selected page in the catalog.

![](<../../../.gitbook/assets/image (1245).png>)

To open the preview, Design Studio starts Decisyon Web and automatically manages user authentication without having to enter credentials.

The system will show the preview page even if it is not published.

When accessing in preview, the system requires the address of Decisyon Web, stored in the **decisyonWebURL** Tool>>Preferences property.

The page in Preview behaves exactly as though it were opened by Decisyon RunTime. So all functions are active, such as the filter functions with respect to the page parameters, the drill-through, or the commands of the execution form objects (Submit, Params Cleaner, Execute Object).

After you made changes, reload the browser to view the changes applied to the page.

**Note:** The browser used is by default the one of the machine's operating system.

## Publish the page

To publish a Page, first set the _**display privileges**_.

In the Groups **section** of _the Page_ select the user groups tab.

![](<../../../.gitbook/assets/image (907).png>)

By default the page is associated with the _**Everyone**_ group. This Group is created by the system, includes all users on the system, and includes the permissions to access the application and display all objects of the application.

In the next step, the pages you want to publish in DAC are moved to the **Published** folder.

Drag and drop the page in the Published folder

![](<../../../.gitbook/assets/image (1606).png>)

The **Published** folder catalogs the Pages that are made available to the end users, respecting the privileges assigned. The catalog defined in this way is published on DAC RunTime in the **Pages Catalog .**

![](<../../../.gitbook/assets/image (971).png>)

The first Page in the list will be the Page, visible to the connected user, run automatically when accessing DAC.

## Change the page

To edit a page select the Edit button on the button toolbar.

![](<../../../.gitbook/assets/image (1632).png>)



When the page is in edit mode, it will be possible to modify both the page structure and the properties of the various widgets . After finishing editing the page you press the button Save to make the changes effective.

![](<../../../.gitbook/assets/image (1087).png>)

To view the changes from the Web it will not be necessary to reconnect to the RunTime but it will be sufficiently to double-click on the tabl of the page name to refresh it.

![](<../../../.gitbook/assets/image (1532).png>)

## Title for a Page

When you create a new page, the Page Design starts a wizard that allows you to set the name for the page (see image below). The title defined in the Page Design Catalog will be associated by default with the page container. This way, you can easily and quickly create new pages and assign the name.

In the group **Title** of the **Container** folder, the property **show-title** is enabled by default and the property **title-text** is set as **%PAGE\_TITLE%.**

When you access **DAC**, the title of the page will be the same as the name defined in the Page Design catalog.

![](<../../../.gitbook/assets/4 (11).png>)

<br>

## Example

### Example: Creating a New Page Via Template

**Step 1: Example of creating a new page via template.**

![](<../../../.gitbook/assets/2 (11).png>)

_Access Page Designer:_



1. _Select the Not-published folder._
2. _Press the New button_
3. _In the template selection window, enter the name of the new page._
4. &#x20;_Select the template to use as base structure. In the example, template 3 box 1 Row has been chosen._

**Step 2: Template Structure Visualization**

![](<../../../.gitbook/assets/3 (14).png>)

Selecting template “3 box 1 Row” will have the structure shown in the figure, to which additional row containers and column containers can be added.

_This is the structure, to which additional row containers and column containers can be added._



## Video Tutorial

### How to create new Page

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/3.PageCreation/PageCreation.mp4" %}



### Widgets

{% embed url="https://bitbucket.org/decisyon/manual/downloads/Widgets.mp4" %}

### **How to Publish a Page**

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/DesignStudio/4.PagePublication/PagePublishing.mp4" %}

##

##

