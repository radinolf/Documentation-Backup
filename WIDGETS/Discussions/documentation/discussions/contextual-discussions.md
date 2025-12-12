# Contextual Discussions

We call a Discussion started on a report cell or level a **Contextual Discussion** since it is limited to that context.

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

Just following the title are the references to that context (OLAP Key).

<figure><img src="../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
A Discussion is visible on a report when the cell referred by his OLAP Key is visible.&#x20;

The Discussion's visibility may be affected by filters and Security filters.
{% endhint %}

The Discussion created on a report will no longer be displayed if the OLAP key coordinates will be changed.&#x20;

In the first picture, a Discussion has been created on the cell.

<figure><img src="../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

In the second picture, we changed the value on the page by, and the Discussion is not visible anymore.

<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

The Page Developer enables **contextual discussions** using the **activateCellsDiscussions** property in the **Report Properties** ![](<../../.gitbook/assets/image (26).png>) on **Design Studio.**

<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

In the Web Application, the Business User right-clicks any element of the report (level, metrics, cells) associated with a **Smart Grid** widget or a **Crosstab** and selects **Attach Discussion**.

<figure><img src="../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

The posted Discussion can be read by any users who have privileges on the same Report (or Page) and precisely on the same cell.

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

![](<../../.gitbook/assets/image (76).png>)

The icon of the Discussion has a green color when the user hasn't yet read it.
