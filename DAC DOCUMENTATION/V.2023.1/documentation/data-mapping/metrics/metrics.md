---
description: How to create Metrics
---

# Metric Functions

You can apply more complex functions for both Advanced Metrics and Composite Metrics.

The functions are grouped into five families:

* Basic, for the simplest aggregation functions, such as sum, average, maximum, etc., applied however only to the data which respect the partitioning.
* Advanced, where functions with a certain complexity are collected, such as the top, bottom, rank, etc.
* Financial Group for calculating financial functions such as Cash Flow.
* Forecast for the functions which apply typical forecasting algorithms. The forecast group is subdivided in turn into **regression** and **time-series.**
* Window, where the present functions apply to a particular operation, such as aggregations or replacements, among the data belonging to a window, defined in the properties of each function.

To access the _**Metric functions**_ window, press the ![](<../../../.gitbook/assets/69 (3).png>) button.

![](<../../../.gitbook/assets/70 (4).png>)

The selected function is _**applied to a data set**_ defined in the [Pa](/broken/pages/-MfHs_PiXlCm3eSy1MKC#_Partizionamento)rtitionin&#x67;_._ _**The data set may also be**_ _**sorted**_ before applying the function (_Sorting setting)_.

For each function, some properties may be customized, in the section at the bottom left. The **Filter** group properties are always present for all of them:

* **loadingFilter** sets the Filter to be applied to the data used by the functio&#x6E;**.**
* **considerNull** specifies whether the function considers the null values or not (True is the predefined value).

### Partitioning

You define rules in partitioning according to which the system must segment the data, which the function will be applied to.

The selected function can be applied to a different partitioning than the one of the report. The partitioning of the report is defined by the dimensional levels chosen in it.

To define the partitioning, you initially establish whether to consider the report or not:

* in the **Default** field , _Partition_ considers report partitioning, and _No_ _Partition_ ignores it.

If the report is partitioned (_Default set to Partition_), you establish the levels at which partitioning is ignored.

If the partitioning of the report is ignored (_Default to No Partition_), the levels to which partitioning is applied are defined .

![](<../../../.gitbook/assets/71 (5).png>)

The partitioning on the dimensions is applied:

Subsequently the selection of the level/dimension may be assigned to each one of the two options: _Partition_ / _No Partition._

The next example explains the use of the partition.

Step 1: **Metric Partitioned by Month**

![](<../../../.gitbook/assets/74 (4).png>)

_Create the first metric called Order Qty Partition._

_Through the_ ![](<../../../.gitbook/assets/75 (5).png>)_button, access the window of the Metric Functions and select Sum function from the basic folder._

_Define partitioning for the Month dimensional level:_

* _Set by Default to No Partition_
* _Select the Month level from the_ ![](<../../../.gitbook/assets/76 (5).png>) _button_
* _Set the month level to Partition_

_Create a second Metric called Order Qty No Partition._

_Access the window of the Metric Functions and select Sum function from the basic folder._

_Define that the Metric will not be partitioned for any level by setting the Default to No Partition_**.**

Step 2: **Report with Partitioned and Non-partitioned Metric**

![](<../../../.gitbook/assets/77 (2).png>)

_Create_ _a report containing dimensional levels: Month and Category. For the metrics:_

* _First Level Metric: Order qty_
* _Metric partitioned by month (Sum function): Order Qty Partition_
* _Metric not partitioned (Sum function): Order Qty No Partition_

_The partitioned metric Order Qty Partition will partition the total value of the ordered quantities for the months 200601 and 200602_

_The Order Qty No Partition Metric that is not partitioned will indicate the total of the ordered quantities for all occurrences of the report._

Step 3: **Verifying Data**

![](<../../../.gitbook/assets/78 (4).png>)

_To check the data enter a total at row level. Note that for the first share of the data relating to the month 200601 the quantity equals 505,85Step 1: For the second portion relating to the month 200602, it equals 500,477. These values are reported in the Order Qty Partition partitioned Metric. The total quantities for the two months is 1,006,328. This value is calculated in the Order Qty No Partition Metric._

### Sorting

You can specify the levels and Metrics which are to be sorted in the Sorting pane of the _**Metric Function**_ screen. For each element added to the sorting, level or metric, it is possible to specify:

* **Type of sorting**: ascending or descending
* The **priority in the sorting**: i.e. the assessment order of the element in the sorting: -1 assigns to the element the predefined order in constructing the report. You can set values from -1 to 200.

![](<../../../.gitbook/assets/79 (3).png>)

## Advanced Operations

In the group of advanced functions are those of the calculation:

* best or worst values
* counter
* assigning a rank (Rank or Dense Rank)
* belonging to a tile directly or through a measure (NTile or NTile Size)

### Bottom and Top

The _**Bottom**_ function only displays the **last** n elements contained in the Metric that you are creating.

The value n is set in the _**Limit-number**_ propert&#x79;_**.**_ This property is enabled in the Property _Setting section_ at the time when it is selected.

The _**Top**_ property only displays the _**first**_ n elements, where n is set from the _**Limit-number**_ property _as_ in the _Bottom_ function.

### Counter

You _use_ the _**Counter**_ function for TOP(n) or BOTTOM(n) type calculations or to calculate the best/worst value from among the records. It counts the record (sequential number) relative to the start of the partition. Therefore, the value is applied to the valued record.

Step 1: **Counter Function**

![](<../../../.gitbook/assets/80 (2).png>)

_In the following figure an example is shown of using the Advanced Order QtyTopN metric in which the Counter function of the advanced group with descending sorting by OrderQtySum was applied and with no partitioning. The example report analyzes the order quantities relating to product categories 01 and 02 for the first 6 months of 2006._

_The Order Qty TopN metric counts the data set, assigning to each row a sorted sequence calculated based on the descending order of the base metric ORDER\_QTY\_Sum. Therefore, for April 2005 for product category 01 the highest number of orders was made; while for February 2006 for product category 02 the lowest number of orders was made._

Step 2: **Example of Advanced Metric with Counter Function and Partitioned**

![](<../../../.gitbook/assets/81 (1).png>)

_In the following figure an example is shown of using the Advanced OrderQtyTopN\_P metric in which the Counter function of the advanced group with descending sorting by Order\_QtySum and with partitioning for the Month level._

_The example report analyzes the order quantities relating to product categories 01 and 02 for the first 6 months of 2006. The OrderQtyTopN\_P Metric counts the data set for all months and assigns each row with a sorted sequence calculated based on the descending order of the OrderQty\_Sum base Metric. Thus, the highest number of orders was made in April 2006 for product category 01 and the lowest number of orders was for product category 02. The highest number of orders was made in January 2006 for product category 02 and the lowest number of orders was made for product category 01._

### Rank and Dense Rank

These functions provide the resulting rank compared to the other values of the metric, both starting from the highest values and the lowest values, according to the sorting type chosen for the metric.

The difference between the two functions is the numbering from where to restart counting which finds elements with the same value (therefore with the same rank):

* the **Dense Rank** restarts from the next number (or from the next rank)
* the **Rank** continues from the actual number of positions where the data is.

The example in the figure shows these two cases.

![](<../../../.gitbook/assets/82 (3).png>)

_The following figure shows you an example of how to use the Advanced Rank Sales and Dense Rank Sales Metrics. The Rank and Dense Rank functions were applied to them respectively. Both are set with descending sorting on the Sales\_Sum metric and with no partitioning._

Step 1: **Report Using the Rank and Dense Rank Functions**

![](<../../../.gitbook/assets/83 (4).png>)

_The QtyOrdiniRank metric calculates the ranking of the record compared to the sorted partition descending by Order Qty, skipping the ranks where more than one element has the same value._

_Thus, for March 2006 the same product was calculated for Product Family 10 and 13 since it is the same quantity of orders, but for April 2006 Product Family 03 was assigned a rank of 2 units higher despite it having a order quantity immediately lower than Product Family 13 in March 2006._

_The QtyOrdersDenseRank Metric calculates the ranking of the record relative to the decreasing sorted partition by Order Qty, and does not skip the rankings where more than one element have the same value. Therefore, the same ranking was calculated for the month of March 2006 for Product Families 10 and 13 because they have the same order quantity. For the month of April 2006, Product Family 03 was assigned a position immediately after Product Family 13 of the month of March 2006._

### Ntile

This divides the data set identified by the partition into Tiles (buckets, shares), with an equal number of elements as the value set in the NTileNumber property.

This property sets the number of elements per block.

![](<../../../.gitbook/assets/84 (3).png>)

| **Product** | **Qty** | **Ntile** |
| ----------- | ------- | --------- |
| PRODUCT1    | 100     | 1         |
| PRODUCT2    | 99      | 1         |
| PRODUCT3    | 96      | 2         |
| PRODUCT4    | 80      | 2         |
| PRODUCT5    | 70      | 3         |
| PRODUCT6    | 60      | 3         |

If you set the Ntile function to 2, you would obtain the results shown in the table.

The following figure is an example of how you can use the Advanced QtyOrdersTile Metric. The **NTile** function of the advancedgroup was applied to it with descending sorting by QTY\_ORDERS\_Sum and with no partitioning. The example report analyzes the order quantities relating to all the product categories for the first 6 months of 2006.

Step 1: **Report using NTile Functions**

![](<../../../.gitbook/assets/85 (4).png>)

_The QtyOrdiniTile metric subdivides the data set into blocks consisting of the number of elements indicated in the NTileNumber property of the same metric._

_In the example report (the number of elements per block was set to 5) the system sorts the data in a descending order for the QTA\_ORDINI\_Sum metric assigning to each row the related numbering._

### NTile Size

It subdivides the dataset identified by the partition, in Tile (bucket, shares), with a number of elements where the difference between the maximum value and minimum value is less than the Tile size value.

This function has the following properties:

* **NTileSize**: sets the number of units as the difference between the maximum and minimum value of the elements of a block.
* **extraElementPerTile:** sets an additional number of additional elements which will be considered as belonging to a block.
* **sum-tile-values:** calculates the blocks not based on the original values of the Metric but by previously applying a _running_ _sum_ function.

| **Product** | **Qty** | **NTile size** |
| ----------- | ------- | -------------- |
| PRODUCT1    | 100     | 1              |
| PRODUCT2    | 99      | 1              |
| PRODUCT3    | 96      | 1              |
| PRODUCT4    | 80      | 2              |
| PRODUCT5    | 70      | 3              |

The table shows the result obtained by setting the property NTile Tile size = 10

Please note that for Products 1, 2, 3 a value was associated equal to 1 since these three elements are not decreased by 10 units. The quantity is equal to 80 for Product 4. Therefore the Ntile Size function associates a new position (therefore a value equal to 2) because it decreased by 10 units relative to the previous values. The same situation occurs for PRODUCT5, which has a quantity decreased by 10 units relative to the previous value. In this case, the associated value will be 3 (new position).

The following figure shows an example of how to use the Advanced QtyOrdersNTile\_Size Metric. The **Ntile** **size** function of the advanced group was applied to it with descending sorting by QTY\_ORDERS\_Sum and with no partitioning.

Step 1: **Report with Metric on NTile Size**

![](<../../../.gitbook/assets/86 (3).png>)

_The example report analyzes the order quantities relating to all the product categories for the first 6 months of 2006._

_The QtyOrdiniNTile\_Size metric subdivides the data set into blocks whose elements have a difference between the maximum and minimum value lower than the one indicated in the NTileSize property of the same metric. In the example report (the difference between the maximum and minimum value of the elements of a block was set to 20 units) the system sorts the data in a descending order for the QTA\_ORDINI\_Sum metric by assigning the related numbering to each row._

### Custom Association

This function edits the value of the metric using in the place of the value normally calculated, the one which the metric assumes in the element specified by the association, defined through a SQL query. It has a similar behavior to the time functions.

To clarify this function, we have indicated the standard steps you must follow to create i.e. a Last Year time function.

The Last Year function is an association between a day of the year and the respective one of the previous year. If you were to define the LY function with Custom Association, you would perform the following operations:

1. if there isn’t already one, construct a table (which you will call LK\_ASSOCIATION\_LY) with two fields, one for the day (ID\_DAY) and the other for the day of the previous year (ID\_DAY\_LY)

**Note:** _The table fields must be numeric._

1. the day level is associated with the function level (**levelAssociated**) (which points for example to the table LK\_DATE, column DAY\_ID)
2. write the **sql-formula** for the association that must follow the function (SELECT ID\_DAY, ID\_DAY\_LY FROM LK\_ASSOCIATION\_LY)

![SNAGHTMLc1a1a4](<../../../.gitbook/assets/87 (4).png>)

Each time you use a metric defined as in the example, the metric will be valued not with the value calculated for the day in the report, but with the value which the metric assumes in the association day (e.g.: in the day “2006/01/01” the value of the metric assumed on the day “2005/01/01” will be present).

If the association returns several values, the value of the Metric will be given by the sum of all the values that the Metric assumes in the corresponding elements of the association.

In the next example you have the detail for the creation of a metric which uses a function of this type, relating to the calculation of the running sum of the sales from the beginning of the month to the day in question (this function coincides with the Month to date, Time functions section)

Step 1: **Creating a Table**

![](<../../../.gitbook/assets/88 (3).png>)

_Construct on the database a table like the one created in the figure, where for each day (ID\_DAY) all the previous days (in ID\_DAY\_MTD) for that month are associated (e.g. for 6 feb 2007 is associated with ID\_DAY\_MTD, from 1 feb 2007 to the same day)._

Step 2: **Metric with Custom Association**

![](../../../.gitbook/assets/89.png)

v

_Perform the operations summarized in the figure: create a new metric called Sales Month Beginning. Select the Custom association function in the advanced folder. In the levelAssociated property, select the DAY level (TIME Dimension) that coincides with the one of the table created. Write an sql-formula query._

Step 3: **Metric with Custom Association**

![](<../../../.gitbook/assets/90 (3).png>)

Now generate a report for the sales analysis from the start of the month, compared to the Business Unit. The result is shown in the figure. Please note that the DAY level must be in the repor&#x74;_._

## Forecasting Functions

DAC provides a series of forecasting functions which cover a broad range of standard data trends. Once you have identified the best forecasting function to represent the trend of the measure in question, you can apply it to the measure itself by setting the:

* period of history, characterized by the period for which you have the observation data available
* forecast period, up to where you want to extend the calculation for the forecast data.

You can define time intervals in a fixed or dynamic mode, depending on the current period. By entering a dynamic time interval for the historical data, you have the ability to perform a _rolling forecast_.

The forecast functions are applied by selecting them from the _**Metric Function**_ window, under the _**forecast**_ folder; they are subdivided into two groups:

* **Regression**: which introduce forecasting forms, where linear and non-linear functions approximate the trend of the entire forecast according to parameters _**a**_ and _**b**_, as a function of time _**t**_**.**;

Parameters _**a**_ and _**b**_ are estimated using the method of least squares, which minimizes the deviations between the actual and estimated value. The estimate is performed on the historical data. The available functions are:

*
  * Linear
  * Logarithmic
  * Exponential
  * Quadratic
* **Time-series**: where the functions apply forecasting techniques characterized by smoothing constants ranging between 0 and 1. These assign an exponentially decreasing weight to the observations as they become older. The _smoothing_ constants are:
* **α** for the series level
* **β** for the series trend, which applications the increasing or decreasing trend of the series
* **γ** for the seasonality

If invalid parameters are entered, the system automatically reports the parameters with their default value (0.5).

The available functions are:

*
  * Moving average
  * Single exponential smoothing
  * Double exponential smoothing
  * Triple Exponential Smoothing (_**Holt Winters**_) with multiplicative type seasonality
*
  * Last Actual

Before you apply a forecasting function, you can remove the seasonality effect in the historical series using a Filter that uses a moving average.

This option is requested when you enable the **deseasonalize** property. You define the amplitude of the calculation window for the moving average in the **seasonal-period** parameter, which indicates the seasonality in the historical series. For example, if the data is monthly the seasonality is 12.

Both properties are present for all forecasting functions in the _Forecast_ group.

### Historical and Forecast Period

Before you establish the time intervals for the historical and forecast period, you must set the _**time level**_ to apply the forecasting function to (monthly, weekly, daily, etc.).

In the **data-level** property (_Forecast_ group) select the calculation time level, among the time type dimensional levels.

With the **outer-join** property, you can activate/deactivate the outer-join of the chosen time level.

The time level selected enables the following properties for defining the historical and forecast intervals:

* **start-period-type** is the initial historical period (in some cases also initial forecast period)
* **end-period-type is** the end of the historical period
* **final-period-type** is the forecast time horizon. The starting point for the forecast depends on the functions applied: for some it is the start of the historical period, for others the end.

In each of the properties related to details of the intervals (_**start-period-type, end-period-type, final-period-type**_) it is established whether the period must be valued in a mode that is:

* **FIXED** (_\<Value>_), by indicating the period in the **period-value** property

The format must be the one of the time level chosen in _**data-level**_ and indicated here.

![](../../../.gitbook/assets/91.png).

This format respects the one set in the property of the _**level-type**_ dimensional level, during the dimension _creation phase (_&#x73;ee _Dimensions, chap._)

* **DYNAMIC** (_\<Dynamic bucket>_), indicating the number of events to be added to the current period, in the **bucket-shift** property

In **zero-ext-periods** it is established whether to put 0 at all the values external to the forecast interval.

### Linear Regression

The linear regression calculates the estimate in linear terms. The result is a straight line. The applied formula is as follows:

![](<../../../.gitbook/assets/92 (3).png>)

### Exponential Regression

The exponential regression is a non linear technique which follows a trend of the curve in an exponential manner. The applied formula is as follows:

![](<../../../.gitbook/assets/93 (3).png>)

### Logarithmic Regression

The logarithmic regression is a non linear function, particularly suitable when the historical period presents a logarithmic trend. The applied formula is as follows:

![](<../../../.gitbook/assets/94 (2).png>)

### Quadratic Regression

Quadratic regression is a non-linear function, which estimates the forecast with a quadratic trend. The applied formula is as follows:

![](<../../../.gitbook/assets/95 (3).png>)

### Moving Average

The moving average produces the value in an instant as average of the _p_ previous values. It is suitable for short-term forecasts. The applied formula is as follows:

![](<../../../.gitbook/assets/96 (1).png>)

Set the value p of the amplitude of the calculation interval for the moving average in the **window-amplitude** property.

Step 1: **Moving AVG Metric**

![](<../../../.gitbook/assets/97 (4).png>)

_Create a new advanced metric on the sold value (as sum) and apply the Moving Average function metric._

_The calculation time level is the month (date-level:MONTH)._

_The historical period is January 2005-January 2006 (start-period-type--end-period-type)._

_The forecast goes up to January 2008 (final-period-type)._

_The amplitude on which the moving average is calculated is 12 months (window-amplitude): i.e. each value is calculated on the average of the previous 12 months._

Step 2: **Moving AVG Metric**

![](../../../.gitbook/assets/98.png)

_You want the report to display the monthly trend of the sold value, both as historical (Val Sold-orange line Metric) and as forecast (FC\_Moving\_AVG-blue line Metric) data. From January 2006 the graph of the forecast is obtained._

### Single Exponential Smoothing

This forecasting technique produces an exponentially weighted moving average, in which each calculation is dependent on all the previous observations.

It is especially suitable for short-term forecasts and for data which does not show seasonality or trends.

The expected value in the next period Ft+1 (where _t_ represents the actual time) is calculated as a weighted average between the current value Yt and the forecast value Ft of the actual period (time _t_). The formula is as follows:

![](<../../../.gitbook/assets/99 (3).png>)

The parameter attributes more or less importance to the previous observation rather than the past data.

By assigning to a value close to 0, greater importance is given to the past values: the value expected is calculated recursively compared to the previous period, until reaching the first value available in the historical series.

By convention this is put at the same value as the first of the historical series (F0=Y1).

In contrast, a value of close to 1 places greater weight on the previous period, while the past data has a lower weight.

### Double Exponential Smoothing

This forecasting technique produces an exponentially weighted moving average, in which each calculation is dependent both on the previous observations and the trend. It is particularly suitable for historical series which show a trend, but not a seasonality.

The value expected in the next period Ft+1 is calculated as the sum of two components:

*
  * The component relating to the series level, calculated in a similar way to Single Exponential Smoothing
  * The component relating to the trend

The value at time _t+1_ is calculated as follows:

![](<../../../.gitbook/assets/100 (1).png>)

Where,

| ![](<../../../.gitbook/assets/101 (1).png>) | **Level** |
| ------------------------------------------- | --------- |
| ![](<../../../.gitbook/assets/102 (2).png>) | **Trend** |

The parameter β attributes a greater or lower weight to the trend in the last observations, rather than in the first.

Value β close to 1 gives greater weight to the most recent trend, while β close to 0 gives greater weight to the trend of the first observations.

The initialization values of the two components are:

![](../../../.gitbook/assets/103.png)

### Holt Winters

This forecasting technique produces a moving average, exponentially weighted, in which each calculation is dependent on the previous observations, the trend and the seasonality.

The value expected in the next period Ft+1 is a combination of three components:

*
  * The component relating to the _**level of**_ _**the series**_, calculated in a similar way to Single Exponential Smoothing ![](<../../../.gitbook/assets/104 (2).png>)
  * Except that the current value is _deseasonalized_ .
  * The component relating _**to the trend**_, calculated in a similar way to Double Exponential Smoothing
  * The component relating to the _**seasonality**_ of the series

The forecast at the time _t_+1 is:

![](<../../../.gitbook/assets/105 (2).png>)

where p indicates _the_ seasonality parameter and the updating equations of the three components are:

The parameter γ attributes a greater or lower weight to the seasonality in the last observations, rather than in the first.

The seasonality parameter is set in the **seasonal-period** property, i.e. the same property used to deseasonalize the historical data.

**IMPORTANT:** If you want to use this function properly, you must arrange a number of observations equal to a least twice the seasonality value. If, for example, you want to apply the function to a historical series with seasonality _p=_ 12 (monthly level data), it is necessary to have at least 12×2=24 observations available.

Since the formula is recursive, when you indicate seasonality with _p_ and the number of seasons available with _m_, the initialization parameters are calculated as:

which in turn is calculated as\
![](../../../.gitbook/assets/113.png)

Value represents the average of the season corresponding to index _t_, and _j_ is the position of period _t_ within the season.

Step 1: **Holt Winters Metric**

![](<../../../.gitbook/assets/114 (3).png>)

_Create a new advanced metric on the Sold Value of the cube Sales FC\_HOLT\_WINTERS:_

_Open the window for the Metrics function and select the HOLT WINTERS function (subfolder forecast>>time-series)_

_for data-level choose MONTH (this means that the metric will be applied to a monthly calculation)_

_Set the FIXED calculation period (\<Value>):_

*
  1. _start-period-type (period-value) - January 2005_
  2. _end-period-type (period-value) - January 2006_
  3. _final-period-type(period-value) – January 2020_

_therefore the calculation period is January 2005 – January 2006, while the application period is January 2005 – January 2020_

_creation of a report with the MONTH level and the two metrics:_

* _first level Val Venduto_
* _forecast Metric FC\_HOLT\_WINTERS_

Step 2: **The Historical Monthly Trend of the Sold Values and the Forecast Trend**

![](<../../../.gitbook/assets/115 (2).png>)

_The historical monthly trend of the sold values and the forecast trend, calculated with the new metric, are obtained. The forecasting metric in the first period approximates the historical period, while from January 2006 (end-period) you have the forecast of the sold value._

### Best Fit

The **Best Fit** function chooses among the _Linear Regression_, _Exponential Regression_, _Moving Average, Single Exponential Smoothing, Holt Winters_ algorithm&#x73;_, the_ one which has the lowest MAPE.

MAPE, _Mean Absolute Percentage_ _Error_, is a criterion with which the forecasting capacity of an algorithm is assessed and is defined as:

![](<../../../.gitbook/assets/116 (2).png>)

Where:

### Last Actual

The **Last Actual** function repeats the last value of the historical series for all the elements in the forecast period.

## Window Functions

The window functions apply a special operation (aggregations or replacements) among the data belonging to a window, defined in the properties of each function.

The functions that belong to this group are:

* Previous values
* Next values
* Aggregation of previous or next values
* Incremental sum
* Decrease in the sum
* Balance between income and outwards
* Data Shift

### Previous

It replaces the current value with the one of **n** previous positions, respecting the partition set.

The following are the properties relating to the Previous function:

* **windowPreceding**: specifies by how many backward positions, compared to the current value, the value to be replaced must be searched.
* **windowDefault** : default value to be applied should you not be able to identify the value of the moving window (Numeric)

### Next

It replaces the current value with the one of **n** previous positions, respecting the partition set.

* **windowFollowing**: specifies by how many positions following the current value, the value to be replaced must be searched (Numeric)
* **windowDefault**: default value to be applied should you not be able to identify the value of the moving window (Numeric)

The following figure is an example of how you can use the Advanced Sold\_NextSixMonths Metric to which the **Next** function of the group window was applied with partitioning for the Product level. The value 6 was set for the windowFollowing property.

Step 1: **Report Using the Next Function**

![](<../../../.gitbook/assets/117 (1).png>)

_The example report analyzes for each product the sales by year and month, and in addition for each month it analyzes the sales relating to next 6th month. Therefore, for January 2005 for product 77, the sales relating to the next 6th month are 219. You can verify this by observing the Val Sold Metric for July 2005._

### Windowing

This function allows you to perform calculations on the Report Data Set in a moving window. The function runs through the values of the partition. When calculating each element, it considers n previous elements and m next elements (variable amplitude of the window).

The calculated value, which is applied to the central element, is therefore the result of the aggregation (sum, average, minimum, etc.) of the values of the window.

* **windowAggregation**: Aggregation operation to be applied for the calculation \[aggregation types of the DBMS. Sum (Default)
* **windowFollowing**: Number of next elements considered in the calculation (Numeric)
* **windowPreceding**: Number of previous elements considered in the calculation (Numeric)
* **windowDefault**: Value to be applied if the value of the moving window is not present (Numeric).

The table below shows an example of using the **Windowing** function.

Create the Advanced **Sold\_WindowingAvg** Metric to which the **windowing** function is applied. Only partition the Product level.

The Avg value was set for the **windowAggregation** property. The value 1 was set for the **windowFollowing** and **windowPreceding** properties.

Step 1: **Report Using the Windowing Function**

![](<../../../.gitbook/assets/118 (1).png>)

_The example report analyzes for each product the sales by year and month, and in addition for each month it analyzes the result of the sales average compared to a time window which considers a previous month and a next month. Therefore, for February 2005 for product 77, the average sales is 282. This is calculated relative to a time window which considers the previous month (January 2005) and the next month (March 2005). In fact \[(238 + 147 + 462)/3] = 282,33._

### Running Sum

Calculates the incremental sum of the values of the current partition.

Step 1: **Report Using the Running Sum Function**

![](<../../../.gitbook/assets/119 (4).png>)

_In the following figure an example is shown of using the Advanced ValVenduto\_RunningSum metric to which the Running sum function of the window group with the partitioning by Year level and Product level was applied._

_The example report analyzes for each product the sales by year and month, and in addition for each month it analyzes the result of the progressive sum compared to the previous months. Thus, for March 2005 for product 77 the progressive sum of the sales is 847, calculated compared to the previous months, i.e. starting from January 2005. The result obtained is: (238 + 147 + 462) = 847._

### Running Decrease

The Running Decrease function is the opposite operation of Running Sum and de-accumulates the values progressively.

The **Running Decrease** function is among the functions of the **Window** group of the **Metric Function** section.

The example below shows an application of the Running Decrease function, and the comparison with the opposite or Running Sum function.

Example: Running Decrease Function

![](../../../.gitbook/assets/120.png)

_The example report analyzes the sales by year and month for all products._

_It analyzes the result of the progressive sum for all months relative to the previous months for the Running Sum._

_The example in in red the pane performs the following calculation:_

_the base metric is the Sales Val. If we add the first two rows together (4,880,330+1,655,037) the result for the Running Sum will be 6,535,367._

_While the Running Decrease performs the inverted operation i.e. it decreases the value compared the previous months._

_The example in green in the pane in green performs the following calculation:_

_the base Metric is the Sales Val. If you subtract the rows highlighted in green (6,716,302-4,880,334), the result for the Running Decrease is 1,831,968._

_The Running Sum and Running Decrease metrics are both partitioned for the Year and Product level._

### Closing Opening

The _Closing Opening_ function calculates the balance relative to income and outwards.

The **Closing opening** function is among the functions of the **Window** group of the **Metric Function** section.

The measure or Metric on which the function is applied will represent the _**initial balance value**_. The Metric containing the values relating to income and outwards are selected in the properties (_values group_):

* **toAddValue** for income
* **toSubstractValue** for the outwards

Below an example of applying the functions is shown.

Step 1: **Closing Opening Metric**

![](<../../../.gitbook/assets/121 (2).png>)

_The Closing Opening metric is defined in the following mode:_

* _Partitioned for the Product level_
* _Metric of the income in the toAddValue: Income property_
* _Metric of the outwards in the toSubtractValue: Outwards property_

Step 2: **Report with Closing Opening Function**

![](<../../../.gitbook/assets/122 (3).png>)

_The function is applied to a report with a detail level on the month and the product as maximum aggregation level. This is because the function is applied to a partition on the product. For each product you get:_

* _on the Income metric, the values related to the income._
* _on the Outwards Metric, the values relating to outwards._
* _on the Closing Opening Metric, the actual balance available for all months._

_The following calculation is applied to the Closing Opening Metric:_

_for the first month (July 2005) the balance is equal to the income because it has no previous month to be able to perform the calculation_

_The next month (August 2005) has a balance equal to € 848,275. The data are obtained from the following calculation:_

**((Closing Opening&#x20;**_**Last Month**_**)-(Outwards&#x20;**_**Last Month**_**))+(Income&#x20;**_**Last Month**_**))**

&#x20;_(429,801-14,327)+429,801=845,275_

### Data Shift

Data Shift replaces the current value, with a value of **n** previous or next positions, inside the partition, where the search for the value to be replaced must respect a time rule.

* **ruleDateFormat**: Format of the date according to Java specifications (Text)
* **levelAssociated**: Level considered when the time rule (Text) is calculated
* **dataShiftField**: Time element relative to which the search is to be performed YEAR (default); MONTH Day:
* **dataShiftNumber**: number of previous positions (in the case of a negative value) or next positions (in the case of a positive value) used to search for the value (Numeric)

The following figure is an example of how you use the Advanced Sold\_LastYearDataShift Metric to which the **Data shift** function of the group window was applied with partitioning for the Product level.

Step 1: **Report Using the Next Function**

![](../../../.gitbook/assets/123.png)

_The following properties are: ruleDateFormat = yyyyMM, levelAssociated = MONTH, dataShiftField = YEAR,_

_dataShiftNumber = -1. The example report analyzes the sales by year and month for all products. It also analyzes the sales for all months relating to the month of the previous year. Therefore, for January 2006 for product 77, the sales relating to the month of the previous year are 238. You can verify this by observing the Val Sold Metric for January 2005._

## Financial Functions

The financial functions in DAC calculate the collections and depreciation.

### Cash Flow

The _Cash Flow_ function allows you to divide a total value among the positions indicated in a specific dimensional level or Metric.

The **Cash** **Flow** function is among the **Financial** functions in the **Metric Function section.**

The values for the cash flow must therefore be saved in a table, on which the dimensional level or a measure of a cube will then be mapped.

These values must be separated by the character “**|**”. Each value will be interpreted as number of next positions where you must move the initial value. It was previously divided into just as many equal parts as the cash flows saved.

_For example, the cash flow_ **60|90|120** _will be interpreted as division of the initial value into 3 equal parts, moved to 60, 90, and 120 next positions from the initial value._

When the metric is applied to the report, you get a division in the positions indicated in the table: this implies that the level of detail of the report coincides with the one indicated in the cash flow.

The use of a dimensional level for the cash flow links the collection information to a particular dimension. For example, it is easy to set the cash flow for each product of the company: just enter an extra column in the dimensional table of the product and associate the corresponding cash flow to each product. This way, when you enter a product in a report, you will have the information relating to its cash flow. The cash flow metric will use it to present the collections of the product exactly in the period indicated in the level. The example below shows this specific application.

To apply the _Cash Flow_ function, you must:

1. save the cash flows in a field of a table
2. map the field as dimensional level or as measure of a cube
3. define the Metric with the **Cash Flow** function to the measure containing the value to be divided (e.g. turnover)
4. select the dimensional level or the Metric on the cash flow (defined in point 2)
5. from the **objectAssociateDSype** property set the object type: _LEVEL_ or _METRIC_
6. Depending on the type of object, you enable the corresponding property where you select the level (**level-associated**) or the Metric (**metric-associated**), which contains the information on the cash flow.

Step 1: **Cash Flow Function**

| **Product**   | **CashFlow** |
| ------------- | ------------ |
| **Product 1** | **0**        |
| **Product 2** | **3\|5**     |
| **Product 3** | **1\|6**     |

_The example shows a case where you have a different cash flow for each product sold. The collection times relative to the product are:_

_Product 1 has an immediate collection_

_Product 2 collects the first amount after three quarters and the second after 5_

_for Product 3 collects an amount after a quarter and the other after six_

_This information is saved in the product tables, where a column for the cash flow has been entered_

Step 2: Cash Flow Function

![](<../../../.gitbook/assets/124 (3).png>)

_Subsequently create the Cash\_Flow dimensional level on the Product dimension mappedon this new cash flow column. Now it is possible to define the metric for the Cash Flow, selecting the just created level: in objectAssociateDSype set the LEVEL item and in d levelAssociated associate the Cash\_Flow dimensional level_

Step 3: **Cash Flow Function**

![](<../../../.gitbook/assets/125 (1).png>)

_Create a report by entering the first level and advanced metrics, which the cashflow was applied to. The Total Collection First Level Metric represents the initial value. The Cash Flow Value Advanced Metric will show the initial value moved by the positions indicated in the Cash Flow dimensional level._

_On the report therefore the level on the product and on the quarter will be entered, the latter as detail level._

_Also the level on the Cash Flow was entered, in a way to see the value of the cash flows._

_The division of the initial value was highlighted for each product:_

_Product_ _1 has a collection total equal to 1000 and a cash flow equal to 0, therefore it will be collected in the same quarter_

_Product 2 has a collection total equal to 5000 and a cash flow of 3|5: the division will take place on two amounts, respectively after 3 and 5 quarters after the collection one_

_Product 3 has a collection of 6000 and a cash flow of 1|6: the division will be moved after 1 and 6 quarters after the collection._

### Depreciation

The Depreciation function divides the total cost of an investment along a certain timescale.

The **Depreciation** function is among the functions of the **Financial** group of the **Metric Function** section.

The time period on which the initial value must be divided must be indicated in a dimensional level or a metric, which will be interpreted as number of elements, starting from the initial value, on which the same value must be divided.

_For example, a value of 10 will be interpreted as the division in the 10 next positions after the initial one, as detailed in the next example._

The use of a dimensional level for the depreciation links this value to a particular dimension, as explained for the cash flow.

To apply the _Depreciation_ function, you must:

1. save the depreciation in a field of a table
2. map the field as dimensional level or as measure of a cube
3. define the Metric with the **Depreciation** function to the measure containing the value to be divided (e.g. cost)
4. select the dimensional level or the metric on the depreciation (defined in point 2):

from the **objectAssociateDSype** property set the object type: _LEVEL_ or _METRIC_

according to the type of object, enable the corresponding property where you choose the level (**level-associated**) or the metric (**metric-associated**), which contain the information on the depreciation

When the metric is applied to the report you get a subdivision of the value of the total, in as many parts as indicated in the field in the table, relating to the depreciation. The detail level in the report must be the same as that set for depreciation (point 1 above).

_For example, if depreciation in the table is indicated for months, then you must have month as detail level in the report._

Example: **Depreciation Function**

![](<../../../.gitbook/assets/126 (3).png>)

_The example shows a different depreciation for each product sold. In addition the depreciation times must be calculated compared to the month: in particular for Product 10 you have a depreciation equal to 10._

_You save this information in the product table by entering a column for depreciation._

_Subsequently create the Depreciation dimensional level on the Product dimension, associated with the column (created previously)._

_Now you can define the Metric for dividing the investment according to the depreciation plan:_

* _the investment is associated with the measure of the total (Total Collection)_
* _the Depreciation dimensional level will be selected in the levelAssociated property_

_The report analyzes the depreciation distributed over time for product 10 (in page-by). In the report, month is entered as the last level, to have a coherent division with the information saved in the table. It is worth remembering that the system interprets the information on the Depreciation level in a position mode. Therefore, if the quarter level were present, the division would be compared to the latter (depreciation on 10 quarters)._

_For Product 10 the depreciation amount is equal to 10 months. The investment begins in April 2010. The depreciation amount is equal to Euro 600 a month, which will be subtracted over the next 10 months._

