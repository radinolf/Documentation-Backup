# Task Board

Thanks to the Task Board, task management becomes more transparent and accessible. Every user can have an overview of their responsibilities and contribute to work in a coordinated and accountable manner, supported by tools designed to simplify daily operations.

* Attach documents or link to reports and platform pages
* Interact with other users through comments and mentions
* Track the progress of assigned or shared tasks
* Create new tasks quickly and intuitively

The Task Board is not just an organizational view; it is an active workspace where you can:

* Modify, comment, or update tasks directly

At the heart of this experience is the **Task Board**, a dedicated platform section where all tasks are displayed in a **column board** format, sorted by status (e.g., _New_, _To Do_, _In Progress_, _Completed_). This visual representation allows users to quickly understand task status, see priorities, and make direct interventions with changes or updates.

The platform offers an advanced task management system, designed to improve work organization, team collaboration, and action traceability. Every task can be created, assigned, monitored, and completed directly within the digital workspace. Task transitions are free, with no predefined constraints.

<figure><img src="../../../.gitbook/assets/image (2371).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

Features Offered by the Task Board for Optimizing Task Management

* **Search Bar**: Located at the top right, it allows users to search for tasks using keywords.​
* **Order By**: Enables sorting of tasks based on criteria such as Priority, Due Date, or Creation Date.​

<figure><img src="../../../.gitbook/assets/image (2373).png" alt=""><figcaption></figcaption></figure>

* **“+” Button in Each Column**: Facilitates the creation of new tasks directly within the desired status column, supporting quick task creation.
* **Sidebar Sections**:
  * **My Tasks**: Displays the current user's tasks.
  * [**Archived**](create-task.md#tasks-archived): Provides access to archived tasks.​
  * [**Followed**](create-task.md#follow-task): Provides access to Followed tasks.​

### Task Status Label Customization

It's possible to customize the labels for task status. The terminology can be adapted to precisely reflect project's language, using specific names like "New," "To Do," "In Progress," "Completed," or "Paused." For international organizations, multilingual support is available, labels can be configured in various languages, allowing each user to view them in the language set in their profile. If a custom translation isn't available for a specific language, the system will automatically display the default label.

For each task status ("NEW", "TO DO", "IN PROGRESS", "DONE", "PAUSED"), enter desired translations, managing both the displayed label and an associated description.

#### Label Configuration Fields

Each task status has the following attributes to support customization and multilingualism:

* `label-tag`: This is the multilingual tag for the status label. For example:
  * `<#TASK_ST_DONE_LBL/>` for the "DONE" status
  * `<#TASK_ST_INPROG_LBL/>` for the "IN PROGRESS" status
  * `<#TASK_ST_NEW_LBL/>` for the "NEW" status
  * `<#TASK_ST_PAUSED_LBL/>` for the "PAUSED" status
  * `<#TASK_ST_TO_DO_LBL/>` for the "TO DO" status
* `label-default`: The default label displayed if a custom translation is missing for a specific language.
* `desc-tag`: This is the multilingual tag for the tooltip associated with the status label. For example:
  * `<#TASK_ST_DONE_DS/>` for the "DONE"  tooltip
  * `<#TASK_ST_INPROG_DS/>` for the "IN PROGRESS" tooltip
  * `<#TASK_ST_NEW_DS/>` for the "NEW" tooltip
  * `<#TASK_ST_PAUSED_DS/>` for the "PAUSED" tooltip
  * `<#TASK_ST_TO_DO_DS/>` for the "TO DO" tooltip
* `desc-default`: The default description displayed if a translation for the description is missing.

For more details see the documentation [Labels](../../instance-configuration/multilanguage-and-localization/labels-management.md)

{% hint style="success" %}
The App Builder enters the desired translation in the Labels Management section. If no custom label is configured for a status, the default label will be displayed.
{% endhint %}

#### Multilingual Support

Each label and description can be configured in multiple languages. The platform automatically selects the correct version based on the language set in each user's profile, ensuring a localized and consistent experience.e&#x20;
