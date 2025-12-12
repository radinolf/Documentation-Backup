# Migration Notes

## Multilanguage Labels

The legacy API endpoint for creating multilingual tags has been deprecated. Use the new endpoint that accepts the tag in the request body.

* Existing integrations using the **old API** path with {tag} parameter should be updated to use the new endpoint
  * **Deprecated API**:
    * **URL**: `/api/v2/rest/languages/tag/{tag}`
    * **Method**: PUT
    * **Description**: Old endpoint that uses path variable for tag creation
    * **Deprecation** Reason: The tag restrictions were removed to support all characters in multilanguage labels, making it inappropriate to include tags in the URL path
    * **Migration**: Users needs to switch to the new API that uses RequestBody
* Applications needs to migrate to the **new endpoint** to take advantage of the enhanced tag support features
  * **New API (Recommended)**:
    * **URL**: `/api/v2/rest/languages/labels`
    * **Method**: PUT
    * **Content-Type**: application/json
    * **Request Body:** Contains the tag as a string
    * **Description**: Creates a new business label with support for all characters including spaces and up to 100 characters in length.

{% hint style="danger" %}
&#x20;The old endpoint will continue to work but is marked for future removal. See thte [Deprecation ](../../deprecations.md)document
{% endhint %}

### Timeturner

**Added optional** `sqlserver` **Spring profile.**\
The `sqlserver` Spring profile is now mandatory in SQL Server environments for proper Quartz job store configuration.



