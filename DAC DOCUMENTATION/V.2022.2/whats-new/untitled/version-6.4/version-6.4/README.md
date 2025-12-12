# Migration Notes 6.4

## 6.4.1

Decisyon App Composer 6.4.1 “Katy” cannot be installed to upgrade versions before the 6.2.0 “Jake”: if it were the case, before installing “Katy”, DAC must be upgraded to the 6.3.0 “Jalapeño” and then proceed upgrading to “Katy”.

– Decisyon App Composer’s Docker Image has change its artefact id from “_appcomposer-home_” and “_appcomposer-azure_” to “_appcomposer-docker_” and “_appcomposer-k8s_“. So the images names now are com.decisyon.appcomposer-k8s and com.decisyon.appcomposer-docker. You need to change them in your configurations in order to upgrade to KATY: _“**appcomposer-home”**_**&#x20;and&#x20;**_**“appcomposer-azure”**_**&#x20;are no longer supported**, use _“appcomposer-k8s”_ only in Kubernetes cluster, for any other purpose user _“appcomposer-docker”._&#x20;

– Decisyon App Composer’s Docker Image has a new startup file and if you are running on Azure App Service, you need to change the configuration setting the “Startup File” as “_bash -c /usr/bin/start.sh_“.

– Cornelius has changed its running port from 8888 to 8080: any configuration (e.g. docker or docker-compose) must be changed. If you have Cornelius’ image to bind its running port to an host port, xxxx:8888, this has to change to xxxx:8080. Furthermore, check your AppComposer configuration, and see if you need to change config.server.port property accordingly.

– In order to use Cornelius as Configuration Server you need to change your spring.profiles.active property, adding the profile “_cornelius”_: for example, if you have “_spring.profiles.active=prod”_ you need to change it to “_spring.profiles.active=prod,cornelius”_

– Static Charts have been replaced with new better-looking ones. Even if the migration shall be done automatically, it is possible that any of them would change its appear a bit. **The Gantt chart is an exception and it must be checked and reconfigured from scratch if necessary.**

Then, for the following static charts, some properties must be reviewed:

* _Dual Y-Axis Line_ becomes a _Custom Layer_ plotting both series (first y axis and second y axis) as lines, setting the _property “custom-layer”_ accordingly;
* _Dual Y-Axis Bar_ becomes a _Custom Layer_  plotting both series (first y axis and second y axis) as columns, setting the _property “custom-layer”_ accordingly;
* _Dual Y-Axis_ becomes a _Custom Layer_ plotting the first serie as a column on the first y axis, the second one as a line in the second y axis, setting the _property “custom-layer”_ accordingly.
* &#x20;_Area Percentage_ become a _2D Area Stack_ enabling the “show-percentage” property.

### Content

* [Changes and migration of version 6.4.1](changes-and-migration-of-version-6.4.1.md)
* [Keycloak Installation Guide](/broken/pages/-MfX-fMpmZoFFcAHs9vN)
* [Configuring App Composer with Keycloak](/broken/pages/-MfX-fMpmZoFFcAHs9vN#configuring-app-composer-with-keycloak)

