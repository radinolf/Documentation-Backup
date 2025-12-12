# Version 1.0.1

### 🔧Fixed  <a href="#toc78540232" id="toc78540232"></a>

* DC-1007 – **Filtering Issue with PageBy Selector Paramaters**

We fixed an issue where the Map widget was set up to import two parameters, 'Customer' and 'Site' from the **PageBy selector**. Despite selecting these parameters, the Map was not filtered.

* DC-1009 – **Map Rendering Issue Linked to 'R02\_kpi\_icon' Field in KPI Report Mapping**

We resolved an issue where the Map failed to render when the '**R02\_kpi\_icon**' field was specified in the second report (KPI report) and mapped in the `fields association` widget's property.
