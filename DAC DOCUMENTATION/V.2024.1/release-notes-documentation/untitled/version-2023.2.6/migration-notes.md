# Migration Notes

**D4C-9184:** **Fix the problem where columns defined as mandatory were not set as mandatory in the JSON sent to widgets.**

Regarding reports created after the update to version 2023.2.6, the 'key' and 'mandatory' columns are managed correctly.&#x20;

For **existing reports**, **no changes are necessary** as the alignment of the 'mandatory' columns with the 'key' columns occurs automatically during Smart Grid rendering.&#x20;

However, there may be an inconsistency in the report metadata information because for reports created in previous versions, the value will remain at 0 (non-mandatory).

&#x20;If you want to make the alignment of the 'key' and 'mandatory' values persistent, you need to:

1. Edit the report&#x20;
2. Select the columns-definition property
3.  Deselect the Key and Mandatory properties.

    <figure><img src="../../../.gitbook/assets/image (2001).png" alt=""><figcaption></figcaption></figure>
4.  Select Key and Mandatroy properties again

    <figure><img src="../../../.gitbook/assets/image (2002).png" alt=""><figcaption></figcaption></figure>
5. Save the report
