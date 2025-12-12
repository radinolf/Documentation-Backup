# Configuring Pagination in DAC API

## Introduction

In the following example, we will show you how to make a DAC API request using Postman and how to configure pagination for resource visualization.&#x20;

Pagination is a useful method for managing large amounts of data, allowing you to navigate through results efficiently. Follow the steps below to execute the API call correctly and configure pagination for your data viewing experience.

## :dart:Objective of the example

In this example we use the API that return the list of [Task](../../../collaboration/task.md) visible to the user who make the request. In the figure below we can see the task opens in the Task Board. The API will be configured to return two tasks (`size=2`) with the status New (`status=0`).

{% hint style="info" %}
To make this example work, add some tasks to the taskboard.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

## **Step 1 -  Access on Swagger Documentation**

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (1884).png" alt=""><figcaption></figcaption></figure></div>

In the figure above, we can see the documentation related to the API used in this example.&#x20;

The API is the following:

```
/api/v2/rest/tasks/all
```

This API return the list of task visible to the user who makes the request.

The API request the valorization of this parameters:&#x20;

* **predicate** : These parameters filter the API results based on all the fields set for the creation of the task, such as title, priority, and status etc. (For more details wee the [Task ](../../../collaboration/enabling-collaboration/task.md)documentation)
* **pageble**: Set the pagination value.

## **Step 2 - Configure the request in Postman**&#x20;

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure></div>

1. Open Postman insert API URL `https://`**`DAC_URL`**`/api/v2/rest/`**`tasks`**`/all?`**`page`**`=0&`**`size`**`=2&`**`sort`**`=title,desc&status=0`
2. Headers insert in Key `accept = application/json`
3. Headers  insert in Key `Authorization : Bearer <your token>`

Open **Params** tab

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure></div>

Now define the parameters for pagination and data filtering. For pagination:

* `Page = 0`: Visualizes the data on page number 0.
* `Size = 2`: Specifies that 2 elements will be displayed per page.
* `Sort = title,desc`: Sorts by title in descending order.
* `Status = 0:` Filters the data to include only items with a status of 1. Status 0 corresponds to the 'New' state on the Task Board."
* Now click on Send button.

## Step 3- Response of API

The API response is shown in JSON format below, with the Tasks sorted alphabetically by their titles.

{% hint style="success" %}
In JSON file click on the title of the Task ![](<../../../../.gitbook/assets/image (3).png>)
{% endhint %}

<pre class="language-json"><code class="lang-json">{
    "content": [
        {
            "id": "684658916626110",
            "application": "SOCIALM",
            "reporter": {
                "id": 942656502150444,
                "name": "Tilly Jennifer"
            },
            "title": "<a data-footnote-ref href="#user-content-fn-1">Task of PO DT22180001-L</a>",
            "description": {
                "text": [
                    {
                        "v": "Task of 11111"
                    }
                ],
                "meta": []
            },
            "assignee": null,
            "cc": [],
            "status": 0,
            "priority": 2,
            "categories": null,
            "tags": [],
            "discussionId": 686658916626117,
            "discRootId": "SOCIALM_0_-1",
            "dueDate": 1658923823874,
            "expired": true,
            "timeZoneId": "Etc/UTC",
            "refObjId": "-1",
            "refObjType": 0,
            "refObjName": "NA",
            "refObjKeyDesc": "NA",
            "refObjKeyDesc2": "NA",
            "target": "",
            "kpiValue": null,
            "kpiFormValue": null,
            "mainObjUID": null,
            "secondaryObjUID": null,
            "solution": {
                "text": [
                    {
                        "v": "This is the solution of the task"
                    }
                ],
                "meta": []
            },
            "followers": 1,
            "archived": false,
            "invalid": false,
            "canModify": true,
            "followed": true
        },
        {
            "id": "183658916102826",
            "application": "SOCIALM",
            "reporter": {
                "id": 942656502150444,
                "name": "Tilly Jennifer"
            },
            "title": <a data-footnote-ref href="#user-content-fn-2">"Task of PO AG52180151-T</a>",
            "description": {
                "text": [
                    {
                        "v": "Task of AG52180151-T"
                    }
                ],
                "meta": []
            },
            "assignee": {
                "id": 942656502150444,
                "name": "Tilly Jennifer",
                "profileImage": "/content/image/T4230T/NA_182662370263550/2_0/S55.png"
            },
            "cc": [],
            "status": 0,
            "priority": 2,
            "categories": null,
            "tags": [],
            "discussionId": 185658916102829,
            "discRootId": "SOCIALM_0_-1",
            "dueDate": 1658923291006,
            "expired": true,
            "timeZoneId": "Etc/UTC",
            "refObjId": "-1",
            "refObjType": 0,
            "refObjName": "NA",
            "refObjKeyDesc": "NA",
            "refObjKeyDesc2": "NA",
            "target": "",
            "kpiValue": null,
            "kpiFormValue": null,
            "mainObjUID": null,
            "secondaryObjUID": null,
            "solution": {
                "text": [
                    {
                        "v": "This is the solution of the task"
                    }
                ],
                "meta": []
            },
            "followers": 1,
            "archived": false,
            "invalid": false,
            "canModify": true,
            "followed": true
        }
    ],
    "totalPages": 11,
    "totalElements": 21,
    "last": false,
    "size": 2,
    "number": 2,
    "numberOfElements": 2,
    "first": false,
    "empty": false
}
</code></pre>

