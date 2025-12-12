# Join Type

It is possible to combine data for metrics and dimensions in a report by defining the type of join to carry out for each element.

The _**metricsJoin**_ and _**dimensionsJoin**_ properties, found in the report editing window, in the section for the Join group, allow you to select the type of join to perform on basic metrics and dimensions of a report. The possible values are _Inner_ and _Outer_ . By default the system uses _**Outer Join**_ excludes rows containing null values.

The _**metricJoin**_ property allows users to apply the type of join on the basic metrics of the report, while _**dimensionsJoin**_ applies the join to dimensions.

The outer join between the metrics can only be implemented for databases supporting the syntax of outer join with the operator (+) (such as Oracle and SQL Server). The inner join allows you to recover only the levels for which the basic metric is valued. The operation of outer join instead allows users to recover also the levels for which the basic metric is not valued.

The _**allow-cartesian**_ property, if activated, allows users to enable execution of the report even if the latter generates, on execution, a cartesian.

See the example below of the use of the _**metricsJoin**_ property and of the _**dimensionsJoin**_ property.

Step 1: Dimensions in INNER Join

![](<../../../.gitbook/assets/11 (18).png>)

_Let’s assume we want to display the data for quantities sold of products 112-113-114-115 and 116 for month 200507. As you can see in the figure, only quantities sold for products 114 and 115, the only two valued, are displayed. This is due to the fact that the system automatically excludes NULL values inside the report because it uses by default the INNER JOIN on the dimensions._

Step 2: Dimensions in OUTER Join

![](<../../../.gitbook/assets/12 (7).png>)

_If we wanted to display products that have no quantity sold for the month 200507, we would just have to set the OUTER JOIN property on the dimension of the product._

Step 1: Metrics in INNER Join

![](<../../../.gitbook/assets/13 (7).png>)

&#x20;_Let’s assume we want to display the data for quantities sold of products 10-107-117 for year 2004. As we can see in the figure, only quantities sold for products 10, the only one valued, are displayed. This is due to the fact that the system automatically excludes NULL values inside the report because it uses by default the INNER JOIN on the metrics._

Step 2:Metrics in OUTER Join

![](<../../../.gitbook/assets/14 (6).png>)

_If we wanted to display even products with no inventory quantity for \[the month] the year 2004 , we would just set the OUTER JOIN property on the metrics for the budget and the \[inventory]._
