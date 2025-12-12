# Disabling User Filters on Report

In DAC, user filters allow you to manage the visibility of data with _respect to groups._

There may be cases where the report does not need to have this type of constraint, for example, because you need to make visible the totals of the data on which the security constraints are placed (for example, totals of asset are visible, while you can only access one region).

This operation is performed through the property (_Main_ group):

* _**advanced**_ which opens a pop-up with the property:
  * _**disable-sec-filters**_ (_Filters_ group) to enable at report level, the use of the security filters; in this case the security filters for the report will be ignored, for each user accessing the same report
