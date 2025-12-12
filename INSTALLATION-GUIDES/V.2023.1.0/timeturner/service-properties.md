# Service properties

### DATA SOURCE

<table data-full-width="true"><thead><tr><th width="276">Property</th><th width="219">Description</th><th>Type</th><th>Mandatory</th><th>Default value</th></tr></thead><tbody><tr><td>spring.datasource.url </td><td>JDBC URL of the database.</td><td>string</td><td>yes </td><td></td></tr><tr><td>spring.datasource.username </td><td>Login username of the database. Username must be the same as Rabbit MQ RABBITMQ_DEFAULT_USER</td><td>string</td><td>yes</td><td></td></tr><tr><td>spring.datasource.password</td><td>Login password of the database. The password must be the same entered on Rabbit MQ RABBITMQ_DEFAULT_PASS</td><td>string</td><td>yes</td><td></td></tr></tbody></table>

### RABBIT MQ

<table data-full-width="true"><thead><tr><th width="271">Property</th><th>Description</th><th>Type</th><th>Mandatory</th><th>Default value</th></tr></thead><tbody><tr><td>spring.rabbitmq.host</td><td>RabbitMQ host.</td><td>string</td><td>yes </td><td></td></tr><tr><td>spring.rabbitmq.port </td><td>RabbitMQ port. Ignored if an address is set. </td><td>string</td><td>yes</td><td>Default to 5672, or 5671 if SSL is enabled.</td></tr><tr><td>spring.rabbitmq.username </td><td>Login user to authenticate to the broker.</td><td>string</td><td>yes</td><td></td></tr><tr><td>spring.rabbitmq.password </td><td>Login password to authenticate to the broker</td><td>string</td><td>yes</td><td></td></tr><tr><td><p>spring.quartz.properties.org.quartz.jobStore.driverDelegateClass</p><p></p></td><td>If using MS SQL Server must be set on <code>org.quartz.impl.jdbcjobstore.MSSQLDelegate</code> </td><td>string</td><td>no</td><td></td></tr></tbody></table>
