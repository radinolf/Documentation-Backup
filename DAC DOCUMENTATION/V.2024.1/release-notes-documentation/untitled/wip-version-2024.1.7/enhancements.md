# Enhancements

* **DACXX-1802 - Enhancement of the Page API to Support Arrays in the Request Body**\
  Extended the page event API to support ARRAY values in the request body. The involved endpoints now accept arrays such as `"operation_status": ["Success", "OK"]`, improving integration flexibility.
*   **DACXX-1780 - User Group Realignment During Login**\
    Introduced the ability to realign user groups at login based on OIDC claims, using new workspace-level properties. The solution implements two new properties (`enable-group-sync-on-login` and `deny-access-if-no-groups`) and a Spring parameter to specify the claim with group data.              See [the documentation for details](../../../documentation/instance-configuration/tools/preferences.md#web)                                                                                                                      The porperty `spring.security.oauth2.client.provider.keycloak.claim-as-groups` (string) specifies the name of the claim in the OIDC token that contains the list of groups associated with the user. Default value is `groups`.

    The installation guide include these new properties and their configuration methods.&#x20;
* **DACXX-1825: Improve Report's HTTP Endpoint Memory Footprint**\
  Optimized memory management for the HTTP endpoint responsible for report generation and delivery. The improvement reduces memory usage, lowers the risk of Out Of Memory errors in high-load environments, and enhances server scalability
*   **DACXX-1092 - Multilingual Labels – Modify the Constraints for Tag Creation**\
    All previous restrictions on tags have been removed: it is now possible to include spaces, special characters, and use names up to 100 characters in length. A new API endpoint (`PUT /api/v2/rest/languages/labels`) has been introduced that accepts the tag as a JSON string in the request body, while the previous endpoint using a `PathVariable` has been deprecated.

    [See Migration note documentation](migration-notes.md#multilanguage-labels)

{% hint style="danger" %}
The old endpoint will continue to work but is marked for future removal. See thte [Deprecation ](../../deprecations.md)document
{% endhint %}

* **DACXX-1886 Provide image URL in JSON when using Decisyon TAG IMG on levels/report**            Now the JSON response for the SmartGrid widget include the direct image URL when using the Decisyon TAG IMG on report levels
* **D4C-5532 Remove constraints to enable report editing**\
  SQL reports are now considered editable as long as custom queries for add, delete, and update are defined. The previous restriction was removed, and a warning is shown if required queries are missing, but it no longer blocks saving or SmartGrid integration.
* **D4C-6524 Allow column definition even when there are more levels in the column**\
  Column definitions are now supported even when reports include multiple levels or a mix of levels and metrics in the column area. This enhancement removes prior limitations, making Smart Grid layouts viable for complex reports and reducing reliance on the deprecated Crosstab widget. See the Smart Grid Documentation
* **D4C-9305 Allow App Developers to configure the number of decimal digits for metrics in SQL-based reports**\
  A new report property `metric-decimal-digit` was added to allow developers to define decimal precision for metrics in SQL reports. If unset, the system falls back to the `decimalPosition` of metric properties in the application, ensuring greater formatting control. See the [property ](../../../documentation/report/execution/post-execution-sql/sql-interactions.md)
* **D4C-10222 Redirect Snippet logs to a dedicated file**\
  Snippet logs are now written to a separate log file to improve debugging without cluttering `Decisyon.log`.  The pages POD now contains the file `Sinippet.log.`
* **D4C-10484 Test Parameters when running a Report in DS: exclude knowing variables.**\
  Design Studio was enhanced to skip requesting values for built-in parameters like `%MODEL_SCHEMA%` when running reports. This simplification avoids redundant prompts and improves the execution flow.
