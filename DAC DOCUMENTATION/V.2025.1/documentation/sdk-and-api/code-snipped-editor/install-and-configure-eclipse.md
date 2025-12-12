# Install and configure Eclipse

## Introduction

This guide outlines the steps for installing and configuring Eclipse within the DAC, which is necessary for creating and managing Snippets. By following the points listed below, you will be able to download, install, and properly configure Eclipse, integrating it with the DAC development environment.&#x20;

## Requirements and constrains  <a href="#requirements-and-constrains" id="requirements-and-constrains"></a>

* **Which version of Eclipse IDE should I install?** The recommended version is Eclipse IDE 2023-03.
* **What specific version of Java is required to be installed on the operating system?** It is required to have the JRE for **Java SE 21** installed on the operating system.
* **What permissions must the Windows user have on the folder where Eclipse is installed when using Design Studio?** The Window user that is using Design Studio must have read/write grants on the folder where Eclipse is installed . For more information see this [document](/broken/pages/3ZxNxNUjNBoWMRBSXWAP).

## Installation&#x20;

The steps of installation include :

1. Download Eclipse
2. Run Eclipse Installer
3. Install Eclipse on the snippetDesigner
4. Configure Eclipse's path
5. Open Snippet and Launch Eclipse
6. Open Project
7. Import Project from the File System
8. Configure Java Build Path for snippetCode
9. Add JRE System Library to Modulepath
10. Add External JARs from Lib Folder

### **STEP 1 -** Download Eclipse

Access on [![](https://www.eclipse.org/eclipse.org-common/themes/solstice/public/images/favicon.ico)Eclipse Downloads | The Eclipse Foundation](https://www.eclipse.org/downloads/) and download the last version of Eclipse

<figure><img src="../../../.gitbook/assets/image (548).png" alt=""><figcaption></figcaption></figure>

&#x20;

### **STEP 2  -** Install Eclipse&#x20;

Run the Eclipse Installer and then select **Eclips IDE for Java Developers.**

<figure><img src="../../../.gitbook/assets/image (635).png" alt=""><figcaption></figcaption></figure>

Select the "_snipperDesigner_" subfolder of Design Studio as installation folder of Eclipse:

```
D:\Users\<your_user>\Decisyon App Composer Design Studio <version>\snippetDesigner
```

Unselect "**Create start menu entry"** and "**Create desktop shortcut"** and follow the steps of Eclipse's installer. The process may take few minutes.

<figure><img src="../../../.gitbook/assets/image (1132).png" alt=""><figcaption></figcaption></figure>

Once the installer completed, just close it. **Do not click on "Launch"**.



### **STEP 3 -** Configure Eclipse's path in Design Studio

Open Design Studio and configure Eclipse's path from the workspace property **Tools -> Preferences** -> **Main** -> **External Editors** as follows:

`.\snippetDesigner\eclipse\eclipse.exe`

<figure><img src="../../../.gitbook/assets/image (441).png" alt=""><figcaption></figcaption></figure>

### **STEP 4 -** Create a Snippet and Launch Eclipse

Open the **Snippet Code Editor**, create a new Snippet and click the Eclipse button to open the IDE.

<figure><img src="../../../.gitbook/assets/image (780).png" alt=""><figcaption></figcaption></figure>

### **STEP 5 -  Open Project in Eclipse**&#x20;

From the Eclipse menu select **File -> Open Project from File System**…

<figure><img src="../../../.gitbook/assets/image (1125).png" alt=""><figcaption></figcaption></figure>

### **STEP 6 - Import Project from Design Studio**

In **Import source** insert the path of the folder snippetCode present in the following subpath of Design Studio

{% code overflow="wrap" %}
```
D:\Users\<your_user>\Decisyon App Composer Design Studio <version>\snippetDesigner\workspace\snippetCode
```
{% endcode %}

<figure><img src="../../../.gitbook/assets/image (2252).png" alt=""><figcaption></figcaption></figure>

### **STEP 7 -** Configure Java Build Path

The Package Explores panel now contains the "_snippetCode_" package.

Now right click on **snippetCode** and then **Properties -> Java Build Path -> Libraries**

<figure><img src="../../../.gitbook/assets/image (898).png" alt=""><figcaption></figcaption></figure>

&#x20;

### &#x20;**STEP 8 - Add JRE System Library to Modulepath**

You need to include the JRE in the Modulepath of Eclipse

1. Select the **Modulepath** node
2. Click on **Add Library panel** and select **JRE System library.**&#x20;
3. Click **Next** button
4. From the **JRE System Library** panel select **Workspace default JRE (JDK-18.0.1.1)**&#x20;
5. Click **Finish**

{% hint style="info" %}
The version of the "Workspace default JRE" depends on the JVM installed in the client where Design Studio and Eclipse is installed. In this example it was JDK-18.0.1.1
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (776).png" alt=""><figcaption></figcaption></figure>

### &#x20;**STEP 9 -** Add External JARs from Lib Folder

Now you need to include all the libraries (JARs) that Eclipse can use when you write code.

* Select the **Classpath** node
* click on **Add External JARs…**
* Select the "_lib_" folder in Design Studio, in example at `D:\Users\<your_user>\Decisyon App Composer Design Studio <version>\lib` .
* Select all libraries in the **Lib** folder
* Click **Open.**
* Click **Apply And Close**

<figure><img src="../../../.gitbook/assets/image (783).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1334).png" alt=""><figcaption></figcaption></figure>

The left tree will have folders with imported libraries.

<figure><img src="../../../.gitbook/assets/image (897).png" alt=""><figcaption></figcaption></figure>

## Troubleshooting

The following sections will outline common problems, their causes, and recommended solutions.

### User Permissions for snippetEditor Folder

Verify that the Window users that is using Design Studio has read/write grants on the folder “_snippetEditor_” and its subfolders.

1. Open the "_snippetDesigner"_ folder in the Decisyon App Composer Design Studio and open the Properties folder.

<figure><img src="../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

2. Select the Security tab and verify that the users that is using Design Studio has read/write grants

<figure><img src="../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

### **Errors a after Version Upgrade**

An error may occur at [step 7](install-and-configure-eclipse.md#step-7-import-project-from-the-file-system) of the Eclipse installation guide when entering the path of the **snippetCode** folder in **Import source**. This issue particularly arises after a version upgrade. In this case, it is necessary to remove the project and reinstall it by following the installation procedure.

<figure><img src="../../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

Open the _snippetDesigner>>workspace_ and remove the folder `.metadata`

<figure><img src="../../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

Ensure that all the references libraries are in the correct folder for the current version of Design Studio

<figure><img src="../../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

