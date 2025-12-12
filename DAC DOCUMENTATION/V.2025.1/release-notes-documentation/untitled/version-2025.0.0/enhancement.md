# Enhancement

This section outlines the enhancements made to existing features. These improvements are designed to refine the user experience, optimize interfaces, and improve overall system performance.

* **DACXX-1806 - Increase DAC’s Level API**\
  The API level version has been updated to 2.6 for both Pages and Appcomposer to support contextual task creation through the new JS Task API.
* **DACXX-1795 - Update Task API function**\
  The JavaScript function label used in the SmartGrid menu was updated from “attach task” to “create task” to better reflect its behavior.
* **DACXX-1768 - Internationalize task notification emails**\
  Notification emails related to task creation, updates, and user mentions now reflect the language preference of the recipient user.
* **DACXX-1767 - Change "Open Task" label to "View Task" in notification emails**\
  The “Open Task” button in notification emails was renamed to “View Task” to improve clarity and consistency with platform terminology.
* **DACXX-1766 - Clearly highlight overdue tasks**\
  Overdue tasks are now visually highlighted with a red background and icon both in the task board and detail view to help users identify them quickly.
* **DACXX-1765 - Notify users when a task opened from a mention email can be followed Improved Description**\
  Added a visible “Follow Task” button and new UI messages to indicate when a task can be followed and commented on after following.
* **DACXX-1764 - Display the task description first when opening a task**\
  When opening the task detail dialog, the Description tab is now displayed as the default view to provide immediate context.
* **DACXX-1556 - Add an header into TASK section toolbar**\
  A header was added to the Task section toolbar to align with the design used in the Pages and Users sections.
* **DACXX-1536 - Improve the task details dialog aesthetics and style**\
  Improved the visual design of the task detail dialog with rounded borders, bold section titles, and better visual separation for readability.
* **DACXX-1505 - Add logs and exception when env variables/properties are missing**\
  Added validation checks and logging for missing MongoDB configuration properties during application startup to prevent runtime issues.
* **DACXX-1486 - Add UI Reactions for Organization and Team Management Actions**\
  Implemented UI updates and reactions when managing users, organizations, and teams, such as keeping panels in sync and reflecting count updates.
* **DACXX-1460 - Improve Task Board Visual Design for Better Usability**\
  Redesigned the task board for improved readability, increased spacing, and consistent appearance across desktop and mobile views.
* **DACXX-1459 - Refactoring RestTemplate Configuration to use JdkClientHttpRequestFactory**\
  Replaced Apache HttpClient 5 with JdkClientHttpRequestFactory in RestTemplate configuration to fix chunked response issues.
* **DACXX-1455 - Optimize Refresh data for Task Query Model**\
  Optimized the task query model to reflect updates when users, teams, or organizations are changed, added, or removed.
* **DACXX-1322 - Split Task Status "NEW/TO\_DO" into Separate States - "NEW" and "TO\_DO"**\
  Separated the combined “NEW/TO\_DO” status into two distinct states to better align with task planning and execution phases.
* **DACXX-1313 - Managing external events on kreacher**\
  Ensured that external events (e.g. user/team/org creation, updates, deletions) are reflected in tasks for data consistency.
* **DACXX-1311 - Modify user events to use Rabbit queues**\
  Updated the user event handling mechanism to use RabbitMQ queues for better consistency and async processing.
* **DACXX-1278 - Rich Text Support in Task Description and Solution Fields**\
  Enabled rich text editing in the “Description” and “Solution” fields of tasks, allowing formatted content for better clarity.
* **DACXX-1275 - Task editing - Update due date**\
  Introduced the ability for task assignees and reporters to edit the task’s due date.
* **DACXX-1182 - User API Rest refactoring**\
  Refactored the User Administration REST API, introducing new endpoints for timezone, language, email notifications, scopes, and group management.
* **DACXX-1177 - API Rest Team refactoring**\
  Refactored Team REST API endpoints, including naming changes, team-user assignment management, and new CRUD endpoints.
* **DACXX-1176 - API Rest Organizations refactoring**\
  Refactored Organization API structure with updated paths and new endpoints for creation, deletion, renaming, and user listing.
* **DACXX-1143 - Users administration api to retrieve users**\
  Refactored internal API to retrieve users with support for organizations and teams, including pagination and filtering options.
* **DACXX-1137 - Service proxy to forward request to Kreacher**\
  Implemented a service proxy to forward authenticated requests to Kreacher using JWT in the `x-auth-token` header.
* **DACXX-1093 - \[Assessment] Support for Microsoft Edge Browser in DAC**\
  Ensured full compatibility with Microsoft Edge to support organizations where it is the default browser. [See documentation](../../../documentation/introduction/supported-browsers-and-devices.md)
* **DACXX-943 - Remove Users from a Team from Team’s User List**\
  Enabled user administrators to remove one or multiple users directly from a team's user list, with appropriate error handling.
* **DACXX-920 - JS API - Enhance DECISYON.page.getPageParameters to capture all parameters**\
  Improved the `DECISYON.page.getPageParameters()` JS API to return dynamically created parameters and their updated values even without widgets.
* **D4C-10247: Remove the metadata installer from Design Studio**\
  Design Studio is no longer able to create or update metadata on a schema. This responsibility has been shifted entirely to AppComposer Runtime or Pages. All Liquibase dependencies, migration scripts, and metadata references have been removed from both Design Studio and Common Core, and moved to the Runtime codebase. If a user attempts to launch Design Studio on an empty schema, a clear warning is now displayed.
