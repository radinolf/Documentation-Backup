# Tenant

## What is a Tenant?​ <a href="#what-is-a-tenant" id="what-is-a-tenant"></a>

The segregation of users by Tenant, unlike that by groups, allows to create a more hierarchically structured group.

Users, Administrators and Users Administration can be defined in a tenant. Users created in the DAC are automatically associated with a default Tenant. Then they are associated with specific Tenants.

Any users could be associated to no Tenant or to one or more Tenants. If no Tenant is selected during user creation or modification then the user created or modified will be assigned to no Tenant.

![](<../../../.gitbook/assets/image (98).png>)



In the discussion widget it’s possible to mention users belonging to, at least, one of the tenant the writer belongs to. The user that are not listed in any tenant are visible only if the discussion author does not belong to any tenant too.

Watch the video for a brief overview of the tenants:

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/3.Ludwig/Tenant/TenantOverview.mp4" %}



**​**

Administrator and Business User grants :

* **Administrator Grants:**
  * An Administrator manages all existing Tenants and all existing users.
  * An Administrator manages all Users’ Attribute. A User Attribute is defined for any users, regardless of the Tenant he is associated to.
  * An Administrator is able to create new Users and Administrators and can associate them to any Tenants he wants or no Tenants.
  * An Administrator can move Users and Administrators to any Tenants he wants or can remove them from all Tenants they are associated to.
  * Administrator is able to manage any tenants and their users, including any users in associated with no tenants.
*   **Business User Grants:**

    * Any user have all Users’ Attribute defined in the Users’ Attribute section, regardless of the Tenant he is associated to
    * A User can belong to one or more Tenant.
    * A User can set a default tenant and change it during the session.

    ​

## Who to manages the tenants​ by Scope <a href="#who-manages-the-tenants" id="who-manages-the-tenants"></a>

![](<../../../.gitbook/assets/image (782).png>)

### Assign or revoke the "Tenant Administration" scope

If the Administrator assign revoke the “Tenant Administration” scope to a user the them can manage the tenants thae belongs to and their users.



