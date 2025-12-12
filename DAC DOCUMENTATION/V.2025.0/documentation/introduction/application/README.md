---
description: Brief overview of the application
---

# Services

## Introduction

AppComposer is built on a modular architecture that allows for efficient application development, deployment, and management.&#x20;

The platform consists of several microservices, each designed to cater to specific roles/personas within the customer —administrators, app developers and business users.&#x20;

These services provide role-specific interfaces, ensuring a smooth and integrated workflow across the platform. The key microservices include:

* **Pages:** An user interface for business users to interact with applications built by app developers, offering easy navigation between pages, access to reports, data, insights, actions and whatever feature app developer included in the application.
* **App Composer:** A service for app developers and/or administrators to create, manage, modify and publish applications created in DAC Design Studio. App Composer allow for fine-tuning, additional configuration and previews before the applications are made available to end users.
* **Cockpit:** A user interface for administrator that centralizes the monitoring and management of applications when in production, ensuring operations and monitoring in live environments. It is not required to have Cockpit to be always up\&runing in production.

Each service operates via its own dedicated API and user interface, accessible from a browser using a URL. In a typical deployment, the microservices are configured to respond at the following URLs:

| Service      | Typical URL                        |
| ------------ | ---------------------------------- |
| Pages        | `https://<my-app-url>`             |
| App Composer | `https://<my-app-url>/appcomposer` |
| Cockpit      | `https://<my-app-url>/cockpit`     |

This flexibility in deployment allows DevOps teams to modify these URLs as needed, adapting the system to various network configurations and customer requirements.&#x20;

## AppComposer

AppComposer is the core web interface for **app developers**, providing them with the tools to publish and manage applications built in DAC Design Studio. It includes features that allow developers to preview the application pages as they will appear to business users, helping to ensure that the final product meets business requirements.

