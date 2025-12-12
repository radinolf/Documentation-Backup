# Enhancement

In this version, significant improvements have been made to the user interface, new microservices have been introduced, and a new navigation has been implemented. Additionally, the Document Repository and collaboration tables are no longer managed through Design Studio but through properties in the HELM Chart. Below, you will find a list of all the tickets related to the enhancements for this new section.

## Microservice - Pages and Cockpit

#### Enable "Single Tenant" Mode

* **DACXX-90** Enable "Single Tenant" Mode

#### Remove Translation for Description Label of the Property

* **DACXX-136** Remove the translation for the description label fo the property

#### Review Helm Chart Using Azure Vault

* **DACXX-440, DACXX-442, DACXX-443,DACXX-444, DACXX-445** Review Helm Chart using Azure Vault

#### Others

* **DACXX-193** Manage the attachMessage
* **DACXX-238** Close the websocket after logout
* **DACXX-277** Show the number of users for each navigation panel voice
* **DACXX-296** Implement a new ControllerAdvice Exception
* **DACXX-323** Set CORS directives
* **DACXX-356** Update Helm Chart of batch-jobs micro-service
* **DACXX-362** Review Page's REST API
* **DACXX-401** Show the "Current Version" property of the Job/Service
* **DACXX-428** Refactoring of the Application selector
* **DACXX-437** Create new Tenant Metadata's table "theme\_settings"
* **DACXX-448** Use the Service Token to invoke DAC and Dumbella's API
* **DACXX-449** User Authorization to access Cockpit
* **DACXX-455** Replace HTTP 701 with a RFC-Compliant Code to Avoid Firewall Blockage
* **DACXX-480** Rename the "Scopes" in "Users scopes" and add the "Scopes" for the Theme scope
* **DACXX-498** First accessed user scopes in Pages
* **DACXX-516** Delete all check over the administration license in Pages

## Microservices -  AppComposer



**Platform and Services**

* **D4C-9392** Exclude Keycloak from the Standard AppComposer's architecture
* **D4C-9540** Application Update using ADP File
* **D4C-9595** Enable Report's Automatic and Absolute Caches

**Synchronization**

* **D4C-9066** Review the synchronization of groups deletion
* **D4C-9067** Review the synchronization of a new application
* **D4C-9216** Review the installation of the Collaboration's tables
* **D4C-9541** Expose Synchronisation Event to Rabbit
* **D4C-9547** Synchronization API

**Security and Access**

* **D4C-9137** Review the Access Token generation
* **D4C-9567** Removed the user administration section from AppComposer

**Helm Chart**

* **D4C-9158,D4C-9390,D4C-9538** Revision and improvement of HELM chart Update Helm Chart

**Miscellaneous**

* **D4C-9529** Review the management of the Document's tables
* **D4C-9552** Replaced any non RFC-compliant response status code with an RFC-Compliant Code to Avoid Firewall Blockage
* **D4C-9431** Implements Notification management in multi Tenant environment

## Technological and dependency upgrades:

* Spring, Spring Boot, Angular etc
* Upgrade of Java version
* Material upgrade
* Code cleanup and removal of legacy libraries and frameworks
* HTTP response code are now all RFC-7321 compliant

