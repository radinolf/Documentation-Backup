# Excel Like

## Excel-like Functions <a href="#toc498423816" id="toc498423816"></a>

In DAC you can analyze the data in a report by operating as an Excel sheet.

The system is able to perform highly complex mathematical operations with the help of some default functions.

You can apply the new function to the rows and columns, and call it from the **Custom Total** pop-up menu item. This defines a function that will then be inserted in the row immediately below and in the column immediately to the right.

![](../../../.gitbook/assets/0)

After selecting the _Custom Total-> Add custom Column_ property from the pop-up menu, the system automatically enables the box to insert a new total, from which you can construct the new formula. When a total is applied, the functionality to move rows or columns of the report is activated.

The section at the left shows the tree that contains functions applicable to the Custom Total.

The function tree is subdivided into four categories:

* Math Functions: contains mathematical formulas.
* Report Reference: contains the functions for the reference to data in the report.
* Sum Functions: contains the sum type functions applicable to cells, rows and columns.
* Conversion Functions: contains the conversion functions that may be used in case a formula is entered which uses java code. The numeric values displayed in the reports are of the “long” type.

![](<../../../.gitbook/assets/image (88).png>)

The formula of the total is defined in the area on the left. The name to be associated with the new total (**Name** section) is inserted in the upper section. The mathematical operators are available to build the formula (_**Math Operators**_ section).

The functions of the _Report Reference_ and _Sum Function_ group functions are applicable with absolute and relative reference:

