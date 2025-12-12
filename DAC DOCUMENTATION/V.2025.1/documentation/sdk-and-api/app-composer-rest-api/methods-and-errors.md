# Methods & Errors

## Methods

The commonly used HTTP methods in DAC API include:

* GET
* POST
* PUT
* DELETE

## Error Code

Errors during API calls are an inevitable part of the development and integration process. Below, we provide an overview of the main error codes you may encounter during interactions with the DAC APIs.



| Error Code                      | Description                                                                                                                                    |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **200** OK/ Deleted/Unpublished | Indicate that the request was successful for the GET and POST method. In the method Delete may try indicate a deleted request or published Job |
| **201** Created                 | Indicates that the request was successful and the object was created.                                                                          |
| **400** Bad Request             | Indicates that the request sent to the server is incorrect or incomplete.                                                                      |
| **401** Unauthorized            | The server requires user authentication to access the resource.                                                                                |
| **404** Not Found               | The server cannot find the requested resource.                                                                                                 |
| **405** Method Not Allowed      | The HTTP method used in the request is not supported for the resource.                                                                         |
| **406** Not Acceptable          | Indicate that the request cannot be processed                                                                                                  |
| **409** Version conflict        | Indicate that the version is in conflict                                                                                                       |
| **500** Internal Server Error   | Indicates a generic server-side error.                                                                                                         |
| **503** Service Unavailable     | The server is unable to handle the request at the moment due to overload or maintenance.                                                       |
| **505** Updated failed          | Indicates that the update failed                                                                                                               |

