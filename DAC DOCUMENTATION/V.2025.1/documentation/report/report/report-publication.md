# ⛔ Report Publication



{% hint style="danger" %}
This feature has been deprecated and it will be removed in a later version. Please refer to the changelog for additional information.
{% endhint %}

To publish a report you must:

1. 1.Create a main folder, in the catalog Root, where the reports to be published are placed
2. 2.Open the pop-up menu, in the new folder, and click on Privileges
3.  3.Choose the privilege to assign to all users (Default Privilege):

    * no publication (Access denied): folder and relative reports are not published on DAC
    * the folder and the reports are published on DAC (Read)



<figure><img src="https://350623438-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LwNIm22v7i4UWM_U60u%2F-MGHpHIMnau8eawuckYl%2F-MGHpNMbtJhGEjP32xiR%2Fimage.png?alt=media&#x26;token=095c088d-7907-46a7-bb68-d67840f565f3" alt=""><figcaption></figcaption></figure>

If the publication of a folder was denied (Access denied as default privilege), you may still give specific users, or user groups, full access to the folder:

* Select Read for these users or user groups.
* If a user is part of more than one user group, with different authorization levels, the highest access privilege will be granted.

You can extend or superimpose the privileges for one folder to all subfolders (and not to the reports: in order to do this, select the **Extend to subfolder** flag. This choice is not permanent and if new folders are created, a new request must be made.Each time a main folder or a subfolder is created, DAC sets the privilege to Access denied, so that you can decide which users should be given access to it at a later time. The same happens when a folder is created by a cut and paste operation: the privilege for the copied folder changes to Access denied. Reports created (or copied and pasted) in a folder always have Read set as default privilege.
