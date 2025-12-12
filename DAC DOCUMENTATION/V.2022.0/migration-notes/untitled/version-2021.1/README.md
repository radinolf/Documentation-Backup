# Version 2021.1

* Decisyon App Composer changes its versioning convention, adopting calVer syntax.
* Decisyon App Composer 2021.1.1 introduces a new component: Dumbella, a microservice dedicated to the execution of jobs. Its configuration requires two new App Composer’s variables to be set: _appcomposer.dumbella.enabled_ and _appcomposer.dumbella.url._ The configuration of the container running Dumbella requires three properties to be set: _spring.datasource.url, spring.datasource.username_ and _spring.datasource.password_

### Content

* [Changes and migration of version 2021.1.1](changes-and-migration-of-version-2021.1.1.md)
* [Keycloak Installation Guide](../../../installation-guides/keycloak-installation-guide.md)
* [Configuring App Composer with Keycloak](../../../installation-guides/keycloak-installation-guide.md#configuring-app-composer-with-keycloak)
* [Configuring App Composer with Dumbella](../../../installation-guides/dumbella-installation-guide.md#configuring-app-composer-with-dumbella)
* [Dumbella Installation Guide](../../../installation-guides/dumbella-installation-guide.md#dumbella-installation-guide)
