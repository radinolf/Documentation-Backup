# Jobs in Cockpit

The Jobs section of Cockpit allows you to monitor the JOBS published in [App Composer](../../../app-functionality/jobs.md).

Since Cockpit is installed in production environments, the functionalities available for job management are limited. Monitoring information such as job status, job type, and whether it is running are still accessible. However, [stopping ](jobs-in-cockpit.md#howtousedumbellaservice-howtokilljob)the execution of a job will only be possible through the [Job Manager](jobs-in-cockpit.md#job-manager)

<figure><img src="../../../../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

For each Job the following information is given:

* **Name**: Job Name
* **Type:** It indicates whether the job has been published as Job , Job si Service or **NONE** in case of Job not yet published.
* **Status**: Job status.
  * When the Job is not published the status is DISABLED .
  * When the Job is published as Job the status is ENABLED.
  * When the Job is published as a service the status is STOPPED Job automatically started after a crash have status RESTARTED.
  * If a Job goes wrong the sato will be ERROR and you will have the detail of the error..
* **Execution**: Shows the type of job execution which can be Sequential or Parallel. This is set from the context menu.
* **Current version**: Show the job version imported into the Design Studio. Every time the job is modified and re-imported, the version number changes.
* **Published Versions:** Show the version number of the job published on the RunTime
* **Last Update:** Date and time of the last update.

### Job Manager

To know which Jobs are currently running on Dumbella click the button on the top right to open the **Job manager.**

<figure><img src="../../../../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>

It is possible to display the latest update date and you can refresh data cliking on the UPDATE button. For each running Job you can see the following information:

* **Start date:** timestamp when the job started
* **Name:** name of the job in execution
* **Id:** Identification code of the running Job
* **Execution:** unique ID assigned to the current execution
* &#x20;[Trash icon ](jobs-in-cockpit.md#howtousedumbellaservice-howtokilljob): To stop a job from running
* **Contextual menu**&#x20;
  * **Url**: The Dumbella service exposes the APIs for managing and executing Jobs. You can use the REST API Client of the Composer APP or Postman, cURL or any other HTTP client to run the API of a Job. When you run the API via the **App Composer REST API Client**, the reference URL is the one in the Job section. For mode details plese see the [Execution Job](https://documentation.decisyon.com/documentation/app-functionality/jobs#howtousedumbellaservice-composerrestapiclientappcomposerrestapiclient) documentation.
  * **Update**: Refresh the data for the selecte job.

<figure><img src="../../../../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure>

### Kill a job <a href="#howtousedumbellaservice-howtokilljob" id="howtousedumbellaservice-howtokilljob"></a>

To stop a job from running, select the Trash icon on the right of the job.

<figure><img src="../../../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

Once stopped the execution of the Job the icon changes status.

If you refresh the list of running jobs cliking on the **UPDATE** button (or the **Job Manager** dialog is closed and reopened), killed jobs will no longer be visible in the list.

<figure><img src="../../../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

