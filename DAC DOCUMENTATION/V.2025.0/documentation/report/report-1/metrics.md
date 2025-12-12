# Metrics

### Introduction <a href="#introduction" id="introduction"></a>

‌In addition to using default metrics, you can also create new ones.‌

Starting from a report it will be possible to define new composite metric&#x73;**,** such as a combination of those in the same report. These will be used exclusively by the report and will not be added to those published by the administrator.‌

The format of the metrics pertains to the style and color of the characters, as well as the formatting which depends on the threshold value. You can change the format of the metrics, which will remain exclusively used by the report in which it was defined.‌

The decoration formatting of the metrics can only be defined in a development environment.‌

### Creating a Composite Metrics <a href="#creating-a-composite-metrics" id="creating-a-composite-metrics"></a>

In addition to using default metrics, you can also create new ones.

Starting from a report it will be possible to define new composite metric&#x73;**,** such as a combination of those in the same report. These will be used exclusively by the report and will not be added to those published by the administrator.

The format of the metrics pertains to the style and color of the characters, as well as the formatting which depends on the threshold value. You can change the format of the metrics, which will remain exclusively used by the report in which it was defined.

The decoration formatting of the metrics can only be defined in a development environment.

Select **New metric composed** from the toolbar of the report or from the pop-up menu (_Objects explorer_ section) and access the new metric creation window, where you can combine the metrics in the report to create a new, composite metric.

**Note**_**:**_   Metric creation is disabled on Tablet devices.

The report’s metrics are listed in the left side of the window. To select a metric, double click on it. In the right side of the window, you set the new metric as a combination of the available metrics.

![](<../../../.gitbook/assets/image (707).png>)

Mathematical operators are available (_**Math Operators**_ section) in the area to define the formula.

The metric defined will continue to be used exclusively by the report on which it was defined. You can change the metric you defined by accessing the list of the report metrics.<br>

### Tutorial​&#x20;

{% embed url="https://bitbucket.org/decisyon/manual/downloads/MetricComposite.mp4" %}

### Formatting a Metric <a href="#formatting-a-metric" id="formatting-a-metric"></a>

You can define a custom format for each metric, and the color to assign to a metric to denote the metric’s value.

The conditions on the values are placed on the thresholds, which define:

* Positive metrics (values higher than a threshold);
* Negative metrics (values lower than a threshold);
* Central metrics (values ranging between the negative and positive threshold).

Activate this function by selecting _**Metric Format**_ from the pop-up menu of the metric:

![](<../../../.gitbook/assets/image (1844).png>)

A window opens such as the one in the figure above, where you can define:

* **Common Setting:** the type of character, the dimension (font and size), the decimal places and the additional character (selected between %, $ and €);
* **Positive metric:**  the color of the character and the background, the style settings (bold, underlined and italic) and the positive threshold. All the values of the metric that exceed this threshold will assume this color.
* **Central metric:** the color of the character and background and the settings of the style (bold, underlined and italic). All the values of the metric included between the negative and positive threshold will assume this color.
* **Negative metric:** the color of the character and the background, the style settings (bold, underlined and italic) and the positive threshold. All the values of the metric below this threshold will assume this color.

The metric defined will continue to be used exclusively by the report on which it was defined.

### Tutorial



{% embed url="https://bitbucket.org/decisyon/manual/downloads/FormattingMetric.mp4" %}



​‌
