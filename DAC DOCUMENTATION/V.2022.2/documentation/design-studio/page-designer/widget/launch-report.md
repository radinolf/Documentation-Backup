# Launch report

You can access the report for the components which have an associated report. This behavior can be customized using the _**launch-report**_ property _**(ObjectStyle**_ group); if it is enabled, it lets you open, in the catalog, the report associated with the object (crosstab, graph, indicator, map) used for data display by double-clicking on the object or by clicking on the title of the object.

This property enables _**instance-type**_ which allows the user to decide, once the report associated with the object is launched, if the changes made to the report should have an impact on the starting object (_same instance_) or if the launched report is to be considered a separate instance (_clone instance_).

If you access the report associated with a crosstab (“launch report” property enabled), and perform operations on it (e.g. pivoting, operations on the page-bys, adding metrics or levels) and then use the “reload report” button, the report will return to the initial situation while maintaining the settings it had in the Page when the catalog was launched.
