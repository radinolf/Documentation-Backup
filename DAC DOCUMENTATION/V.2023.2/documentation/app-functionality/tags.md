---
description: DAC provides the TAG function.
---

# TAGs

DAC provides the TAG function, so you can:

* Customize the display of the Drill-throughs associated with the levels and metrics of a report
* Display Tooltips in the cells of a report
* Customize cell coloring (background and characters) of a report
* Display images in the cells of a report
* Add references to external files in the cells of a report
* Enter a Link to open an internet page
* Disable the drill on a level

You can condition by applying a TAG to a user who logs in using user parameters, such as _%U\_username%_ or _%GROUPS%_ (see _System Administrator_, _User parameters and_ _attributes section_).

These properties can be viewed by accessing the reports from the DAC and are applicable to the cells of the report which contain the values of **a compound metric** and to the cells containing values of a **dimension**.

The specification of a TAG implies for the user the writing of an expression of the type:

_**<@DECISYON\_TAG = value/>**_

or, in the case where you want to specify more than one property:

_**<@DECISYON\_TAG\_1 = value\_1; DECISYON\_TAG\_2 = value\_2;……………; DECISYON\_TAG\_n = value\_n/>**_

If there are several of the same type of TAGS, only the last TAG entered of that type will be interpreted. The others are ignored.

_For example, if there are two TAGS for images, only the last one entered is considered: < @IMG = logo1.jpg; FILE = document.pdf; IMG = logo2.jpg; TOOLTIPS = message/>, only logo2.jpg is displayed._

The expression is entered in the formula of a Composite Metric or in the formula of the description of a dimensional level.

Concerning the dimensional levels, the expression may be entered through the _**description-formula property**_ (_Main_ group), and the _**Read-description-formula**_ property (_ReadSQL_ group), available in the second step of the creation/edit wizard of a dimension: the difference lies in the fact that in the first case the description is processed during the access to the fact table, instead in the second case it takes place during the access to the datamart.

A Content Assist is also enabled, which suggests applicable TAGS, and possible values are suggested for some of them.

Finally, note that a tag within a description must always be entered as a string, i.e. be put in quotes.

**Note:**

_If a DAC Tag is used in an Oracle environment which is concatenated to other elements (see example below), the system generates an error since the @ key indicates a DBlin._

_In the following example the indicated error is generated:_

_**‘<@DT1=0/>’||Product@Description**_

_To avoid it, just enter a space before and after the pipe as follows:_

_**‘<@DT1=0/>’ || Product@Descriptio**_

## TAGS <a href="#tags" id="tags"></a>

DAC provides the TAG function, so you can:

* Customize the display of the Drill-throughs associated with the levels and metrics of a report
* Display Tooltips in the cells of a report
* Customize cell coloring (background and characters) of a report
* Display images in the cells of a report
* Add references to external files in the cells of a report
* Enter a Link to open an internet page
* Disable the drill on a level

You can condition by applying a TAG to a user who logs in using user parameters, such as _%U\_username%_ or _%GROUPS%_ (see _System Administrator_, _User parameters and attributes section_).

These properties can be viewed by accessing the reports from the DAC and are applicable to the cells of the report which contain the values of **a compound metric** and to the cells containing values of a **dimension**.

The specification of a TAG implies for the user the writing of an expression of the type:

_**<@DECISYON\_TAG = value/>**_

or, in the case where you want to specify more than one property:

_**<@DECISYON\_TAG\_1 = value\_1; DECISYON\_TAG\_2 = value\_2;……………; DECISYON\_TAG\_n = value\_n/>**_

If there are several of the same type of TAGS, only the last TAG entered of that type will be interpreted. The others are ignored.

_For example, if there are two TAGS for images, only the last one entered is considered: < @IMG = logo1.jpg; FILE = document.pdf; IMG = logo2.jpg; TOOLTIPS = message/>, only logo2.jpg is displayed._

The expression is entered in the formula of a Composite Metric or in the formula of the description of a dimensional level.

Concerning the dimensional levels, the expression may be entered through the _**description-formula property**_ (_Main_ group), and the _**Read-description-formula**_ property (_ReadSQL_ group), available in the second step of the creation/edit wizard of a dimension: the difference lies in the fact that in the first case the description is processed during the access to the fact table, instead in the second case it takes place during the access to the datamart.

A Content Assist is also enabled, which suggests applicable TAGS, and possible values are suggested for some of them.

Finally, note that a tag within a description must always be entered as a string, i.e. be put in quotes.

**Note:**

_If a DAC Tag is used in an Oracle environment which is concatenated to other elements (see example below), the system generates an error since the @ key indicates a DBlin._

_In the following example the indicated error is generated:_

