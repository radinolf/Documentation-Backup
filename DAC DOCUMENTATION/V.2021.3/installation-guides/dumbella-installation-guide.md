# Dumbella Installation Guide

## Dumbella Installation Guide

* Dumbella requires a schema on a database (PostgreSQL or MS SQL Server), connection data must be provided setting its environment variables appropriately.
* In order to work with AppComposer safely, Appcomposer and Dumbella must share a common token seed, that allow the services to authenticate each others.&#x20;

| **VARIABLES**                   | **DESCRIPTION**                                                                                                           |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| SPRING\_DATASOURCE\_USERNAME    | Username                                                                                                                  |
| SPRING\_DATASOURCE\_PASSWORD    | Password                                                                                                                  |
| SPRING\_DATASOURCE\_URL         | Database JDBC url                                                                                                         |
| dac.security.service.token.seed | Must be equal to DAC's property appcomposer.security.service.token.seed It's must be a randomly generate 20-chars string. |

## Configuring App Composer with Dumbella

You can enable App Composer to use a Dumbella instance as job executor by setting the following environment variables:

* appcomposer.dumbella.enable=true
* appcomposer.dumbella.url=\<dumbella-url>
* appcomposer.security.service.token.seed
