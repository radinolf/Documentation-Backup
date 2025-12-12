---
description: Jobs section contain the list of jobs  imported into the DAC.
---

# Jobs

The list of Jobs imported into the DAC is available in the _**Administration>> Jobs section .**_

![](<../../../.gitbook/assets/image (240).png>)

The panel shows the lists of imported processes in the system, and for each process the following information are given

* **Name**: Job Name
* **Status**: Job status. The Job can assume the following status NOT-PUBLISHED, PUBLISHED, DELETED
* **Current version**: Show the job version imported into the Design Studio. Every time the job is modified and and is re-imported, the version number changes
* **Published Versions:** Show the version number of job published on the RunTime
* **Last Update:** Date and time of the last update.\
  <br>

Only published jobs, in their published version, can be used and then run from DAC.

The side menu items change according with the job status.

**Job Not Published**

* If the job is in the Not Published status the side menu allows to publish the selected job.



![](<../../../.gitbook/assets/image (242).png>)

**Job Published**

* If the job is in the Published status, the side menu will allow you to:
  * **Unpublish**: unpublish the selected job
  * **Update**: update the version of the Job .Versions are aligned when the current version differs from the published one.

Only published jobs, in their published version, can be used and then run from DAC.

![](<../../../.gitbook/assets/image (232).png>)

* &#x20;**URL:** the system generates the URL to use for example in APIs. The Endpoint provided is the one that can be used to run the job.

\
**Job Deleted**

* If the Job is in the Deleted status the side menu will show the Remove item to permanently remove the Job from the list.

![](<../../../.gitbook/assets/image (233).png>)