```json

    "content": [
        {
            "id": "684658916626110",
            "application": "SOCIALM",
            "reporter": {
                "id": 942656502150444,
                "name": "Tilly Jennifer"
            },
          
  "title": "Task of PO DT22180001-L",




            "description": {
                "text": [
                    {
                        "v": "Task of 11111"
                    }
                ],
                "meta": []
            },
            "assignee": null,
            "cc": [],
            "status": 0,
            "priority": 2,
            "categories": null,
            "tags": [],
            "discussionId": 686658916626117,
            "discRootId": "SOCIALM_0_-1",
            "dueDate": 1658923823874,
            "expired": true,
            "timeZoneId": "Etc/UTC",
            "refObjId": "-1",
            "refObjType": 0,
            "refObjName": "NA",
            "refObjKeyDesc": "NA",
            "refObjKeyDesc2": "NA",
            "target": "",
            "kpiValue": null,
            "kpiFormValue": null,
            "mainObjUID": null,
            "secondaryObjUID": null,
            "solution": {
                "text": [
                    {
                        "v": "This is the solution of the task"
                    }
                ],
                "meta": []
            },
            "followers": 1,
            "archived": false,
            "invalid": false,
            "canModify": true,
            "followed": true
        },
        {
            "id": "183658916102826",
            "application": "SOCIALM",
            "reporter": {
                "id": 942656502150444,
                "name": "Tilly Jennifer"
            },
            
"title": "Task of PO AG52180151-T"



,
            "description": {
                "text": [
                    {
                        "v": "Task of AG52180151-T"
                    }
                ],
                "meta": []
            },
            "assignee": {
                "id": 942656502150444,
                "name": "Tilly Jennifer",
                "profileImage": "/content/image/T4230T/NA_182662370263550/2_0/S55.png"
            },
            "cc": [],
            "status": 0,
            "priority": 2,
            "categories": null,
            "tags": [],
            "discussionId": 185658916102829,
            "discRootId": "SOCIALM_0_-1",
            "dueDate": 1658923291006,
            "expired": true,
            "timeZoneId": "Etc/UTC",
            "refObjId": "-1",
            "refObjType": 0,
            "refObjName": "NA",
            "refObjKeyDesc": "NA",
            "refObjKeyDesc2": "NA",
            "target": "",
            "kpiValue": null,
            "kpiFormValue": null,
            "mainObjUID": null,
            "secondaryObjUID": null,
            "solution": {
                "text": [
                    {
                        "v": "This is the solution of the task"
                    }
                ],
                "meta": []
            },
            "followers": 1,
            "archived": false,
            "invalid": false,
            "canModify": true,
            "followed": true
        },
        {
            "id": "440678279074203",
            "application": "J3FFGSC",
            "reporter": {
                "id": 942656502150444,
                "name": "Tilly Jennifer"
            },
            
```

[^1]: ![](<../../../../.gitbook/assets/image (2).png>)

[^2]: ![](<../../../../.gitbook/assets/image (4).png>)
