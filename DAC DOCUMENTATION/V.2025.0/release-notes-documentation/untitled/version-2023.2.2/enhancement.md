# Enhancement

## REST API Client

### Configurable timeout for REST API Client

Now it is possible to set the timeout of a [REST API client](../../../documentation/sdk-and-api/rest-api-client.md), so that the REST request times out only after exceeding the value applied in the App Composer.

The properties must be configured in the pod.&#x20;

### HTTP Client

| Property                                   | Description                                                                                                                                                     | Type    | Mandatory | Default Value       |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | --------- | ------------------- |
| appcomposer.http.client.connection-timeout | set the maximum time a REST request can take to establish connection to the server . The unit of measure is expressed in _milliseconds_.                        | integer | false     | 180000 milliseconds |
| appcomposer.http.client.read-timeout       | sets the maximum time allowed to receive a response after the connection has been successfully established. The unit of measure is expressed in _milliseconds_. | integer | false     | 180000 milliseconds |

### New additional HTTP methods in the Rest API Client

Now, in the Rest API Client, it is possible to use the method `PATCH`.

<figure><img src="../../../.gitbook/assets/image (376).png" alt=""><figcaption></figcaption></figure>

### Apply the URL encoding in the REST API Client

In the REST API Client, the URL is now encoded to handle and transmit parameters containing spaces or other special characters.&#x20;

## Server side validation

#### Smartgrid

Now the Business User is promptly informed if the file loaded as an XLSX template in a Smart Grid widget is inconsistent. This procedure is intended to ensure that only files conforming to the required format, specifically XLSX files, can be successfully loaded into the Smart Grid widget. In case the update file is not a XLSX the DAC will display an error will be indicating the wrong extension of the uploaded file

#### Terms of Use

Now the Business User is promptly informed if the file loaded as an PDF template in a Terms Of Use is inconsistent. This procedure is intended to ensure that only files conforming to the required format, specifically PDF files, can be successfully loaded into the Terms of User section. In case the uploaded file is not a PDF the DAC will display an error message indicating the wrong extension of the uploaded file

## Page Catalog Search

The search functionality in the Page Catalog has been improved. Initially, folders without matching items during the search were not hidden, and if a folder contained at least one matching item, it was not automatically expanded.

Now  the search behavior in the Page Catalog ensures that folders without matching items are hidden, and folders containing at least one matching item are expanded automatically.

## File Validation

#### Discussion widget

In the Discussion widget has been introduce the validation of the file uploaded in the widget.

<figure><img src="../../../.gitbook/assets/image (377).png" alt=""><figcaption></figcaption></figure>

For the Discussion widget, a new property, "mime-type," has been introduced, allowing the association of the file type that can be uploaded. If no type is selected, then all file types can be uploaded through the widget.&#x20;

Additionally, it is possible to add custom file types beyond the predefined ones. In the "Insert" section, enter the desired type and press the "ADD" button to include it in the list.

<figure><img src="../../../.gitbook/assets/image (378).png" alt=""><figcaption></figcaption></figure>

## Widget Designer&#x20;

Added a new boolean property **For Excel integration.**

&#x20;For more information please see the widget [documentation](../../../documentation/widgets/widget-editor/widget-settings.md#main-settings).

## Tab name in the pages

The tab names of the pages in the DAC used to be written in uppercase, regardless of the actual page name. Now, it reflects the name assigned to each page.

<figure><img src="../../../.gitbook/assets/image (1953).png" alt=""><figcaption></figcaption></figure>

