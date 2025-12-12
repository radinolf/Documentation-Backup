---
description: >-
  It is possible to start discussions or create tasks on the individual cells of
  the report. Details on these functions are described in the Social User ,
  Discussion section and Task section.
---

# Contextual collaboration

DAC offers functionalities for Collaboration related to the data.

It is possible to start [discussions ](discussion.md)or create [tasks ](../task.md)on the individual cells of the report.

<figure><img src="../../../.gitbook/assets/image (823).png" alt=""><figcaption></figcaption></figure>

&#x20;

DAC users can use these functions only on the reports enabled by the administrator.

The following figure highlights the collaboration menu items enabled on the report .



<figure><img src="../../../.gitbook/assets/image (1396).png" alt=""><figcaption></figcaption></figure>

&#x20;

Tasks can be notified to recipients through e-mails which give direct access to the task. Therefore, in order to access the task, the mail server and DAC server must be configured (see paragraph [Manage Services & Servers](../../instance-configuration/tools/manage-services-and-servers.md)).

You can also define a shared context between reports, so that multiple reports can share the Discussions or the Tasks:

For example, when a discussion or a task on a certain level (such as product) is added, this will also be visible on the second report if the two reports share the same context.

The **Discussion** and the **Task** on the report is enabled by the property (Collaboration group) :

<figure><img src="../../../.gitbook/assets/image (731).png" alt=""><figcaption></figcaption></figure>

### Discussion <a href="#discussion" id="discussion"></a>

To enable report discussion , select the **Collaboration** property group from the **Properties** tab.

<figure><img src="../../../.gitbook/assets/image (510).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (822).png" alt=""><figcaption></figcaption></figure>

* **activateCellsDiscussion** enables the Attach Discussion item in the pop-up menu of DAC report cells. This property enables the following:
  * **shared-context** enables context sharing with other reports, so that discussions in it can be useful not only on the report itself, but also on other reports.
  * **context-id** is the shared context identifier

if, for example, two reports have the same context-id when a discussion is submitted on a certain level (such as product), this will also be visible on the second report.

**Note:** Users can comment on or change Discussions on all the reports that share the context, if they have the permissions on at least one of the reports.

* **activateCellsTask** enables the Attach Task item in the pop-up menu to the cells of the report in DAC. This property enables the following:
  * **viewCellinfoTask** displays, on the cells of the report, the information relating to the task
  * **visualizationMode** provides two task display methods **inline** or **new-line** (respectively in relation to the value of the cell or below it)
  *

      <figure><img src="../../../.gitbook/assets/image (367).png" alt=""><figcaption></figcaption></figure>

**shared-context** enables the sharing of a context with other reports, so that the tasks opened in it may be used not just on the same report, but also on other reports

**Note:** In the Tasks created in reports where this property is activated, users may comment on or change discussions if they have the permissions on at least one of these reports.

– **context-id** identification of the shared context

If, for example, two reports have the same context-id when a discussion is submitted on a certain level (such as product), this will also be visible on the second report.

**Note:** Users can comment on or change the Tasks on all the reports that share the context, if they have the permissions on at least one of the reports.

Viewing a Task of the Cell / Metric of a Report with the Use of Multiple Tags

<figure><img src="../../../.gitbook/assets/image (517).png" alt=""><figcaption></figcaption></figure>

Discussion Enabled on the Report Cells

<figure><img src="../../../.gitbook/assets/image (908).png" alt=""><figcaption></figcaption></figure>



