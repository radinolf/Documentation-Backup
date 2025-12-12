# Version  6.3

### New Features Introduced <a href="#new-features-introduced" id="new-features-introduced"></a>

‌

This section of the Change Log provides a list of the new requirements implemented in version Jalapeño‌

* **D4C-4539 Consume POST endpoint in REST/JSON data source:** Ability to select the method GET or Post in the REST/JSON datasource. It’s also possible to insert the body of the request if POST method selected. The parameters can be use within the body of the request
* **D4C-4617 Enhance the UI of the sections when no content is available:** The user interface of several sections has been improved, when content is not available for connected users.

‌

### Enhancements Introduced <a href="#enhancements-introduced" id="enhancements-introduced"></a>

‌

This section of the Change Log provides a list of the new enhancements implemented in version Jalapeño‌

* **D4C-4583 Use proprietary opaque Token for REST Api:** Now the user, on his user profile, can generate a token that must be used to perform actions that need authorization and/or authentication, e.g. DAC’s REST Api invocation. User can set the expiration time of the token, and can choose the scopes the token contains.
* **D4C-4325 Integrate KeyCloak IODC Server:** Now KeyCloak OIDC Server has been integrated.
* **D4C-4586 Replace Flyway with Liquibase:** Flyway han been replaced with Liquibase for database refactoring.
* **D4C-4620 Run App Composer on MSSQL:** Now it’s possible to run App Composer on MSSQL database.
* **D4C-4621 Connect Design Studio to MSSQL metadata:** Now it’s possible to connect the Design Studio to MSSQL metadata

‌

### Fixed Defects <a href="#fixed-defects" id="fixed-defects"></a>

‌

This section of the Change Log provides a list of the defects solved.‌

**D4C-4657** Crosstab’s Excel and CSV export create corrupted file‌

**D4C-4708** Error when mapping Levels with Recursive Hierarchy (Parent-Child)‌

**D4C-4694** Error reading Widget’s resources‌

**D4C-4703** Session expired creating an alert‌

**D4C-4276** Wrong icon color in the taskboard search field‌

**D4C-4481** \[Azure] Everyone in the space as assignee of the task has showed an error, clicking from space’s area widgets‌

**D4C-4638** Alert log notification are not deleted together with alert log rows‌

**D4C-4658** “Whitelabel Error Page” when creating a new metric from web report editor‌

**D4C-4690** Administrator Menu (Web) disappears when user language is changed‌

**D4C-4695** Error retriving sample content from POST rest api datasource‌

**D4C-4696** Wrong data using %ACCESS\_TOKEN% key word on REST/JSON datasource‌

**D4C-4697** Impossible to add new label‌

### Removed Features​ <a href="#removed-features" id="removed-features"></a>

‌

**This section of the Change Log provides a list of features removed by Decisyon in version Jalapeño**‌

There are no component removals for this version‌

### Known Issue <a href="#known-issue" id="known-issue"></a>

‌

**This section of the Change Log provides a list of known anomalies that are going to be fixed in the next releases. For some of them, there are workarounds to be applied. Please, contact Decisyon Support Team if the reported anomalies affect one of your applications**

| **Activity ID** | **Description**                                                                                                                                                              | **Workaround**                                         |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| **D4C-4736**    | Opening more than one authenticated session in more than one tab in a browser causes the expiring of all the sessions, which result in the disconnection of the logged user. | Open a single session authenticated, in a browser tab. |
