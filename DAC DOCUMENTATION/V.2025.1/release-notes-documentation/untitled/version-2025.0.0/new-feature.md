# New Feature

**DACXX-1586**: **Mentioning Users and Pages in the Comment of the Task**\
As a user of the task management module, I want to be able to mention other users in the comment section using the user name or the page name so that I can directly notify relevant team members and involve them in task discussions. This helps save time, ensure updates reach the right people, and centralize communication in task threads.

**DACXX-1580**: **Direct Link to Task in Notification Email for mentioning**\
Adds clickable links in mention notifications that redirect the user to the mentioned task, depending on their role (involved or follower). If not logged in, users are redirected to login first, then to the task.

**DACXX-1579**: **Receiving Notifications for mentioning in task**\
Triggers email notifications when a user is mentioned in a task. The email includes information like the task title, the name of the person who mentioned the user, and the time of the mention, while respecting the organization’s visual identity.

**DACXX-1538**: **Direct Link to Task in Notification Email for tasks updates**\
Notification emails now contain direct links to the updated tasks. Users can be redirected based on access rights and are informed if a task is no longer available.

**DACXX-1456**: **Quick Task Creation on Task Board**\
A "+" button on task board columns allows users to quickly create a task by entering only the title. The task appears immediately at the top, ignoring filters temporarily.

**DACXX-1334**: **Me API Rest to retrieve user teams**\
Introduced REST APIs `/me/teams` and `/me/organizations/{organization}/teams` to retrieve the teams associated with a user, improving integration capabilities.

**DACXX-1279**: **Third-party integration API Rest**\
Exposes APIs for third-party services to access and manage organizations and teams. These are resource-based and designed for non-user tokens.

**DACXX-1266**: **Remove files attached to Task**\
Assignees and reporters can now remove attached files from tasks. The feature is backed by a new BlobStore microservice that handles external blob storage like AWS S3 or Azure.

**DACXX-1249**: **View comments associated to a Task**\
Users involved in a task can view its comments, sorted chronologically. Comments include author information and timestamps for creation and last update.

**DACXX-1248**: **Delete comments from Task**\
Only the user who created a comment can delete it. Deleted comments are no longer visible.

**DACXX-1247**: **Modify comments associated to a Task**\
Users can edit their own comments. The original timestamp remains, and a new "last modified" timestamp is shown.

**DACXX-1225**: **TASK – Option to disable task-related features**\
A new configuration property disables the task and team management UI entirely. This avoids confusion for customers not using those features and hides related menus and APIs.

**DACXX-1214**: **View Task details**\
Task dialogs now display all relevant details including title, organization, team, assignee, priority, description, due date, solution, and timestamps.

**DACXX-1206**: **Contextual Tasks – Link to Page**\
Contextual tasks now include a link back to the report page where they were created. Filters are preserved and applied upon opening.

**DACXX-1205**: **View Report Contextual Tasks**\
Users can see tasks linked to specific report cells. These tasks appear with a visual indicator and respect visibility rules.

**DACXX-1202**: **Following Task View**\
Added a dedicated view for tasks that the user follows. Tasks are categorized by status, and followers can comment but not edit the task.

**DACXX-1201**: **Task List for the Archived View**\
A list-based view allows users to browse archived tasks they are associated with. Includes metadata and menu options for restoring or deleting.

**DACXX-1200**: **Sorting Tasks on the Archived TaskList**\
Introduced sorting by title, due date, team, and user in the archived task list. Sort order persists during navigation.

**DACXX-1199**: **Sorting Tasks on the Taskboard**\
Tasks on the taskboard can now be sorted by priority, due date, and creation date, and the sort order is preserved between sections.

**DACXX-1198**: **Task Deletion**\
Only the reporter or assignee of a task can delete it. Deletion requires confirmation and removes the task from all views.

**DACXX-1197**: **Task Editing**\
Assignees and reporters can edit specific fields (title, priority, description, solution) of a task using a dedicated UI.

**DACXX-1172**: **Delete File from Blob Store**\
Provides a secure API endpoint for deleting files from the external blob store using JWT and tenant authentication.

**DACXX-1170**: **Upload files to Task**\
Assignees and reporters can upload and manage attachments on tasks. Files are stored via the BlobStore service and shown with filenames.

**DACXX-1169**: **Retrieve File from Blob Store**\
Introduced a secure GET endpoint to retrieve files from blob storage by unique ID, supporting metadata and content delivery.