_**‘<@DT1=0/>’||Product@Description**_

_To avoid it, just enter a space before and after the pipe as follows:_

_**‘<@DT1=0/>’ || Product@Descriptio**_

## @Bg,@FG <a href="#bg-fg" id="bg-fg"></a>

It is possible to set the color of the background and foreground in a cell of a dimensional level or of a metric based on a certain condition, using the BG (BackGround) and FG (ForeGround) properties in a TAG.

The syntax is:

_**<@BG =rgb(x, y, z)/> (x, y, z between 0 and 255)**_ for the background color

_**<@FG =rgb(x, y, z)/> (x, y, z between 0 and 255)**_ for the foreground color

## @Tooltips <a href="#tooltips" id="tooltips"></a>

When setting the Tooltip property, the user will view a message (may be set arbitrarily) upon passing on a cell of a dimensional level or of a metric with the mouse. The presence of a tooltip on a cell is marked by a small image indicating an “i”.

The syntax i&#x73;_**: <@TOOLTIP = message/>**_

## @File <a href="#file" id="file"></a>

You use the FILE property to indicate the link to a file in the cell of a Metric or dimensional level. The file may be referred to in two ways which the respective syntax corresponds to:

* File contained in a repository indicated in the **Tools>>path** (_**Tags File Repository group**_ , see _System Administrator_, _Data Model properties section)_

_**<@FILE = \[path]/\[file] />**_, where

* _**\[path]**_ is the path following the one indicated in the _Tools_ _**property**_
* _**\[file]**_ is the name of the image file including the extension.
* In the event of files previously loaded in the resource catalog the functions proposed by content assist are used

The characters allowed to specify the file or the folder are: \_(underscore), -(minus sign) and space. The folder separator is the “/” (slash) character. The file or folder name can contain numbers and letters but must start with a letter.

The file name may be preset or dynamically created based on the level in which it is displayed.

If the path is not defined in the system properties or the file is not found, DAC will display an exception message in the cell.

## @Img <a href="#img" id="img"></a>

It is possible to make an image appear inside a cell of a dimensional level or a metric.

In order to be accessed, the image must be in the folder predefined for DAC images: _customizations/img_ or must have been previously loaded in the resource catalog

The syntax is:

* In the event of reference to images loaded in DAC

_**<@IMG = \[path]/\[image] />**_, where

* _**\[path]**_ is the path after _customizations/img_
* _**\[image]**_ is the name of the image file including the extension.

If the image is in the predefined folder, this is the only value to be entered in the TAG. However, if subfolders have been created in the predefined folder and the image is in one of them, then the complete path must be entered.

* In the event of images loaded in the resource catalog the functions proposed by content assist are use&#x64;_**.**_

## @Link <a href="#link" id="link"></a>

You can use the Link tag to a URL, together with the IMG tag. In this case, the system will provide an image to click on to open an Internet page.

The syntax is:

_**<@IMG= …;LINK= URL />**_

At the bottom an example of using this type of TAG applied to Excel-like type customized totals is proposed.

## @DT\[n] <a href="#ds-n" id="ds-n"></a>

Drill-throughs are links associated with the dimensional and metric levels in the reports, which allow you to open different types of new pages, such as other reports, Pages, URLs, etc. . You can condition visibility using a DAC TAG. This is particularly useful when several drill-throughs (DT) are defined on the same level or Metric.

The syntax of the TAG to use is of the type:

_**<@DTn = 0/> (n = 1, 2, 3, ……)**_

where the value 0 indicates that the nth Drill-through on the dimensional level in question will not be visible.

## @DT <a href="#ds" id="ds"></a>

The DRILL TAG disables the possibility of performing drills on the reports grouped by dimension or layout. It is set on the dimensional levels only and as an effect the reports which contain the level do not have the + command to open the levels of detail.

The syntax i&#x73;_**: <@DRILL=0/>**_

**Note:** This notation must be entered in the alternative description of the level; in the alternative key it has no effect.

## Content Assist for TAGS <a href="#content-assist-for-tags" id="content-assist-for-tags"></a>

**Typing “< @”** strings in the formula definition area activates a menu with the list of DAC TAGS.

Possible values are also suggested for certain TAGS.

The _Content Assist_ for TAG **<@IMG=/>** e **<@FILE=/>** allows you to select the image or file from the Resource Catalog in the following two ways:

* _**getElementByID**_**:** which only specifies the resource ID (image file)

E.g._: <@IMG=ID(239329292929123)/>_

* _**getElementByPath**_**:** to also specify the path of the resource

_E.g.: <@IMG=PATH(Root\myFolder)/>_[<br>](https://dac-documentation-1.gitbook.io/user-manual/design-studio-manual/preferences)
