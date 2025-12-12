# Fix Defect

This section lists bugs that have been resolved. Each fix improves the stability and reliability of the platform.



*   **DACXX-886 – Drill-through dialog title wrongly encoded with vi-VN and mr-IN**

    Fixed encoding issues for multilingual tags containing non-Western characters in drill-through dialog titles.
*   **DACXX-1255 – Incorrect direct access page URL copied from "Share Page"**

    The page ID is now correctly updated when navigating between pages before copying the direct access URL.
*   **DACXX-1541 – Page layout not reflowing properly when sidebar is reopened**

    Adjusted container configuration by applying overflow: auto to column containers to ensure correct resizing on complex page layouts when reopening the sidebar.
*   **DACXX-1721 – Search feature not working with Chinese and other non-Western characters in ‘Users Administration’**

    Updated search filters in the Users and Tasks sections to support Unicode characters.
*   **DACXX-2723 – Drill-through dialog title not translated for specific languages**

    Fixed an issue where drill-through titles using Kebab mode translation were not rendered correctly in Indian or Russian languages.
*   **DACXX-2724 – Application Import (UPDATE) stuck using ADP file created with different metadata**

    Resolved an issue that caused the import operation to hang when updating an application with an ADP file generated from a Control file belonging to different metadata.
*   **DACXX-2751 – Connection pool saturation when opening drill-through page with Talend job**

    Refactored thread-safe handling of page loading to prevent connection pool saturation during drill-through operations involving Talend jobs.
*   **DACXX-2784 – Error during widget synchronization on MS SQL Server metadata**

    Fixed connection handling during widget synchronization on MS SQL Server databases to ensure existing connections are reused, preventing metadata locks and synchronization freezes. Regression testing on other DBMS is recommended.
*   **DACXX-2858-ldap user first access issue** When an LDAP user attempted to log in to Pages for the first time, the system returned an error. The issue has been resolved — users can now access successfully on their first login attempt.

