# New Features

**D4C-8691 Expose ID Token as system parameter**

App Composer now expose as [system parameter](../../../documentation/app-functionality/system-parameters.md) the ID Token issued by the configured Identity Provider, so that app developers can use them in the business logic of the application (i.e. to forward the token to a third party service).



**D4C-8627 IDMS SSO logout management**

App Composer introduced a validation of the `access token` issued by IDMS: a request to the introspect endpoint (configured in the [App Composer service property](https://dac-documentation-1.gitbook.io/installation-guides/app-composer/service-properties) `oc.checkTokenEndpoint`) is executed to verify if the token is still valid.&#x20;

The endpoint return a JSON similar to this one

```json
{
  "active": true,
  "scope": "read write email",
  "client_id": "J8NFmU4tJVgDxKaJFmXTWvaHO",
  "username": "aaronpk",
  "exp": 1437275311
}
```

The field name `active` is used to verify the token validity:

* when `"active":true` the access token is still valid and the user remains logged.
* when `"active":false` the access token is not valid anymore and the user is logged off App Composer

The request on the introspect endpoint is executed at each pint/pong request of App Composer: by default, the ping/pong is executed every 20 seconds but it could be modified using the App Composer service property `appcomposer.ws.heart-beat.client`

This feature is applicable only when the Identity Provider is IDMS.



