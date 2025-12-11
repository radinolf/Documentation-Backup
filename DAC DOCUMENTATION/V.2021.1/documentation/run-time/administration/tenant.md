# Tenant

## What is a Tenant?​ <a href="#what-is-a-tenant" id="what-is-a-tenant"></a>

The segregation of users by Tenant, unlike that by groups, allows to create a more hierarchically structured group.

Users, Administrators and Users Administration can be defined in a tenant. Users created in the DAC are automatically associated with a default Tenant. Then they are associated with specific Tenants.

Any users could be associated to no Tenant or to one or more Tenants. If no Tenant is selected during user creation or modification then the user created or modified will be assigned to no Tenant.

In the discussion widget it’s possible to mention users belonging to, at least, one of the tenant the writer belongs to. The user that are not listed in any tenant are visible only if the discussion author does not belong to any tenant too.

Watch the video for a brief overview of the tenants:

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/Tenant/TenantOverview.mp4" %}



Administrator and Business User grants :

* **Administrator Grants:**
  * An Administrator manages all existing Tenants and all existing users.
  * An Administrator manages all Users’ Attribute. A User Attribute is defined for any users, regardless of the Tenant he is associated to.
  * An Administrator is able to create new Users and Administrators and can associate them to any Tenants he wants or no Tenants.
  * An Administrator can move Users and Administrators to any Tenants he wants or can remove them from all Tenants they are associated to.
*   **Business User Grants:**

    * Any user have all Users’ Attribute defined in the Users’ Attribute section, regardless of the Tenant he is associated to
    * A User can belong to one or more Tenant.
    * A User can set a default tenant and change it during the session.

    ​

## Who manages the tenants​ <a href="#who-manages-the-tenants" id="who-manages-the-tenants"></a>

### Tenant Management by scoop <a href="#tenant-management-by-scoop" id="tenant-management-by-scoop"></a>

| **Scope**                 | **Create Tenant** | **Modify Tenant**                                    | **Delete Tenant**                                    | <p><strong>Create</strong></p><p><strong>User</strong></p> | **Assign Scope to New User**                                                                             | **Assign Tenant to new User**                           |
| ------------------------- | ----------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| All Tenant Administration | Yes               | <p>Yes</p><p>All Tenant</p>                          | <p>Yes</p><p>All Tenant</p>                          | Yes                                                        | <p>Yes</p><p>All Scope</p>                                                                               | <p>Yes</p><p>All Tenant</p>                             |
| Tenant Administration     | Yes               | <p>Yes</p><p>Only the tenants he is associate to</p> | <p>Yes</p><p>Only the tenants he is associate to</p> | Yes                                                        | <p>Yes</p><p>Only:</p><ul><li>None</li><li>Users Administration</li><li>Tenants Administration</li></ul> | <p>Yes</p><p>(Only the tenants he is associate to)</p>  |
| Users Administration      | No                | No                                                   | No                                                   | Yes                                                        | <p>Yes</p><p>Only:</p><ul><li>None</li><li>Users Administration</li></ul>                                | <p>Yes</p><p>(Only the tenants he is associated to)</p> |
| **None**                  | No                | No                                                   | No                                                   | No                                                         | No                                                                                                       | No                                                      |

### Tenants users’ management by scope <a href="#tenants-users-management-by-scope" id="tenants-users-management-by-scope"></a>

| **Scope** | <p><strong>Create</strong></p><p><strong>User</strong></p> | <p><strong>Modify</strong></p><p><strong>User</strong></p> | <p><strong>Delete</strong></p><p><strong>User</strong></p> |
| --------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |

| **Scope**                     | <p><strong>Create</strong></p><p><strong>User</strong></p>                         | <p><strong>Modify</strong></p><p><strong>User</strong></p> | <p><strong>Delete</strong></p><p><strong>User</strong></p> |
| ----------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| **All Tenant Administration** | Yes                                                                                | Yes                                                        | Yes                                                        |
| **Tenant Administration**     | Yes (but he can only associate him to the tenants he is associate to or no Tenant) | Yes (in the Tenants he is associate to or no Tenant)       | Yes (in the Tenants he is associate to or no Tenant)       |
| **Users Administration**      | Yes (but he can only associate him to the tenants he is associate to or no Tenant) | Yes (in the Tenants he is associate to or no Tenant)       | Yes (in the Tenants he is associate to or no Tenant)       |

## How to create a new Tenant <a href="#how-to-create-a-new-tenant" id="how-to-create-a-new-tenant"></a>

To create a new tenant, access the Users Administration section.

Tenants can only be created by users who have an “All tenants administration” or “Tenants administration” scope. All the users belonging to the Tenant are shown in the tenant management panel. After creating the tenant the users can be associated to it.

## How to delete a Tenant <a href="#how-to-delete-a-tenant" id="how-to-delete-a-tenant"></a>

Tenants can only be removed by users who have a scope of type:

* **“All tenants administration”:** is able to delete all Tenant regardless of whether they belong to them or not.
* **“Users Administration” and “Tenants administration”:** is able to delete Business User belonging to Tenants he manages, Business Users belonging to other Tenants (no Tenant excluded) won’t be delete.

When the tenant is deleted, the users associated with it are automatically assigned to “No Tenant” if not assigned to other tenants.

### ​ <a href="#undefined" id="undefined"></a>
