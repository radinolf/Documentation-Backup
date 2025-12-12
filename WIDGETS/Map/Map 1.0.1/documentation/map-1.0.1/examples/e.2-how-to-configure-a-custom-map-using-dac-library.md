# E.2 How to configure a custom Map using DAC Library

This example explains how to configure **custom map** using two simple reports and setting a **DAC Shared Library** as the Map provider. It also shows how to configure custom pins which open a dialog box containing the pin's KPIs when clicked.&#x20;

{% hint style="warning" %}
It is assumed that your own map tiles were previously created through an external application and imported into the **DAC Widget Catalog** as a **Shared Library** resource.
{% endhint %}

In the **Report Editor,** create the first data source report. This report must have the following fields:

* **R01\_item**
* **R01\_latitude**
* **R01\_longitude**
* **R01\_active\_flag**
* **R01\_pin\_icon**
* **R01\_pin\_color**

**R01\_item, R01\_latitude, R01\_longitude,** and **R01\_active\_flag** are mandatory fields.

<figure><img src="../../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Since this is a custom map, the pin's latitude and longitude data will be included in the report in a second step, as they will be retrieved using the widget's feature **Export coordinates on the click**.
{% endhint %}

Create the second report with the pins' KPIs information so that they may be displayed when a pin is clicked.

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
**The second report is optional, however, when using it the R02\_item field is a mandatory field.** It is the identifier of the KPI and the ID in this column must match the ID (R01\_item) in the column of the first report. This is required for the join to work.
{% endhint %}

In the Page Design, create a new page, drag the Map widget, and associate the previously created reports.

Map the columns of the two reports to the specific fields in the **fields association** widget's property:

<div align="left"><figure><img src="../../../.gitbook/assets/image (60).png" alt="" width="563"><figcaption></figcaption></figure></div>

Enable the widget's property **Export coordinates on click** (**Map Settings** group)**.**

Add in the page two [**Plain Text**](https://app.gitbook.com/o/-Mf1nqOzbgLBl5PsDWsN/s/FOIJ7vRnKOrG4ODpMfQV/) widgets and specify in each of them the parameters exported by the widget when selecting a point on the map.

The parameters name must respect the following synta&#x78;**:**

* {baseName}\_selected\_longitude
* {baseName}\_selected\_latitude

{% hint style="warning" %}
These parameters are exported only if the property **Export coordinates on click** is enabled.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

In the widget properties (**Map Source** group), set the following properties:

* **Map provider**: Select **DAC Library** option from the dropdown list.
* **Server URL:** Enter the path of the DAC Library where the tiles of your custom map were imported. In this example:

```
smart_building_maps/LATINA_NERVI_F1_BLUE/{z}/{x}/{y}.png
```

The path should respect the following template:

* **smart\_building\_maps**: The logical name of the Shared Library
* **LATINA\_NERVI\_F1\_BLUE:** Custom folder inside the Shared Library&#x20;
* **{z}:** It represents the zoom (level)
* **{x} :** It indicates tile image x-position (tileX)
* **{y}:** It indicates tile image y-position (tileY)

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

Open the page of your Map in the Web Application. Select the points where you want to place your pins and obtain the Longitude and the Latitude.

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Repeat this procedure to get data for all of your pins.
{% endhint %}

Update the database by including the obtained data in the Latitude and Longitude fields.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

Open your Map in the Web Application. Now, the widget will show the pins on the map based on the coordinates provided.

<figure><img src="../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Even if a custom color has been specified in the report, the disabled pin (**R01\_active\_flag** field set to 0) will be displayed in grey.
{% endhint %}

In the Page Design, configure the following widget's properties :

* **Show pin dialog** (**Pin Settings** group): Enable this property to show the dialog box with the pins' KPIs information when an active pin is clicked.
* **Export coordinates on click** (**Map Settings** group): Disable this property, previously enabled.

{% hint style="warning" %}
**Export coordinates on click**, if enabled, will disable any dialog box opening on the pins for a better selection.
{% endhint %}

* Re-open your Map again in the Web Application. Click the active pin to display the dialogue box with the pin's KPIs information provided from the second data source.

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>
