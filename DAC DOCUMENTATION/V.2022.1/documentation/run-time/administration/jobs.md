# Jobs

The list of Jobs imported into the DAC [resources catalog ](../../design-studio/application/resource-catalog/),  is available in the _**Administration>> Jobs section of Run Time.**_

![C:\5e900e416a68667e10924215dd4acc18](../../../.gitbook/assets/1)

The panel shows the lists of imported processes in the system, and for each process the following information are given

* **Name**: Job Name
* **Status**: Job status. The Job can assume the following status NOT-PUBLISHED, PUBLISHED. If the job is published in the colums is show the icon in the figure on top
* **Execution**: Shows the type of job execution which can be Sequential or Parallel. This is set from the context menu.
* **Current version**: Show the job version imported into the Design Studio. Every time the job is modified and and is re-imported, the version number changes.
* **Published Versions:** Show the version number of job published on the RunTime
* **Last Update:** Date and time of the last update.

Only published jobs, in their published version, can be used and then run from DAC.

The side menu items change according with the job status.

**Job Not Published**

If the job is in the Not Published the side menu allows to publish the selected job.

![C:\d4223b936a658df334cee3b43eb5c751](<../../../.gitbook/assets/2 (6)>)

**Job Published**

![C:\4e8350595d31db53925d6a4b0f0f1810](<../../../.gitbook/assets/3 (5)>)

If the job is in the Published , the side menu will allow you to:

* **Unpublish**: unpublish the selected job
* **Enable Parallel Execution** : Lets you run the job in parallel with other jobs. To disable the parallel execution mode, simply select the Disable Parallel Execution item from the side menu.
* **Update**: update the version of the Job .Versions are aligned when the current version differs from the published one.

Only published jobs, in their published version, can be used and then run from DAC.

* **URL:** the system generates the URL to use for example in APIs. The Endpoint provided is the one that can be used to run the job.

![C:\f6ec7d0bc1654764a45664526b1a0ba6](../../../.gitbook/assets/4)

\
**Job Deleted**

If the Job is remove by the Resource Catalog the side menu will show the _**Remove**_ item to permanently remove the Job from the list.

![C:\cfd77542a4e81c360f66985ed3f3a031](<../../../.gitbook/assets/5 (4)>)

\
Watch the video tutorial to learn more about this feature.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/ImgSito/RunTime/Jobs/Jobs.mp4" %}

