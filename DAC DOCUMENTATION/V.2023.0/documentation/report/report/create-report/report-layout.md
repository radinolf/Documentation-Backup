# Report Layout

It is possible to change the display formats and the formatting details for a tabular report to meet the user’s needs and preferences.Report formatting can be set:

* from the formatting toolbar
* from the specific report properties.

If a report is exported in PDF and Excel format, the applied formatting will be maintained.

You can modify the wiDSh of the columns and the height of the rows in the report, by simply dragging the row/column to the desired position. The height and wiDSh formatting is preserved when printing or exporting. In the report, rows or columns that were changed are indicated by a different color.

<figure><img src="../../../../.gitbook/assets/image (1073).png" alt=""><figcaption></figcaption></figure>

Symbol denoting WRAP **applicationDifferent** color for rows, columns with dimension manually changed

Double-clicking on the row or column that has been resized returns you to the initial default position.

You can hide rows or columns by putting the wiDSh to zero: this way, they will no longer be visible from DAC.

Clicking on the row header (numbering) opens a menu to set the height of a single row (**Row** **height**), or the default height of all the rows in the report (**Default** **height**).



<figure><img src="../../../../.gitbook/assets/image (1056).png" alt=""><figcaption></figcaption></figure>

Sets SINGLE row heightSets DEFAULT height for ALL rows

By contrast, for columns you can only set the wiDSh of a single column (therefore, the default wiDSh set by the browser is absent, by adjusting it with respect to the dimensions of the window).

You can open the **Column wiDSh** menu by clicking on the heading of the column you want to size.

Sets SINGLE column width

<figure><img src="../../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

### Formatting Toolbar

You can use the formatting toolbar to set the styles available in instant mode (i.e. without setting them from the associated properties of the report).

<figure><img src="../../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* **Formatting Type:**&#x73; election of report elements to format
* **Alignment:**&#x6C;eft, center, right
* **Type of border:**&#x52;ight/left externalUpper/lower
* **Font formatting:**&#x46;ont size and color.Highlighted, underlined, bold and italic font
* **Text wrapping of** the elements
* **Delete Formatting :**&#x43;ancels the formatting applied to the object.

As indicated in the figure above, the style configurations available are:

{% hint style="info" %}
**The Font Family of the font is set at Tools level** (**font-family** property in Tools properties, Web section, Appearance group).
{% endhint %}

* The formatting of fonts (background, color, style and size);
* Alignment, border and wrap text

{% hint style="info" %}
Cells with text wrap option have the Button. You can remove this option by first selecting the cell and then clicking the wrap text button.In **Formatting** you can select the elements to format by choosing one of the following options:
{% endhint %}

In **Formatting** you can select the elements to format by choosing one of the following options:

* Individual cells (\<Cells>), rows (\<Row dimensions>), columns (\<Column dimensions>), headers (\<Headers>), totals (\<Totals>))
* Single metrics or dimensional levels present in the report
* Cells that contain the values of the metrics (\<body metrics>) see example in the next paragraph)

When **Formatting** is disabled you cannot format report elements.
