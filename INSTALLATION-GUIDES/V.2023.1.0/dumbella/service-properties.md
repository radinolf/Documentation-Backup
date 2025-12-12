# Service properties



<table><thead><tr><th width="224">Property</th><th width="238">Description</th><th width="87">Type</th><th width="119">Mandatory</th><th width="100">Default value</th></tr></thead><tbody><tr><td>spring_datasource_url</td><td>The JDBC connection string to the database, i.e. “<code>jdbc:postgresql://&#x3C;database_host>:5432/&#x3C;database_name>?currentSchema=&#x3C;schema></code> “</td><td>string</td><td>yes</td><td></td></tr><tr><td>spring_datasource_username</td><td>The username of the database user</td><td>string</td><td>yes</td><td></td></tr><tr><td>spring_datasource_password</td><td>The password of the database user</td><td>string</td><td>yes</td><td></td></tr><tr><td>dac.security.service.token.seed</td><td>A randomly generate 20-chars string that is used to autheticate requests with App Composer service. This value must be the same of the App Composer service property appcomposer.security.service.token.seed</td><td>string</td><td>yes</td><td></td></tr><tr><td>dac.url</td><td>The URL of App Composer service, i.e. https://appplication.decisyon.com. Please note that if you are in a K8S cluster you can also use internal service name.</td><td>string</td><td>yes</td><td></td></tr><tr><td>dumbella.job.result.availability</td><td>In Dumbella must be possible to configure how time a job execution result have to be available. </td><td>integer</td><td>No</td><td>24</td></tr></tbody></table>

## RabbitMQ



<table><thead><tr><th width="167">Property</th><th>Description</th><th>Type</th><th>Mandatory</th><th>Default value</th></tr></thead><tbody><tr><td>spring.rabbitmq.host</td><td>RabbitMQ host.</td><td>string</td><td>yes </td><td></td></tr><tr><td>spring.rabbitmq.port </td><td>RabbitMQ port. Ignored if an address is set. </td><td>string</td><td>yes</td><td>Default to 5672, or 5671 if SSL is enabled.</td></tr><tr><td>spring.rabbitmq.username </td><td>Login user to authenticate to the broker.</td><td>string</td><td>yes</td><td></td></tr><tr><td>spring.rabbitmq.password </td><td>Login password to authenticate to the broker</td><td>string</td><td>yes</td><td></td></tr></tbody></table>
