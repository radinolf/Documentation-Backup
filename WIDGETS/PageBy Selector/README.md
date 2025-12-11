# PageBy Selctor

## Overview

The **PageBy Selector** is a versatile widget designed to improve interactivity and data filtering within a page. The PageBy selector corresponds to the page-by of a report because most of the properties of the Page-bys of the reports are present in the selector. It is useful to explore data, focus on specific slices, and enhance the user experience on the pages.

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

The **PageBy Selector** widget, belonging to the **Form** group of the Page Designer components, lets you build a selector starting from one or more dimensional levels.

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

**Key Features:**

1. **Dimensional Filtering**:
   * Allows business users to filter data displayed on a page based on one or more dimensional levels.
   * The selected levels act as filters for all widgets on the page that share the same levels.
2. **Customization Options**:&#x20;
   * **Aliases**: Assign meaningful names (e.g., "Select Year" for the YEAR dimension) for user-friendly navigation.
   * **Selection Types**: Choose between single, single with search, or multiple with search for each dimension.
   * **Layout Adjustments**: Configure the number of elements per row, adjust selector widths, and enable reset buttons.
3. **Advanced Features**:
   * **Default Selection**: Configure whether the first, last, total, or a query-defined value is preselected.
   * **Total Visibility**: Enable or disable a totalization element (`[Total]`) for specific levels.
   * **Hiding Levels**: Hides certain levels from display in the web application if needed.

## Properties

The properties that are specific for the configuration of the **PageBy Selector** widget on **Decisyon App Composer** are listed below:

<table data-full-width="true"><thead><tr><th width="122">Group</th><th width="279">Name</th><th width="511">Description</th><th align="center">Type</th><th width="163" align="center">Default Value</th><th align="center">Allow Page Parameters</th></tr></thead><tbody><tr><td><strong>Main</strong></td><td><code>level-associated</code></td><td>Associates dimensional levels with the widget, creating selectors for each level.</td><td align="center">SELECT</td><td align="center">Undefined</td><td align="center">No</td></tr><tr><td><strong>Main</strong></td><td><code>alias-level</code></td><td>Assigns aliases to dimensional levels for better usability.</td><td align="center">SELECT</td><td align="center">Undefined</td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><code>default-selection-type</code></td><td><p></p><p>Sets default selection type. You can set the following options:</p><ul><li>&#x3C;single (search)></li><li>&#x3C;single></li><li>&#x3C;multiple></li></ul></td><td align="center">SELECT</td><td align="center">&#x3C;single (search)<strong>></strong></td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><h4><code>selection-type</code></h4></td><td>Sets the type of initial page-by selection: multiple or single.</td><td align="center">SELECT</td><td align="center">Undefined</td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><code>opening-selection</code></td><td><p>Specifies the initial value selected during the first execution:</p><ul><li> <strong>First</strong>: selection of the first element of the list.</li><li> <strong>Last</strong>: selection of the last element of the list. </li><li><strong>Total</strong>: selection of the totalization element.</li><li> <strong>Page-by-content</strong>: automatic selection of all the elements present in the list. Available only if the page-by is in multiple selection mode &#x3C; multiple >.</li><li><strong>Query</strong>: allows you to define a SQL query that will be used to determine the selected element.</li></ul></td><td align="center">SELECT</td><td align="center">Undefined</td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><code>total-visibility</code></td><td>Configures the presence of the <code>[Total]</code> item for all, none, or selected levels.</td><td align="center">SELECT</td><td align="center">&#x3C; all-levels ></td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><code>hidden-pageBy</code></td><td>Hides the selected page-by levels associated with the widget in the web app application.</td><td align="center">SELECT</td><td align="center">Undefined</td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><code>selector-width (web)</code></td><td>Sets the width of page-by levels in pixels. Setting the value "-1 " the width will be automatically calculated by the widget.</td><td align="center">TEXTFIELD</td><td align="center">&#x3C; auto ></td><td align="center">No</td></tr><tr><td><strong>Page-By</strong></td><td><code>show-initializer (web)</code></td><td>Enables a reset button to revert page-bys to their initial values.</td><td align="center">SWITCH</td><td align="center">0</td><td align="center">No</td></tr></tbody></table>

## Widget Parameters

**Imported Parameters**

The following parameters are imported by the **PageBy** widget:

| Name         | Description                               |
| ------------ | ----------------------------------------- |
| \<levelName> | Imports the ID value of the selected item |

**Exported Parameters**

The following parameters are exported by the widget when selecting data in the **Dropdown**:

<table><thead><tr><th width="241.51019215963237">Name</th><th>Description</th></tr></thead><tbody><tr><td>&#x3C;levelName></td><td>Exports the ID value of the selected item</td></tr></tbody></table>

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (7).png" alt="" width="563"><figcaption></figcaption></figure>
