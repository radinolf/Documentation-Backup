# Version 2021.3.3

## 2021.3.3 (Patch)- Dec  30,2021

### New Features Introduced

**This section of the Change Log provides a list of the new requirements implemented in version Quackmore.**

No new features introduced in this version.

### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Quackmore.**

[D4C-6686](https://decisyon.atlassian.net/browse/D4C-6682) Update Log4j2 dependency to 2.17.1 to prevent CVE-2021-44832

### Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

No defect fixed this version.

## 2021.3.2 (Patch) - Dec  15,2021

### New Features Introduced

**This section of the Change Log provides a list of the new requirements implemented in version Quackmore.**

No new features introduced in this version



### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Quackmore.**

D4C-6638 Set LOG4J\_FORMAT\_MSG\_NO\_LOOKUPS to prevent CVE-2021-44228



### Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

D4C-6625 REST API for user: exception "possible non-threadsafe access to session"

D4C-6626 Access token variable lost its value after a page fresh

D4C-6627 Wrong context when report's CRUD API are used in custom widget

D4C-6637 Parameters are not interpreted in the CRUD API of the report

D4C-6629 User management UI doesn't show error message on existing username

D4C-6632 Javascript Exception on execute object: "Cannot read properties of null"

D4C-6636 JS extGetDialogWindowOpener().extRefreshMashboardPage(); doesn't seems to work in some cases

D4C-6628 Console exception in Roast.1



## 2021.3.1 (Patch) - Nov 16 2021,

### New Features Introduced

**This section of the Change Log provides a list of the new requirements implemented in version Quackmore.**

[D4C-6196](https://decisyon.atlassian.net/browse/D4C-6196) Environment Variables must be interpreted in REST Client test params.

{% hint style="info" %}
Don't use a param valorized with an environment variable into the request of API, but use directly the environment variable. It'll be automatically valorized with the variable value.
{% endhint %}

### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Quackmore.**

[D4C-6469](https://decisyon.atlassian.net/browse/D4C-6469) Performance of endpoint /api/rest/application/\<owner>/report/\<report\_id>

[D4C-6432](https://decisyon.atlassian.net/browse/D4C-6432) Refactor Filters' SQL expression to use JsqlParser for validation

[D4C-6408](https://decisyon.atlassian.net/browse/D4C-6408) Refactory of page catalogue for enhance the performance

[D4C-6392](https://decisyon.atlassian.net/browse/D4C-6392) Extend length of server name in the metadata table

[D4C-6391](https://decisyon.atlassian.net/browse/D4C-6391) \[Security] Env variable to configure the length of parameter

### Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

[D4C-6509](https://decisyon.atlassian.net/browse/D4C-6509) NullPointer in DS when opening a widget associated to SQL Report

[D4C-6506](https://decisyon.atlassian.net/browse/D4C-6506) Sql report saving problems

[D4C-6503](https://decisyon.atlassian.net/browse/D4C-6503) Removal of a group from a user is not saved

[D4C-6492](https://decisyon.atlassian.net/browse/D4C-6492) Error editing or adding a label

[D4C-6486](https://decisyon.atlassian.net/browse/D4C-6486) Error on new group creation

[D4C-6474](https://decisyon.atlassian.net/browse/D4C-6474) Report export without "create-temp-table" flag

[D4C-6467](https://decisyon.atlassian.net/browse/D4C-6467) PEPSICO - "Button" WIdget does not execute "Submit"

[D4C-6466](https://decisyon.atlassian.net/browse/D4C-6466) PEPSICO - Empty Breadcrumb when on last element

[D4C-6434](https://decisyon.atlassian.net/browse/D4C-6434) Search user by name and surname doesn't work

[D4C-6433](https://decisyon.atlassian.net/browse/D4C-6433) \[Security] Validation fails when file name includes Chinese Character

[D4C-6418](https://decisyon.atlassian.net/browse/D4C-6418) Report SQL shows wrong columns when temporary table property is disabled

[D4C-6406](https://decisyon.atlassian.net/browse/D4C-6406) Console log exception about promise after a disconnection toast

[D4C-6348](https://decisyon.atlassian.net/browse/D4C-6348) File size of background image is bigger than original

[D4C-6344](https://decisyon.atlassian.net/browse/D4C-6344) Missing Type Bars Stack in the Custom Layer chart

[D4C-6320](https://decisyon.atlassian.net/browse/D4C-6320) Reports mapped with boolean fields of a "datasource rest" fails

[D4C-6276](https://decisyon.atlassian.net/browse/D4C-6276) Edit button on User editing dialog

[D4C-6233](https://decisyon.atlassian.net/browse/D4C-6233) field too large while modifying a user (manager info)

[D4C-6203](https://decisyon.atlassian.net/browse/D4C-6203) Error in tenant visualization

[D4C-6178](https://decisyon.atlassian.net/browse/D4C-6178) Smart table visualization in DAC

[D4C-6095](https://decisyon.atlassian.net/browse/D4C-6095) Design Studio doesn't show all the records returned from the db

[D4C-6085](https://decisyon.atlassian.net/browse/D4C-6085) Wrong tenant number on user Administration

[D4C-6020](https://decisyon.atlassian.net/browse/D4C-6020) Slow application opening on DS

[D4C-5910](https://decisyon.atlassian.net/browse/D4C-5910) REST Client not validated if container variables are used

[D4C-490](https://decisyon.atlassian.net/browse/D4C-490) Column of data type double are truncated when report is executed in REST/JSON data source

## 2021.3.0

### New Features Introduced

**This section of the Change Log provides a list of the new requirements implemented in version Quackmore.**

[D4C-6462](https://decisyon.atlassian.net/browse/D4C-6462) "Too many redirects" after logging in using HTTP instead of HTTPS

[D4C-6455](https://decisyon.atlassian.net/browse/D4C-6455) Browser cache of shared library is not invalidated

[D4C-6453](https://decisyon.atlassian.net/browse/D4C-6453) Pagination doesn't work in the People section

[D4C-6438](https://decisyon.atlassian.net/browse/D4C-6438) Error updating SQL Server metadata to Roast

[D4C-6437](https://decisyon.atlassian.net/browse/D4C-6437) Documentation for widgets does not open

[D4C-6435](https://decisyon.atlassian.net/browse/D4C-6435) Not possible to select file on Widget Designer >> Setting Deps

[D4C-6416](https://decisyon.atlassian.net/browse/D4C-6416) DISS - SIM1 - KPI Configuration by Line >> view by KPI "ERROR"

[D4C-6413](https://decisyon.atlassian.net/browse/D4C-6413) DISS - Department page error

[D4C-6412](https://decisyon.atlassian.net/browse/D4C-6412) DISS - Create Barrier error

[D4C-6401](https://decisyon.atlassian.net/browse/D4C-6401) \[Helm Chart] Liveness, Readiness and Startup probes don't have the context set

[D4C-6400](https://decisyon.atlassian.net/browse/D4C-6400) Smart grid widget executes reports twice

[D4C-6398](https://decisyon.atlassian.net/browse/D4C-6398) User Profile change password doens't check old password

[D4C-6396](https://decisyon.atlassian.net/browse/D4C-6396) 404 error opening a specific page

[D4C-6389](https://decisyon.atlassian.net/browse/D4C-6389) No context on favicon call

[D4C-6388](https://decisyon.atlassian.net/browse/D4C-6388) Column definition of editable report

[D4C-6386](https://decisyon.atlassian.net/browse/D4C-6386) Error opening a page, using relative path

[D4C-6385](https://decisyon.atlassian.net/browse/D4C-6385) Error reading Report property read-only-columns when never changed on old report

[D4C-6383](https://decisyon.atlassian.net/browse/D4C-6383) Console Error on user change password on User Profile

[D4C-6382](https://decisyon.atlassian.net/browse/D4C-6382) 404 error opening Rest API documentation

[D4C-6379](https://decisyon.atlassian.net/browse/D4C-6379) 404 error opening a Widget element code in external page

[D4C-6377](https://decisyon.atlassian.net/browse/D4C-6377) Img not found sorting a report column

[D4C-6376](https://decisyon.atlassian.net/browse/D4C-6376) Console Error moving a task on taskboard

[D4C-6374](https://decisyon.atlassian.net/browse/D4C-6374) \[Security] Impossible to export in CSV due to security validation

[D4C-6373](https://decisyon.atlassian.net/browse/D4C-6373) New Report Editor show an empty executed report

[D4C-6365](https://decisyon.atlassian.net/browse/D4C-6365) \[Security] Exception on drill through opening

[D4C-6362](https://decisyon.atlassian.net/browse/D4C-6362) Console error on page opening on widget Datetime picker

[D4C-6360](https://decisyon.atlassian.net/browse/D4C-6360) User editing and password definition

[D4C-6359](https://decisyon.atlassian.net/browse/D4C-6359) Debug info opening on a page

[D4C-6358](https://decisyon.atlassian.net/browse/D4C-6358) New user not associated to Everyone

[D4C-6353](https://decisyon.atlassian.net/browse/D4C-6353) Main toolbar show on page's embed link refresh

[D4C-6352](https://decisyon.atlassian.net/browse/D4C-6352) Wrong path loading when "Totals Definition"

[D4C-6351](https://decisyon.atlassian.net/browse/D4C-6351) Console error on User Side Nav opening

[D4C-6350](https://decisyon.atlassian.net/browse/D4C-6350) No file downloaded on CSV, PDF, Print for report

[D4C-6349](https://decisyon.atlassian.net/browse/D4C-6349) Error on drill context menù opening

[D4C-6347](https://decisyon.atlassian.net/browse/D4C-6347) White Label Error when "Totals Definition"

[D4C-6346](https://decisyon.atlassian.net/browse/D4C-6346) 404 Error adding metric or level to a report

[D4C-6342](https://decisyon.atlassian.net/browse/D4C-6342) Widget designer section refresh

[D4C-6341](https://decisyon.atlassian.net/browse/D4C-6341) API user creatio of a user with no timezone doesn't work

[D4C-6337](https://decisyon.atlassian.net/browse/D4C-6337) DS Cluster leader management on multipod environment

[D4C-6336](https://decisyon.atlassian.net/browse/D4C-6336) Pensil icon on Taskboard

[D4C-6335](https://decisyon.atlassian.net/browse/D4C-6335) Task card highlighted when side nav closed

[D4C-6334](https://decisyon.atlassian.net/browse/D4C-6334) Task side bar not refreshed on priority changes

[D4C-6333](https://decisyon.atlassian.net/browse/D4C-6333) Error Opening Report Catalogue on DS

[D4C-6330](https://decisyon.atlassian.net/browse/D4C-6330) Access denied to dimension when executing report

[D4C-6327](https://decisyon.atlassian.net/browse/D4C-6327) Error on javascript function execution

[D4C-6318](https://decisyon.atlassian.net/browse/D4C-6318) User administration section : Switch to next page is not working

[D4C-6317](https://decisyon.atlassian.net/browse/D4C-6317) DUMBELLA readinessprobe failure

[D4C-6312](https://decisyon.atlassian.net/browse/D4C-6312) Error restoring default image on Page/Application

[D4C-6311](https://decisyon.atlassian.net/browse/D4C-6311) DB connections that probably are not closed (PostgreSQL)

[D4C-6308](https://decisyon.atlassian.net/browse/D4C-6308) Wrong Label on Application edit dialog

[D4C-6305](https://decisyon.atlassian.net/browse/D4C-6305) Chart not rendered again if the previous dataset was empty

[D4C-6304](https://decisyon.atlassian.net/browse/D4C-6304) Chart "Pareto" enlarges the page

[D4C-6290](https://decisyon.atlassian.net/browse/D4C-6290) Migrate Custom total dialog on report contextual menù to Angular Material

[D4C-6286](https://decisyon.atlassian.net/browse/D4C-6286) Close-on-execution-success function on an execute object

[D4C-6279](https://decisyon.atlassian.net/browse/D4C-6279) Edit of old schedules on Roast version

[D4C-6272](https://decisyon.atlassian.net/browse/D4C-6272) Chart value is not rendered if null value are input in data grid

[D4C-6268](https://decisyon.atlassian.net/browse/D4C-6268) Error on ROAST deploy

[D4C-6236](https://decisyon.atlassian.net/browse/D4C-6236) SQL Parser fails when the word "from" is used in a db function - SQL Report

[D4C-6230](https://decisyon.atlassian.net/browse/D4C-6230) Fix workspace attributes dependencies on user craetion/modify dialog

[D4C-6226](https://decisyon.atlassian.net/browse/D4C-6226) Response time in the user administration page is very long since last update

[D4C-6212](https://decisyon.atlassian.net/browse/D4C-6212) Impossible to create an user : "Username exists" but doesn't appear in any lists

[D4C-6198](https://decisyon.atlassian.net/browse/D4C-6198) Widgets built with widget designer rendered also if the mandatory param is empty

[D4C-6179](https://decisyon.atlassian.net/browse/D4C-6179) Delete a parameter in the page, Pre-selection values are not updated

[D4C-6143](https://decisyon.atlassian.net/browse/D4C-6143) Z-index of error dialog from DT is wrong

[D4C-6112](https://decisyon.atlassian.net/browse/D4C-6112) Console error after login: "The transition has been superseded by..."

[D4C-5887](https://decisyon.atlassian.net/browse/D4C-5887) Console errors on DAC operations

[D4C-5837](https://decisyon.atlassian.net/browse/D4C-5837) Parameters in pre-selection are interpreted only when apply-type=default

[D4C-5758](https://decisyon.atlassian.net/browse/D4C-5758) Rule with SQL action raise exception

[D4C-5697](https://decisyon.atlassian.net/browse/D4C-5697) SQL Query report configured on datasource rest with variables does not require setting on these variables

[D4C-5365](https://decisyon.atlassian.net/browse/D4C-5365) Parameter used in read-description-formula doesn't open param dialog in report editor

[D4C-5364](https://decisyon.atlassian.net/browse/D4C-5364) Parameter used in description formula of a level are not interpreted

[D4C-4935](https://decisyon.atlassian.net/browse/D4C-4935) Debug info of page has higher z-index of signal dialog

[D4C-4867](https://decisyon.atlassian.net/browse/D4C-4867) Timezone NO set in the DS after a new metadata installation

[D4C-4405](https://decisyon.atlassian.net/browse/D4C-4405) Delete signal from internal hamburg menù, with modal window "old style", opened it wrongly

[D4C-4093](https://decisyon.atlassian.net/browse/D4C-4093) Dialog opened in drill and contextual menù dialog

[D4C-3353](https://decisyon.atlassian.net/browse/D4C-3353) SQL Parser fails when using subselect and UNION ALL - SQL Report

[D4C-3344](https://decisyon.atlassian.net/browse/D4C-3344) Report execution fails when the word "from" is used in a db function - OLAP report

### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Quackmore.**

[D4C-6414](https://decisyon.atlassian.net/browse/D4C-6414) Improve efficiency of WebDshManager's methods for loading Pages

[D4C-6397](https://decisyon.atlassian.net/browse/D4C-6397) Add indexes on metadata tables

[D4C-6378](https://decisyon.atlassian.net/browse/D4C-6378) Expose "appcomposer.context" properties to set context as configurable settings in the Helm Chart

[D4C-6372](https://decisyon.atlassian.net/browse/D4C-6372) Show the landing page as home page when using the Api Gateway

[D4C-6313](https://decisyon.atlassian.net/browse/D4C-6313) Manage concurrent delete on FT\_OBJECT\_EXECUTION

[D4C-6287](https://decisyon.atlassian.net/browse/D4C-6287) Update App Composer's Helm Chart

[D4C-6284](https://decisyon.atlassian.net/browse/D4C-6284) Creation and management of a service DAC token for Dumbella service

[D4C-6283](https://decisyon.atlassian.net/browse/D4C-6283) Creation and management of a service DAC token for Flowable service

[D4C-6282](https://decisyon.atlassian.net/browse/D4C-6282) Creation and management of a service DAC token for Gertrude service

[D4C-6258](https://decisyon.atlassian.net/browse/D4C-6258) Drop of temporary tables on multi pod architecture

[D4C-6254](https://decisyon.atlassian.net/browse/D4C-6254) Migrate 404 error dialog to Angular Material

[D4C-6238](https://decisyon.atlassian.net/browse/D4C-6238) See published widget in the widget catalog of widget designer

[D4C-6235](https://decisyon.atlassian.net/browse/D4C-6235) cURL on dumbella container for Healtcheck

[D4C-6211](https://decisyon.atlassian.net/browse/D4C-6211) Optimize the current application setting in the Page Routing engine

[D4C-6208](https://decisyon.atlassian.net/browse/D4C-6208) Move the edit of a task from Sidenav to Dialog

[D4C-6207](https://decisyon.atlassian.net/browse/D4C-6207) Move the edit of page and application from Sidenav to Dialog

[D4C-6188](https://decisyon.atlassian.net/browse/D4C-6188) Migrate the Dialogs from Jquery to Angular Material

[D4C-6183](https://decisyon.atlassian.net/browse/D4C-6183) Move the edit of an user from sidenav to dialog

[D4C-6142](https://decisyon.atlassian.net/browse/D4C-6142) Disable browser autocomplete on username and password on user creation dialog

[D4C-6140](https://decisyon.atlassian.net/browse/D4C-6140) Search box in the tenant dropdown

[D4C-6139](https://decisyon.atlassian.net/browse/D4C-6139) Autoselection of tenant in the user creation dialog

[D4C-6107](https://decisyon.atlassian.net/browse/D4C-6107) Migrate the Drill Trought Dialogs from Jquery to Angular Material

[D4C-6104](https://decisyon.atlassian.net/browse/D4C-6104) Separate angular's jquery-lite from the current jQuery version

[D4C-6101](https://decisyon.atlassian.net/browse/D4C-6101) Refactoring and Simplification of Timezone settings

[D4C-6070](https://decisyon.atlassian.net/browse/D4C-6070) Remove Drools code

[D4C-5879](https://decisyon.atlassian.net/browse/D4C-5879) Metric formatt ignored on charts tooltip

[D4C-5843](https://decisyon.atlassian.net/browse/D4C-5843) Remove 3 workspace properties

[D4C-5805](https://decisyon.atlassian.net/browse/D4C-5805) Widget designer - publish/unpublish widgets from the catalog

[D4C-5671](https://decisyon.atlassian.net/browse/D4C-5671) Param sorting on Api-params-mapping

[D4C-5658](https://decisyon.atlassian.net/browse/D4C-5658) Only one column editable on a read-only record

[D4C-5573](https://decisyon.atlassian.net/browse/D4C-5573) Automatic creation of authentication service in Design Studio

[D4C-3988](https://decisyon.atlassian.net/browse/D4C-3988) Use material design in the dialog of discussion removal

### Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

[D4C-6462](https://decisyon.atlassian.net/browse/D4C-6462) "Too many redirects" after logging in using HTTP instead of HTTPS

[D4C-6455](https://decisyon.atlassian.net/browse/D4C-6455) Browser cache of shared library is not invalidated

[D4C-6453](https://decisyon.atlassian.net/browse/D4C-6453) Pagination doesn't work in the People section

[D4C-6438](https://decisyon.atlassian.net/browse/D4C-6438) Error updating SQL Server metadata to Roast

[D4C-6437](https://decisyon.atlassian.net/browse/D4C-6437) Documentation for widgets does not open

[D4C-6435](https://decisyon.atlassian.net/browse/D4C-6435) Not possible to select file on Widget Designer >> Setting Deps

[D4C-6416](https://decisyon.atlassian.net/browse/D4C-6416) DISS - SIM1 - KPI Configuration by Line >> view by KPI "ERROR"

[D4C-6413](https://decisyon.atlassian.net/browse/D4C-6413) DISS - Department page error

[D4C-6412](https://decisyon.atlassian.net/browse/D4C-6412) DISS - Create Barrier error

[D4C-6401](https://decisyon.atlassian.net/browse/D4C-6401) \[Helm Chart] Liveness, Readiness and Startup probes don't have the context set

[D4C-6400](https://decisyon.atlassian.net/browse/D4C-6400) Smart grid widget executes reports twice

[D4C-6398](https://decisyon.atlassian.net/browse/D4C-6398) User Profile change password doens't check old password

[D4C-6396](https://decisyon.atlassian.net/browse/D4C-6396) 404 error opening a specific page

[D4C-6389](https://decisyon.atlassian.net/browse/D4C-6389) No context on favicon call

[D4C-6388](https://decisyon.atlassian.net/browse/D4C-6388) Column definition of editable report

[D4C-6386](https://decisyon.atlassian.net/browse/D4C-6386) Error opening a page, using relative path

[D4C-6385](https://decisyon.atlassian.net/browse/D4C-6385) Error reading Report property read-only-columns when never changed on old report

[D4C-6383](https://decisyon.atlassian.net/browse/D4C-6383) Console Error on user change password on User Profile

[D4C-6382](https://decisyon.atlassian.net/browse/D4C-6382) 404 error opening Rest API documentation

[D4C-6379](https://decisyon.atlassian.net/browse/D4C-6379) 404 error opening a Widget element code in external page

[D4C-6377](https://decisyon.atlassian.net/browse/D4C-6377) Img not found sorting a report column

[D4C-6376](https://decisyon.atlassian.net/browse/D4C-6376) Console Error moving a task on taskboard

[D4C-6374](https://decisyon.atlassian.net/browse/D4C-6374) \[Security] Impossible to export in CSV due to security validation

[D4C-6373](https://decisyon.atlassian.net/browse/D4C-6373) New Report Editor show an empty executed report

[D4C-6365](https://decisyon.atlassian.net/browse/D4C-6365) \[Security] Exception on drill through opening

[D4C-6362](https://decisyon.atlassian.net/browse/D4C-6362) Console error on page opening on widget Datetime picker

[D4C-6360](https://decisyon.atlassian.net/browse/D4C-6360) User editing and password definition

[D4C-6359](https://decisyon.atlassian.net/browse/D4C-6359) Debug info opening on a page

[D4C-6358](https://decisyon.atlassian.net/browse/D4C-6358) New user not associated to Everyone

[D4C-6353](https://decisyon.atlassian.net/browse/D4C-6353) Main toolbar show on page's embed link refresh

[D4C-6352](https://decisyon.atlassian.net/browse/D4C-6352) Wrong path loading when "Totals Definition"

[D4C-6351](https://decisyon.atlassian.net/browse/D4C-6351) Console error on User Side Nav opening

[D4C-6350](https://decisyon.atlassian.net/browse/D4C-6350) No file downloaded on CSV, PDF, Print for report

[D4C-6349](https://decisyon.atlassian.net/browse/D4C-6349) Error on drill context menù opening

[D4C-6347](https://decisyon.atlassian.net/browse/D4C-6347) White Label Error when "Totals Definition"

[D4C-6346](https://decisyon.atlassian.net/browse/D4C-6346) 404 Error adding metric or level to a report

[D4C-6342](https://decisyon.atlassian.net/browse/D4C-6342) Widget designer section refresh

[D4C-6341](https://decisyon.atlassian.net/browse/D4C-6341) API user creatio of a user with no timezone doesn't work

[D4C-6337](https://decisyon.atlassian.net/browse/D4C-6337) DS Cluster leader management on multipod environment

[D4C-6336](https://decisyon.atlassian.net/browse/D4C-6336) Pensil icon on Taskboard

[D4C-6335](https://decisyon.atlassian.net/browse/D4C-6335) Task card highlighted when side nav closed

[D4C-6334](https://decisyon.atlassian.net/browse/D4C-6334) Task side bar not refreshed on priority changes

[D4C-6333](https://decisyon.atlassian.net/browse/D4C-6333) Error Opening Report Catalogue on DS

[D4C-6330](https://decisyon.atlassian.net/browse/D4C-6330) Access denied to dimension when executing report

[D4C-6327](https://decisyon.atlassian.net/browse/D4C-6327) Error on javascript function execution

[D4C-6318](https://decisyon.atlassian.net/browse/D4C-6318) User administration section : Switch to next page is not working

[D4C-6317](https://decisyon.atlassian.net/browse/D4C-6317) DUMBELLA readinessprobe failure

[D4C-6312](https://decisyon.atlassian.net/browse/D4C-6312) Error restoring default image on Page/Application

[D4C-6311](https://decisyon.atlassian.net/browse/D4C-6311) DB connections that probably are not closed (PostgreSQL)

[D4C-6308](https://decisyon.atlassian.net/browse/D4C-6308) Wrong Label on Application edit dialog

[D4C-6305](https://decisyon.atlassian.net/browse/D4C-6305) Chart not rendered again if the previous dataset was empty

[D4C-6304](https://decisyon.atlassian.net/browse/D4C-6304) Chart "Pareto" enlarges the page

[D4C-6290](https://decisyon.atlassian.net/browse/D4C-6290) Migrate Custom total dialog on report contextual menù to Angular Material

[D4C-6286](https://decisyon.atlassian.net/browse/D4C-6286) Close-on-execution-success function on an execute object

[D4C-6279](https://decisyon.atlassian.net/browse/D4C-6279) Edit of old schedules on Roast version

[D4C-6272](https://decisyon.atlassian.net/browse/D4C-6272) Chart value is not rendered if null value are input in data grid

[D4C-6268](https://decisyon.atlassian.net/browse/D4C-6268) Error on ROAST deploy

[D4C-6236](https://decisyon.atlassian.net/browse/D4C-6236) SQL Parser fails when the word "from" is used in a db function - SQL Report

[D4C-6230](https://decisyon.atlassian.net/browse/D4C-6230) Fix workspace attributes dependencies on user craetion/modify dialog

[D4C-6226](https://decisyon.atlassian.net/browse/D4C-6226) Response time in the user administration page is very long since last update

[D4C-6212](https://decisyon.atlassian.net/browse/D4C-6212) Impossible to create an user : "Username exists" but doesn't appear in any lists

[D4C-6198](https://decisyon.atlassian.net/browse/D4C-6198) Widgets built with widget designer rendered also if the mandatory param is empty

[D4C-6179](https://decisyon.atlassian.net/browse/D4C-6179) Delete a parameter in the page, Pre-selection values are not updated

[D4C-6143](https://decisyon.atlassian.net/browse/D4C-6143) Z-index of error dialog from DT is wrong

[D4C-6112](https://decisyon.atlassian.net/browse/D4C-6112) Console error after login: "The transition has been superseded by..."

[D4C-5887](https://decisyon.atlassian.net/browse/D4C-5887) Console errors on DAC operations

[D4C-5837](https://decisyon.atlassian.net/browse/D4C-5837) Parameters in pre-selection are interpreted only when apply-type=default

[D4C-5758](https://decisyon.atlassian.net/browse/D4C-5758) Rule with SQL action raise exception

[D4C-5697](https://decisyon.atlassian.net/browse/D4C-5697) SQL Query report configured on datasource rest with variables does not require setting on these variables

[D4C-5365](https://decisyon.atlassian.net/browse/D4C-5365) Parameter used in read-description-formula doesn't open param dialog in report editor

[D4C-5364](https://decisyon.atlassian.net/browse/D4C-5364) Parameter used in description formula of a level are not interpreted

[D4C-4935](https://decisyon.atlassian.net/browse/D4C-4935) Debug info of page has higher z-index of signal dialog

[D4C-4867](https://decisyon.atlassian.net/browse/D4C-4867) Timezone NO set in the DS after a new metadata installation

[D4C-4405](https://decisyon.atlassian.net/browse/D4C-4405) Delete signal from internal hamburg menù, with modal window "old style", opened it wrongly

[D4C-4093](https://decisyon.atlassian.net/browse/D4C-4093) Dialog opened in drill and contextual menù dialog

[D4C-3353](https://decisyon.atlassian.net/browse/D4C-3353) SQL Parser fails when using subselect and UNION ALL - SQL Report

[D4C-3344](https://decisyon.atlassian.net/browse/D4C-3344) Report execution fails when the word "from" is used in a db function - OLAP report

### Deprecation <a href="#deprecation" id="deprecation"></a>

This section of the Change Log, updated to the DAC **2021.3.0** version, provides a list of the deprecated functions, i.e. functions which are started to be abandoned in the DAC Platform. The FUNCTION GUARANTEED UNTIL VERSION column of the table in the following paragraph shows the release until which the function will be guaranteed; this means that, if a function is guaranteed until version 5.4, the function is guaranteed on the version prior to 5.4 and all its patches 5.4.x but it is potentially removable by Decisyon starting from version 5.5.0.

&#x20;

| DESCRIPTION                                                                           | IMPACT                                                                                                                                                                                                     | ALTERNATIVE CONFIGURATION                                                                                                                                                                                                                                                                                                          | FUNCTION GUARANTEED UNTIL VERSION |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------- |
|                                                                                       |                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                                                                                    |                                   |
| Removal the **Social Space** in the RunTime.                                          | <p>It will no longer be possible to use the <strong>Social Spaces</strong>, their widgets and any other related function.</p><p>They will be replace by a more flexible technology in future releases.</p> | In case it will affect features already available in a production environment please contact your account in Decisyon.                                                                                                                                                                                                             | 2022.2                            |
| Removal the widget **Tag Cloud** in the widget catalog of Page Designer.              | It will no longer be possible to use the **Tag Cloud** widget in the Page Designer.                                                                                                                        | The alternative solution will be to create the same widget as a custom widget using widget designer. In case it will affect features already available in a production environment please contact your account in Decisyon.                                                                                                        | 2022.2                            |
| Removal the **Signal** in the **RunTime.**                                            | It will no longer be possible to use the **Signal in the Run Time**                                                                                                                                        | <p>No alternative will be provided.</p><p>In case it will affect features already available in a production environment please contact your account in Decisyon</p>                                                                                                                                                                | 2022.2                            |
| Removal "**Indicator Designer**" and its widget "**Indicator**" in the Page Designer. | It will no longer be possible to use the **Indicator Designer** and its **widget "Indicator"..**                                                                                                           | <p>The alternative solution will be to create the same widget as a custom widget using widget designer or waiting that Decisyon will progressively replace the object with new dedicated widgets.</p><p>In case it will affect features already available in a production environment please contact your account in Decisyon.</p> | 2022.2                            |
