# Architecture

## Introduction

App Composer is designed as a highly flexible and adaptable low-code platform that empowers developers to build, deploy, and manage applications across different environments with ease.&#x20;

Its architecture is based on a **microservices** framework that can be tailored to the specific needs of the deployment, whether for development, production, or multi-tenant environments. This flexibility ensures that both business users and application developers can leverage the platform effectively while maintaining clear boundaries between their respective roles.

At the core of App Composer's flexibility is its ability to adapt to different installation environments. For example, in **development environments**, some microservices that are essential for production may not be necessary. These services can be excluded to create a leaner setup that optimizes resources (and costs...) for development activities. On the other hand, in **production environments**, the full suite of microservices is deployed to ensure robust application performance and scalability, enabling the platform to handle larger loads and maintain stability under growing demand.&#x20;

This architecture is deployed on Kubernetes, which provides automatic scaling, load balancing, and resilience, ensuring that the infrastructure can easily grow alongside the applications built on it.

{% hint style="info" %}
You can find more information about the installation in the following page:
{% endhint %}

{% embed url="https://dac-documentation-1.gitbook.io/installation-guides" %}

One of the key strengths of App Composer is its **optional support for multi-tenancy**. The platform can serve multiple tenants from a single application instance, with each tenant’s data, configurations, and user management remaining isolated. This "**Shared App, Separate Database**" model ensures security and privacy, where each tenant—whether a customer, business unit, or another entity—has its own database.&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcxQoYnOp4yTtTSxeQgfYQKZhgqxBTM8h8elFqF9n7oXRraTmUb_8TT26HhHCGaPuxRg9DoF3ojWNplMiyqW1Acc84kA-LYHnFAbazGTwaTqjUF9nCfjFN-s22q66XsYhelmnuKirWIJuvcn76JTs4o6h7l5xvpDxee0mqOCWpy5FtIev1VTw=s2048?key=ILkLwzFIBhmyIxuOIOSQ3w" alt=""><figcaption></figcaption></figure>

Importantly, multi-tenancy has minimal impact on the app developer’s workflow. Even in complex environments like a multi-tenant architecture, developers experience a seamless development process, with no need for special configurations or significant adjustments when building the application. While there is additional infrastructure involved to manage multiple tenants, this is abstracted away from the developer, allowing them to focus solely on building features and functionality.

App Composer’s architecture supports both **no-tenant** and **multi-tenant** deployments, making it highly adaptable to different use cases. For businesses that require a single, dedicated instance for internal use, App Composer can be deployed in a no-tenant mode. For companies managing multiple tenants—such as SaaS providers—the platform can scale to support many users across different entities, each with their own isolated environments. This scalability ensures that App Composer can meet the needs of different business scenarios, from small-scale internal applications to large-scale enterprise solutions.

## No-Tenant Architecture

In the below image, you can observe the architectural layout of the App Composer in a no-tenant architecture and how the microservices interact to deliver functionality and scalable performance.&#x20;

Each service and component is designed to handle specific tasks, supporting the modular architecture of DAC. The microservices are organized to optimize communication and data flow within App Composer, ensuring integration and robust service delivery.&#x20;

<figure><img src="../../../.gitbook/assets/No-Tenant Architecture.png" alt=""><figcaption></figcaption></figure>

