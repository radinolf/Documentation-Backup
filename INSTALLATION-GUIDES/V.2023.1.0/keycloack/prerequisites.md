# Prerequisites

## RDBMS

Keycloak service requires a RDMS to store the settings and configuration it needs to run.

The connection between the service and the database happens via JDBC. Please see the properties to configure the required parameters.

Supported RDBMS are:

* PosgtreSQL 10 or above
* Microsoft SQL Server 2014 or above

{% hint style="info" %}
Regardless Keycloak supports more RDBMS vendor, it is strongely suggested to use the same RDBMS compatible with App Composer.
{% endhint %}

The database and the database users must be already created before App Composer is deployed.

The database user that is used by Keycloak requires the following grants on the database schema.

```sql
CREATE TABLE
ALTER TABLE
DROP TABLE
INSERT
SELECT
DELETE
UPDATE
```

The service will automatically create the tables it needs when it is started.

## Minimum resources

The minimun resource that must be allocated to the service:

* 2 GB of RAM
* 500 mCPU&#x20;

