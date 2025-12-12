# Monitoring

Keycloak service exposes endpoints to allow monitoring of the service.

The **readiness** endpoint is available out of the box at this URL

`http://`_`<service_name>`_`/health/ready`

The **liveness** endpoints is available at this url

`http://`_`<service_name>`_`/health/live`

Please refer to [Keycloak documentation](https://www.keycloak.org/server/health) for more information.
