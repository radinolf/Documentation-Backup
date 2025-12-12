# Services Authorization Matrix

The following table lists all the microservices available within our application and specifies the type of user that can access each microservice. Users are classified into two main categories: **Business User** and **App Developer**.

* **Business User**: This type of user accesses the microservices to perform business activities, such as data analysis, reporting, resource management, etc.
* **App Developer**: This type of user accesses the microservices for application development and maintenance activities, such as API management, implementing new features, debugging, etc.

The table provides a clear overview of access permissions, helping users understand which microservices are available for their specific role within the organization.

| Microservice               | Business User | App Developer |
| -------------------------- | ------------- | ------------- |
| OIDC Service               | ✅Yes          | ✅Yes          |
| Pages                      | ✅Yes          | ⛔No           |
| App Composer               | ⛔No           | ✅Yes          |
| Cockpit                    | ⛔No           | ✅Yes          |
| Design Studio              | ⛔No           | ✅Yes          |
| Tenant Meta Data Installer | ⛔No           | ⛔No           |
| Tenant Batch Job           | ⛔No           | ⛔No           |
| Tenant Master Data         | ⛔No           | ️⛔No          |
| Dumbella                   | ⛔No           | ⛔No           |
| TimeTurner                 | ⛔No           | ⛔No           |

**Note**: A "Yes" indicates that the user has access to the microservice, while a "No" indicates that the user does not have access. If both are "no", it means that the service doesn't have a user interface and it is a back-end only service.
