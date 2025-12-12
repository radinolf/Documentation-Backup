# Format of Response

Any App Composer API delivers responses in JSON format, ensuring that the data is easily readable and interpretable. Additionally, certain APIs [support pagination](methods-and-errors.md#paging).&#x20;

In the below example, the `content` section of the JSON document outlines data about two users, including unique IDs, usernames, emails, and other personal details such as first names, last names, and extended profile specifics.

```json
{
    "content": [
        {
            "id": 521603368512649,
            "oidcIdentifier": null,
            "password": null,
            "username": "User1.@decisyon.com",
            "firstName": "UserName",
            "lastName": "UserLastName",
            "name": "firstName lastName ",
            "email": "User1@decisyon.com",
            "profileImage": null,
            "profileImageSmall": "/content/dcy/img/T103714753544237T/img/ctxDefaults/PROFILE_IMAGE/S55/default.png",
            "profileImageMedium": null,
            "defaultImage": null,
            "admin": true,
            "active": true,
            "lastConnectionTime": null,
            "tenants": null,
            "attributes": null,
            "scopes": null,
            "dacuser": true,
            "onLine": false
        },
        {
            "id": 596603469469333,
            "oidcIdentifier": null,
            "password": null,
            "username": "User2.@decisyon.com",
            "firstName": "UserName",
            "lastName": "UserLastName",
            "name": "firstName lastName",
            "email": "User2@decisyon.com",
            "profileImage": null,
            "profileImageSmall": "/content/image/T760T/NA_874603548305096/2_0/S55.png",
            "profileImageMedium": null,
            "defaultImage": null,
            "admin": true,
            "active": true,
            "lastConnectionTime": null,
            "tenants": null,
            "attributes": null,
            "scopes": null,
            "dacuser": true,
            "onLine": false
        }
    ],
// Information about pagination and the number of elements
    "pageable": {
        "sort": {
            "empty": false,
            "unsorted": false,
            "sorted": true
        },
        "offset": 2,
        "pageNumber": 1,
        "pageSize": 2,
        "paged": true,
        "unpaged": false
    },
    "totalPages": 55,
    "totalElements": 109,
    "last": false,
    "size": 2,
    "number": 1,
    "sort": {
        "empty": false,
        "unsorted": false,
        "sorted": true
    },
    "numberOfElements": 2,
    "first": false,
    "empty": false
}
```

In the second segment of the JSON file, details concerning **pagination** and the **total count of entries** are presented.&#x20;

```json
// Information about pagination and the number of elements

    "pageable": {  // Information about the pagination.
        "sort": {  // Indicates the state of sorting results.
            "empty": false, // The sorting is empty (true/false).
            "unsorted": false, // The sorting is unsorted (true/false).
            "sorted": true  //The sorting is ordered (true/false).
        },
        "offset": 2, //Represents the offset or the initial index of data on the current page.
        "pageNumber": 1, // Indicates the current page number.
        "pageSize": 2, //Represents the page size, which is the maximum number of items per page.
        "paged": true, //Indicates if pagination is enabled.
        "unpaged": false //Indicates if pagination is not enabled.
    },
    "totalPages": 55, // It represents the total number of pages available.
    "totalElements": 109, //Indicates the total number of items on all pages.
    "last": false, // Indica se la page corrente è l'ultima page.
    "size": 2, //Rapresent the number of item in the current page.
    "number": 1, //Indicate the current page number.
    "sort": { // Indicates the state of sorting results.
        "empty": false, // The sorting is empty (true/false).
        "unsorted": false, // The sorting is unsorted (true/false).
        "sorted": true  //The sorting is ordered (true/false).
    },
    "numberOfElements": 2, //Represents the number of elements on the current page.
    "first": false, // Indicates if the current page is the first page.
    "empty": false //Indicates if the current page is empty.
}
```

{% hint style="info" %}
To learn about the JSON format for each API, please check the [Swagger](swagger-e-postman.md) documentation.
{% endhint %}

