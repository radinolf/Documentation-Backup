---
description: List of System Parameters
---

# System Parameters

## Introduction <a href="#introduction" id="introduction"></a>

The **System Parameters** are as follows:

* **%REPORT\_LEVELS%** – logical names of ALL report levels.
* **%SELECT\_LEVELS%** – logical names of the levels VISIBLE in the report; therefore the levels in page-by and in drill mode are excluded.
* **%PAGE\_BY\_LEVELS%** – logical names of ALL levels in page-by mode.
* **%PAGE\_BY\_FILTER\_LEVELS%** – logical names of the levels in page-by mode that have a selection (those in which the total is selected are excluded).
* %SELECT\_IS\_AGGREGATE% – verifies if the metric is aggregated.
* **%SELECT\_IS\_TOTAL%** verifies if the level associated with the metric is a total. Can be used solely in the the formulae of the metrics, i.e. 0 or 1 depending on whether the crossing of the metric corresponds to a total or not.
* User parameters and attributes
* **%SELECT\_IS\_AGGREGATE%:** The parameter %SELECT\_IS\_AGGREGATE%, which can be used exclusively in the formulas of the metrics, is 0 or 1 depending on whether the crossing of the metric corresponds to an aggregate value of the information present in the report or not.
* **% TENANTS% :** Contains a CSV string made up tenants’ ID. If the Business User is associated with no tenants, variable contain no value.
* **%CURRENT\_TENANT%:** Contains the current working session for the selected tenant ID. If the Business User is associated with no tenants, variable contains a constant ID.

## User Parameters and Attributes <a href="#user-parameters-and-attributes" id="user-parameters-and-attributes"></a>

DAC allows user parameters to be used not only in the formulas of metrics and levels, but also in the following objects:

* Security filters .
* View Filter of the reports
* Default values or filter conditions in the Pages

The user parameters are:

* _**%U\_username%**_, for username;
* _**%U\_subjectName%**_, for the subject name;
* _**%U\_subjectSurname%**_, for the surname;
* _**%U\_subjectFullName%**_, the parameter concatenates the name and surname of the user;
* _**%U\_mail%**_ , for the e-mail address;
* _**%U\_phone%**_, for the phone number;
* _**%SUBJECT\_ID%**_ , for the user ID in DAC;
* _\*\*%U\_attribute\\_\[n]%**\_, with n=1-5, for the 5 attributes that can be assigned to a user in the** Attribute\*\* folder.
* _**%GROUPS%,**_ for the groups the user belongs to (if the user belongs to several groups, the parameter lists the group codes in square brackets, separated by a comma: e.g. \[123,345]).
* **%G\_GroupName%**, it’s the ID attribute of the group(s) nodes in DAC.
* **%G\_GroupUserMemberName%**, it’s the ID attribute of the group(s) members.
* _**%U\_utc\_real\_offset%,**_ shows the offset with respect to the UTC (considers the solar and hemisphere time). It is expressed in hours (or fractions of hours) in which the decimal separator is the dot ‘.’ (4 3.5 2.25 5.75).

_**% U\_language%,**_ shows the lan[<br>](https://dac-documentation-1.gitbook.io/user-manual/design-studio-manual/tags)
