# Requirements & Limitations

Creating and using data sources in App Composer is straightforward and transparent. However, there are certain limitations and constraints that need to be considered to avoid any issues or complications.

Here is a brief list of the se limitations and constraints:

* The connection can be impacted by firewalls and network configurations. It is crucial to ensure that the necessary ports are open and correctly configured. You must verify that the cluster where App Composer is deployed can reach the database server.
* The same data source is used for both the web application deployed in the cluster and Design Studio. This means that Design Studio also needs to be able to access the configured database server in order to execute reports successfully. It is common to face issues when security policies, network constraints, or routing prevent Design Studio from reaching the database server.
* Network latency can affect connection performance, especially if Design Studio, the cluster, and the database server are geographically distant or have intermediate layers like VPNs.
* Secure practices, such as encryption and proper authentication mechanisms, should be managed externally on the database server and configured appropriately when defining the data source in App Composer.
* In high-traffic applications, it is important to fine-tune the connection parameters to prevent resource exhaustion.
* Compatibility of JDBC drivers used by App Composer for specific database systems must be considered.
