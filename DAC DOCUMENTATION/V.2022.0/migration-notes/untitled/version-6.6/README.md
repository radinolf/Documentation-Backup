# Version 6.6

* [D4C-58616](https://decisyon.atlassian.net/browse/D4C-5861) User Scopes introduced a breaking change on the REST API “_/api/rest/v2/users/{user}_“, both GET and POST methods: in the response there is a new array property “scopes” containing the scopes of the user. It replaces the single scopes properties (e.g. tenantManager) and legal values are **U\_ADMIN**, **T\_ADMIN** and **ALL\_T\_ADMIN** which stand for _User Administration_, _Tenant Administration_ and _All Tenants Administration_ scopes.
* [D4C-58616](https://decisyon.atlassian.net/browse/D4C-5861) User Scopes introduces new scopes _User Administration_, _Tenant Administration_ and _All Tenants Administration_ assignable to **non administrator** users. As migration from the old scopes to the new ones, any administrators having any scopes will be migrated to a non administrator user having the given scopes: as example, a current administrator user having the Manage Tenant scope, will be migrated as a user (no longer administrator) with the new _Tenant Administration_ scope. Default Administrators will no be impacted by this migration.



### Content

* [Changes and migration of version 6.6.2](/broken/pages/-Me9bRLRok8iK7B4rcz6)
* [Keycloak Installation Guide](/broken/pages/-Mda_PBDhkl3nLlh5Bct)
* [Configuring App Composer with Keycloak](/broken/pages/-Mda_Qa95GjK4quX6h3r)
