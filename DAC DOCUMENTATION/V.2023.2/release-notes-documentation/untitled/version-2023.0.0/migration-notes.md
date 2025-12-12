# Migration notes

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
