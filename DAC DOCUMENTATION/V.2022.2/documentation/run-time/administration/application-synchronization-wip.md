# Application Synchronization

The Application Synronization section under the Administration menu item allows you to connect between two applications.

![](<../../../.gitbook/assets/image (15).png>)

Web synchronization compared to Design Studio[ <img src="https://gblobscdn.gitbook.com/spaces%2F-Me9l9764sQiD6lw0m1F%2Favatar-1625825938272.png?alt=media" alt="" data-size="line">Application Management](https://documentation.decisyon.com/documentation/design-studio/application-management) allows you to connect via Run Time to the target application if it is not possible to connect to the Design Studio.

Following diagram summarizes synchronization crucial steps.

![](<../../../.gitbook/assets/image (717).png>)

1. Connect at the Run Time of the target application
2. &#x20;Share Metadata File. Save into the file all the metadata information.
3. Choose the type of Metadata File to be generated. Difference Metadata Files are created if you want update an existing application or you want to import a brand new application.
4. The control file must be imported from the source application.
5. Connect to the design studio of the source application.
6. Generate the File of export (ExportFile. Adp) that contains the metadata information of the object to be synchronized.
7. Connect at the Run Time of the target application and import ExportFile.adp to synchronize the application.

For more details on using Application Synchronization, please _see the tutorial_.

{% embed url="https://dac-docs.s3-us-west-1.amazonaws.com/Quackmore/Synchronization/Synchronization.mp4" %}

