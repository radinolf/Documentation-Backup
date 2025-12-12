# Swagger e Postman

Swagger serves as the reference documentation for the App Composer API. This resource is designed to provide developers with detailed information on how to effectively integrate and utilize the DAC APIs within their applications.&#x20;

The Swagger documentation includes specifications on available endpoints, supported operations, expected request and response structures, and examples of use cases.&#x20;

Additionally, the Swagger documentation offers interactive features that allow developers to directly test API calls within the documentation environment, promoting a deeper understanding and facilitating easier integration.

For each web app AppComposer, Pages, and Cockpit there is corresponding Swagger documentation.

* **Swagger AppComposer**: You can access the AppComposer Swagger documentation from the main menu of the web app by navigating to **Online Help >> REST API Documentation for App Composer.**

For the Pages and Cockpit web apps, access the documentation by entering the URLs provided below, replacing `[Pages/Cockpit domain]` with the domain of the web app:

* **Swagger Pages**: \[https://\[Pages domain]/swagger-ui/index.html]
* **Swagger Cockpit**: \[https://\[Cockpit domain]/swagger-ui/index.html]

{% hint style="success" %}


**Example**:

* `https://`**`Pages.com`**`/swagger-ui/index.html`
* `https://`**`Cockpit.com`**`/swagger-ui/index.html`
{% endhint %}

Below, we provide a guide to the main features of the Swagger interface for the App Composer API. Our Swagger documentation offers intuitive tools for interacting with the API, allowing you to explore and test various API calls directly from the page. Here’s how to test an API directly from the documentation.

<figure><img src="../../../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

1. You can select the API version from the dropdown in the upper right corner
2. In "server" you can see the URL of your application.
3. The "Authorize" button lets you insert a Bearer token in Swagger, enabling you to run API requests straight from the documentation.
4. In the Swagger documentation, APIs are grouped by category for both versions.
5. This link  opens the Open API definition of App Composer API for the version selected. To many info please see the details

### List of Cockpit API

{% tabs %}
{% tab title="API Details" %}
1. `cockpit-controller-impl:`  manage various operations related to job and service management within the application. They allow you to update job statuses, control service operations (start and stop), and retrieve information about jobs and their executions.
2. `security-controller-impl:` handle the creation, retrieval, and deletion of API keys. These keys are used for authorizing access to the application's APIs.
3. `application-controller-impl:`manage application imports and provide access to application details and control files. They allow you to import applications, retrieve application information, and delete applications.
4. `metadata-controller-impl:` allows you to retrieve metadata information for a specific object within an application.
5. `action-list-controller-impl:` manage action lists within an application. They provide functionality for retrieving action lists, their details, statistics, logs, and actions performed by users.
{% endtab %}
{% endtabs %}

#### List of AppComposer APIs&#x20;

{% tabs %}
{% tab title="API Version 1" %}
1. `Action List Read Operations`:  enables users to retrieve data from the Action List, allowing them to access and view information related to action items, tasks, or activities within the system.
2. `Document`:  provides operations related to documents, allowing users to create, retrieve, update, and delete documents within the application.
3. `Resources`: manage operations related to resources within an application. These operations include uploading, updating, retrieving, and deleting resources, as well as obtaining metadata about them. Resources can be files or other entities associated with the application.
4. `Widget`:  handles operations concerning widgets, which are graphical components or elements used to display information, interact with users, or perform specific functions within the user interface.
5. `Query`: for executing queries and retrieving results within the application.
6. `Tag`: for managing tags within the application, including retrieving items that can be used as tags in discussions.
7. `Action List Scheduling Write Operations`:   allows users to write or create scheduling configurations for action lists, enabling them to schedule and automate the execution of action list tasks or processes.
8. `DAC Instance:` for managing and retrieving information about DAC instances, including resetting caches, retrieving version and configuration details, and general instance information.
9. `Report`: for managing reports, including retrieving, updating, and deleting report data, as well as working with report levels and inheriting parameters from pages.
10. `Pages`:  manages operations related to pages or page configurations, allowing users to create, edit, delete, and manage pages within the application.
11. `Action List Write Operations:` for modifying and creating action lists and actions within an application, including adding actions, creating new action lists, changing descriptions, and managing action positions.
12. `DAC Objects`:   handles operations concerning DAC objects or application objects, allowing users to create, retrieve, update, and delete objects or entities within the DAC application.
13. `Talend`:   provides operations related to Talend jobs or data integration processes, allowing users to trigger, monitor, and manage Talend job executions within the application.
14. `Olap Object`:  facilitates operations concerning OLAP objects or data cubes, enabling users to create, configure, and manage OLAP data structures for multidimensional analysis and reporting.
15. `Application`: manages operations related to applications, allowing users to create, configure, and manage applications within the DAC platform.
16. `Action List Statistics`:enables users to retrieve statistics or metrics related to Action List executions, providing insights into the performance and status of action list tasks or processes.
17. `Notification`: for managing notifications, including retrieving recipients for mail notifications and getting all defined notifications.
18. `Log`: provides operations related to logs or log data, allowing users to retrieve, filter, and analyze log entries generated by system activities, events, or processes.
19. `Resource`: manages operations related to resources, such as files, images, or assets used within the application, allowing users to upload, download, and manage resource files.
20. `Rule`: for executing rules within the application.
21. `Log`: for managing logging operations, including changing log levels and retrieving log files in various formats.
22. `Action List Logs:` for retrieving logs related to the execution of action lists, including filtering by executing object IDs.
23. `Social Content`:for managing social content, including retrieving tags and categories that can be associated with social objects.
24. `page-element-controller`: manages operations related to page elements or components, allowing users to create, configure, and manage various elements displayed on application pages. These elements may include forms, buttons, tables, charts, and other interactive or visual components.
25. `datasource-controller`: handles operations concerning data sources, enabling users to create, configure, and manage connections to external data sources or databases. Users can perform tasks such as defining data schemas, querying data, retrieving data, and managing data source configurations within the application.
{% endtab %}

{% tab title="API Version 2" %}
1. `CustomErrorMessages`: allows users to manage custom error messages, enabling operations such as creating, updating, and deleting custom error messages to provide specific feedback to users in case of errors.
2. `Languages`:  provides operations related to managing languages in the system, allowing users to add, modify, or remove language settings and translations for multi-language support.
3. `User`: facilitates user management operations, including user creation, modification, deletion, and retrieval of user-related information such as profiles, preferences, and permissions.
4. `Task`: handles task-related operations, allowing users to create, update, delete, and track tasks within the system, including assigning tasks to users, setting deadlines, and tracking task progress.
5. `Group`: manages user groups or teams within the system, allowing operations such as creating, updating, and deleting groups, as well as adding or removing users from groups and managing group permissions.
6. `BusinessLabel`:  deals with business labels or tags used to categorize data or entities within the system, enabling operations such as creating, updating, deleting, and assigning labels to different objects or records.
7. `Report`: provides functionality for managing reports, allowing users to create, modify, delete, and run reports to analyze data and generate insights for decision-making purposes.
8. `REST Api`:offers operations related to the REST API itself, providing endpoints for querying information about the API, managing API versions, and accessing API documentation and usage guidelines.
9. `workspace-attribute-controller`: manages workspace attributes, allowing operations such as creating, modifying, and deleting attributes.
10. `Organization-controller-v2`: manages tenants or environments within the system, allowing operations such as creating, modifying, and deleting tenants.
11. `synchronization-operation-controller`: manages synchronization operations between multiple components or systems, facilitating communication and data transfer.
12. `workspace-settings-controller`:manages workspace settings, allowing users to customize the appearance and behavior of their workspace.
13. `terms-of-use-controller`: manages terms of use or system policies, allowing administrators to define and update the terms that users must adhere to.
14. `smart-table-controller`:provides advanced functionality for managing tables or data grids, allowing operations such as sorting, filtering, and pagination of displayed data.
15. `security-controller`: manages security and access operations, allowing administrators to configure security policies and manage users, roles, and privileges within the system.
{% endtab %}
{% endtabs %}

## List of Pages API

{% tabs %}
{% tab title="First Tab" %}
1. `Action List Read Operations`:for retrieving information about action lists and their associated elements, including specific action lists and objects linked to actions.
2. `Document`:for managing documents within the social content system, including operations for following/unfollowing documents, listing visible documents, and deleting documents.
3. `Resource`:for managing resources in an application, including uploading, updating, retrieving, and deleting resources, as well as fetching metadata for resources.
4. `Tag`:for handling tags in discussions, including retrieving items that can be used as tags.
5. `Widget`:for managing widgets within an application, covering operations for retrieving, saving, activating widgets, and managing widget settings.
6. `Action List Scheduling Write Operations:`for modifying the scheduling and parameters of action lists, including setting parameters, adjusting scheduling times, and updating descriptions.
7. `DAC Instance:` for managing DAC instances, including resetting caches, retrieving version and configuration details, and general instance information.
8. `Report:`for working with reports, including retrieving, updating, deleting report data, and handling report levels and page-specific reports.
9. `Catalog Read Operations`:for reading catalog structures, providing details on the structure of specific catalogs within an application.
10. `Pages`:for managing pages within an application, including operations for creating events, modifying page details, and managing folder details.
11. `DAC Objects`:for handling DAC objects, including retrieving metadata, getting information about all application objects, and deleting specific objects.
12. `Talend`:for managing jobs and services within the Talend framework, covering job updates, executions, stopping/starting services, and handling job parameters and contexts.
13. `Olap Object:`for managing OLAP objects, including retrieving items contained within specific OLAP levels.
14. `Application`:for creating, deploying, modifying, and deleting applications, as well as retrieving information about all applications.
15. `Action List Statistics`: for retrieving statistics related to the execution of action lists and individual action units.
16. `Snippet`:for executing code snippets within an application and returning results, either via GET or POST requests.
17. `Notification`:for managing notifications, including retrieving selectable mail notification recipients and getting all defined notifications.
18. `Rule`:API for executing rules within the application.
19. `Log`: for managing log operations, including changing log levels and retrieving log files in plain text or zip format.
20. `Action List Scheduling Read Operations`:for retrieving information about the scheduling of action lists.
{% endtab %}
{% endtabs %}



## Open API definition of App Composer API

The link under the Swagger documentation title allows you to open the API definition for the App Composer. As shown in the figure, the API definition is in JSON format.&#x20;

If you import this JSON file into Postman, all DAC APIs will be automatically added to the Postman API catalog.

<figure><img src="../../../.gitbook/assets/image (196).png" alt=""><figcaption></figcaption></figure>

## Swagger: how to execute requests

To test DAC APIs, it's essential to be authorized through the [authorization token](authentication.md#generate-token), which is generated in the DAC user profile. The video below shows you how to proceed step by step.

{% embed url="https://app.arcade.software/share/DAoRA9yQVZzTtU5GxoD4" %}

## Postman

Postman is a third part of tool that you can use to execute the DAC APIs.

{% hint style="info" %}
Remember : to invoke a **DAC REST API**, a bearer token is required to authorize the request. The token to be use is generated from the [user profile](../../user-management/user-profile-and-change-password.md) page.

`Authorization: Bearer <DAC Token>`
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (223).png" alt=""><figcaption></figcaption></figure>

1. Insert the URL of DAC APIs
2. In the Headers insert  key and value :`Authorization: Bearer <DAC Token>`

The response of an API call is displayed in the response body section, located at the bottom of the Postman window. After sending a request, the response is shown below the request pane in the bottom part of the Postman user interface. You can expand this section to view all response details, including JSON data, errors, and other metadata returned by the API call.

<figure><img src="../../../.gitbook/assets/image (225).png" alt=""><figcaption></figcaption></figure>

### Import OpenAPI in Postman

This is how you can download and import in Postman the API definition

{% tabs %}
{% tab title="Stap 1" %}
<figure><img src="../../../.gitbook/assets/image (196).png" alt=""><figcaption></figcaption></figure>

In the first step, choose the Swagger version from the 'Select a Definition' dropdown menu. In this example  we select the Version 1. Select the link located above the documentation title . This will open a new window containing the list of DAC APIs in JSON format. Save the content in a **.JSON** format.
{% endtab %}

{% tab title="Step 2" %}
<figure><img src="../../../.gitbook/assets/image (205).png" alt=""><figcaption></figcaption></figure>

Open Postman and import the file saved in the previous step. For more information about the integration of Postman with an open API please see the reference documentation[ >>Integrate Postman with OpenAPI](https://learning.postman.com/docs/integrations/available-integrations/working-with-openAPI/)
{% endtab %}

{% tab title="Step 3" %}
<figure><img src="../../../.gitbook/assets/image (197).png" alt=""><figcaption></figcaption></figure>

We choose where to import DAC APIs
{% endtab %}

{% tab title="Step 4" %}
<figure><img src="../../../.gitbook/assets/image (203).png" alt=""><figcaption></figcaption></figure>

In the image we can see how swagger create a new group that contains all the API for the Version 1.&#x20;
{% endtab %}
{% endtabs %}
