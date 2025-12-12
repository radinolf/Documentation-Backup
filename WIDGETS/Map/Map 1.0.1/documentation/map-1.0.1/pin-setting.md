# Pin Setting

**Pin Settings** properties include the customization of the pins, such as the icon and color, and other specific features.

### **Default pin icon** and **default pin color**&#x20;

The **Default pin icon** and **default pin color** properties allow you to customize the icon and the color of the active pins on the map when they have not been defined in the first report.&#x20;

The default pin icon and color are as shown in the picture:

<div align="left"><figure><img src="../../.gitbook/assets/image (46).png" alt="" width="153"><figcaption></figcaption></figure></div>

In order to use different icon shapes than the default one and custom colors, enter the icon's **Material** name in the **Default pin icon** property by referring to the website [https://material.io/icons/](https://material.io/icons/) and set a custom color for the icon in the **Default pin color** property.

<div align="left"><figure><img src="../../.gitbook/assets/image (70).png" alt="" width="156"><figcaption></figcaption></figure></div>

{% hint style="warning" %}
If the icon and pin color have been provided and mapped in the first data source report, the configuration of these properties won't be applied to the map.

The icon and color available in the record of the report has higher priority.
{% endhint %}

{% hint style="warning" %}
Disabled pins will be displayed in grey, even when a custom color in the **default pin color** property is set.
{% endhint %}

### Clustering

The **Clustering** feature (**Cluster enabled** property) is used to aggregate the data on maps that have layers with a lot of interlocking pins in order to observe data that would otherwise be hard to display. When the **Cluster** **enabled** property is active, the Map widget group together the pins that are located on the map within a specific distance into a single pin. The **Cluster range** property allows for the specification of this distance.

<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

The clustering is applied dynamically at multiple scales, which means that as the map is zoomed in, more pins are aggregated into fewer groups.

{% hint style="warning" %}
When the **Cluster enabled** property is active, the export of parameters is not triggered when the business user clicks on the pins.
{% endhint %}

### Show pin dialog

The **Show pin dialog** property enables the visualization of a box dialog when the business user clicks a pin. Depending on the map associated to one or two reports, this dialog box may display different information:

If the map is only associated with one report, the box dialog will provide only the id of the map element.

<div align="left"><figure><img src="../../.gitbook/assets/image (89).png" alt="" width="464"><figcaption></figcaption></figure></div>

If the map is associated with two reports, the box dialog will display the id of the map element and the pin's KPIs.

<div align="left"><figure><img src="../../.gitbook/assets/image (31).png" alt="" width="563"><figcaption></figcaption></figure></div>

In both instances, the dialog box will also display the link to open the drill-through if the first report has a drill-through enabled.