* **AppComposer:** a microservice equipped with APIs and a user interface, designed for app developer to build and modify applications. It handles all administrative aspects of DAC, except for user management that is in the scope of "Pages".
* **Pages:** a microservice equipped APIs and a user interface that is the entry point for business users to consume applications built by app developers in AppComposer and Design Studio. Pages offers key functionalities such as page visualization, user management, theme customization and others.
* **Cockpit:** a microservice with APIs and a user interface, designed for app developer to execute administrative tasks that must be carries our in a production environment, such as monitoring of job execution or importing application upgrades.
* **Tenant MD Installer:** a back-end only microservice that is responsible to install in the database all the tables required to persist the information needed by the other services.
* **Hub:** a back-end only microservice, a message broker that all services use internally to exchange events.
* **Time Turner:** a back-end only microservice that manages scheduled tasks, such as [Action List](../../app-functionality/action-list/#schedule-action-list).
* **Dumbella:** a back-end only microservice that execute [jobs](../../app-functionality/jobs.md).
* **OIDC:** a User Authentication Service, OpenID Connect compliant. It is not included in the App Composer deployment and it is a pre-requisite to use App Composer.
* **Metadata (MD):** a database schema that stores all settings and configurations. It is not included in the App Composer deployment and it is a pre-requisite to use App Composer.

## Production Vs Development <a href="#production-vs-development" id="production-vs-development"></a>

With App Composer's flexible architecture, you can tailor the deployment of microservices to fit the specific needs of development and production environments.&#x20;

In **development**, where rapid iteration and testing are very important, you can exclude production-focused services like Cockpit, which is designed mostly for monitoring and other infrequent tasks.&#x20;

In **production**, where stability and user access matter most, you can deploy and scale only services for the business user, such as "Pages, omitting the services used only to create the application, such as AppComposer.&#x20;

This modularity helps you to define a resource-smart deployment strategy for any stage of the application lifecycle.

In the image below, you have highlighted which microservices can be deployed or omitted in a **development environment**.

<figure><img src="../../../.gitbook/assets/Production Vs Development 1 (1).png" alt=""><figcaption></figcaption></figure>



In the image below, you have highlighted the microservices required in a **production environment**. In this case, the service and clients dedicated to the design the application (Appcomposer and Design Studio) can be omitted.

<figure><img src="../../../.gitbook/assets/Production Vs Development 2 (1).png" alt=""><figcaption></figcaption></figure>

## Multi-Tenant Architecture

DAC offers the capability to create a multi-tenant application. This allows multiple tenants to share the same application infrastructure while keeping their data, configurations, and user management isolated from one another.&#x20;

The multitenancy model we use is structured as follows: we have a single application with separate databases for each tenant.

Each tenant have its own unique set of users and settings ensuring that their resources are securely separated from those of other tenants. Additionally, DAC provides APIs and management tools to efficiently handle tenant-specific operations and tenant provisioning, making it easier for administrators to manage multiple tenants within a single instance of the application.&#x20;

<figure><img src="../../../.gitbook/assets/Multi-Tenant Architecture (2).png" alt=""><figcaption></figcaption></figure>

In this architecture, additional microservices are deployed to handle the complexities of multi-tenancy. These microservices provide essential functionality to create, manage, and maintain multiple tenants while ensuring seamless and secure operations:

* **Metadata (MD)**: A a database schema that stores all settings and configurations shared across tenants. Common elements are centralized here and managed for all tenants..&#x20;
* **Tenant Metadata:** A a database instance or schema dedicated to each tenant, containing settings and configurations unique to that tenant. This includes tenant-specific data like users, discussions, and files, ensuring complete isolation of tenant information.&#x20;
* **Tenant Master Data:** A microservice responsible for managing database connections for each tenant, ensuring the correct database is accessed for tenant-specific operations. For example, it handles data retrieval for users within a particular tenant..
* **Tenant Batch Jobs:** A microservice that performs scheduled internal back-end tasks, such as cleaning up temporary or outdated data.
* **Tenant MD Installer:** A microservice that provisions the tenant metadata in the database. It runs on demand when a new tenant is provisioned, ensuring the tenant’s database is set up correctly and efficiently.

## Technology stack <a href="#technology-stack" id="technology-stack"></a>

* Container based architecture
* Java 21+ / JEE platform
* Spring Framework 3.x
* Angular, HTML 5 and CSS 3
* REST API with JSON payload
* Cloud agnostics
* Deploy on-premise or in cloud

