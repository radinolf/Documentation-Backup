---
description: >-
  DAC has a module that allows users to create Java code snippets using DAC
  objects.
---

# Code Snippet

## What is a Snippet  <a href="#what-is-a-snippet-ok" id="what-is-a-snippet-ok"></a>

The Code Snippet Editor is a tool that allows developers to write, edit and manage re-usable code written in Java. With a few lines of code, app developers can create snippets of code that allows developers to execute custom actions in java and allows them to associate the custom code to other App Composer objects.

The DAC’s Code Snippet Editor provides a specially designed editing interface to simplify the creation and management of snippet tails, offering several features such as code formatting, syntax highlighting, and navigation in the code and much more.

Code snippets are developed in the Eclipse environment and are then saved in DACs as **Code Snippet** objects.

The snippet can be executed through:

* associated with the **Execute Buttons** on the Page
* when setting schedules with the _**Scheduler module**_ (deprecated)
* exposed with a REST API

The module used to create the snippets of code is the **Code Snippet Editor** , accessible from the menu item **Application** :

<figure><img src="https://1992103909-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2Fdac-documentatin-home%2F-MifFsBi8ofIITvYfugw%2F-MifFzR5UTNiIt4YejeZ%2F0.png?generation=1630665964560949&#x26;alt=media" alt=""><figcaption></figcaption></figure>

A snippet of code can be created starting from a snippet of code empty.

After selecting a new blank code snippet, you enter the development environment (Eclipse) where you can make changes to the code snippet.

With the **auto-save-on-edit** property, changes to the code in the development environment are saved automatically. When Eclipse is closed, the Code Snippet object also closes automatically, with all changes made in the development environment.

## Install and configure Eclipse OK <a href="#install-and-configure-eclipse-ok" id="install-and-configure-eclipse-ok"></a>

To install Eclipse proceed as follows:

**STEP 1**

