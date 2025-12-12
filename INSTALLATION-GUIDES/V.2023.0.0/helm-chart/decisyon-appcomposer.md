# Decisyon AppComposer

Here's how-to deploy Decisyon AppComposer architecture on Kubernetes (_a.k.a_ **K8S**) using [Helm Chart](https://helm.sh/). For any further details about Helm you can see the [official documentation](https://helm.sh/docs/).

## TL;DR

> $ helm repo add decisyon https://decisyon.jfrog.io/artifactory/dac-helm-dev/\
> $ helm repo update

## Installation

> $ kubectl create namespace appcomposer\
> $ helm install decisyon/appcomposer appcomposer --namespace appcomposer -f values.yaml

## Uninstalling the Chart

To uninstall/delete the AppComposer Helm chart:

> helm uninstall appcomposer

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

Following are the properties to configure the resource on Kubernetes related to the DAC microservices. Use them as reference for editing the _values.yaml_ file for your installation (see next sections for an example of values.yaml file)

> NB: when referring to the configuration of resource of Kubernetes (e.g. _K8S's containers\[].securityContext_), please see the [Kubernetes official documentation](https://kubernetes.io/) to get the available options.

### Global Settings

| Property                              | Type    | Description                                                            | Mandatory                                | Default                      |
| ------------------------------------- | ------- | ---------------------------------------------------------------------- | ---------------------------------------- | ---------------------------- |
| global.registry.name                  | String  | Image Registry                                                         | yes                                      | decisyon-dac-docker.jfrog.io |
| global.registry.secretNamed           | String  | Name of the Secret to store registry's data                            | yes                                      | appcomposer-registry-secret  |
| global.registry.credentials.username  | String  | Username to connect to the image registry                              | yes                                      |                              |
| global.registry.credentials.password  | String  | Password to connect to the image registry                              | yes                                      |                              |
| global.registry.credentials.email     | String  | Email to connect to the image registry                                 | yes                                      |                              |
| global.security.apiGateway.enabled    | Bool    | Set to true to enable ApiGateway                                       | yes                                      | false                        |
| global.security.apiGateway.cookieName | String  | The name of the cookie storing the user data                           | only if _apiGateway.enabled_ is **true** |                              |
| global.security.apiGateway.uidClaim   | String  | Claim containing the user identifier                                   | only if _apiGateway.enabled_ is **true** |                              |
| global.security.apiGateway.logOutUrl  | String  | Endpoint to call on logout                                             | only if _apiGateway.enabled_ is **true** |                              |
| global.security.token.seed            | String  | Random 20-length string to generate a token for services communication | yes                                      |                              |
| global.rabbit.host                    | String  | Rabbit's host                                                          | yes                                      | rabbit                       |
| global.rabbit.username                | String  | Rabbit's username                                                      | yes                                      |                              |
| global.rabbit.password                | String  | Rabbit's password                                                      | yes                                      |                              |
| global.rabbit.port                    | Integer | Rabbit's service port                                                  | yes                                      | 5672                         |
| global.keycloak.enabled               | Bool    | Set to true for enabling Keycloak                                      | yes                                      | false                        |
| global.appcomposer.url                | String  | AppComposer's URL                                                      | yes                                      | http://appcomposer           |
| global.dumbella.enabled               | Bool    | Set to true for enabling Dumbella                                      | yes                                      | true                         |
| global.dumbella.url                   | String  | Dumbella's URL                                                         | only if _dumbella.enabled_ is **true**   | http://dumbella              |



### Decisyon AppComposer

| Property                                       | Type    | Description                                                  | Mandatory                                  | Default                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ---------------------------------------------- | ------- | ------------------------------------------------------------ | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| application.fullnameOverride                   | String  | The name of the AppComposer resources                        | yes                                        | appcomposer                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| application.context.root                       | String  | The context root                                             | no                                         | /                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| application.context.ui                         | String  | The context where the UI                                     | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.context.api                        | String  | The context where the Rest API                               | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.image.tag                          | String  | Tag of the AppComposer image                                 | yes                                        | 2023.0.0                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| application.image.name                         | String  | Name of the AppComposer image                                | yes                                        | com.decisyon.appcomposer-k8s                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| application.image.pullPolicy                   | String  | K8S's image pull policy                                      | yes                                        | Always                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| application.replicas                           | Integer | Number of replicas                                           | yes                                        | 1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| application.profileActive                      | String  | Spring profile to run AppComposer with                       | yes                                        | prod,kubernetes,monitoring,streams                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| application.jvmOptions                         | String  | JVM Options                                                  | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.resources                          | Object  | K8S's containers\[].resources                                | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.securityContext                    | Object  | K8S's spec.securityContext                                   | no                                         | <p>allowPrivilegeEscalation:false<br>privileged: false<br>readOnlyRootFilesystem: false<br>runAsNonRoot: true<br>runAsUser: 1000</p>                                                                                                                                                                                                                                                                                                                                                                                           |
| application.podSecurityContext                 | Object  | K8S's containers\[].securityContext                          | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.podAnnotations                     | Object  | K8S's template.metadata.annotations                          | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.service.type                       | String  | Service type                                                 | yes                                        | ClusterIP                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| application.service.port                       | Integer | Service port                                                 | yes                                        | 8080                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| application.security.starter.azureEnabled      | Bool    | Set true to enable Azure AD                                  | yes                                        | false                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| application.security.starter.schneiderEnabled  | Bool    | Set true to enable IDMS authentication                       | yes                                        | false                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| application.security.csp                       | Object  | CSP directives                                               | no                                         | <p>script-src: "'unsafe-inline' 'unsafe-eval' 'self' ;"<br>img-src: "data: https://*.openstreetmap.org 'unsafe-inline' 'unsafe-eval' 'self' ;"<br>font-src: "data: https://fonts.gstatic.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"<br>style-src: "https://fonts.googleapis.com/ https://maxcdn.bootstrapcdn.com https://getbootstrap.com/ 'self' 'unsafe-inline' ;"<br>default-src: "https://widgethub.decisyon.com/ 'self';"<br>frame-ancestors: "'self' ;"<br>worker-src: "blob: 'self' ;"<br>form-action: "'self' ;"</p> |
| application.security.cors                      | Object  | Set CORS directives                                          | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.properties.port           | Integer | Metadata database port                                       | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.properties.host           | String  | Metadata database host                                       | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.properties.database       | String  | Metadata database                                            | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.properties.schema         | String  | Metadata schema                                              | only on PostgresQL                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.properties.url            | String  | Metadata database JDBC url                                   | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.credentials.user          | String  | Metadata database user                                       | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.metadata.credentials.password      | String  | Metadata database password                                   | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.azureADTenantId                 | String  | Azure AD Tenant Id                                           | only if _starter.azureEnabled_ is **true** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.properties.userIdentifierClaim  | String  | Claim containing the users' identifier                       | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.properties.realm                | String  | Realm                                                        | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.logoutEndpoint        | String  | The endpoint to call on logout                               | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.authorizationEndpoint | String  | OpenID Connect authorization endpoint                        | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.checkTokenEndpoint    | String  | OpenID Connect check token endpoint                          | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.loginRedirectUri      | String  | OpenID Connect login redirect uri                            | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.tokenEndpoint         | String  | OpenID Connect token endpoint                                | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.userInfoEndpoint      | String  | OpenID Connect userInfo endpoint                             | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.endpoints.jwkEndpoint           | String  | OpenID Connect jwk endpoint                                  | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.client.id                       | String  | The Client Id the AppComposer uses to call the OIDC Api.     | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.oc.client.secret                   | String  | The Client Secret the AppComposer uses to call the OIDC Api. | yes                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.ingress.enabled                    | Bool    | Set to true to configure the ingress for the AppComposer     | yes                                        | false                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| application.ingress.annotations                | Object  | Ingress annotations                                          | only if _ingress.enabled_ is **true**      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.ingress.className                  | String  | Ingress className                                            | only if _ingress.enabled_ is **true**      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.properties                         | Object  | AppComposer's additional properties                          | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.nodeSelector                       | Object  | K8S's spec.nodeSelector                                      | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.tolerations                        | Object  | K8S's spec.tolerations                                       | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.affinity                           | Object  | K8S's spec.affinity                                          | no                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| application.uaaUrl                             | String  | Url of the UAA Service                                       | only if _keycloak.enabled_ is **true**     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

#### Decisyon AppComposer additional properties

Those properties can be added as child of _application.properties_.

#### METADATA DATASOURCE

| Property                        | Description                                                                                                                                                                                                                                                                                      | Type    | Default      | Mandatory |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------- | ------------ | --------- |
| metadata.minIdle                | Min number of idle connections                                                                                                                                                                                                                                                                   | Integer | 5            | NO        |
| metadata.maxPoolSize            | Maximum pool size                                                                                                                                                                                                                                                                                | Integer | 100          | NO        |
| metadata.idleTimeout            | Maximum idle time for connection                                                                                                                                                                                                                                                                 | Integer | 30000        | NO        |
| metadata.connectionTimeout      | Maximum number of milliseconds that a client will wait for a connection                                                                                                                                                                                                                          | Integer | 600000       | NO        |
| metadata.maxLifeTime            | Maximum lifetime in milliseconds of a connection in the pool after it is closed                                                                                                                                                                                                                  | Integer | 600000       | NO        |
| metadata.leakDetectionThreshold | Sets maximum time after which a jdbc connection may be considered unclosed and symptom of a potential leak, in milliseconds. It prints out, on the Decisyon.log file, the stack trace of the thread invoking the connection. default value is 0 (disabled). The value MUSt be greater than 2000. | Integer | 0 (disabled) | NO        |

#### **SECURITY**

<table><thead><tr><th width="175">Property</th><th width="100">Type</th><th>Description</th><th width="141">Mandatory</th><th width="100">Default</th></tr></thead><tbody><tr><td>appcomposer.security.debug</td><td>true | false</td><td>Enables UI Toast to show any security alert due to param validation.</td><td>NO</td><td>False</td></tr><tr><td>appcomposer.security.validation.string.big</td><td>Integer</td><td>Sets the max length for param values validation.</td><td>NO</td><td>10000</td></tr></tbody></table>

#### **WORKFLOW**

<table><thead><tr><th width="230">Property</th><th width="100">Type</th><th>Description</th><th width="100">Mandatory</th><th width="100">Default</th></tr></thead><tbody><tr><td>appcomposer.workflow.enabled</td><td>true | false</td><td>This is mandatory if you use the workflow</td><td>NO</td><td>False</td></tr><tr><td>flowable.task.url</td><td>URL</td><td>Gertrude url</td><td>YES, only if workflow is enabled</td><td></td></tr><tr><td>flowable.task.url</td><td>URL</td><td>Flowable Modeler url</td><td>YES, only if workflow is enabled</td><td></td></tr></tbody></table>

#### **NETWORKING SETTINGS**

<table><thead><tr><th>Property</th><th width="100">Type</th><th>Description</th><th width="100">Mandatory</th><th width="100">Default</th></tr></thead><tbody><tr><td>appcomposer.ws.heart-beat.timeout</td><td>Integer</td><td></td><td>NO</td><td>50000</td></tr></tbody></table>

#### **THREAD SETTINGS**

<table><thead><tr><th>Property</th><th width="100">Type</th><th>Description</th><th width="100">Mandatory</th><th width="100">Default</th></tr></thead><tbody><tr><td>appcomposer.task.execution.pool.core-size</td><td>Integer</td><td></td><td>NO</td><td>50</td></tr><tr><td>appcomposer.task.execution.pool.max-size</td><td>Integer</td><td></td><td>NO</td><td>50</td></tr><tr><td>appcomposer.task.session-content.delay</td><td>Integer</td><td>Delay, in millisec, of the session content thread</td><td></td><td></td></tr></tbody></table>

#### **WEB SOCKET SETTINGS**

<table><thead><tr><th>Property</th><th width="100">Type</th><th>Description</th><th width="100">Mandatory</th><th width="100">Default Valu</th></tr></thead><tbody><tr><td>appcomposer.ws.reconnect.attempts</td><td>Integer</td><td>Numbers of attempts to reconnect on a closing connection.</td><td>NO</td><td>2</td></tr><tr><td>appcomposer.ws.reconnect.stomp-attempts</td><td>Integer</td><td>Numbers of attempts to reconnect using a brand new connection.</td><td>NO</td><td>1</td></tr><tr><td>appcomposer.ws.reconnect.delay</td><td>Integer</td><td>Delay, in millisec, between attempts of reconnecting.</td><td>NO</td><td>2000</td></tr><tr><td>appcomposer.ws.heart-beat.client</td><td>Integer</td><td>STOMP heart-beat, in millisec</td><td>NO </td><td>20000</td></tr><tr><td>appcomposer.ws.heart-beat.server</td><td>Integer</td><td>STOMP heart-beat, in millisec</td><td>NO</td><td>20000</td></tr><tr><td>appcomposer.ws.heart-beat.master.client</td><td>Integer</td><td>STOMP heart-beat, in millisec of the main ws connection.</td><td>NO </td><td>20000</td></tr><tr><td>appcomposer.ws.heart-beat.master.server</td><td>Integer</td><td>STOMP heart-beat, in millisec of the main ws connection.</td><td>NO</td><td>2000</td></tr><tr><td>appcomposer.ws.ping-pong.timeout</td><td>Integer</td><td>Applicative ping/pong timing, in millisec.</td><td>NO</td><td>25000</td></tr><tr><td>appcomposer.ws.session-max-idle.timeout</td><td>Integer</td><td>Web Socket connection idle timeout, in millisec.  Should be equal to the http session timeout</td><td>NO</td><td>1800000 (30 minutes)</td></tr></tbody></table>

**CLUSTER**

<table><thead><tr><th>Property</th><th width="100">Type</th><th>Description</th><th width="100">Mandatory</th><th width="100">Default Value</th></tr></thead><tbody><tr><td>appcomposer.cluster.leader-election.task-delay</td><td>Integer</td><td>Leader Check interval rate, timing of the election of a new leader of the DAC cluster, in milliseconds</td><td>NO</td><td>30000</td></tr></tbody></table>

### Rabbit

| Property                              | Type   | Description                         | Mandatory | Default                                                                                                                              |
| ------------------------------------- | ------ | ----------------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| rabbit.application.fullnameOverride   | String | The name of the Rabbit resources    | yes       | rabbit                                                                                                                               |
| rabbit.application.image.name         | String | Name of the Rabbit image            | yes       | com.decisyon.rabbitmq                                                                                                                |
| rabbit.application.image.tag          | String | Tag of the Rabbit image             | yes       | 2023.0.0                                                                                                                             |
| rabbit.application.image.pullPolicy   | String | K8S's image pull policy             | yes       | Always                                                                                                                               |
| rabbit.application.podAnnotations     | Object | K8S's template.metadata.annotations | no        |                                                                                                                                      |
| rabbit.application.podSecurityContext | Object | K8S's containers\[].securityContext | no        |                                                                                                                                      |
| rabbit.application.securityContext    | Object | K8S's spec.securityContext          | no        | <p>allowPrivilegeEscalation:false<br>privileged: false<br>readOnlyRootFilesystem: false<br>runAsNonRoot: true<br>runAsUser: 1000</p> |
| rabbit.application.service.type       | String | Service type                        | yes       | ClusterIP                                                                                                                            |
| rabbit.application.nodeSelector       | Object | K8S's spec.nodeSelector             | no        |                                                                                                                                      |
| rabbit.application.tolerations        | Object | K8S's spec.tolerations              | no        |                                                                                                                                      |
| rabbit.application.affinity           | Object | K8S's spec.affinity                 | no        |                                                                                                                                      |

### TimeTurner

| Property                                   | Type   | Description                                 | Mandatory | Default                                                                                                                              |
| ------------------------------------------ | ------ | ------------------------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| timeturner.application.fullnameOverride    | String | The name of the TimeTurner resources        | yes       | timeturner                                                                                                                           |
| timeturner.application.image.name          | String | Name of the TimeTurner image                | yes       | com.decisyon.timeturner                                                                                                              |
| timeturner.application.image.tag           | String | Tag of the TimeTurner image                 | yes       | 2023.0.0                                                                                                                             |
| timeturner.application.image.pullPolicy    | String | K8S's image pull policy                     | yes       | Always                                                                                                                               |
| timeturner.application.podAnnotations      | Object | K8S's template.metadata.annotations         | no        |                                                                                                                                      |
| timeturner.application.podSecurityContext  | Object | K8S's containers\[].securityContext         | no        |                                                                                                                                      |
| timeturner.application.securityContext     | Object | K8S's spec.securityContext                  | no        | <p>allowPrivilegeEscalation:false<br>privileged: false<br>readOnlyRootFilesystem: false<br>runAsNonRoot: true<br>runAsUser: 1000</p> |
| timeturner.application.service.type        | String | Service type                                | yes       |                                                                                                                                      |
| timeturner.application.nodeSelector        | Object | K8S's spec.nodeSelector                     | no        |                                                                                                                                      |
| timeturner.application.tolerations         | Object | K8S's spec.tolerations                      | no        |                                                                                                                                      |
| timeturner.application.affinity            | Object | K8S's spec.affinity                         | no        |                                                                                                                                      |
| timeturner.application.properties          | Object | TimeTurner's additional properties          | no        |                                                                                                                                      |
| timeturner.application.datasource.url      | String | Database JDBC Url                           | yes       |                                                                                                                                      |
| timeturner.application.datasource.username | String | Username to connect to the database         | yes       |                                                                                                                                      |
| timeturner.application.datasource.password | String | Users's password to connect to the database | yes       |                                                                                                                                      |



### Dumbella

Those properties are required only if _global.dumbella.enabled_ is _true_.

| Property                                     | Type    | Description                                             | Mandatory                        | Default                                                                                                                              |
| -------------------------------------------- | ------- | ------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| dumbella.application.fullnameOverride        | String  | The name of the Dumbella resources                      | yes                              | dumbella                                                                                                                             |
| dumbella.application.datasource.url          | String  | Database JDBC url                                       | yes                              |                                                                                                                                      |
| dumbella.application.datasource.password     | String  | Database password                                       | yes                              |                                                                                                                                      |
| dumbella.application.datasource.username     | String  | Database username                                       | yes                              |                                                                                                                                      |
| dumbella.application.image.name              | String  | Name of the Dumbella image                              | yes                              | com.decisyon.dumbella                                                                                                                |
| dumbella.application.image.tag               | String  | Tag of the Dumbella image                               | yes                              | 2023.0.0                                                                                                                             |
| dumbella.application.image.pullPolicy        | String  | K8S's image pull policy                                 | yes                              | Always                                                                                                                               |
| dumbella.application.replicas                | Integer | Number of replicas                                      | yes                              | 1                                                                                                                                    |
| dumbella.application.service.type            | String  | Service type                                            | yes                              | ClusterIP                                                                                                                            |
| dumbella.application.service.port            | Integer | Service port                                            | yes                              | 8080                                                                                                                                 |
| dumbella.application.resources               | Object  | K8S's containers\[].resources                           | no                               |                                                                                                                                      |
| dumbella.application.volume.enabled          | String  | Enable the configuration of Persistent Volume and Claim | yes                              | false                                                                                                                                |
| dumbella.application.volume.storageClassName | String  | storageClassName of the Volume                          | only if _volume.enabled_ is true |                                                                                                                                      |
| dumbella.application.volume.capacity         | String  | capacity of the Volume                                  | only if _volume.enabled_ is true |                                                                                                                                      |
| dumbella.application.volume.accessModes      | String  | accessModes of the Volume                               | only if _volume.enabled_ is true |                                                                                                                                      |
| dumbella.application.securityContext         | Object  | K8S's spec.securityContext                              | no                               | <p>allowPrivilegeEscalation:false<br>privileged: false<br>readOnlyRootFilesystem: false<br>runAsNonRoot: true<br>runAsUser: 1000</p> |
| dumbella.application.podSecurityContext      | Object  | K8S's containers\[].securityContext                     | no                               |                                                                                                                                      |
| dumbella.application.podAnnotations          | Object  | K8S's template.metadata.annotations                     | no                               |                                                                                                                                      |
| dumbella.application.volumes                 | Object  | K8S's spec.volumes                                      | only if _volume.enabled_ is true |                                                                                                                                      |
| dumbella.application.volumeMounts            | String  | K8S's containers\[].volumeMounts                        | only if _volume.enabled_ is true |                                                                                                                                      |
| dumbella.application.nodeSelector            | String  | K8S's spec.nodeSelector                                 | no                               |                                                                                                                                      |
| dumbella.application.tolerations             | String  | K8S's spec.tolerations                                  | no                               |                                                                                                                                      |
| dumbella.application.affinity                | String  | K8S's spec.affinity                                     | no                               |                                                                                                                                      |
| dumbella.application.properties              | Object  | Dumbella's additional properties                        | no                               |                                                                                                                                      |

#### Dumbella additional properties

Those properties can be added as child of _dumbella.application.properties_

<table><thead><tr><th width="224">Property</th><th width="87">Type</th><th width="238">Description</th><th width="119">Mandatory</th><th width="100">Default</th></tr></thead><tbody><tr><td>dumbella.job.result.availability</td><td>Integer</td><td>In Dumbella must be possible to configure how time a job execution result have to be available. </td><td>No</td><td>24</td></tr></tbody></table>

### Keycloak

Those properties are required only if _global.keycloak.enabled_ is **true**.

| Parameter                                        | Type    | Description                                                                                                   | Mandatory                             | Default                                                                                                                              |
| ------------------------------------------------ | ------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| keyclock.application.fullnameOverride            | String  | The name of the Keycloak resources                                                                            | yes                                   | keycloak                                                                                                                             |
| keyclock.application.image.name                  | String  | Name of the Keycloak image                                                                                    | yes                                   | com.decisyon.keycloak                                                                                                                |
| keyclock.application.image.tag                   | String  | Tag of the Keycloak image                                                                                     | yes                                   | 2023.0.0                                                                                                                             |
| keyclock.application.image.pullPolicy            | String  | K8S's image pull policy                                                                                       | yes                                   | Always                                                                                                                               |
| keyclock.application.podAnnotations              | Object  | K8S's template.metadata.annotations                                                                           | no                                    |                                                                                                                                      |
| keyclock.application.podSecurityContext          | Object  | K8S's containers\[].securityContext                                                                           | no                                    |                                                                                                                                      |
| keyclock.application.securityContext             | Object  | K8S's spec.securityContext                                                                                    | no                                    | <p>allowPrivilegeEscalation:false<br>privileged: false<br>readOnlyRootFilesystem: false<br>runAsNonRoot: true<br>runAsUser: 1000</p> |
| keyclock.application.service.type                | String  | Service type                                                                                                  | yes                                   | ClusterIP                                                                                                                            |
| keyclock.application.service.port                | Integer | Service port                                                                                                  | yes                                   | 8081                                                                                                                                 |
| keyclock.application.nodeSelector                | Object  | K8S's spec.nodeSelector                                                                                       | no                                    |                                                                                                                                      |
| keyclock.application.tolerations                 | Object  | K8S's spec.tolerations                                                                                        | no                                    |                                                                                                                                      |
| keyclock.application.affinity                    | Object  | K8S's spec.affinity                                                                                           | no                                    |                                                                                                                                      |
| keyclock.application.db.addr                     | String  | Database host                                                                                                 | yes                                   |                                                                                                                                      |
| keyclock.application.db.database                 | String  | Database name                                                                                                 | yes                                   |                                                                                                                                      |
| keyclock.application.db.user                     | String  | Database user                                                                                                 | yes                                   |                                                                                                                                      |
| keyclock.application.db.password                 | String  | Database password                                                                                             | yes                                   |                                                                                                                                      |
| keyclock.application.db.port                     | Integer | Database port                                                                                                 | yes                                   |                                                                                                                                      |
| keyclock.application.db.schema                   | String  | Database schema                                                                                               | only on PostgreSQL                    |                                                                                                                                      |
| keyclock.application.db.vendor                   | String  | Database vendor                                                                                               | yes                                   |                                                                                                                                      |
| keyclock.application.client.appcomposerClientId  | String  | The Client Id the AppComposer uses to call the OIDC Api. It must be the same as _application.oc.client.id_    | yes                                   | appcomposer                                                                                                                          |
| keyclock.application.client.appcomposerClientPwd | String  | The Password the AppComposer uses to call the OIDC Api. It must be the same as _application.oc.client.secret_ | yes                                   |                                                                                                                                      |
| keyclock.application.ingress.enabled             | Bool    | Set to true to configure the ingress for the Keycloak                                                         | yes                                   | false                                                                                                                                |
| keyclock.application.ingress.annotations         | Object  | Ingress annotations                                                                                           | only if _ingress.enabled_ is **true** |                                                                                                                                      |
| keyclock.application.password                    | String  | Keycloak password                                                                                             | yes                                   |                                                                                                                                      |
| keyclock.application.user                        | String  | Keycloak user                                                                                                 | yes                                   |                                                                                                                                      |
| keyclock.application.logoutRedirectUri           | String  | Valid logout URI to the AppComposer                                                                           | yes                                   |                                                                                                                                      |
| keyclock.application.redirectUri                 | String  | Valid redirect URI to the AppComposer                                                                         | yes                                   |                                                                                                                                      |
| keyclock.application.zoneId                      | String  | Valid zone Id                                                                                                 | yes                                   |                                                                                                                                      |

## Values.yaml

This is an example of a valid values.yaml file.

```
global:
  registry:
    credentials:
      username: <username>
      password: <password>
      email: <email>
  security:
    token:
      seed: EIRTUDO23KDFIEUHFYWEPO
  rabbit:
    username: <username>
    password: <password>
  keycloak:
    enabled: true
application:
  resources:
    requests:
      cpu: "0.5"
      memory: 1Gi
    limits:
      cpu: "1"
      memory: 4Gi    
  oc:
    client:
      id: appcomposer
      secret: <secret>
    properties:
      realm: "appcomposer"
      userIdentifierClaim: "sub"
    endpoints:
      logoutEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/logout?redirect_uri=%LOGOUT_REDIRECT_URI%"
      loginRedirectUri: "https://somewhere/index.cas"
      checkTokenEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/token/introspect"
      userInfoEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/userinfo"
      jwkEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/certs"
      tokenEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/token"
      authorizationEndpoint: "https://somewhere/auth/realms/${oc.realm}/protocol/openid-connect/auth"
  metadata:
    properties:
      port: 5432
      host: "somewhere.eu-west-3.rds.amazonaws.com"
      database: helm
      schema: appcomposer
      url: "jdbc:postgresql://somewhere.eu-west-3.rds.amazonaws.com:5432/helm?currentSchema=appcomposer"
    credentials:
      user: <username>
      password: <password>
  uaaUrl: "https://somewhere/auth/admin/realms"
  ingress:
    enabled: true
    annotations:
      cert-manager.io/cluster-issuer: letsencrypt-prod
      ingress.kubernetes.io/rewrite-target: /
      kubernetes.io/ingress.class: nginx
      nginx.ingress.kubernetes.io/affinity: cookie
      nginx.ingress.kubernetes.io/affinity-mode: persistent
      nginx.ingress.kubernetes.io/proxy-body-size: 150m
      nginx.ingress.kubernetes.io/proxy-read-timeout: '120'
      nginx.ingress.kubernetes.io/proxy-send-timeout: '240'
      nginx.ingress.kubernetes.io/session-cookie-change-on-failure: 'true'
      nginx.ingress.kubernetes.io/session-cookie-expires: '172800'
      nginx.ingress.kubernetes.io/session-cookie-max-age: '172800'
      nginx.ingress.kubernetes.io/session-cookie-name: route
      nginx.ingress.kubernetes.io/use-gzip: 'false'
      nginx.org/lb-method: least_conn
    tls:
      - hosts:
          - somewhere
        secretName: appcomposer
    hosts:
      - host: somewhere
        paths:
          - path: /
            pathType: ImplementationSpecific

rabbit:
  application:
    resources:
      requests:
        cpu: '0.5'
        memory: 512Mi
      limits:
        cpu: "1"
        memory: 1Gi 

dumbella:
  application:
    securityContext:
      runAsNonRoot: true
    datasource:
      password: <password>
      username: <username>
      url: "jdbc:postgresql://somewhere.eu-west-3.rds.amazonaws.com:5432/helm?currentSchema=dumbella"

timeturner:
  application: 
    datasource:
      url: "jdbc:postgresql://somewhere.eu-west-3.rds.amazonaws.com:5432/helm?currentSchema=timeturner"
      password: "<password>"
      username: "<username>"

keycloak:
  application:
    client:
      appcomposerClientId: appcomposer
      appcomposerClientPwd: <secret>
    db:
      addr: "somewhere.eu-west-3.rds.amazonaws.com"
      database: helm
      user: <username>
      password: <password>
      port: 5432
      schema: keycloak
      vendor: postgres
    password: appcomposer
    user: appcomposer
    logoutRedirectUri: "https://somewhere"
    redirectUri: "https://somewhere/index.cas"
    zoneId: "somewhere"     
    ingress:
      enabled: true
      annotations:
        cert-manager.io/cluster-issuer: letsencrypt-prod
        ingress.kubernetes.io/rewrite-target: /
        kubernetes.io/ingress.class: nginx
        nginx.ingress.kubernetes.io/affinity: cookie
        nginx.ingress.kubernetes.io/affinity-mode: persistent
        nginx.ingress.kubernetes.io/proxy-body-size: 150m
        nginx.ingress.kubernetes.io/proxy-read-timeout: '120'
        nginx.ingress.kubernetes.io/proxy-send-timeout: '240'
        nginx.ingress.kubernetes.io/session-cookie-change-on-failure: 'true'
        nginx.ingress.kubernetes.io/session-cookie-expires: '172800'
        nginx.ingress.kubernetes.io/session-cookie-max-age: '172800'
        nginx.ingress.kubernetes.io/session-cookie-name: route
        nginx.ingress.kubernetes.io/use-gzip: 'false'
        nginx.org/lb-method: least_conn
      tls:
        - hosts:
            - somewhere
          secretName: appcomposer
      hosts:
        - host: somewhere
          paths:
            - path: /auth
              pathType: ImplementationSpecific

```

## Default values

Those are the default values applied to your configuration but you can override any of them in the values.yaml file, if needed.

<pre><code>global:
  registry:
    name: "decisyon-dac-docker.jfrog.io"
    secretName: "appcomposer-registry-secret"
#    credentials:
#      username:
#      password:
#      email:
  security:
    apiGateway:
      enabled: false
#      cookieName:
#      uidClaim:
#      logOutUrl:
    token:
      seed:
  rabbit:
    host: rabbit
    port: 5672
#    password:
#    username:
  appcomposer:
    url: http://appcomposer:8080
  keycloak:
    enabled: true
  dumbella:
    enabled: true
    url: http://dumbella:8080
<strong>
</strong><strong>application:
</strong>  fullnameOverride: appcomposer
#  context:
#    root:
#    api:
#    ui:

#   metadata:
#    credentials:
#      user:
#      password:
#    properties:
#      port:
#      host:
#      database:
#      schema:
#      url:
#      minIdle: 5
#      maxPoolSize: 100
#      idleTimeout: 300000
#      connectionTimeout: 30000
#      validationTimeout: 15000
#      maxLifeTime: 600000
#  uaaUrl:
  image:
    tag: "2023.0.0"
    name: "com.decisyon.appcomposer-k8s"
    pullPolicy: "Always"
  replicas: 1
  profileActive: "prod,kubernetes,cloud,streams,monitoring"
  jvmOptions: ""
  resources:
    requests:
      cpu: "0.5"
      memory: 1Gi
    limits:
      cpu: "1"
      memory: 4Gi
  podAnnotations: { }
  podSecurityContext: { }
  securityContext:
    allowPrivilegeEscalation: false
    privileged: false
    readOnlyRootFilesystem: false
    runAsNonRoot: true
    runAsUser: 1000
  service:
    type: ClusterIP
    port: 8080
  security:
    starter:
      azureEnabled: false
      schneiderEnabled: false
#    csp:
#      script-src: "'unsafe-inline' 'unsafe-eval' 'self' ;"
#      img-src: "data: https://*.openstreetmap.org 'unsafe-inline' 'unsafe-eval' 'self' ;"
#      font-src: "data: https://fonts.gstatic.com/ 'unsafe-inline' 'unsafe-eval' 'self' ;"
#      style-src: "https://fonts.googleapis.com/ https://maxcdn.bootstrapcdn.com https://getbootstrap.com/ 'self' 'unsafe-inline' ;"
#      default-src: "https://widgethub.decisyon.com/ 'self';"
#      frame-ancestors: "'self' ;"
#      worker-src: "blob: 'self' ;"
#      form-action: "'self' ;"
#    cors:
#      allowed-origins: "*"
#      allowed-methods: "*"
#      allowed-headers: "*"
#      allow-credentials: false
#      exposed-headers: "*"
#  oc:
#    azureADTenantId:
#    properties:
#      userIdentifierClaim:
#      realm:
#    endpoints:
#      logoutEndpoint:
#      authorizationEndpoint:
#      checkTokenEndpoint:
#      loginRedirectUri:
#      tokenEndpoint:
#      userInfoEndpoint:
#      jwkEndpoint:
#    client:
#      id:
#      secret:
  properties: {}
  nodeSelector: {}
  tolerations: []
  affinity: {}
  ingress:
    enabled: false
#    annotations:
#      cert-manager.io/cluster-issuer: letsencrypt-prod
#      ingress.kubernetes.io/rewrite-target: /
#      kubernetes.io/ingress.class: nginx
#      nginx.ingress.kubernetes.io/affinity: cookie
#      nginx.ingress.kubernetes.io/affinity-mode: persistent
#      nginx.ingress.kubernetes.io/proxy-body-size: 150m
#      nginx.ingress.kubernetes.io/proxy-read-timeout: '120'
#      nginx.ingress.kubernetes.io/proxy-send-timeout: '240'
#      nginx.ingress.kubernetes.io/session-cookie-change-on-failure: 'true'
#      nginx.ingress.kubernetes.io/session-cookie-expires: '172800'
#      nginx.ingress.kubernetes.io/session-cookie-max-age: '172800'
#      nginx.ingress.kubernetes.io/session-cookie-name: route
#      nginx.ingress.kubernetes.io/use-gzip: 'false'
#      nginx.org/lb-method: least_conn
#    hosts:
#      - host:
#        paths:
#        - path: /
#          pathType: ImplementationSpecific
#
#    tls:
#      - hosts: []
#        secretName: ""
dumbella:
  application:
    fullnameOverride: "dumbella"
#    datasource:
#      url:
#      password:
#      username:
    image:
      name: "com.decisyon.dumbella"
      tag: "2023.0.0"
      pullPolicy: "Always"
    replicas: 1
    service:
      type: "ClusterIP"
      port: 8080
    resources:
      requests:
        cpu: "0.5"
        memory: "1Gi"
      limits:
        cpu: "1"
        memory: "4Gi"
    volume:
      enabled: false
#      storageClassName:
#      capacity:
#      accessModes:
#      spec:
    podAnnotations: { }
    podSecurityContext: { }
    securityContext:
      allowPrivilegeEscalation: false
      privileged: false
      runAsNonRoot: true
      runAsUser: 1000
    volumes: []
    volumeMounts: []
    nodeSelector: {}
    tolerations: []
    affinity: {}
    properties: {}
rabbit:
  application:
    fullnameOverride: "rabbit"
    replicaCount: 1
    image:
      name: "com.decisyon.rabbitmq"
      tag: "2023.0.0"
    podAnnotations: { }
    podSecurityContext: { }
    securityContext:
      allowPrivilegeEscalation: false
      privileged: false
      runAsNonRoot: true
      runAsUser: 1000
#      capabilities:
#        drop:
#        - ALL
#      readOnlyRootFilesystem: true
    service:
      type: "ClusterIP"
      port: 80
    resources:
      requests:
        cpu: '0.5'
        memory: 512Mi
      limits:
        cpu: "1"
        memory: 2Gi
    nodeSelector: { }
    tolerations: [ ]
    affinity: { }

keycloak:
  application:
    fullnameOverride: "keycloak"
#    db:
#      addr:
#      database:
#      user:
#      password:
#      port:
#      schema:
#      vendor:
    client:
      appcomposerClientId: "appcomposer"
#      appcomposerClientPwd: ""
    replicas: 1
    image:
      tag: "2023.0.0"
      name: "com.decisyon.keycloak"
    resources:
      requests:
        cpu: "0.5"
        memory: 1Gi
      limits:
        cpu: "1"
        memory: 2Gi
    service:
      port: 8180
      type: "ClusterIP"
    podAnnotations: { }
    podSecurityContext: { }
    securityContext:
      allowPrivilegeEscalation: false
      privileged: false
      runAsNonRoot: true
      runAsUser: 1000
#    password:
#    user:
#    logoutRedirectUri:
#    redirectUri:
#    zoneId:
    nodeSelector: { }
    tolerations: [ ]
    affinity: { }
    ingress:
      enabled: false
    #    annotations:
    #      cert-manager.io/cluster-issuer: letsencrypt-prod
    #      ingress.kubernetes.io/rewrite-target: /
    #      kubernetes.io/ingress.class: nginx
    #      nginx.ingress.kubernetes.io/affinity: cookie
    #      nginx.ingress.kubernetes.io/affinity-mode: persistent
    #      nginx.ingress.kubernetes.io/proxy-body-size: 150m
    #      nginx.ingress.kubernetes.io/proxy-read-timeout: '120'
    #      nginx.ingress.kubernetes.io/proxy-send-timeout: '240'
    #      nginx.ingress.kubernetes.io/session-cookie-change-on-failure: 'true'
    #      nginx.ingress.kubernetes.io/session-cookie-expires: '172800'
    #      nginx.ingress.kubernetes.io/session-cookie-max-age: '172800'
    #      nginx.ingress.kubernetes.io/session-cookie-name: route
    #      nginx.ingress.kubernetes.io/use-gzip: 'false'
    #      nginx.org/lb-method: least_conn
    #    hosts:
    #      - host:
    #        paths:
    #        - path: /
    #          pathType: ImplementationSpecific
    #
    #    tls:
    #      - hosts: []
    #        secretName: ""
timeturner:
  application:
#    datasource:
#      url:
#      password:
#      username:
    fullnameOverride: "timeturner"
    properties: {}
    replicaCount: 1
    image:
      name: "com.decisyon.timeturner"
      tag: "2023.0.0"
      pullPolicy: "Always"
    podAnnotations: { }
    podSecurityContext: { }
    securityContext:
      allowPrivilegeEscalation: false
      privileged: false
      runAsNonRoot: true
      runAsUser: 1000
    service:
      type: "ClusterIP"
    resources:
      requests:
        cpu: "0.5"
        memory: 1Gi
      limits:
        cpu: "1"
        memory: 4Gi
    nodeSelector: { }
    tolerations: [ ]
    affinity: { }


</code></pre>
