# Prerequisites

## RDBMS

Dumbella service requires a RDMS to store the settings and configuration it needs to run.

The connection between the service and the database happens via JDBC. Please see the properties to configure the required parameters.

Supported RDBMS are:

* PosgtreSQL 10 or above
* Microsoft SQL Server 2014 or above

The database and the database users must be already created before App Composer is deployed.

Metadata tables are stored in a specific schema: if the database user has the proper grant, the schema can be created by the service; if the database user doesn't have the grants, also the database schema must be created upfront.

The database user that is used by Dumbella requires the following grants on the metadata schema.

```sql
CREATE TABLE
ALTER TABLE
DROP TABLE
INSERT
SELECT
DELETE
UPDATE
```

When the schema is empty or doesn't contain the metadata tables, the service will automatically create the tables.

## Minimum resources

The minimun resource that must be allocated to the service:

* 1024 GB of RAM
* 500 mCPU&#x20;
* 2 GB of persistent volume

{% hint style="info" %}
The resources to allocate to the service depends also on the number of jobs that are expected to be executed in the same moment and on the resource consumption of each job that will be executed.&#x20;
{% endhint %}

## Volumes

Dumbella needs a persistent volume to be configured in the stack.

The size of the volume depends on the number of jobs and the folder size of each single uncompressed jobs.&#x20;

It is suggested to allocate at least 2Gb to the volume.

Please refer to Kubernetes documentation to learn how to configure a persistent volume.
