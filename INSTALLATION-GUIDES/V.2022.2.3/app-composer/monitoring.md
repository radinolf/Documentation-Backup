# Monitoring

App Composer service exposes endpoints to allow monitoring of the service.

The **readiness** endpoint is available out of the box at this URL

`http://`_`<service_name>`_`/actuator/health/readiness`

The **liveness** endpoints is available at this url

`http://`_`<service_name>/`_`actuator/health/liveness`

The **metrics** are exposed at this endpoint.

`http://`_`<service_name>/`_`actuator/`_`metrics`_

`http://`_`<service_name>/`_`actuator/`_`prometheus`_&#x20;

{% hint style="info" %}
By default, metrics are not exposed. You need to modify the service property `profiles.active` in order to expose metrics. Please refer to [service properties documentation.](service-properties.md)
{% endhint %}

The applications **logs** are forwarded to the container log and it is possible to configure an external log collector to send the log to a third party service.