* A relative reference _**(**&#x77;ithout notation $)_ is based on the relative position of the cell. If the position of the cell containing the formula changes, the reference also changes. For example, if you move a cell from position B3 to position B5, the system will automatically change the reference inside the formula.
* An absolute reference _**(**&#x77;ith notation $)_ always refers to the specific position of a cell. If the position of the cell containing the formula changes, the absolute reference will remain unchanged. Therefore, if you move the cell to the rows below or to the adjacent columns, the reference will not be adapted.

### Math Functions <a href="#toc498423817" id="toc498423817"></a>

The functions in the Math Functions category are strictly mathematical functions and are used for the These are used for calculation of complex formulas, such as calculation of the trigonometric functions, and are also used for simpler operations such as the search of a maximum or minimum number among a couple of numbers.

* **ABS:** Function to calculate the absolute value of a number.

Example: _ABS(4.28)=4 , ABS(-7)=7._

* **ATAN:** Function to calculate the arctangent angle.

Exampl&#x65;_: ATAN(0)=0°._

* **CQRT:** Function to calculate the cube root of a number.

Exampl&#x65;_: CQRT(27)=3._

* **EXP:** Function to calculate an E-base power (Euler's number equal to approximately 2.718).
* **FLOR:** Function to calculate the rounding off of the nearest lower integer (rounding down).
* **HYPOT:** Function to calculate the square root of the sum of squares.

Exampl&#x65;_: HYPOT(3,6)= SQRT(45) = 6.7._

* **LOG:** Calculation of the natural base logarithm of a number.

Exampl&#x65;_: LOG(10) = 2._

* **LOG10**_**:**_ Calculation of the 10-base logarithm of a number.

Exampl&#x65;_: LOG10(10) = 1_

* **MAX:** Calculation of maximum value between the two numbers.

Exampl&#x65;_: MAX(6,28) = 28 , MAX(1,-22) = 1]_

* MIN: Function to calculate the minimum value between the two numbers.

Example: MIN(6,28) = 6 , Min(1,-22) = -22.

* _**POW:**_ Function to calculate the (base) number raised to the exponent.

Exampl&#x65;_: POW(2,6) = 64._

* **REST:** Function to calculate the rest of the division between 2 numbers.

Exampl&#x65;_: REST(27,2)=1._

* **RINT:** Function to calculate the truncation to an integer.

Example: _RINT(6.01)=6 , RINT(12.86)=12_

* **ROUND:** Function to calculate the nearest integer (rounding up or down).

Exampl&#x65;_: ROUND(4.45)=4 , ROUND(6.52)=7._

* _**RANDOM:**_ Function to calculate a random decimal number between 0.0 and 1.0.
* _**SIGNUM:**_ Function that returns the +1 and -1 values based on the number sign.

Exampl&#x65;_: SIGNUM(44.6)=+1,SIGNUM(-62)=1._

* _**SQRT:**_ Function to calculate the square root of a positive number.

Example: _SQRT(100)=10._

* **TANH:** Function to calculate the hyperbolic tangent.

Exampl&#x65;_: TANH(0.6)=0.53._

You will be notified of any error that occurs during the calculation of the formula via a detailed message and the word “\[Err.]” inside the cell of the report.

Only the detail of the first error occurring will be displayed; after an additional adjustment of the formula, any other mismatches will be displayed (if present).

**Example of Using Math Functions**

This example shows how to use the mathematical function _**MIN**_ to calculate the minimum value between two numbers.

**Step 1: Using (x)MIN**

![](<../../../.gitbook/assets/2 (1)>)

_After creating the report, add a new total to the row level._

_Go to the row where you want to add the function, and with the right mouse button, enable the entry of the new total (Custom Total -> Add custom Column)._

Step 2: Using (x)MIN

![](<../../../.gitbook/assets/3 (5)>)

_The system enables the window to define the new total:_

* _enter the title in the Title section;_
* _select, in the Math Function section, the Min function;_
* _with a double click, select the two cells (Cell B2 and Cell B3)._

**Step 3: Using (x)MIN**

![](<../../../.gitbook/assets/4 (3)>)

_In the position where the total is entered, the system calculates the minimum number between the two values of the selected cells. The cells were formatted to highlight the total entered._

### Report References Functions <a href="#toc498423818" id="toc498423818"></a>

The functions in the Report References category contain all the functions that may be applied to the rows, columns and cells of the report. Functions with the notation “$” maintain the position through the absolute key.

* **CELL**: Finds the value of the cell on the indicated position which is specified by the column index and row index \[e.g.: CELL(B3)]. The position is maintained by the OLAP key.
* **CELL$:**&#x46;inds the value of the cell on the indicated position which is specified by the column index and row index \[e.g.: CELL$(B3)]. The position is maintained by the absolute key.
* **COL:** Finds the cell value on the specified column, in alphanumeric format. \[e.g.: COL(B)]. The position is maintained by the OLAP key.
* **COL$:** Finds the cell value on the specified column, in alphanumeric format. \[e.g.: COL$(B)]. The position is maintained by the absolute key.
* **CURRENTCOL:** Finds the value of the current column \[e.g.: CURRENTCOL()].
* **CURRENTROW:** Finds the value of the current row \[e.g.: CURRENTROW()].
* **OLAPCELL:** Finds the cell value of a predefined OLAP key \[e.g.: OLAPCELL(olap\_key)].
* **OLAPCOL:** Finds the cell value of a predefined OLAP key \[e.g.: OLAPCELL(olap\_key)].
* **OLAPROW:** Finds the cell value on the specified row, in OLAP key \[e.g.: OLAPROW(olap\_key)].
* **ROW:** Finds the cell value on the specified row, in numeric format \[e.g.: ROW(3)]. The position is maintained by the OLAP key.
* **ROW$:** Finds the cell value on the specified row, in numeric format \[e.g.: ROW(3)]. The position is maintained by the OLAP key.

**Examples of Using the Report Reference Formulas**

The example reported in this section shows what it means to use a function with or without the dollar notation e.g.(**CELL,** (**CELL$)).**

The functions without dollar ($) notation have a common property, i.e. to consider the position of the cell to which the total is applied.

If the reference cell is moved to another position inside the report due, for example, to a selection of values from the report pages, the system automatically updates the formula with the new position.

In regard to the functions with dollar ($) notation, if the reference cell of the formula loses the initial position in the report, the system automatically updates the total with the new value contained in the cell inserted in the formula.

Example: Using (x) CELL

**Step 1: Using (x) CELL**

![](<../../../.gitbook/assets/5 (3)>)

_Create a report and enter a Custom Total that uses the CELL function._

_Specify the value you want to show on the total._

_In this example, the displayed value will be the one in the cell with coordinates B2 associated with Product10._

**Step 2: Using (x) CELL**

![](<../../../.gitbook/assets/6 (1)>)

_Next, we move Product 10 to row 9. The system automatically recalculates the new position of the cell previously chosen in the formula, thus avoiding editing the formula again._

_If we were to edit the total again, we would realize that the system has updated the formula with the new coordinate of the cell that contains the value being analyzed, in this case B9._

**Example: Using (x) CELL$**

**Step 1: Using (x) CELL$**

![](<../../../.gitbook/assets/7 (1)>)

_We create a report and use grouping by levels. When the CELL$ total is selected, the CELL$ total takes account of the contents in the specified cell in the formula._

**Step 2: Using (x) CELL$**

![](<../../../.gitbook/assets/image (155).png>)

_In this example, it takes the value of cell C3. As a result, the value is reported in the column of the CELL$C3 total, because the value is repeated for all the events of the report._

_Group the values for the year 2005 again._

_Now, in cell C3, the value 57,358.00 no longer exists, and the value is now 134,816.00. Please note that the column of the CELL$ C3 total no longer contains the old value, but recalculates its content based on what is inside the selected cell._

**Example:** **Using (x) CELL/OLAPCEL**

**Step 1: Using (x) CELL/OLAPCEL**

![](<../../../.gitbook/assets/9 (2)>)

_Create a new report that groups the Business Unit and Product levels._

_Enter a custom total with the CELL function at the Sales Qty of product 10 (cell B3)._

**Step 2: Using (x) CELL/ OLAPCELL**

![](<../../../.gitbook/assets/10 (1)>)

_If the values are grouped by Business Unit, the Custom total calculated with the Cell function loses the reference to the value of the cell inserted in the formula._

_Therefore the system warns the user that the element specified in the CELL function is not visible in the report. The system automatically uses the OLPACELL function to maintain the position of the data. The formula is displayed in the key form, referring to rows and columns._

**OLAPCELL(("#@SALES\_QTY\_1\_Sum#Business\_Unit\~0#Product\~SKU\_10"))**

_The OLAPCELL function continues to use the values of the initial formula, and formulas can continue to be added._

### Sum Functions <a href="#toc498423819" id="toc498423819"></a>

Sum functions are functions used to instantly calculate the report’s column or row values.

* **COLSUM:** The function is used to find the sum of the values on the selected column in alphanumeric format, considering only the rows relating to the same element of the dimension in penultimate position in relation to the rows \[e.g.: COLSUM(C)]. The position is maintained by the OLAP key.
* **COLSUM$:** The function is used to find the sum of the values on the selected column in alphanumeric format, considering only the rows relating to the same element of the dimension in penultimate position in relation to the rows \[e.g.: COLSUM$(C)]. The position is maintained by the absolute key.
* **COLSUMTOTAL:** The function is used to find the sum of the values on the selected column in alphanumeric format, taking into account all the report rows \[e.g.: COLSUMTOTAL$(C)]. The position is maintained by the OLAP key.
* COLSUMTOTAL$: This function is used to find the sum of the values on the selected column in alphanumeric format, taking into account all the report rows \[e.g.: COLSUMTOTAL$(C)]. The position is maintained by the absolute key.
* **ROWSUM:** The function is used to find the sum of the values on the selected row in numeric format, including only the columns relating to the same item of the dimension in penultimate position in relation to the columns \[e.g.: ROWSUM(3)]. The position is maintained by the OLAP key.
* **ROWSUM$:** The function is used to find the sum of the values on the selected row in numeric format, including only the columns relating to the same item of the dimension in penultimate position in relation to the columns \[e.g.: ROWSUM$(3)]. The position is maintained by the absolute key.
* **ROWSUMTOTAL:** This function is used to find the sum of the values in the selected row in numeric format, taking into account all the report columns \[E.g.: ROWSUMTOTAL(3)]. The position is maintained by the OLAP key.
* **ROWSUMTOTAL$:** This function is used to find the sum of the values in the selected row in numeric format, taking into account all the report columns \[e.g.: ROWSUMTOTAL$(3)]. The position is maintained by the absolute key.

**Example of Using SUM Functions**

The examples show how to use the Sum Functions (**COLSUMTOTAL$, ROWSUM**).

Example: Using (x) COLSUMTOTAL$

**Step 1: Using (x) COLSUMTOTAL$**

![](<../../../.gitbook/assets/11 (4)>)

_The report in the figure above contains the dimensions product, year and month with grouping by dimensions._

_The basic metric is Sales Qty._

_Create a custom total that uses the COLSUMTOTAL function and specify the column where the total will be calculated: in this example, column C._

_After saving the function, the system automatically adds the column with the new total to the report._

_Note that for each instance, the total of years 2006/2007/2008 is shown._

**Step 2: Using (x) COLSUMTOTAL$**

![](<../../../.gitbook/assets/12 (3)>)

_If you decide to show the months of a year (in this case 2005) the system automatically recalculates the overall total for the months displayed, updating the total column._

Example: Using (x) ROWSUM

![](../../../.gitbook/assets/13)

_Build a report with the metrics positioned on the row. Enter a ROWSUM total and specify the row where you must calculate the sum, in this example, row 3. The system automatically calculates the sum of the sold quantities in row 3 for the years in the report._

**Example of Two Functions Crossed**

The example shows how to use the two functions **COL$** and **COLSUM$** in a crossed fashion.

A total will be created which calculates the percentage of the values in the metric, compared to the overall total of the year.

Step 1: Using (x) COL$ and (x) COLSUM$

![](/broken/files/aQu0UJ8nDhTiprtn96xd)

![](<../../../.gitbook/assets/14 (1)>)![](../../../.gitbook/assets/15)

_Create a new report that contains the product, month and year with grouping by dimensions._

_Create a new custom total that uses the following functions:_

* _COL$ to indicate all the values contained in column C_
* _COLSUM$ calculates the sum of the Sales Qty for each product._

Step 2: (x) COL$ and (x) COLSUM$

![](<../../../.gitbook/assets/16 (1)>)

_The system automatically calculates the percentage of the sold quantities in the single year compared to the total of the years by product._

**(330,007.00/1.055496.00)\* 100 = 31.27**

COL$(C) / COLSUM$(C) \* 100

_In the reported example, the totals were entered to check the formula entered above._

_Please note that the total of the sold quantities for Product 10 is 1,055496.00._

_Divide the Sales Qty of the year 2005 by the totals of the years and multiply by 100._

Step 3: Using (x) COL$ and (x) COLSUM$

![](../../../.gitbook/assets/17)

_If the months of a specific year are shown, the system calculates the percentage of each month compared to the total of all the months._

**Step 4: Using (x) COL$ and (x) COLSUM$**

![](../../../.gitbook/assets/18)

_In the example shown, the totals were inserted to check the formula entered above._

**(57,358.00/,.055,496.00) \* 100 = 17.38**

COL$(C) / COLSUM$(C) \* 100

_Note that the total of the quantities sold for the months of 2005 is 1,055,496.00._

_Divide the Sales Qty of the month 200507 by the total of the months, and multiply by 100._

### Conversion Function and Formulas in Java Code <a href="#toc498423820" id="toc498423820"></a>

The conversion functions are in the Conversion Functions section. These functions are needed to convert the numeric values displayed inside the report if formulas must be applied that require conversion into numeric integer or data string that are of the long type by default. This conversion is applied when formulas in java code are inserted.

* **TOINT:** Conversion function of a double value into integer. The report reference functions return to a double value \[e.g.: TOINT(CELL(B2))].
* **TONUMBER$:** Conversion function of an alphanumeric value into integer \[e.g.: TONUMBER("100")].
* **TOSTRING:** Conversion function of a numeric value into String \[e.g.: TOSTRING(100)].

**Examples of Using Java Code Integrated with Conversion Functions**

The examples below show how to build formulas that perform checks on the selected data through java code and custom total functions.

**Using JAVA “SWITCH”**

The example shows how to use the TOINT function and a total constructed with java code, by using the [**switch**](http://adv.edintorni.net/click/?mo=T\&ky=switch\&af=4117\&ct=it\&rf=http%3A%2F%2Fwww%2Ewebmasterpoint%2Eorg%2Fjava%2F05%2Easp\&re=\&ts=1271421997562\&hs=ce91d70d021354fab35208ed8a45f426) function. You can use the [**switch**](http://adv.edintorni.net/click/?mo=T\&ky=switch\&af=4117\&ct=it\&rf=http%3A%2F%2Fwww%2Ewebmasterpoint%2Eorg%2Fjava%2F05%2Easp\&re=\&ts=1271421997562\&hs=ce91d70d021354fab35208ed8a45f426) instruction when you need to perform a series of controls on the same variable, instead of writing an if...else...else... series .

The java code will perform a check for each customer group in the report, and based on the sold quantity, the bonuses to be associated with each customer group will be returned.

Example: Using (x) TOINT and JAVA SWITCH

**Step 1: Using (x) TOINT and JAVA SWITCH**

![](../../../.gitbook/assets/19)

_Create a report that contains 2 dimensional levels and 1 metrics for example:_

* _Year_
* _Customer Group_
* _Sales Qty_

Step 2: Using (x) TOINT and (x) ROUND

![](../../../.gitbook/assets/20)

_Define a formula that extrapolates the decimal part of the value relating to the sold quantity of the Sales Qty metric._

_The TOINT function will transform the value from long to integer and the ROUND function rounds off the excess value. Then select the reference column._

Step 3: Using (x) TOINT and JAVA SWITCH



_Define the switch statement that will be used to check that the values passed to the variable are equal to a specific defined value. If this situation occurs, the system will display the string or the defined value._

_Define a variable of an integer type called “million” to which the value contained in column D will be passed (value relating to column C but with rounding)._

_The Switch key word will be passed to the million variable._

_For each example, various bonus cases were defined, along with actions to take when the cases met the criteria. If:_

* _equal to 6 the total will return the string “50 extra bonus"_
* _equal to 36 the total will return “500 extra bonus”_
* _equal to 36 the total will return “500 extra bonus”_
* _none of the defined conditions occurs the system returns the string “no bonus”._

0; **int million** = TOINT(COL(D));

**switch** (million)

{**case**{case 6: result = 50 +" extra bonus";

**break**;

**case**case 25: result =150 +" extra bonus";

**break**;

**case**case 36: result = 500 +" extra bonus";

**break**;

defaul&#x74;**:** result = "no bonus"; }

_**Note:** You can also perform the rounding of the value in the java formula._

0; **int million** = TOINT(ROUND(COL(C)/10000000));

**switch** (million)

{**case**{case 6: result = 50 +" extra bonus";

**break**;

**case**case 25: result =150 +" extra bonus";

**break**;

**case**case 36: result = 500 +" extra bonus";

**break**;

defaul&#x74;**:** result = "no bonus"; }

**Using JAVA “IF”**

You can define totals which use the java code’s IF function. The IF statement compares the value passed to a variable defined in the code, to a value set by the user. The check performed will be a Boolean type check. A Boolean expression can only return Boolean values, i.e. true or false.

Example Java IF

**Step 1: Using JAVA if**

_Create a report containing levels: YEAR, CUSTOMER GROUP and Sales QTY metric._

_Define the custom total that will use configuration IF as check._

_The Quantities sold for each Customer Group belonging to 2006 will be checked._

_If the value of sales is greater than 100, this means that the value for our analysis is positive, therefore it will return “OK”; if lower than 100 it will equal “KO”._

_The initial value set in the formula will be the one shown, in case the next condition does not take place._

_IF checks the values contained in column C and ensures these are greater than 100; in this case, the system will display the string OK in the total._

**"KO";**

**if ((COL$(C)>100) { result = " = "OK"; }"; }**

_**Note:** As you can see in the previous example, a return value of the function is always specified (in this case the “KO” value). This is because the formula must have an obligatory default return in case the possible_ _condition of IF_ is not met.

**Using JAVA Ternary**

This particular operator acts on three operations and is indicated by the symbols **?**“?” and “:”.**:**”.

Specifically the form of this operator is the following “ ? **? :”**:”where the compiler first assesses expression 1, if it is true the value of expression 2 is assessed and returned; otherwise the value of expression 3 is assessed and returned. For example, if we have to assign the maximum between A and B to variable X, this is synthesized in Java in the single row x=(a>b?a:b).

Example: **Using JAVA TERNARY**

_The report in the figure above shows the quantities sold by month and year._

_You want to build a total type column which reports the string “Year 2005” only for the quantities sold in 2005._

_In this case, you may use the ternary notation that allows you to select a range of rows and set the year only for those selected._

_Therefore use the CURRENTROW function that scans the ID of the rows, and for each row included in the defined range, inserts the string “Year 2005” in the total._

_Note that for rows between 2 and 7 the string Year 2005 was entered, while for the rest, the string “not year” was entered._

### Tutorial



{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/1.MatildaJakeJalapeno/21.Excel-Like/Excel-Like.mp4" %}
