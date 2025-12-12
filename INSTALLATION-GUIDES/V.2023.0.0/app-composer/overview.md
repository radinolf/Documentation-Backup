# Overview

App Composer is the core service in the stack and it is responsible of

* providing the user interface for the user
* generating page at Runtime (accordingly to how they are designed in Design Studio)
* serving API requests
* metadata management
* service coordination
* instance activation
* application internal maintenance activity
* etc.

It is mandatory to have **at least one** App Composer service in the stack to make the instance works.

It is possible to deploy the stack on Docker and Kubernetes.

App Composer service is not responsible for user authentication and needs to use one of the following identity provider service

* Decisyon authentication service (Keycloak)
* Schneider IDMS
* Microsoft Azure Active directory.

Please refer to the properties to properly configure the services.
