# Migration notes

Welcome to the "Migration notes" section of DAC! Here you will find detailed information about migrations and updates required to transition from the previous version of the software to the latest version. The migration notes provide clear and precise instructions on how to handle changes in the software, including any modifications to data structure, features, or configurations. Please make sure to carefully read these notes before proceeding with the upgrade, so you can be prepared and able to perform a smooth migration and maximize your experience with the new version of the software.

### Dumbella Jobs <a href="#dumbella-jobs" id="dumbella-jobs"></a>

With the ticket 7177, where it had been reported an exception when a Dumbella Job was removed from the "Jobs Administration" section. Working on the solution has been refactor he logging of Dumbella, and this introduces a break changes when updating the version that requires you to drop/delete the log tables, losing all data.

If you need to keep that data, you need to create your own "**job\_audit\_event**" **backup** table.

&#x20;

### Microsoft SQL Server JDBC Drive 10 <a href="#microsoft-sql-server-jdbc-drive-10" id="microsoft-sql-server-jdbc-drive-10"></a>

{% embed url="https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.7-Release-Notes#microsoft-sql-server-jdbc-drive-10" %}

Spring Boot 2.7 has upgrade the MSSQL driver from v9 to v10. The updated driver now enables encryption by default which may break existing applications. You can read about the change in the "Breaking Changes" section of this article.



### Design Studio Connection

The recommended advice is to either install a trusted certificate on your server or update your JDBC connection URL to include **encrypt=false**.

<figure><img src="../../../.gitbook/assets/image (755).png" alt=""><figcaption></figcaption></figure>

&#x20;
