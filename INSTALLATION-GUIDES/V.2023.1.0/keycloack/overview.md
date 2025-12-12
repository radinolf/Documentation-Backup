# Overview

![](<../.gitbook/assets/image (1).png>)

[Keycloak](https://www.keycloak.org/) is the authentication service provided by DAC and it is sponsored by RedHat.

Keycloak is required to authenticate users within App Composer when external authetication provider like Azure AD or Schneider IDMS are not used.

When Keycloak is used, the specific [service properties](service-properties.md) must be configured.&#x20;

Keycloack has its own administation UI available at the following link:

`https://`_`<service_name>/`_`auth/admin`

Please refer to Keycloak documentation for more details.

During the first startup of the service, a realm and a default user are automatically created using the names specified in the service's properties. This is applicable only for the first startup, if you need to modify them you need to manually change them in Keycloak.&#x20;

{% hint style="warning" %}
It is strongly suggested to modify the default password once the user has been created!
{% endhint %}
