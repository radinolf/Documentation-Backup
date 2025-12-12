# Version 2022.1.4

## Version 2022.1.4 (Patch) - 04 Oct 2022

### Fixed Defects ​​ <a href="#fixed-defects" id="fixed-defects"></a>

**This section of the Change Log provides a list of the defects solved.**



[D4C-7490](https://decisyon.atlassian.net/browse/D4C-7490) Requested timed out due to POD not responding

Fixed the problem of displaying a red box instead of a widget.

&#x20;

<figure><img src="../../../.gitbook/assets/image (869).png" alt=""><figcaption></figcaption></figure>

### Deprecation <a href="#deprecation" id="deprecation"></a>

This section of the Change Log, updated to the DAC **2022.0.0** version, provides a list of the deprecated functions, i.e. functions which are started to be abandoned in the DAC Platform. The FUNCTION GUARANTEED UNTIL VERSION column of the table in the following paragraph shows the release until which the function will be guaranteed; this means that, if a function is guaranteed until version 5.4, the function is guaranteed on the version prior to 5.4 and all its patches 5.4.x but it is potentially removable by Decisyon starting from version 5.5.0.

&#x20;

| **DEPRECATION** | **IMPACT** | **ALTERNATIVE CONFIGURATION** | **FUNCTION GUARANTEED UNTIL VERSION** |
| --------------- | ---------- | ----------------------------- | ------------------------------------- |

| **DEPRECATION**                                                                                                                                                          | **IMPACT**                                                                                                                                                                                                                                                      | **ALTERNATIVE CONFIGURATION**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | **FUNCTION GUARANTEED UNTIL VERSION** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------- |
| Removal Java 11                                                                                                                                                          | Design Studio will no longer support java 11                                                                                                                                                                                                                    | <p>The jdk will be managed directly by the new installer, therefore the user will not have to perform any operation.<br><br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                         | 2022.1.0                              |
| ext\* Javascript function                                                                                                                                                | Deprecate all ext\* Javascript function accessible from the Page's Javascript object.                                                                                                                                                                           | In the function panel, the new function is indicated for each deprecated function.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | <p>2023.0.0</p><p> </p>               |
| <p>Widget SDK Api, leave Template and Target objects only.</p><p> </p>                                                                                                   | All the Widget SDK documentation which refer to the global DECISYON object are deprecated and will be removed. Refer to the [Decisyon API](https://dac.decisyon.net/docs/widget_sdk/index.html#/api_decisyon/@Introduction) documentation for next developments | <p>The new documentation is available on the Decision API tab in the Widget Designer documentation.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                                                          | <p>2023.0.0</p><p> </p>               |
| Widget [**Styled Selector**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                | It will no longer be possible to use the legacy widget "Styled Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | <p>Several new widgets will be distributed via Widget Hub and it replace each "style" of the legacy widget. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                           | 2021.3.0                              |
| Widget[ **Inner Container**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                | It will no longer be possible to use the legacy widget "Inner Container" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                                                                                                                                                                                                                                                                  | 2021.3.0                              |
| Widget [**Image**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                          | It will no longer be possible to use the legacy widget "Image" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                            | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                                                                                                                                                                                                                                                                  | 2021.3.0                              |
| Widget [Map](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                                | It will no longer be possible to use the legacy widget "Map" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                              | <p>A new "map" widget will be distributed via WidgeHub. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                               | 2021.3.0                              |
| Widget [Wizard](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                             | It will no longer be possible to use the legacy widget "Wizard" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                           | <p>A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                                   | 2021.3.0                              |
| Widget[ File Selector](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/bhu84cM46ITfHln35pSX/documentation/design-studio/page-widget/form#file-selector-file-selection)​ | It will no longer be possible to use the legacy widget "File Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                    | <p>A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                                   | 2021.3.0                              |
| Data Source XML                                                                                                                                                          | It will no longer be possible to use the data source "XML". In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                                                     | No alternative configuration will be provided.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | 2022.3.0                              |
| api/rest/{application}/report/{id}).                                                                                                                                     | It will no longer be possible to use the API                                                                                                                                                                                                                    | <p>A New API is available:</p><p>api/v2/rest/{application}/report/{id}</p><p>Include (by default) information about the report's properties (task and annotation-enabled, column definition, edit grants and delete message), cell's decorations (drill, task) and data. Information about the report and cells now includes the writable and read-only flags.</p><p>It's possible to exclude any of those to retrieve a minimal set of data using the query string parameter "exclude" (possible values are: "drill","span","decorations","properties" and "data").</p> |                                       |

&#x20;

## Version 2022.1.3 (Patch) - 21 Sept 2022

### Enhancements Introduced <a href="#enhancements-introduced" id="enhancements-introduced"></a>

**This section of the Change Log provides a list of the new enhancements implemented**

[D4C-7428](https://decisyon.atlassian.net/browse/D4C-7428) Downporting D4C-6933 - Get report metadata (column definition, drill through etc)

**Solution :** A new REST endpoint has been added **api/v2/rest/{application}/report/{id}**, which deprecates _api/rest/{application}/report/{id})_.

It include (by default) information about the report's properties:

* task and annotation-enabled,
* column definition,
* edit grants and delete message
* cell's decorations (drill, task) and data.
* Information about the report and cells now includes the writable and read-only flags.
* It's possible to exclude any of those to retrieve a minimal set of data using the query string parameter "exclude" (possible values are: "drill","span","decorations","properties" and "data").

This is an example how to invoke it:&#x20;

https://host:port/api/v2/rest/application/{application}/report/{id}/\
to only retrive report's data.



### Fixed Defects ​​ <a href="#fixed-defects" id="fixed-defects"></a>

**This section of the Change Log provides a list of the defects solved.**

[D4C-7454](https://decisyon.atlassian.net/browse/D4C-7454) Download DAC from an existing Web Application, open a page with an error message.

[D4C-7436](https://decisyon.atlassian.net/browse/D4C-7436) Errors filtering users by User Attribute

[D4C-7425](https://decisyon.atlassian.net/browse/D4C-7425) data not exported if a report (SQL or OLAP) has HTML code associated to

[D4C-7347](https://decisyon.atlassian.net/browse/D4C-7347) Metric is not editable on the datagrid when the read-only filter is applied

[D4C-7333](https://decisyon.atlassian.net/browse/D4C-7333) Too many CLOSE\_WAIT connection in a K8S POD&#x20;

[D4C-7330](https://decisyon.atlassian.net/browse/D4C-7330) User Administration : department attribute isn’t filtered by plant attribute on user edit

&#x20;

### Deprecation <a href="#deprecation" id="deprecation"></a>

This section of the Change Log, updated to the DAC **2022.0.0** version, provides a list of the deprecated functions, i.e. functions which are started to be abandoned in the DAC Platform. The FUNCTION GUARANTEED UNTIL VERSION column of the table in the following paragraph shows the release until which the function will be guaranteed; this means that, if a function is guaranteed until version 5.4, the function is guaranteed on the version prior to 5.4 and all its patches 5.4.x but it is potentially removable by Decisyon starting from version 5.5.0.

&#x20;

| **DEPRECATION**                                                                                                                                                          | **IMPACT**                                                                                                                                                                                                                                                      | **ALTERNATIVE CONFIGURATION**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | **FUNCTION GUARANTEED UNTIL VERSION** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------- |
| Removal Java 11                                                                                                                                                          | Design Studio will no longer support java 11                                                                                                                                                                                                                    | <p>The jdk will be managed directly by the new installer, therefore the user will not have to perform any operation.<br><br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                         | 2022.1.0                              |
| ext\* Javascript function                                                                                                                                                | Deprecate all ext\* Javascript function accessible from the Page's Javascript object.                                                                                                                                                                           | In the function panel, the new function is indicated for each deprecated function.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | <p>2023.0.0</p><p> </p>               |
| <p>Widget SDK Api, leave Template and Target objects only.</p><p> </p>                                                                                                   | All the Widget SDK documentation which refer to the global DECISYON object are deprecated and will be removed. Refer to the [Decisyon API](https://dac.decisyon.net/docs/widget_sdk/index.html#/api_decisyon/@Introduction) documentation for next developments | <p>The new documentation is available on the Decision API tab in the Widget Designer documentation.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                                                          | <p>2023.0.0</p><p> </p>               |
| Widget [**Styled Selector**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                | It will no longer be possible to use the legacy widget "Styled Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | <p>Several new widgets will be distributed via Widget Hub and it replace each "style" of the legacy widget. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                           | 2021.3.0                              |
| Widget[ **Inner Container**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                | It will no longer be possible to use the legacy widget "Inner Container" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                                                                                                                                                                                                                                                                  | 2021.3.0                              |
| Widget [**Image**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                          | It will no longer be possible to use the legacy widget "Image" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                            | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                                                                                                                                                                                                                                                                  | 2021.3.0                              |
| Widget [Map](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                                | It will no longer be possible to use the legacy widget "Map" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                              | <p>A new "map" widget will be distributed via WidgeHub. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                               | 2021.3.0                              |
| Widget [Wizard](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                             | It will no longer be possible to use the legacy widget "Wizard" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                           | <p>A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                                   | 2021.3.0                              |
| Widget[ File Selector](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/bhu84cM46ITfHln35pSX/documentation/design-studio/page-widget/form#file-selector-file-selection)​ | It will no longer be possible to use the legacy widget "File Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                    | <p>A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.</p><p> </p>                                                                                                                                                                                                                                                                                                                                                                                                                                   | 2021.3.0                              |
| Data Source XML                                                                                                                                                          | It will no longer be possible to use the data source "XML". In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                                                     | No alternative configuration will be provided.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | 2022.3.0                              |
| api/rest/{application}/report/{id}).                                                                                                                                     | It will no longer be possible to use the API                                                                                                                                                                                                                    | <p>A New API is available:</p><p>api/v2/rest/{application}/report/{id}</p><p>Include (by default) information about the report's properties (task and annotation-enabled, column definition, edit grants and delete message), cell's decorations (drill, task) and data. Information about the report and cells now includes the writable and read-only flags.</p><p>It's possible to exclude any of those to retrieve a minimal set of data using the query string parameter "exclude" (possible values are: "drill","span","decorations","properties" and "data").</p> |                                       |

&#x20;

## Version 2022.1.1 (Patch) - 16 May 2022

### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Quackmore.**

[D4C-7085](https://decisyon.atlassian.net/browse/D4C-7085) Widget Hub enabled by default

[D4C-7042](https://decisyon.atlassian.net/browse/D4C-7042) Default must not be enabled by default on user creation for the attributes

### &#x20;Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

[D4C-7071](https://decisyon.atlassian.net/browse/D4C-7071) The discussion widget is not visible for some users after version upgrade

[D4C-7070](https://decisyon.atlassian.net/browse/D4C-7070) Export report in CSV from Data Grid not executed

[D4C-7063](https://decisyon.atlassian.net/browse/D4C-7063) Default Value displayed in error after creation

[D4C-7059](https://decisyon.atlassian.net/browse/D4C-7059) Page display error box when opening

[D4C-7057](https://decisyon.atlassian.net/browse/D4C-7057) Multilanguage tag not applied in the body of a crosstab

[D4C-7053](https://decisyon.atlassian.net/browse/D4C-7053) New folder on widget editor doesn't work

[D4C-7052](https://decisyon.atlassian.net/browse/D4C-7052) Labels not traslated for metric on Crosstab

[D4C-7040](https://decisyon.atlassian.net/browse/D4C-7040) Crosstab widget now allows to remove metric - Regression bug

[D4C-7019](https://decisyon.atlassian.net/browse/D4C-7019) Wrong Items name on Widget Designer

[D4C-6875](https://decisyon.atlassian.net/browse/D4C-6875) Exception "EDTPR018 Exception found when loading the report. kpi\_value\_Sum" when opening a page

[D4C-6475](https://decisyon.atlassian.net/browse/D4C-6475) Error 'Code: EDTPR000 Unexpected error. For input string: "44L" ' while displaying a smartgrid

[D4C-6288](https://decisyon.atlassian.net/browse/D4C-6288) Necessary restart of the Design Studio when publishing a widget

&#x20;

### Deprecation

This section of the Change Log, updated to the DAC  version, provides a list of the deprecated functions, i.e. functions which are started to be abandoned in the DAC Platform. The FUNCTION GUARANTEED UNTIL VERSION column of the table in the following paragraph shows the release until which the function will be guaranteed; this means that, if a function is guaranteed until version 5.4, the function is guaranteed on the version prior to 5.4 and all its patches 5.4.x but it is potentially removable by Decisyon starting from version 5.5.0.

&#x20;

| **DEPRECATION**                                                                                                                                                          | **IMPACT**                                                                                                                                                                                                                                                      | **ALTERNATIVE CONFIGURATION**                                                                                                                                                                     | **FUNCTION GUARANTEED UNTIL VERSION** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| Removal Java 11                                                                                                                                                          | Design Studio will no longer support java 11                                                                                                                                                                                                                    | <p>The jdk will be managed directly by the new installer, therefore the user will not have to perform any operation.<br></p>                                                                      | 2022.1.0                              |
| ext\* Javascript function                                                                                                                                                | Deprecate all ext\* Javascript function accessible from the Page's Javascript object.                                                                                                                                                                           | In the function panel, the new function is indicated for each deprecated function.                                                                                                                | <p>2023.0.0</p><p> </p>               |
| <p>Widget SDK Api, leave Template and Target objects only.</p><p><br></p>                                                                                                | All the Widget SDK documentation which refer to the global DECISYON object are deprecated and will be removed. Refer to the [Decisyon API](https://dac.decisyon.net/docs/widget_sdk/index.html#/api_decisyon/@Introduction) documentation for next developments | <p>The new documentation is available on the Decision API tab in the Widget Designer documentation.</p><p><br></p>                                                                                | <p>2023.0.0</p><p><br></p>            |
| Widget [**Styled Selector**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                | It will no longer be possible to use the legacy widget "Styled Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | <p>Several new widgets will be distributed via Widget Hub and it replace each "style" of the legacy widget. Existing widgets in pages must be manually migrated to the new widget.</p><p><br></p> | 2021.3.0                              |
| Widget[ **Inner Container**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                | It will no longer be possible to use the legacy widget "Inner Container" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                           | 2021.3.0                              |
| Widget [**Image**](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                          | It will no longer be possible to use the legacy widget "Image" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                            | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                           | 2021.3.0                              |
| Widget [Map](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                                | It will no longer be possible to use the legacy widget "Map" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                              | <p>A new "map" widget will be distributed via WidgeHub. Existing widgets in pages must be manually migrated to the new widget.</p><p><br></p>                                                     | 2021.3.0                              |
| Widget [Wizard](https://decisyon.atlassian.net/wiki/spaces/~436823021/pages/2353496065/Change+Log+Version+2022.1.0+Theobald)                                             | It will no longer be possible to use the legacy widget "Wizard" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                           | <p>A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.</p><p><br></p>                                                         | 2021.3.0                              |
| Widget[ File Selector](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/bhu84cM46ITfHln35pSX/documentation/design-studio/page-widget/form#file-selector-file-selection)​ | It will no longer be possible to use the legacy widget "File Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                    | <p>A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.</p><p><br></p>                                                         | 2021.3.0                              |
| Data Source XML                                                                                                                                                          | It will no longer be possible to use the data source "XML". In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                                                     | No alternative configuration will be provided.                                                                                                                                                    | 2022.3.0                              |

## Version 2022.1.0 - 20 apr 2022

### New Features Introduced

**This section of the Change Log provides a list of the new requirements implemented in version Quackmore.**

[D4C-6911](https://decisyon.atlassian.net/browse/D4C-6911) Tenant dropdown menu improvements

[D4C-6733](https://decisyon.atlassian.net/browse/D4C-6733) REST API - Remove "user making the request" from tasks API

[D4C-6729](https://decisyon.atlassian.net/browse/D4C-6729) REST API - Remove "user making the request" from user's API

[D4C-6691](https://decisyon.atlassian.net/browse/D4C-6691) Upgrade Keycloak to fix CVE-2021-20195

[D4C-6670](https://decisyon.atlassian.net/browse/D4C-6670) Additional information in the metadata table ft\_user\_connection

[D4C-6649](https://decisyon.atlassian.net/browse/D4C-6649) \[Widgethub] Alert about widget used before deleting it

[D4C-6648](https://decisyon.atlassian.net/browse/D4C-6648) Display dependencies to app and pages

[D4C-6217](https://decisyon.atlassian.net/browse/D4C-6217) DAC Bearer token behind Gloo

[D4C-6216](https://decisyon.atlassian.net/browse/D4C-6216) User logout when behind Gloo

[D4C-5754](https://decisyon.atlassian.net/browse/D4C-5754) Manage concurrent execution of jobs in Dumbella

[D4C-5502](https://decisyon.atlassian.net/browse/D4C-5502) REST API - Remove "user making the request"

[D4C-3716](https://decisyon.atlassian.net/browse/D4C-3716) \[Widgethub] - Widget designer built in catalogue path target

### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Quackmore.**

[D4C-6949](https://decisyon.atlassian.net/browse/D4C-6949) Refactor Languages using Spring MessageSource

[D4C-6935](https://decisyon.atlassian.net/browse/D4C-6935) Removal of report property "visualizationPattern"

[D4C-6909](https://decisyon.atlassian.net/browse/D4C-6909) Remove HttpRequestForwarderServlet

[D4C-6908](https://decisyon.atlassian.net/browse/D4C-6908) The People API does not return the list sorted by name insensitive

[D4C-6897](https://decisyon.atlassian.net/browse/D4C-6897) \[Security] Upgrade xercesImp to prevent CVE-2022-23437

[D4C-6891](https://decisyon.atlassian.net/browse/D4C-6891) \[Security] Upgrade jdom to prevent CVE-2021-33813

[D4C-6866](https://decisyon.atlassian.net/browse/D4C-6866) User Management performance - Pagination of result and on Input Value List

[D4C-6865](https://decisyon.atlassian.net/browse/D4C-6865) User Management performance - Asynchronous loading of attributes

[D4C-6864](https://decisyon.atlassian.net/browse/D4C-6864) User Management performance - Input Value List executed when not necessary

[D4C-6861](https://decisyon.atlassian.net/browse/D4C-6861) Option to created disabled users on automatic user creation

[D4C-6847](https://decisyon.atlassian.net/browse/D4C-6847) \[Release Note] Deprecation of XML data source

[D4C-6844](https://decisyon.atlassian.net/browse/D4C-6844) \[Documentation] Enhancements and fixes to the "Data source" manual

[D4C-6836](https://decisyon.atlassian.net/browse/D4C-6836) Attribute Default Value

[D4C-6831](https://decisyon.atlassian.net/browse/D4C-6831) Logo crop does not work

[D4C-6824](https://decisyon.atlassian.net/browse/D4C-6824) \[Documentation] Env variable "server.servlet.context-path"

[D4C-6817](https://decisyon.atlassian.net/browse/D4C-6817) Rename Folder "Social Spaces"

[D4C-6814](https://decisyon.atlassian.net/browse/D4C-6814) Requests optimization - Page by resources

[D4C-6813](https://decisyon.atlassian.net/browse/D4C-6813) Requests optimization - Report resources

[D4C-6778](https://decisyon.atlassian.net/browse/D4C-6778) Upgrade Helm Chart for DataHub with Theobald

[D4C-6773](https://decisyon.atlassian.net/browse/D4C-6773) Remove the old Widget Designer

[D4C-6715](https://decisyon.atlassian.net/browse/D4C-6715) Change library for cropping images

[D4C-6710](https://decisyon.atlassian.net/browse/D4C-6710) Migrate from SpringFox to SpringDOC

[D4C-6709](https://decisyon.atlassian.net/browse/D4C-6709) Update SpringBoot to 2.6.x

[D4C-6705](https://decisyon.atlassian.net/browse/D4C-6705) Disable action bar by default on new page

[D4C-6704](https://decisyon.atlassian.net/browse/D4C-6704) Requests optimization - Widget discussion

[D4C-6703](https://decisyon.atlassian.net/browse/D4C-6703) Requests optimization - Action toolbar requests not triggered if toolbar disabled

[D4C-6700](https://decisyon.atlassian.net/browse/D4C-6700) Move DAC to Java17

[D4C-6697](https://decisyon.atlassian.net/browse/D4C-6697) Component, services and other reasource loaded twice

[D4C-6696](https://decisyon.atlassian.net/browse/D4C-6696) Minify CSS and JS

[D4C-6676](https://decisyon.atlassian.net/browse/D4C-6676) Additional information in the report.log

[D4C-6675](https://decisyon.atlassian.net/browse/D4C-6675) Display the server ip in the system\_env\_instances

[D4C-6569](https://decisyon.atlassian.net/browse/D4C-6569) Remove Bookmark

[D4C-6529](https://decisyon.atlassian.net/browse/D4C-6529) Remove Social Spaces

[D4C-6528](https://decisyon.atlassian.net/browse/D4C-6528) Removal of "Signals"

[D4C-6526](https://decisyon.atlassian.net/browse/D4C-6526) Removal of widget "Tag Cloud"

[D4C-6504](https://decisyon.atlassian.net/browse/D4C-6504) Mandatory param must be evaluated even if not used in the widget

[D4C-6470](https://decisyon.atlassian.net/browse/D4C-6470) Removal/Refactoring of drillThroughBridge

[D4C-6345](https://decisyon.atlassian.net/browse/D4C-6345) Direct/embed link with tenant selection

[D4C-6323](https://decisyon.atlassian.net/browse/D4C-6323) Replace Nashorn template engine with Feemarker

[D4C-6089](https://decisyon.atlassian.net/browse/D4C-6089) Use Pagination to display available users in the Alert Section

[D4C-6032](https://decisyon.atlassian.net/browse/D4C-6032) User Attribute Default value when mandatory

[D4C-5781](https://decisyon.atlassian.net/browse/D4C-5781) Parameter sorting on debug info of a page

[D4C-5556](https://decisyon.atlassian.net/browse/D4C-5556) Remove tika-parser as dependency

### Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

[D4C-6991](https://decisyon.atlassian.net/browse/D4C-6991) Widget JSON idVal is not correct only on the the last level

[D4C-6987](https://decisyon.atlassian.net/browse/D4C-6987) It is not possible tu pubblish WidgetHub Widget

[D4C-6980](https://decisyon.atlassian.net/browse/D4C-6980) Exception "EDTPR000: Unexpected error. Step by is incorrect for the range" raised on report execution

[D4C-6979](https://decisyon.atlassian.net/browse/D4C-6979) Export csv dialog doesn't close automatically

[D4C-6978](https://decisyon.atlassian.net/browse/D4C-6978) Missing search in the Tenant dropdown

[D4C-6977](https://decisyon.atlassian.net/browse/D4C-6977) En exception occurs importing a widget

[D4C-6976](https://decisyon.atlassian.net/browse/D4C-6976) Report's drill through settings are not properly applied when used in data grid widget

[D4C-6975](https://decisyon.atlassian.net/browse/D4C-6975) Dialog "Advanced sorting" of the data grid widget is not rendered

[D4C-6971](https://decisyon.atlassian.net/browse/D4C-6971) No dependencies available for HUB widget

[D4C-6970](https://decisyon.atlassian.net/browse/D4C-6970) Widget dependencies filters does not return any page

[D4C-6969](https://decisyon.atlassian.net/browse/D4C-6969) Widget dependency does not sort for Application ID

[D4C-6968](https://decisyon.atlassian.net/browse/D4C-6968) ERROR on OIDC DAC DS authentication

[D4C-6967](https://decisyon.atlassian.net/browse/D4C-6967) Custom labels not translated

[D4C-6965](https://decisyon.atlassian.net/browse/D4C-6965) Dialog opened by js function does not close

[D4C-6945](https://decisyon.atlassian.net/browse/D4C-6945) ERROR Opening My Documents section

[D4C-6929](https://decisyon.atlassian.net/browse/D4C-6929) Execute button configured on API Rest works discontinuously if the "javascript code before" run extSendParamChanged function

[D4C-6926](https://decisyon.atlassian.net/browse/D4C-6926) User Advanced search do not consider attribute with default value

[D4C-6924](https://decisyon.atlassian.net/browse/D4C-6924) Exception raised by REST API Client

[D4C-6922](https://decisyon.atlassian.net/browse/D4C-6922) Report List not sorted on User Attributer definition

[D4C-6920](https://decisyon.atlassian.net/browse/D4C-6920) Mandatory attribute with default value

[D4C-6915](https://decisyon.atlassian.net/browse/D4C-6915) Task creation with %SPACE% label

[D4C-6913](https://decisyon.atlassian.net/browse/D4C-6913) Page block Selecting a tab on a tab selector

[D4C-6912](https://decisyon.atlassian.net/browse/D4C-6912) \[DataHub] Wrong redirect url in the loading.jsp

[D4C-6910](https://decisyon.atlassian.net/browse/D4C-6910) Attach Task do not open Task dialog

[D4C-6880](https://decisyon.atlassian.net/browse/D4C-6880) Message not visible when wrong tenant on dirct link

[D4C-6878](https://decisyon.atlassian.net/browse/D4C-6878) \[ Grou Administration ] Group's menu voice 'Change folder' does not work

[D4C-6869](https://decisyon.atlassian.net/browse/D4C-6869) Tab not opened on first click ona a Tab Selector

[D4C-6863](https://decisyon.atlassian.net/browse/D4C-6863) Discussion attached to report

[D4C-6859](https://decisyon.atlassian.net/browse/D4C-6859) Logo label not found

[D4C-6857](https://decisyon.atlassian.net/browse/D4C-6857) Logo & colours section doesn't work properly

[D4C-6855](https://decisyon.atlassian.net/browse/D4C-6855) No editor available for CUBES and DIMENSIONS

[D4C-6839](https://decisyon.atlassian.net/browse/D4C-6839) Performance bottleneck when using drillThrough on a data grid widget

[D4C-6838](https://decisyon.atlassian.net/browse/D4C-6838) TASK Search for user does not work

[D4C-6833](https://decisyon.atlassian.net/browse/D4C-6833) Pages containing several nested containers with widgets open very slowly

[D4C-6830](https://decisyon.atlassian.net/browse/D4C-6830) Impossible to create alert due to SQL parser exception

[D4C-6829](https://decisyon.atlassian.net/browse/D4C-6829) No page's link available when show-social-functions active

[D4C-6828](https://decisyon.atlassian.net/browse/D4C-6828) Right click on report body does not open Contextual menu

[D4C-6827](https://decisyon.atlassian.net/browse/D4C-6827) Update Fusion Chart Key

[D4C-6820](https://decisyon.atlassian.net/browse/D4C-6820) LOGO\&COLORS not available

[D4C-6816](https://decisyon.atlassian.net/browse/D4C-6816) Loading DIV is not removed after action from execute button

[D4C-6810](https://decisyon.atlassian.net/browse/D4C-6810) Remove Social spaces folder

[D4C-6809](https://decisyon.atlassian.net/browse/D4C-6809) New page creation

[D4C-6800](https://decisyon.atlassian.net/browse/D4C-6800) Widget not automatically published when upgraded from whub

[D4C-6799](https://decisyon.atlassian.net/browse/D4C-6799) User profile - unable to set default image

[D4C-6797](https://decisyon.atlassian.net/browse/D4C-6797) Javascript exception raised when saving users create before Roast

[D4C-6796](https://decisyon.atlassian.net/browse/D4C-6796) Widget Hub dialog aspect

[D4C-6792](https://decisyon.atlassian.net/browse/D4C-6792) Concurrent execution of the same job in Dumbella returns 503

[D4C-6790](https://decisyon.atlassian.net/browse/D4C-6790) Application customization-background image

[D4C-6783](https://decisyon.atlassian.net/browse/D4C-6783) Appcomposer crashes after few reloads of installed widgets

[D4C-6774](https://decisyon.atlassian.net/browse/D4C-6774) Landing page remains in loading if user doesn't have visibility on any app

[D4C-6757](https://decisyon.atlassian.net/browse/D4C-6757) Reports has one more execution than expected

[D4C-6728](https://decisyon.atlassian.net/browse/D4C-6728) Widget discussion raise exception when a mentioned users is deleted

[D4C-6725](https://decisyon.atlassian.net/browse/D4C-6725) DECISYON.utils.createTask opens the dialog with a different rendering of the "standard"

[D4C-6724](https://decisyon.atlassian.net/browse/D4C-6724) DECISYON.utils.openMessageDialog API open the old style dialog

[D4C-6644](https://decisyon.atlassian.net/browse/D4C-6644) Accented characters not syncronized

[D4C-6630](https://decisyon.atlassian.net/browse/D4C-6630) Empty column returned in the JSON of the smart grid data

[D4C-6595](https://decisyon.atlassian.net/browse/D4C-6595) Dumbella version 2021.3.0 and 2021.3.1 container doesn't start on App Service

[D4C-6395](https://decisyon.atlassian.net/browse/D4C-6395) Page-by empties itself when the value contains the char "+"

[D4C-6319](https://decisyon.atlassian.net/browse/D4C-6319) Page-by levels exported from reports are not correctly refreshed when reports contain no data

[D4C-5884](https://decisyon.atlassian.net/browse/D4C-5884) Application Deploy via file does not invalidate report cache

[D4C-5553](https://decisyon.atlassian.net/browse/D4C-5553) Error message in the Swagger documentation about tenant

[D4C-5552](https://decisyon.atlassian.net/browse/D4C-5552) Tenant API - HTTP 405 on DELETE tenant

[D4C-5551](https://decisyon.atlassian.net/browse/D4C-5551) Tenant API - HTTP 415 on GET tenant

[D4C-5517](https://decisyon.atlassian.net/browse/D4C-5517) The record with a description starting with "<" is not visible in the report

[D4C-4054](https://decisyon.atlassian.net/browse/D4C-4054) Label Tasks incoherent to the others among Filters in Recent Contents

[D4C-4019](https://decisyon.atlassian.net/browse/D4C-4019) Tasks label on Create-->Tasks sidebar

[D4C-3830](https://decisyon.atlassian.net/browse/D4C-3830) Wrong IT and EN labels while publishing/unpublishing a widget via widget designer.

[D4C-3806](https://decisyon.atlassian.net/browse/D4C-3806) \[Widgethub] - Widget installation conflict

### Deprecation

This section of the Change Log, updated to the DAC version, provides a list of the deprecated functions, i.e. functions which are started to be abandoned in the DAC Platform. The FUNCTION GUARANTEED UNTIL VERSION column of the table in the following paragraph shows the release until which the function will be guaranteed; this means that, if a function is guaranteed until version 5.4, the function is guaranteed on the version prior to 5.4 and all its patches 5.4.x but it is potentially removable by Decisyon starting from version 5.5.0.

| **DEPRECATION**                                                                                                                                                                                  | **IMPACT**                                                                                                                                                                                                                                                      | **ALTERNATIVE CONFIGURATION**                                                                                                                                                                                                                                                                                                      | **FUNCTION GUARANTEED UNTIL VERSION** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| Removal Java 11                                                                                                                                                                                  | Design Studio will no longer support java 11                                                                                                                                                                                                                    | The jdk will be managed directly by the new installer, therefore the user will not have to perform any operation.                                                                                                                                                                                                                  | Removed                               |
| ext\* Javascript function                                                                                                                                                                        | Deprecate all ext\* Javascript function accessible from the Page's Javascript object.                                                                                                                                                                           | In the function panel, the new function is indicated for each deprecated function.                                                                                                                                                                                                                                                 | 2023.0.0                              |
| Widget SDK Api, leave Template and Target objects only.                                                                                                                                          | All the Widget SDK documentation which refer to the global DECISYON object are deprecated and will be removed. Refer to the [Decisyon API](https://dac.decisyon.net/docs/widget_sdk/index.html#/api_decisyon/@Introduction) documentation for next developments | The new documentation is available on the Decision API tab in the Widget Designer documentation.                                                                                                                                                                                                                                   | 2023.0.0                              |
| Widget [**Styled Selector**](/broken/pages/RkIgpSHSW2zFy0chNe8E#styled-selector-deprecated)                                                                                                      | It will no longer be possible to use the legacy widget "Styled Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | Several new widgets will be distributed via Widget Hub and it replace each "style" of the legacy widget. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                    | 2022.3.0                              |
| Widget[ **Inner Container**](/broken/pages/FVCbXFc00Jofzi4PgVit#inner-container-deprecated)                                                                                                      | It will no longer be possible to use the legacy widget "Inner Container" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                  | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                            | 2022.3.0                              |
| Widget[ **Image**](/broken/pages/WSw0Y4pP5OtwvMmiRhtG#image-deprecated)                                                                                                                          | It will no longer be possible to use the legacy widget "Image" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                            | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                            | 2022.3.0                              |
| Widget [Map](/broken/pages/4L2M29U5QXnejTWJgLEn#map-deprecated)                                                                                                                                  | It will no longer be possible to use the legacy widget "Map" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                              | A new "map" widget will be distributed via WidgeHub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                        | 2022.3.0                              |
| Widget [Wizard](/broken/pages/FVCbXFc00Jofzi4PgVit#wizard-deprecated)                                                                                                                            | It will no longer be possible to use the legacy widget "Wizard" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                           | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                            | 2022.2.0                              |
| Widget [File Selector​](/broken/pages/RkIgpSHSW2zFy0chNe8E#file-selector-file-selection)                                                                                                         | It will no longer be possible to use the legacy widget "File Selector" in the page designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                    | A new widget will be distributed via Widget Hub. Existing widgets in pages must be manually migrated to the new widget.                                                                                                                                                                                                            | 2022.3.0                              |
| [Data Source XML](../../../documentation/application/data-source.md#data-source-for-xml-files-deprecated)                                                                                        | It will no longer be possible to use the data source "XML". In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                                                     | No alternative configuration will be provided.                                                                                                                                                                                                                                                                                     | 2022.2.0                              |
| Removal "[**Indicator Designer**](/broken/pages/-Mif3_XR_v92dY2ZMhrl)" and its widget "[**Indicator**](/broken/pages/4L2M29U5QXnejTWJgLEn#indicator-component-deprecated)" in the Page Designer. | It will no longer be possible to use the Indicator widget and Indicator Designer. In case the removal will affect features already available in a production environment please contact your account in Decisyon.                                               | <p>The alternative solution will be to create the same widget as a custom widget using widget designer or waiting that Decisyon will progressively replace the object with new dedicated widgets.</p><p>In case it will affect features already available in a production environment please contact your account in Decisyon.</p> | 2022.2.0                              |
|                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                 |                                                                                                                                                                                                                                                                                                                                    |                                       |



## Removal Feature <a href="#removal-feature" id="removal-feature"></a>

In this version are removed this object:

* Widget Tag Cloud
* Signals
* Social Spaces
* Bookmark
* Java 11
