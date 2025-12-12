# How to create a Data Source on Relational Database

In the example, we will show you how to create a data source using a relational database. This is a basic example, and you can customize it according to your specific needs.

**Prerequisites**

To complete the example, make sure you have:

1. A PostgreSQL available
2. The connection parameter to the database
3. Design Studio is able to reach the database

**Step 1: Create a data source on PostgreSQL**

Assuming you have a PostgreSQL database with a table named `Employees` containing columns such as id, `name`, and `salary`.

<figure><img src="../../../../.gitbook/assets/image (1938).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can use these scripts to replicate the example in your database.
{% endhint %}

```sql
-- Create Employees table
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    salary DECIMAL(10, 2)
);
-- Insert sample data
INSERT INTO employees (name, salary) VALUES
    ('John Doe', 50000.00),
    ('Jane Smith', 60000.00),
    ('Bob Johnson', 75000.00);
```

**Step 2: Create a Data Source on App Composer**

<figure><img src="../../../../.gitbook/assets/image (1939).png" alt=""><figcaption></figcaption></figure>

1. Open Design Studio and login
2. From the toolbar, select Tools >> Data source.
3. Select "New."
4. Select PosgtreSQL as database type
5. Input the connection details:
   * **Login**: \<database useranme>
   * **Password**: \<database user password>
   * **Server:** < The address or hostname of the server you are connecting to>
   * **Port (Porta):** \<Port number through which the connection to the database server takes place.
   * **Database:** \<database name>
6. Input an [Alias ](https://documentation.decisyon.com/documentation/report/visualization-and-formatting/aliases)name
7. Save Data Source

**Step 3: Create a SQL Report**

You can now create a simple [report](../../../report/) to read data from data source. From the Design Studio toolbar select the New Report Icon

<figure><img src="../../../../.gitbook/assets/image (1940).png" alt=""><figcaption></figcaption></figure>

1. Select the SQL tab.
2. Choose the PostgreSQL data source created earlier. Select "remote," and from the menu, choose the alias name of your datasource.
3. Use the SQL editor to write your query. For example:

```sql
SELECT 
id AS employee_id, 
name AS employee_name, 
salary AS employee_salary
FROM appcomposer.employees;
```

If you need more details on configuring an SQL report, please refer to the following documentation:

{% content-ref url="../../../report/sql-report.md" %}
[sql-report.md](../../../report/sql-report.md)
{% endcontent-ref %}

**Step 4: View the data**

Go back to editing the report by selecting the OLAP Tab at the bottom.

The Cube metrics created through the query, will have a different color.

<figure><img src="../../../../.gitbook/assets/image (1941).png" alt=""><figcaption></figcaption></figure>

Now, insert the levels into the report to view the data and exec the report.

This is the result.

<figure><img src="../../../../.gitbook/assets/image (1943).png" alt=""><figcaption></figcaption></figure>

