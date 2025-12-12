# New Feature

**D4C-7196 SQL report shows decimal digits even when they are not in the db**

&#x20;SQL reports were displaying decimal digits even for database columns that appeared to contain whole numbers. This behavior was not a malfunction but rather due to the use of the `FLOAT` data type in the database for the affected column. To ensure values are displayed as whole numbers in reports, it's now recommended to use data types like `NUMERIC` (without scale) or `INTEGER` for the relevant columns in the database.
