# Cache management

## Introduction

The **cache for the applications on remote DWHs** is managed in two ways:

For DWH data sources configured on Decisyon in read-only mode (is-read-only option in the connection created with Datasource Designer), the tables for the cache will be created on the metadata.

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

For DWH datasources configuredon Decisyon in write mode, the creation of temporary tables is performed in the schema defined for the datasource.

In these cases, users are advised to create a schema dedicated to the cache, in the environment where the DWH of the data is present.

The datasource is created in read/write mode in respect of this new schema (DWH CACHE), while for the application, the DWH of the data will be selected (Data DWH).

<figure><img src="../../../.gitbook/assets/image (406).png" alt=""><figcaption></figcaption></figure>

With this configuration Decisyon will create the cache tables on the schema to which the datasource points:

**Note:** The schema for writing the cache tables must be used by a single data source. Contrarily, the cache tables created for a first application will be rendered invalid by those of a second application which accesses the same cache schema (DWH CACHE).

## Properties of Cache

The cache is configured at the application level through the accessible properties in the **Administration >> Properties >> Cache** menu.

It is possible to set the properties listed below:

* **defaultExpTime** the maximum time of permanence of the reports in the cache: period in hours, starting from the creation date and time, after which the automatic cache expires
* **maxElementNum** the maximum number of reports which may be in the automatic cache at the same time
* **minExecTime** the minimum execution time (in seconds), so that a report may be saved in the automatic cache ()
* **invalidation-rule (on save)** the management of the cache and the cube-view invalidation following modifications to cubes, dimensions, metrics, direct filters, range filters and cube views. You can decide whether the invalidation is to be managed independently by the system (\<synchronized>) or if it must be requested at each change (\<prompt>)

## System Properties for the Cache

The configuration of the cache at system level is on the property of the Cache group:

**minHoldTimeDatamart (min)** is the minimum duration (in minutes) of the temporary tables used by the datamart and accessible to the user for displaying reports. Before this time, the tables will not be deleted, even if the system has rendered the cache invalid (default value set at 20 minutes).

Please see the [Preferences](../../instance-configuration/tools/preferences.md#main) of the Tool module
