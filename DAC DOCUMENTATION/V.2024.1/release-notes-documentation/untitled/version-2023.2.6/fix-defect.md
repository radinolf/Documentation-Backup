# Fix Defect



**D4C-5869:** Fixed an issue where an exception was returned when creating users with an attribute exceeding 200 characters.

{% hint style="danger" %}
We have increased the value field of the user attribute to 4000 characters. However, it is strongly discouraged to use values in the order of thousands, as they may cause performance impacts.
{% endhint %}

**D4C-9042:** Resolved an issue where execute buttons associated with the REST Client failed to export the response status if the request status was not 200. With the new feature (see [New Feature](new-feature.md) page) is resolved an issue where execute buttons associated with the REST Client failed to export the response status if the request status was not 200.&#x20;

**D4C-9176:** Fixed readability issues with page names when a dark primary color was set.

**D4C-9184:** Addressed a problem where columns defined as mandatory were not set as mandatory in the JSON sent to widgets.

{% hint style="warning" %}
Please read the [**Migration Note**](migration-notes.md) for reports created before this release.
{% endhint %}

**D4C-9212:** Fixed a "label not found" issue on the scheduled action list for API with status 200.

**D4C-9249:**  Resolved an error occurring while editing a report via CRUD on databases Oracle, HANA, Oracle-Mysql.

**D4C-9263:** Fixed an issue where the execute object associated with a REST Client didn't apply default param values.

**D4C-9264:** Addressed an issue where the "Administrator" user could be deleted from the user management. The user "administrator" is no longer visible in the user list from the user administration page.

**D4C-9265:** Resolved an exception raised when synchronizing jobs with large file sizes.

**D4C-9278:** Fixed encoded string visibility in dialog titles of a Drill Through.

**D4C-9284:** Resolved tab scrolling icon issues when a dialog is open.

**D4C-9288:** Fixed errors using `DECISYON.utils.closeCurrentDialog()` on pages opened via E-mail links.

**D4C-9294:** Resolved issues with labels not being decoded for Russian and Latvia languages.

**D4C-9295:** Fixed the `network_info` column not being valued in the metadata table `ft_user_connection`.

**D4C-9402:** Fixed an issue in the HELM chart that was not including the value `Blob:` in the CSP policy of `img-src`

<br>