**DACXX-1165**: **Upload File to Blob Store**\
Added a PUT endpoint for uploading files to a blob store. Includes authentication, validation, and logging for audit purposes.

**DACXX-1162**: **Filtering Tasks on the TaskList**\
Advanced filters allow users to search tasks by various criteria like organization, team, assignee, reporter, status, due date, and creation date.

**DACXX-1100**: **The user profile section must show the teams they belong to**\
User profiles now display a structured list of organizations and corresponding teams for better clarity.

**DACXX-1094**: **After creation, it must be shown how to associate users to the newly created team**\
Improved UX by providing guidance after team creation on how to assign users.

**DACXX-1059**: **Follow/Unfollow a Task**\
Users mentioned in a task can choose to follow it, enabling them to receive updates and comment. Unfollowing stops notifications.

**DACXX-1052**: **Add comments to Task**\
All users involved in a task can now leave plain-text comments, complete with user and timestamp metadata.

**DACXX-1051**: **Archived Task View**\
Archived tasks are now available in a dedicated view and organized by status. Access rules are based on user role.

**DACXX-1050**: **Filtering Tasks on the Taskboard**\
The taskboard now supports advanced filtering by text, organization, team, assignee, reporter, and date ranges.

**DACXX-1043**: **Update from Angular 16 to 18**\
Upgraded the front-end application and Angular Material library to version 18, improving performance and compatibility.

**DACXX-1040**: **Display Organizations and Teams in User Support Panel**\
The support panel now shows which organizations and teams a user belongs to, grouped by organization.

**DACXX-1016**: **Associate Users to a Team from the Organization's User List**\
Allows assigning users to teams directly from the organization’s user list with validation and error messages.

**DACXX-1011**: **Team Renaming**\
Enabled administrators to rename teams within their organization, with validation to avoid duplicates.

**DACXX-1010**: **Team Deletion**\
Admins can delete teams under their organization. The interface prompts confirmation and handles errors gracefully.

**DACXX-1009**: **Team Selection**\
Clicking a team in the navigation panel now shows its members in the content panel, enhancing manageability.

**DACXX-998**: **Archive a Task**\
Tasks can now be archived by reporters or assignees. Archived tasks are removed from the main views but remain editable and retrievable.

**DACXX-979**: **Configuring Status Labels**\
Status labels (e.g., NEW, TO DO, IN PROGRESS) are now configurable per language in the Label Management section.

**DACXX-978**: **Mentioning Reports**\
Allows users to mention reports using @ notation in task descriptions and solutions, with link generation and access validation.

**DACXX-977**: **Mentioning Pages**\
Adds the ability to mention specific pages in tasks using @ notation. Deleted pages are marked and access is permission-based.

**DACXX-976**: **Mentioning Users**\
Business users can mention other users from the same organization in the task description and solution fields, improving collaboration.

**DACXX-972**: **Validating File Uploads for Security Compliance**\
A new property in Design Studio controls MIME types allowed for file uploads. Unauthorized types are blocked with a user-friendly error.

**DACXX-970**: **Creating Contextual Tasks from Report Cells**\
Tasks can now be created directly from report cells with context keys, initial and target values, and pre-filled organizational data.

**DACXX-969**: **Maintaining an Audit Trail for Task Modifications**\
All task changes are now tracked, including who modified what and when, enabling full traceability.

**DACXX-968**: **Receiving Notifications for Task Updates**\
Users now receive detailed email notifications when tasks they follow are updated, including who made the changes.

**DACXX-966: Assigning Tasks to Specific Users or Teams**\
Tasks can be assigned to individual users or teams, with dropdown selection and permission validation.

**DACXX-965**: **Viewing Tasks on the Taskboard**\
The taskboard view displays tasks grouped by status. Each card shows key metadata and supports interaction.

**DACXX-964**: **Managing Task Status with Defined States**\
Tasks now support predefined statuses (NEW, TO DO, IN PROGRESS, DONE, PAUSED), with customizable transitions.

**DACXX-963**: **Creating a Task with Essential Details**\
Introduced form to create new tasks with title, organization, assignee, description, and optional due date.

**DACXX-937**: **Viewing Teams**\
Team structures are now visible under each organization, providing clarity on group assignments.

**DACXX-934**: **Manage Team Creation**\
Admins can create teams and assign them to specific organizations directly from the user section.

**DACXX-925**: **\[REMOVE] – Remove all references to the Task**\
All legacy references to the Task component were removed from the application codebase.
