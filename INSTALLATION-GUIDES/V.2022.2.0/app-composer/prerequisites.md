# Prerequisites

## RDBMS

App Composer service requires a RDMS to store the settings and configurations it needs to run.

The connection between the service and the database happens via JDBC. Please see the properties to configure the required parameters.

Supported RDBMS are:

* PosgtreSQL 10 or above
* Microsoft SQL Server 2014 or above

The database and the database users must be already created before App Composer is deployed.

Metadata are stored in a specific database schema: if the database user has the proper grants, the schema can be created by the service; if the database user doesn't have the grants, also the database schema must be created upfront.

The database user that is used by App Composer requires the following grants on the metadata schema.

```sql
CREATE TABLE
ALTER TABLE
DROP TABLE
INSERT
SELECT
DELETE
UPDATE
```

When the schema is empty or doesn't contain the metadata tables, the service will automatically create the tables at startup.

When the schema already contains a the metadata tables, the service starts successfully.

When the service has a version greater than the one used during the installation, metadata is automatically upgraded to the latest version. App Composer starts successfully only on the proper metadata version.

After a scratch installation, the first user that logins successfully is automatically granted as "administrator". All the following users must be promoted to "administrator" from the first administrator.

It is possible to login in Design Studio using the following default credentials

* administrator
* administrator

Make sure to modify the default password after the login for security compliance.

## Minimum resources

The minimun resource that must be allocated to the service:

* 4096 GB of RAM
* 1000 mCPU&#x20;

## Others

The service is able to scale horizontally and it is necessary to configure **sticky session**. Please refer to Kubernetes documentation to configure it.
