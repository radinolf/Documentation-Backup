# Dumbella Installation Guide

## Dumbella Installation Guide

* Dumbella requires a schema on a database (PostgreSQL or MS SQL Server), connection data must be provided setting its environment variables appropriately.

| **VARIABLES**                | **DESCRIPTION**   |
| ---------------------------- | ----------------- |
| SPRING\_DATASOURCE\_USERNAME | Username          |
| SPRING\_DATASOURCE\_PASSWORD | Password          |
| SPRING\_DATASOURCE\_URL      | Database JDBC url |

## Configuring App Composer with Dumbella

You can enable App Composer to use a Dumbella instance as job executor by setting the following environment variables:

* appcomposer.dumbella.enable=true
* appcomposer.dumbella.url=\<dumbella-url>
