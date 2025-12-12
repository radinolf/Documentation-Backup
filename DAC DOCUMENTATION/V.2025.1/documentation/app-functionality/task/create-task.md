# Create Task

The task creation interface is organized into multiple tabs, each designed to help you define and manage tasks efficiently.

Below is an overview of the key tabs and their functionalities:

{% tabs %}
{% tab title="Description" %}
<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

* **Description**: It is possible to enter a technical explanation and define the objectives of the task. Thanks to the text formatting toolbar, the content can be easily customized.

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* **Attachments**: Within a task, both the _Reporter_ and the _Assignee_ can attach files such as documents, images, or other useful resources. Attachments are displayed with their file name and can be downloaded by clicking on them.\
  File removal is only allowed for users who have the appropriate permissions.
{% endtab %}

{% tab title="Info" %}
<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* At the top is the **title** of the Task. (editable)
* **Reporter**: user who created the task (not editable)
* **Organization**: Indicates the organization to which the user who created the task belongs . If the user is associated to only one organization the Organization field is not visible .
* **Priority**: Allows you to set the ticket's priority from the available options.​ (editable)

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

* **Status** : indicates the current status of the task (not editable)
* **Creation Date** : indicates the date of creation of the Task (not editable)
* **Assegnato to - Team**: Assignment to a team&#x20;
* **Assegnato a utente**: Assignment of the task to a specific user belonging to the team ( if selected) otherwise it is possible to select an organization user
{% endtab %}

{% tab title="Comments" %}
<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

Collaborative section for leaving textual messages. Through the menu (⋮), a contextual menu opens where it is possible to delete or modify the comment. Please see the [Appendix ](create-task.md#comments-and-mentions-direct-collaboration-within-the-task)for more details.
{% endtab %}

{% tab title="Solution" %}
<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

It is possible to enter a technical solution to resolving the task. Thanks to the text formatting toolbar, the content can be easily customized.

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}



## Creation, Edit and Deletion

Effective task management is crucial for maintaining streamlined and collaborative workflows within the platform. The primary operations available include:​

