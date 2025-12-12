# Fix Defect

This section lists bugs that have been resolved. Each fix improves the stability and reliability of the platform.

**DACXX-848: A user with 'Organization Administration' scope is able to Delete an organization even if he does not belong to that organization**\
Fixed a security flaw allowing users with the “Organization Administration” scope to delete organizations to which they were not assigned. The API endpoint for deleting organizations (v2/v3) now validates user-organization association, ensuring that only authorized users can perform such operations.

**DACXX-1410**: **Fix GroupCache @Cache annotations**\
Resolved an improper application of `@Cacheable` annotations on interface definitions instead of concrete classes, as required by SonarCloud rule S7180. The annotations have been refactored into implementing classes to ensure proper caching behavior and framework compatibility.

**DACXX-1453: "revokeTermsOfUsePrivileges's" @Transactional requirement is incompatible with the one for this method**\
Corrected an issue in `TermsOfUseServiceImpl.java` where transactional behavior was being bypassed due to method calls within the same class. The transactional annotation `@Transactional` was not effectively applied because it was invoked via `this`, outside the Spring proxy context. Refactored the code to enforce proper transaction propagation and avoid potential data inconsistencies.

**DACXX-1499**: **Exception Raised While Uploading CSV Files in File Upload and File Manager Widgets**\
Fixed an issue that prevented CSV file uploads due to MIME type and encoding mismatches. The validation logic now uses metadata hints and accepted character sets to determine valid file formats. This ensures consistent and error-free uploads, especially in production environments.

**DACXX-1552**: **Export in CSV of a report with a level set with custom ordering - column**\
Resolved an issue where exporting a report to CSV included unintended extra columns due to the “custom ordering” configuration in a dimension. The fix ensures that only explicitly defined columns are exported, improving CSV accuracy and reducing confusion for end users.

