# Migration notes

## Dumbella and Timeturner Services Properties&#x20;

{% hint style="danger" %}
With the introduction of **Azure Key Vault,** Dumbella and TimeTurner's properties stored in both configmaps and secrets named "dumbella" and "timeturner" must be changed using "\_" in place of "." . For example the property "dac.url" must be renamed into "dac\_url".&#x20;

**This changes is valid only for Kubernetes**
{% endhint %}

{% hint style="info" %}
&#x20;Installations handled by Helm should not be affected by this change.
{% endhint %}

{% hint style="danger" %}
**Keycloack  - Services Properties:**&#x20;

When configuring the Keycloack service, remove the "\_" character from the following properties.

* **KEYCLOAKPASSWORD** ( Before _**KEYCLOAK\_PASSWORD**_)
* **KEYCLOAKUSER** ( Before   _**KEYCLOAK\_USER**_)
* **DBUSER**  (Before _**DB\_USER**_)
* **DBPWD**  (Before _**DB\_Password**_)

Properties are located in Keycloak’s Secret called "keycloak"

**This changes is valid only for Kubernetes**
{% endhint %}

## Rest Api Client URL Whitelist

Any endpoint configured in a REST API Client must be now whitelisted to prevent a `403 - Forbidden` error message. Endpoint that were propely working with DAC 2023.1.x, could now return this error unless they endpoint are whitelisted.

Whitelist is defined as a service property named "`appcomposer.security.whitelist`" containing all the URL allowed. Multiple URL can be separated by semicolon char.&#x20;

If a URL defined in the whitelist is not valid (i.e. no protocol and/or no host in the URL) it will be not considered.

When migrating to version 2023.2.0, it is necessary to define a white list with all URLs that can be invoked by the REST API Client.&#x20;

**Prerequisites to whitelist a URL**:

* Minimum information the URL must contain protocol and host
* URLs in the whitelist must be separated by semicolon

**Other important informations:**

* Only whitelisted URLs can be invoked using the Rest Client: any other invocation will be forbidden.
* Invocation of an URL not in Whitelist will return a `403 forbidden` error.

<figure><img src="../../../.gitbook/assets/image (1917).png" alt=""><figcaption></figcaption></figure>

* The App Composer Dumbella service is always automatically whitelisted
* App Composer URL is always automatically whitelisted
* `Localhost` is always automatically whitelisted

{% hint style="info" %}
Please refer to the [Installation Guide](/broken/pages/WpqhfwheciNIAXkEHwxJ) for additional information
{% endhint %}

### Example of configuration

Below is an example of whitelisting multiple URLs:

```
appcomposer.security.whitelist: http://MyService:8080/Users;http://MyService:8080;http://MyService;http://;MyService:8080
```

{% hint style="warning" %}
The URL must have both the protocol and the host. In the example above, the

&#x20;`http://` and my `service:8080` URLs would not be included in the whitelist.
{% endhint %}

If you have endpoints such as `https://MyService/Users` and `https://MyService/Pages` it's possible to configure in the whitelist only `https://MyService`: both endpoints will be automatically whitelisted:

```yaml
appcomposer.security.whitelist: http://myService
```

















