# Migration Notes

### Configure Content Security Policy "connect-src" in Cockpit

Cockpit now includes Cross-Site Request Forgery (CSRF) protection by default. As a result, it is necessary to upgrade the Content Security Policy (CSP) directive `connect-src` to include the Identity Provider (IdP) host. This change ensures that logout operations via POST requests are allowed without triggering CSP violations.

If this configuration is not implemented, users may encounter CSP exceptions in their browser or face issues logging out of the Cockpit service.

Below is an example YAML file configuration for deployment. While the property `spring_security_oauth2_client_provider_idms_issuer_uri` is shown as a reference, the key focus is on adding the property `security_csp_connect_src:`

```yaml
cockpit:
  application:
    properties:
      spring_security_oauth2_client_provider_idms_issuer_uri: "<issuer URL>"
      security_csp_connect_src: "'self' <issuer URL>;"
```





