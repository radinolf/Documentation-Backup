# Discussions

## Overview <a href="#toc69201839" id="toc69201839"></a>

With the **Discussions** the Business Users can attach comments, notes, and files on the **page** or single **report cell** and start a thread related to a **specific context**.

<figure><img src=".gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

<div data-full-width="true"><figure><img src=".gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure></div>

Page Developers may configure the **Discussion** widget on:

* Decisyon Page&#x20;

<figure><img src=".gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* Report property --> [**contextual discussions**](documentation/discussions/contextual-discussions.md)

<figure><img src=".gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

* Page property --> [**discussions with weak contextuality**](documentation/discussions/discussions-with-weak-contextuality.md)

<figure><img src=".gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

In the **Discussion**, Business Users can:&#x20;

* Publish a new post and reply by posting comments

<figure><img src=".gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

* Attaching files

The attached files (documents or images) will be stored in Decisyon [Document Repository](https://app.gitbook.com/s/wby3Tc9bXfH1wRkOshvv/documentation/design-studio/tools/preferences#caching-document-repository)

Business Users can upload files up to 20 megabytes by default.&#x20;

By using the property [**maxUploadFileSize (MB)**](https://app.gitbook.com/s/pxjGiDUm87sSkRAsKf8t/documentation/instance-configuration/tools/preferences#user-contents) in Design Studio (**Tools--> Preferences--> Web --> User contents**), Page Developer can set the maximum size of the file that can be uploaded.

<figure><img src=".gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

* Edit or delete the posted message (owner only)

<div align="left"><figure><img src=".gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure></div>

{% hint style="info" %}
The widget property **allow-discussion-remove** must be enabled to remove the entire discussion. Otherwise, just the comments can be deleted.&#x20;
{% endhint %}

* Express interest by clicking the **I'm interested** button to get a notification in the **Inbox** every time someone adds a comment.&#x20;

When a user comments on a Discussion, he becomes interested in it automatically.

<div align="left"><figure><img src=".gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure></div>

By clicking I'm not interested, a user can decide to no longer be interested and therefore not get notified anymore.

<div align="left"><figure><img src=".gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure></div>

* [Tag objects](documentation/discussions/tagging-and-notifications.md) or mention users so quickly locate relevant information about them.
* Share a Discussion about a report cell or level with other reports by using the [Shared-Context ](documentation/discussions/shared-context.md)feature.

<figure><img src=".gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

## Properties <a href="#toc69201841" id="toc69201841"></a>

The properties that are specific for the configuration of the **Discussion** widget on **Decisyon App Composer** are listed below:

<table data-full-width="true"><thead><tr><th width="181">Group</th><th width="287">Name</th><th width="436">Description</th><th width="187" align="center">Type</th><th width="258" align="center">Default Value</th><th data-type="checkbox">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Discussions</strong></td><td><a href="documentation/discussions/examples/e.1-discussion-enabled-in-a-context-that-has-no-value.md"><strong>context-parameters</strong></a></td><td>Define the list of pramaters that identify the context of the discussions.</td><td align="center">SELECT</td><td align="center"></td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><strong>allow-discussion-remove</strong></td><td>Allows for the removal of the discussion. The whole discussion and comments may be deleted when this property is enabled. Just the comments may be deleted when this option is disabled.</td><td align="center">SWITCH</td><td align="center">True</td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><a href="documentation/discussions/examples/e.1-discussion-enabled-in-a-context-that-has-no-value.md"><strong>context-root-ID</strong></a></td><td>Set the ID context that the Discussion will be associated. You may see the Discussions that have been created on other pages by using the same ID for the widget on another page. This configuration is useful for displaying the same Discussions on different Pages. The ID is generated automatically by the system and corresponds to the actual ID of the page in which it is included. The ID must be changed manually.</td><td align="center">SELECT</td><td align="center"></td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><strong>groups-post-enabled</strong></td><td>Sets the user group to enter messages in the Discussions. Unless otherwise specified, all groups are allowed to enter messages.</td><td align="center">SELECT</td><td align="center"></td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><strong>post-creation-execute-button</strong></td><td>It sets an action that will be run after creating a Discussion by associating an Execute Object inside the page. The button will be run automatically after successfully creating a new Discussion. Once the execution of the Execute button is completed, a parameter is given a value that identifies the Discussion just created.                                                               The parameter is "<strong>?lastCreatedDiscussionID?</strong>" and is available on the Page. This is useful if you want to save the ID of the Discussion together with the date or the user that generated it.</td><td align="center">SELECT</td><td align="center"></td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><strong>single-discussion</strong></td><td>It enables the creation of a single Discussion. When enabled, it will not be possible to create multiple Discussions associated with the same context.</td><td align="center">SWITCH</td><td align="center">False</td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><a href="documentation/discussions/examples/e.1-discussion-enabled-in-a-context-that-has-no-value.md"><strong>enable-post-discussion-on-total</strong></a></td><td>Enables to post a Discussions even if on the page there is a parameter not defined in the context of the Discussion (e.g. a page-by set to [Total]). The Page Developers should also set the <strong>context-parameters</strong> and <strong>context-root-ID</strong> properties for this configuration.</td><td align="center">SWITCH</td><td align="center">False</td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><strong>activate-message-replay</strong></td><td>Allows you to reply to the Discussion by post messages in it.</td><td align="center">SWITCH</td><td align="center">True</td><td>false</td></tr><tr><td><strong>Discussions</strong></td><td><strong>mime-type</strong></td><td><p>Enables the widget to recognize and validate the types of files that Business Users can upload. By setting this property, you can restrict the accepted file formats to ensure that only files with compatible formats are processed. This helps enhance security and prevent potential issues with incompatible file types. </p><p>Custom file types can be added in addition to the default ones (<strong>Word</strong>, <strong>Audio</strong>, <strong>Excel 2003-2007</strong>, <strong>Image</strong>, <strong>Power Point</strong>, <strong>Video</strong>). In the <strong>Insert</strong> field of the mime-type dialog, input the format type you need and press the <strong>Add</strong> button to add it to the list.                                   </p></td><td align="center">SELECT</td><td align="center"><ul><li>Word</li><li>Audio</li><li>Excel 2003-2007</li><li>Image</li><li>Power point</li><li>Video</li></ul></td><td>false</td></tr></tbody></table>