Appcomposer is accessible only by [**whitelisted** ](#user-content-fn-1)[^1]administrators and developers responsible for managing application life cycles. It provides the web environment for managing the various aspects of an application before it reaches the production stage.

<figure><img src="../../../.gitbook/assets/image (2107).png" alt=""><figcaption></figcaption></figure>

Key features of AppComposer include:

* **Preview Functionality:** The ability to preview application pages before they are made available to business users helps in identifying any issues or required adjustments.
* **App Deployment:** Developers can seamlessly publish applications to the platform, ensuring that all necessary configurations are in place.
* **Management Tools:** A set of tools available to extend and enrich organize applications, such as jobs, REST Client etc.

For more details, please refer to the dedicated documentation:

{% content-ref url="appcomposer/" %}
[appcomposer](appcomposer/)
{% endcontent-ref %}

## **Pages**

Pages is the service dedicated to **business users**, offering an intuitive and user-friendly interface for interacting with applications built by application developers. Business users can easily navigate between the different sections of an application, view reports, interact with data an execute actions, depending on how the application was built.&#x20;

This service is essential for the day-to-day operations of business users.

<figure><img src="../../../.gitbook/assets/image (2108).png" alt=""><figcaption></figcaption></figure>

User privileges in page are managed using scopes[^2], determining what actions they can perform. The first user accessing pages is granted with the highest scope - _All Organization Admin_ -, enabling him to manage the other user and permissions.&#x20;

{% hint style="info" %}
By default, users in pages are created as disabled when they login the first time. It is possible to change this configuration using the property **Tool -> Preference -> Web -> automatic-user-creation** in Design Studio .

For more details:[https://documentation.decisyon.com/documentation/instance-configuration/tools/preferences](https://documentation.decisyon.com/documentation/instance-configuration/tools/preferences)
{% endhint %}

Key features of Pages include:

* **Navigation and Interaction:** Pages allows business users to use application pages and interact with the data, insights and action built for him using DAC platform.
* **User Profile Customization:** Users can manage their own profiles and settings, allowing for a more personalized experience.
* **User and Scope Management:** Authorized users have the ability to manage access and permissions for other users, allowing business users to act as profile managers.
* **Branding Customization:** Authorized users can customize branding elements within Pages to reflect their company identity and enhance the user experience.

For more details, please refer to the dedicated documentation:

{% content-ref url="pages.md" %}
[pages.md](pages.md)
{% endcontent-ref %}

## Cockpit

Cockpit is a microservice that provides **administrators** with the tools to monitor and manage applications in a production environment. It centralizes many tasks that could not be executed in pages into a single interface.&#x20;

Cockpit is particularly important in multitenant environments where managing tenants can be complex.

This service is accessible only to authorized administrators and developers authorized for maintaining a production environment.

&#x20;

<figure><img src="../../../.gitbook/assets/image (2286).png" alt=""><figcaption></figcaption></figure>

Key features of Cockpit include:

* **Job Management**: Allows publishing and unpublishing jobs in a production environment.
* **Action List**: Monitors execution and provides access to logs for action lists and scheduled action lists.
* **Application Manager**: Offers tools to manage applications, such as synchronizing or deleting applications.

For more details, please refer to the dedicated documentation:

{% content-ref url="cockpit/" %}
[cockpit](cockpit/)
{% endcontent-ref %}

## Key Architectural Changes for developers and administrators

If you’re new to the Decisyon App Composer (DAC) platform, feel free to skip this page. For experienced users familiar with earlier DAC versions, this overview will clarify the architectural changes introduced in DAC 2024.1.0 and the benefits of these updates.

Previously, DAC relied on a single web application—**AppComposer**—to serve both business users and app developers, segregating features and functionalities based on user roles. **Design Studio** served as the primary environment for creating, modifying, and maintaining applications.&#x20;

With DAC 2024.1.0, the platform introduces separate web applications to better target the unique needs of business users and developers while progressively shifting certain design functions.

**Pages** is the new web application dedicated solely to business users, offering a optimized interface with only the features needed for exploring and interacting with business applications. Pages removes all development tools, allowing for a lighter, more efficient experience that focuses entirely on the needs of business users. Future releases will continue enhancing Pages based on user feedback and functional needs.

**AppComposer** is the same webapplication of previous versions, but now is used exclusively by app developers. As a result, AppComposer no longer needs to be deployed in production environments, as it is used only during development phase. Over time, some features from Design Studio will be integrated into AppComposer, eventually unifying app development and design capabilities under a single interface to simplify and enhance the developer experience.

To accommodate the administrative and operational tasks previously available in AppComposer only, DAC 2024.1.0 introduces **Cockpit**. Cockpit is designed for production environments and centralizes maintenance and monitoring tasks like application synchronization, jobs maintenance, and scheduled action list monitoring. With Cockpit, administrators have a dedicated space for these activities in a production environment, without requiring to have AppComposer deployed only for few tasks. &#x20;

## Feature by service

In this table you can better understand which feature is housed in which service or component of Decisyon App Composer.

<table data-full-width="true"><thead><tr><th>Feature</th><th>Pages</th><th>AppComposer</th><th>Cockpit</th><th>Design Studio</th></tr></thead><tbody><tr><td>Navigate pages and applications</td><td>✅Yes</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>User Administration</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Organization Administration</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td><td>⛔No</td></tr><tr><td>User Profile Settings</td><td>✅Yes</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Logo &#x26; Colors</td><td>✅Yes</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Setup Terms of user / Privacy Policy</td><td>⛔No</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Create Report and pages</td><td>⛔No</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Creation of user groups and user attributes</td><td>⛔No</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Language Administration  </td><td>⛔No</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Labels Management  / Custom Error</td><td>⛔No</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Rest API Client / Action List</td><td>⛔No</td><td>✅Yes</td><td>⛔No</td><td>⛔No</td></tr><tr><td>Jobs</td><td>⛔No</td><td>✅Yes</td><td>✅Yes “Only Monitoring”</td><td>⛔No</td></tr><tr><td>Action List</td><td>⛔No</td><td>✅Yes</td><td>✅Yes “Only Monitoring”</td><td>⛔No</td></tr><tr><td>Application Administration (Application Synchronization)</td><td>⛔No</td><td>✅Partially</td><td>✅Partially</td><td>✅Partially</td></tr><tr><td>Create cubes, dimension, metrics, filters</td><td>⛔No</td><td>⛔No</td><td>⛔No</td><td>✅Yes</td></tr><tr><td>Create report and pages</td><td>⛔No</td><td>⛔No</td><td>⛔No</td><td>✅Yes</td></tr><tr><td>Rules, Snippets, Notification, Resources</td><td>⛔No</td><td>⛔No</td><td>⛔No</td><td>✅Yes</td></tr><tr><td>Datasource and Services</td><td>⛔No</td><td>⛔No</td><td>⛔No</td><td>✅Yes</td></tr></tbody></table>

[^1]: 

[^2]: Define the specific permissions and access levels assigned to a business user within the instance. In DAC, scopes are application any application in the instance.