* [**Creating a Task**: ](create-task.md#creazione-dei-task)To add a new task, select  the "+" button in the desired section. Enter relevant information such as the title, description, assignee, due date, and priority. Once all details are filled in, save the task to make it visible to all team members.​
* [**Editing a Task**:](create-task.md#task-editing) To update an existing task, open it and select the edit option. Make the necessary changes to the available fields and save to update the shared information.​
* [**Deleting a Task**:](create-task.md#delete-task) To remove a task, access the task's options menu (often represented by three dots or a similar icon) and select "Delete." The system will prompt for confirmation before proceeding with the permanent deletion. Once deleted, the task will be removed from all views and will no longer be accessible.

### **Create Task**

To facilitate agile workflows, a "+" button is available at the top of each column on the task board.

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>





1. It is sufficient to enter only the title of the task (in this case: "Standardize Digital Twin Data Models") and click on Create to generate it.
2. Once created, the task will appear in the column with the other activities.
   * Clicking on the three-dot menu (⋮) opens a contextual menu with three options:
     * **Open**: opens the panel with the task details
     * **Delete**: deletes the task
     * **Move to Archived**: archives the task (without deleting it). Will be present in the folder Archived
3.  Once clicked on **Open**, the detailed panel is accessed, where it is possible to complete the task with all the information:

    * **Organization:** Select the organization to open the task on
    * **Priority**: priority to assign to the task
    * **Due Date**: assign the task’s due date
    * **Assigned to  team**: assign the task to a Team
    * **Assigned to user** :assign the task to a specific user
    * **Description** : technical explanation and objectives of the task
    * **Attachments**: option to upload files (button "Add attachment")
    * **Comments**: collaborative section for leaving textual messages
    * **Solution**: field to write the proposed solution



{% hint style="success" %}
**Task Assignment: Users Based on Team or Organization**

When assigning a task to a team and then to a specific user, the users available in the list are those belonging to the team. If no team is selected but a specific user is chosen, the list of users will show those belonging to the organization.
{% endhint %}

"**Close**" button at the bottom to close the panel.



### Task Editing

To edit the task, click on the three-dot menu (⋮) to open a contextual menu and select "Open." The same action can also be performed by clicking on the task title.

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

Existing tasks can be updated by the users **directly involved** (Reporter or Assignee).

It is possible to modify only this fields<br>

* Title
* Priority
* Description
* Solution
* Due Date
* Target Value
* Assigned to - Team
* Assigned to - User
* Comments&#x20;
* Solution

{% hint style="success" %}
Only the **Reporter** or **Assignee** can make changes.
{% endhint %}

### **Delete Task**

To **delete** a task, access the three-dot menu (⋮) and select the "Delete" option. Only the **Reporter** or the **Assignee** have the permissions to permanently delete a task. The system will request explicit confirmation before proceeding with deletion.&#x20;

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
The attachments of the task are deleted together with the task.
{% endhint %}

## Permissions and Security

n the task management process, editing and deletion operations are reserved exclusively for users who hold an active role in the task, such as the _Reporter_ or the _Assignee_. This approach ensures consistent and responsible control over activities.\
Additionally, all actions performed are recorded in the audit log system, guaranteeing full transparency and enabling the monitoring of every operation carried out.\
The following chapters will provide a detailed overview of the rules for editing, assigning, and managing tasks, with a particular focus on security and traceability.

### Permission Map for Task Management

Every action that can be performed on a task—such as commenting, editing, archiving, or deleting—is governed by a permission system that takes into account the user's role and their relationship to the task (e.g., whether they are the assignee, reporter, mentioned, part of a team, or simply an observer).\
The table below provides a detailed summary of the permissions automatically granted based on the type of relationship between the user and the task.

If the task has an assignee, users with the role listed in the table have or not permissions to manage the tasks. Let’s see in detail what they are:





<table data-full-width="true"><thead><tr><th width="111.44439697265625">Ruolo</th><th width="236.8890380859375" align="center">Does the task have an assignee?</th><th width="98" align="center" valign="middle">COMMENT</th><th width="141.3333740234375" align="center">CHANGE STATUS</th><th width="84.666748046875" align="center">ARCHIVE</th><th width="82.4444580078125" align="center">DELETE</th><th width="98.1112060546875" align="center">MODIFY</th><th width="72.4444580078125" align="center">FOLLOW</th></tr></thead><tbody><tr><td><strong>Assignee</strong></td><td align="center">Any</td><td align="center" valign="middle">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>Reporter</strong></td><td align="center">Any</td><td align="center" valign="middle">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>Users Involved</strong> </p><p><strong>as Team</strong></p></td><td align="center">Yes</td><td align="center" valign="middle">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">⛔</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>Users Involved asTeam</strong></td><td align="center">No</td><td align="center" valign="middle">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>Users Involved asFollower</strong></td><td align="center">Any</td><td align="center" valign="middle">✅</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">✅</td></tr><tr><td><strong>Mention</strong></td><td align="center">Any</td><td align="center" valign="middle">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">✅</td></tr><tr><td><p><strong>Other</strong></p><p><strong>(default)</strong></p></td><td align="center">Any</td><td align="center" valign="middle">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td><td align="center">⛔</td></tr></tbody></table>

Description of permissions:

* **COMMENT**: ability to add comments to the task.
* **CHANGE STATUS**:possibility to change the status of the task (e.g. from "In progress" to "Completed").
* **ARCHIVE**: possibility of archiving the task.
* **DELETE**: possibility to permanently delete the task.
* **MODIFY**: possibility to modify the main fields of the task (title, description, priority, etc.).
* **FOLLOW**: ability to follow the task and receive notifications on updates.

## Tasks archived&#x20;

**An archived task** is an activity that has been completed, suspended, or temporarily removed from the active operational flow, but remains accessible in a dedicated section. Archiving helps keep the interface clean while still allowing access to historical tasks when needed.

Only the **Reporter** or **Assignee** can file a task. The action r**emoves the task from active views** but does not delete it.The task remains accessible in a dedicated section **Archivied**, where it can be managed, consulted or restored.

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

The "**Archived**" section, located in the left-hand toolbar, provides access to all tasks that have been archived.

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

View all archived tasks they have access to (as reporter, assignee, or team member).

Each task is displayed in the corresponding column based on its current status.

In the Archived board, users can sort tasks by:

* priority
* due date
* creation date.

Each task includes a contextual menu, accessible via the three-dot icon, offering the following options:

* **Open**: View the task details
* **Delete**: Permanently remove the task
* **Move to My Task**: [Unarchive ](create-task.md#ripristino-unarchive)the task and move it back to the Taskboard



<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

### Unarchive Task

Archived tasks can be reactivated and moved back to the "My Tasks" board. This option is available directly from the task's contextual menu within the archived view. Only authorized users such as the **reporter** or **assignee** are allowed to perform this action.

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>



## Follow Task &#x20;

Users [mentioned ](create-task.md#mention-resources-user-pages-and-reports)within a Task, for example in a comment, receive an email notification even if they are not the assignees of the activity. In this case as well, the email includes an "**View Task**" button for direct access.

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

**How to follow a Task**\
Start following a Task to receive updates, even if you are not the assignee.\
To do so:

* Open the Task from the email notification.
* Click on the three-dot icon in the top right corner to open the action menu.
* Select the **Follow** option.

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>



Once the follow is activated, the Task will be listed in the "Follow" section of the Taskboard, making it easy to monitor its status and receive notifications for every update.



<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
**Note:** Those who follow a Task cannot modify it or add comments unless they are also the Reporter
{% endhint %}

#### How to Unfollow a Task

To stop following a Task, follow these steps:

1. Open the Task from the Taskboard.
2. Click the icon with three dots in the top right corner.
3. Select **Unfollow**.

The Task will be removed from the "Follow" section, and you will no longer receive notifications regarding its updates.

## Direct access to tasks via email &#x20;

Whenever a user is **assigned to a Task**, they automatically receive an **email notification** containing all the main information related to the Task.\
Within the email, there is an **"View Task"** button that allows direct access to the Task within the **Taskboard**, without needing to search for it manually. Additionally, each time a Task is **modified** (e.g., changes in description, priority, deadline, etc.), **all involved users** (assignees, mentioned, or followers) receive an **email notification** with details of changes.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



## Contextual Tasks&#x20;

Contextual **tasks** allow you to create activities directly from a cell in a report, maintaining the link with the

<figure><img src="../../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

A task can be generated, for example, in the presence of an outlier or data that requires attention. When the task is created, the system automatically saves a link to the source report, including any active filters (such as selected tabs or drill-through). This way, anyone accessing the task can view the data in its original context. Access to the report is restricted to users with the appropriate

#### Create a Contextual Task  <a href="#come-creare-un-task-contestuale" id="come-creare-un-task-contestuale"></a>

To create a new context-specific Task, position yourself on the cell of the relevant report, right-click, and select the **Create Task** option from the context menu. When the task is created on a numeric cell, an icon is displayed directly within the report cell. The icon is only visible to users authorized to view the task.

{% hint style="success" %}
The task will be automatically removed from the report if it is closed, archived, or deleted


{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2374).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

When a contextual Task is created, a set of useful details can be defined to accurately describe and assign the activity. The available fields are as follows:

* **Title**: Enter a clear and concise title that identifies the goal or nature of the task.
* **Description**: Provide a detailed description of the task, specifying the context, any anomalies detected, and the expected actions. This field allows you to share useful information with all involved members.
* **Starting Value**: Automatically displays the initial value of the report cell from which the task was generated. This field is not editable and serves as a reference for evaluating data trends over time.
* **Target**: Define the target value to be achieved. This parameter helps measure the deviation from the current data.
* **Organization**: Select the organization the task refers to. This field is useful in multi-organization environments to properly route activities.
* **Assigned to - Team**: Indicate the Team responsible for executing the task. Assigning it to a group allows for more flexible and collaborative management.
* **Assigned to - User**: Optionally, you can assign the task to a specific user within the selected Team to clearly identify who is responsible for it.
* **Priority**: Select the task’s priority level (e.g., low, medium, high) to help manage tasks based on their urgency or importance.
* **Due Date**: Set a date by which the task must be completed. This helps track deadlines and plan activities over time.

{% hint style="info" %}
**Note:**  The fields "Starting Value" and "Target" are only visible when the task is created on a metrics
{% endhint %}

Each created task is automatically added to the Taskboard. When you open the Task from the taskboard, it contains a link in the _Description_ section to the page and report from which it was generated.

<figure><img src="../../../.gitbook/assets/image (2376).png" alt=""><figcaption></figcaption></figure>

For each contextual task, three key pieces of information are saved:

* **Starting Value**: the initial value of the cell;
* **Target Value**: the target value of the task.

These values make it possible to monitor progress toward the objective directly from the task.

Finally, if multiple reports share the same context (e.g., same filters or parameters), the task will also be visible in those reports, ensuring consistency and collaboration across different reports.

## Appendix

## Comments and Mentions: Direct Collaboration within the Task

Effective communication is essential to ensure all activities are carried out in a coordinated manner. For this reason, the platform integrates a **comprehensive system of comments and mentions**, allowing users to communicate directly within tasks, swiftly involving the people.

### Write comments

Each task has a dedicated comment area where involved users can leave notes, updates, or requests.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}


💡**Who can comment?**

* Assignee
* Reporter
* Members of the team
* Users following the task
{% endhint %}



Comments are in plain text format, show author and timestamp, and are ordered in reverse chronological order so that the most recent messages are displayed first.

### Editing and Delete

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

To **edit** or **delete** a task, access the three-dot menu (⋮) and select option. Users can only edit their own comments. When a comment is edited, the original creation date is preserved, and the interface displays the timestamp of the last modification.\
Users can also delete their own comments. Deletion is permanent, and the content will no longer be visible.

## Mention Resources: User, Pages and Reports

Within tasks, it is possible to use mentions to create direct links to internal resources on the platform, such as pages or reports. This functionality makes it easier and faster to access relevant content, keeping the work context-rich and easily navigable. The following sections will detail the different types of mentions available and how they work.

### Mentioning user: @username&#x20;

It is possible to involve other users directly in the workflow by writing @username in comments or some fields of the task (such as description or solution).

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
💡**What happens when someone is mentioned?**

* The user receives an email notification containing:
  * The task name
  * Who mentioned them
  * Date and time
* The email includes a direct link to the task&#x20;
  * If the user is not logged in, they will be redirected after login.&#x20;
  * If the task has been deleted or invalidated, a message indicating that the content is unavailable will be shown.
* The mentioned person can following the task , and it will appear in their “Followed Tasks” section.
{% endhint %}

{% hint style="danger" %}
If the mention is **removed** and the user is no longer mentioned elsewhere in the task, he will be automatically disconnected from the task .
{% endhint %}

### **Mentioning Pages** @ followed by the name of the page

In addition to tagging users, the mention system can also be used to reference internal resources, making collaboration and navigation even more efficient. By simply typing "`@ followed by the name of the page`"  followed by the name of a page or report, users can create dynamic links directly within the task description or solution field. This feature not only simplifies access to related content but also helps keep all relevant information connected and within reach.

### Mentioning Report `@report-name`

The same logic applies to reports. By typing `@report-name`, users can reference a specific report directly within the task. This creates a quick-access link that enhances clarity and context, especially when the task involves data analysis or reporting activities. As with pages, the system ensures that the user has the necessary permissions before allowing access to the mentioned resource.

### **Audit Log –** Tracking of Task Changes&#x20;

The audit log is an automatic record of changes made to tasks. It serves to ensure transparency, accountability and traceability, and is designed to meet the needs of business users who want to keep control over who did what and when. In the metadata schema of application metadata an `audit_record`   table is available where the information of changes is stored.

To automatically manage the removal of obsolete activity logs, two properties can be configured:

* **`config.tasks-log-retention-time`**: defines the number of days to retain logs related to active tasks.
* **`config.deleted-tasks-log-retention-time`**: defines the number of days to retain logs related to deleted tasks.

Configuring these properties is optional if no value is explicitly set, the system will apply a default retention period of **30 days**.

For more details, refer to the[ installation guide.](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/SZPuXAjYCF5nz4it3bew/)

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>
