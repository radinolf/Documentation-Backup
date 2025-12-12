# Groups Administration



The Group Administrtion module in RunTime allows you to create user groups when they have specific features in common and you want to limit the use of certain application objects such as the use of metrics, dimensions , cubes and events.

<figure><img src="../../.gitbook/assets/image (959).png" alt=""><figcaption></figcaption></figure>

Even when creating pages through the Page Designer you have the option to limit the display to a specific group of users.

You can also define attributes and these can be used within security filters in report filters or as defaults or filter conditions in Pages.

To access the **Group Administratio**n window, select **Groups Administration** item from **Administration** in the vertical toolbar.

Below is a brief overview of the main functions in the interface.

<figure><img src="../../.gitbook/assets/image (1370).png" alt=""><figcaption></figcaption></figure>

## How to create a new Group

Click the New button to create a new group:

In the **DETAILS** tab insert :

* The name of groups
* Select the folder (optional)

In the **SETTINGS** tab can define the attributes of the group

<figure><img src="../../.gitbook/assets/image (1378).png" alt=""><figcaption></figcaption></figure>

After creating the new group, the following information is displayed:

<figure><img src="../../.gitbook/assets/image (1004).png" alt=""><figcaption></figcaption></figure>

* **Name**: group name
* The **Application Owner** and '**Id**' represent the identification code of the group. This code can be used in the Rest API, Program and Javascript Functions.
* **Description**: it’s possible to insert a description for the new group. After save the changes.
* **Landing Page:** in Landing Page you can select the page that the users of the group access after logging in RunTime.

## How to associate users to the group

The list of users in the application is provided in the _**Available user**_ section.

To associate the user with the new group, select the user and press the arrow.

<figure><img src="../../.gitbook/assets/image (1851).png" alt=""><figcaption></figcaption></figure>

You’ll see the user has been added to the group by viewing the _**Associated user**_ section, which lists all users associated with this group.

<figure><img src="../../.gitbook/assets/image (1445).png" alt=""><figcaption></figcaption></figure>

### ⛔ Group Permissions (deprecated)

{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

Group permissions are defined in the **Permissions** folder, on the objects Cubes, Dimensions , Metrics and Event.

<figure><img src="../../.gitbook/assets/image (712).png" alt=""><figcaption></figcaption></figure>

Permissions on all objects are enabled by default but for each specific object there are a different option:

* **Inherit**: all objects (metrics, dimensions or events) associated with that object inherit the same permissions
* **Enable**: permissions used for the user group
* **Disable**: disabled permissions for user group

Decisyon grants or denies access to certain functions, such as refreshing data, formatting cells, editing metrics, and so on.

<figure><img src="../../.gitbook/assets/image (890).png" alt=""><figcaption></figcaption></figure>

In the **Setting** tab can possible to modify or configure new attribute.

<figure><img src="../../.gitbook/assets/image (1362).png" alt=""><figcaption></figcaption></figure>

All changes are saved automatically.

## How to move a group to a folder

**Step 1:** Create a new folder, where we will insert the previously created group,  and then name the folder.

<figure><img src="../../.gitbook/assets/image (1199).png" alt=""><figcaption></figcaption></figure>

**Step 2:** Select **Change folder** from the list owned by the group.

<figure><img src="../../.gitbook/assets/image (1529).png" alt=""><figcaption></figcaption></figure>

**Step 3**: Select the destination folder.

<figure><img src="../../.gitbook/assets/image (1002).png" alt=""><figcaption></figcaption></figure>

**Step 4:** The group has been moved to the Digital Factory folder.

<figure><img src="../../.gitbook/assets/image (587).png" alt=""><figcaption></figcaption></figure>

## How to delete the group

To delete a group, simply select the item below the group of properties.

<figure><img src="../../.gitbook/assets/image (1356).png" alt=""><figcaption></figcaption></figure>

## Video Tutorial

Learn how to create user group, and how to customize the permissions on the objects.



{% embed url="https://bitbucket.org/decisyon/manual/downloads/NewGroup.mp4" %}





[<br>](https://2021.1.0.decisyon.com/runtime-manual/administration-1/users)