Access on [![](https://www.eclipse.org/eclipse.org-common/themes/solstice/public/images/favicon.ico)Eclipse Downloads | The Eclipse Foundation](https://www.eclipse.org/downloads/) and download the last version of Eclipse

<figure><img src="../../../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

&#x20;

**STEP 2**

Run the Eclips Installer and then select **Eclips IDE for Java Developers.**

<figure><img src="../../../.gitbook/assets/image (186).png" alt=""><figcaption></figcaption></figure>

**STEP 3**

Install Eclipse on the snippetDesigner folder of Design Studio:

**Decisyon App Composer Design Studio (Version Name) >> snippetDesigner**

<figure><img src="../../../.gitbook/assets/image (683).png" alt=""><figcaption></figcaption></figure>

**STEP 4**

Access on Design Studio and set uo the Eclips path from the workspace property **Tools --> Preferences** --> **Main** --> **External Editors** as follows:

`.\snippetDesigner\eclipse\eclipse.exe`

**STEP 5**

Open the Snippet Code Editor, create a new Snippet and select the Eclipse icon to open the IDE.

<figure><img src="../../../.gitbook/assets/image (331).png" alt=""><figcaption></figcaption></figure>

**STEP 6**

From the Eclipse menu select **File --> Open Project from File System**…

<figure><img src="../../../.gitbook/assets/image (676).png" alt=""><figcaption></figcaption></figure>

**STEP 7**

In Import source insert the path of the folder snippetCode present in the following path

**Decisyon App Composer Design Studio&#x20;**_**\<version>**_ --> **snippetDesigner** --> **workspace** --> **snippetCode**

<figure><img src="../../../.gitbook/assets/image (680).png" alt=""><figcaption></figcaption></figure>

**STEP 8**&#x20;

The Package Explores panel now contains the snippetCode package.

To open the properties of the snippetCode and select on the left the resource **Java Build Path**.

<figure><img src="../../../.gitbook/assets/image (449).png" alt=""><figcaption></figcaption></figure>

&#x20;

&#x20;**STEP 9**

Select the "Libraries" tab. Now we’ll add the J**RE System** and **Lib libraries**.

**Add the JRE System**

1. Go to the **Modulepath** folder
2. From the **Add Library panel** select **JRE System library** and press **Next** button
3. From the **JRE System Library** panel select **Workspace default JRE (JDK-18.0.1.1)** and press **Finish** butto&#x6E;**.**

<figure><img src="../../../.gitbook/assets/image (327).png" alt=""><figcaption></figcaption></figure>

&#x20;**STEP 10**

**Add the Lib**

* In the Classpath folder select the button **Add External JARs…**
* Place yourself inside the lib folder of the Design Studio .
* Copy to all libraries in the **Lib** folde&#x72;**.**

<figure><img src="../../../.gitbook/assets/image (334).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (885).png" alt=""><figcaption></figcaption></figure>

JRE System Library is imported press apply and close.

<figure><img src="../../../.gitbook/assets/image (456).png" alt=""><figcaption></figcaption></figure>

The left tree will have folders with imported libraries.

<figure><img src="../../../.gitbook/assets/image (448).png" alt=""><figcaption></figcaption></figure>

## Blank Code Snippet <a href="#blank-code-snippet" id="blank-code-snippet"></a>

The **New** item allows you to create a blank code snippet whose code contains the **WorkFile** class, with the following methods:

* **execute**, which receives the context and contains the code for the operations executed by the object _Snippet_
* **main,** executed during testing/debugging; this calls the execute method, to which the metadata context, appropriately created, is transferred

<figure><img src="../../../.gitbook/assets/image (1096).png" alt=""><figcaption></figcaption></figure>

## Creating and using a snippet  <a href="#creating-and-using-a-snippet" id="creating-and-using-a-snippet"></a>

In the following paragraphs, we will explain how to use and create a snippet in detail. We will explore the following aspects:

1. [**Creating a Snippet:**](./#how-to-create-a-snippet) We will show you the necessary steps to create a new snippet.
2. **Using the snippet in App Composer:** You will see how to use a snippet associating it to a widget[ Execute Button](./#inlineextension-execution-of-a-snippet-through-execute-button). In addition, we will explore the use of the snippet in a [Scheduler](./#inlineextension-use-of-the-snippet-in-a-scheduler) (note that this feature is now deprecated).
3. [**Passage of the parameters in the snippet through demands API**](./#passing-parameters-in-the-snippet-through-rest-api)**:** We will show you how to pass the parameters to the snippet using the API requests.

### &#x20;How to create a Snippet&#x20;

To create a Snippet it is essential to have installed Eclipse see **Install and configure Eclipse** once you have made sure that Eclipse is installed follow these simple steps:

**Step1** - **New Code Snippet**

<figure><img src="../../../.gitbook/assets/image (330).png" alt=""><figcaption></figcaption></figure>

Open the Snippet Code Editor and create a new Snippet Code from the New button.

In the central panel we have as reference the snippet example of an empty model.

**Step 2** **Open Eclipse**

<figure><img src="../../../.gitbook/assets/image (522).png" alt=""><figcaption></figcaption></figure>

* Select the **Edit** button
* Open **Eclipse** and start the editor

<figure><img src="../../../.gitbook/assets/image (682).png" alt=""><figcaption></figcaption></figure>

Select the file **Snippet.Java** present under the folder **snippeCode --> src.**

**Step 3- Snippet Code**

<figure><img src="../../../.gitbook/assets/image (450).png" alt=""><figcaption></figcaption></figure>



* Insert the custom Java code at the desired location in the `Snippet.java` file. Make sure to adhere to the correct Java syntax and follow code formatting rules for better readability. Also, remember not to alter the overall structure of the file while inserting the code..
* ~~Select the block of code you want to transform in a snippet and paste it in the Snippet.Java~~

{% hint style="info" %}
Alternatively you can edit the code directly or import the file by selecting the menu item **File --> Open File**
{% endhint %}

* Click "Save" to confirm the creation of the snippet.

The snippet will be saved in the Eclipse snippet library and you can call it anytime during the development of your project.

### Execution of a Snippet through Execute Button <a href="#inlineextension-execution-of-a-snippet-through-execute-button" id="inlineextension-execution-of-a-snippet-through-execute-button"></a>

To run the snippet via the execution button, simply associate the snippet to the corresponding button.

<figure><img src="../../../.gitbook/assets/image (1091).png" alt=""><figcaption></figcaption></figure>

From the **execution-type** property select **CODE\_SNIPPET** and from the snippet property the snippet created in the Snippet Editor.

### Use of the snippet in a Scheduler <a href="#inlineextension-use-of-the-snippet-in-a-scheduler" id="inlineextension-use-of-the-snippet-in-a-scheduler"></a>

The execution of a snippet can be scheduled through the Scheduler.

{% hint style="info" %}
Please note that Scheduler and Schedules Designer are considered Deprecated.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1095).png" alt=""><figcaption></figcaption></figure>

### **Passing parameters in the snippet through rest API**

Below we show the syntax to pass parameters to a Snippet in the API request.

`https://<host>:<port>/api/rest/application/<application_owner>/program/<snippet_id>/body`

`?key1={{par1}}&key2={{par2}}&key2={{par3}}>`

## Requirements and constrains  <a href="#requirements-and-constrains" id="requirements-and-constrains"></a>

* **Which version of Eclipse IDE should I install?** The recommended version is Eclipse IDE 2023-03.
* **Are there specific constraints or requirements?** It's required to have Java 18 JRE in the client where the DS is installed and where eclipse will be installed.
* **Can I import an external library?** No, you cannot import external libraries.
* **Do I need to know which version of Java to use?** Yes, you need to know which version of Java to use to write the code. Usually it's Java 18 or above
* **Should I be aware of how the snippet will be compiled and executed?** No, it is not necessary.
* **Must the snippet have specific classes or methods? (for example, is there a specific way to use the "main")?** You need to follow the provided snippet structure.
* **Can I use the Spring framework as the developer of the snippet in order to create the code of the snippet?** Yes, you can use the Spring framework as it is included.

## Logs and debug

The result of a snippet is recorded in the DAC Log.

In the folder containing the [Logs ](../../introduction/application/overview-of-ui/general-info/#log)downloaded from the web, there is a **Snippet** file that contains and the logs of snippet executions.

<figure><img src="../../../.gitbook/assets/image (1151).png" alt=""><figcaption></figcaption></figure>

In order to write rows in the log file it is necessary to use the following method inside the Snippet

```java
ExtLoggerSDK.debug("<your text>"); 
```

Please see the [Blank Code Snippet](./#blank-code-snippet).[<br>](#user-content-fn-1)[^1]

[^1]: 
