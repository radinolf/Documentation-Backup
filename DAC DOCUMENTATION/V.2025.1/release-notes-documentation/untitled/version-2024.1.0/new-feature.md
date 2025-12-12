# New Feature

## &#x20;Pages

In this update, we've introduced a new microservice called "**Pages**." This addition has led to significant enhancements in both the user interface and the codebase. Below you can find a list of enhancements.

### Create the Pages Section

* DACXX-84 Create the Page Section
* DACXX-87 Create the Main toolbar
* DACXX-91 Create the Navigation Panel
* DACXX-96 Create the Folder View for the Content Panel
* DACXX-97 Create the Page view for the Content Panel
* DACXX-124 Create the Section Toolbar on pages section
* DACXX-125 Create the Bottom toolbar
* DACXX-214 Create the login page for Pages
* DACXX-247 Settings menu on Main Toolbar
* DACXX-248 Create the navigation panel
* DACXX-249 Create the user list content panel in "User administration"
* DACXX-250 Create the support panel
* DACXX-272 Create the section toolbar on user administration section
* DACXX-280 Create the search component for the section toolbar

### Others&#x20;

* DACXX-154 Decisyon AppComposer's Helm Chart
* DACXX-191 Decisyon AppComposer's Helm Chart
* DACXX-198 Migrate the jsp associated with the Crosstab menu "object explorer
* DACXX-233 Highlight search results in the navigation tree
* DACXX-285 Display Action List Execution Log
* DACXX-287 Display the details of the Schedule of an Action List
* DACXX-288 Display the ActionList's Catalog
* DACXX-289 Display Scheduled ActionList Execution Log
* DACXX-375 Differentiate Tenant overlapping concepts on Pages
* DACXX-375 Differentiate Tenant overlapping concepts on Pages&#x20;
* DACXX-434 Absol User Token compatibility with Cherrim

## Cockpit

In this version, we have introduced a new microservice called "**Cockpit**." This new component has resulted in significant developments both in the user interface and in the code. Below, you will find a list of all the tickets related to the new developments for this new section. These innovations are designed to enhance the user experience and optimize the functionalities of our application.

* DACXX-131 Show Dumbella's Jobs
* DACXX-132 Display ActionList details
* DACXX-133 Use OIDC Authentication
* DACXX-139 Monitoring and Controlling Running Jobs of Type "Job"
* DACXX-141 Managing Jobs of Type "Service"
* DACXX-143 Handling Errors in Jobs
* DACXX-146 Cockpit's Helm Chart
* DACXX-181 Import new Application using ADP file
* DACXX-286 Display ActionList Execution Statistics
* DACXX-376 Selecting an Application &#x20;
* DACXX-351 Delete Application&#x20;
* DACXX-404 Updating Job's Published Version&#x20;
* DACXX-408 Show List of Applications&#x20;
* DACXX-409 Show Application Log of Imports&#x20;
* DACXX-411 Download Application Metadata File&#x20;
* DACXX-412 Update Application using ADP File &#x20;
* DACXX-413 Download Metadata File for New Application&#x20;
* DACXX-514 API Key creation&#x20;
* DACXX-537 Abort an on-progress Import Operation&#x20;

## AppComposer

App Composer has remained faithful to its consolidated user interface, thus maintaining familiarity for our users. However, it's important to note that in this version, no significant changes have been made to the user interface (UI). This allows users to continue using the application without needing to undergo additional learning regarding the graphical interface. Below is the list of tickets worked on for this version:

**User Management**

* D4C-9059 Enable OIDC Users for Design Studio
* D4C-9061 Additional scopes for Business Users
* D4C-9068 Implement the synchronization of Users Attributes
* D4C-9069 Synchronisation of Term of Use
* D4C-9566 User management via White List in AppComposer

## Batch Jobs's&#x20;

This microservice performs scheduled tasks, mostly to clean up Metadata and Tenant’s Metadata. It is a microservice that does not have a user interface and is present in the multi-tenant architecture.

* **DACXX-147** Batch Jobs's Helm Char

## Tenant Metadata Installer

Tenant MD Installer is the microservices that installs the Tenant’s Metadata; it runs on demand and its life cycle is independent from all the other components. It does not have a user interface and is present in the multi-tenant architecture.

* **DACXX-149** Tenant Metadata Installer's Helm Chart
