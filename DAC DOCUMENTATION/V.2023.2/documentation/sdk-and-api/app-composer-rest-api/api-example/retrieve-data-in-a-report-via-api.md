# Retrieve data in a report via API

## Introduction

In this example, we will see how to retrieve data from a report in DAC using a DAC API.

The API facilitates real-time access and flexibility in reading report data. It updates automatically, aligning with any changes in the report's structure or content. This ensures immediate availability of updated data to external systems without manual CSV handling. Utilizing the API guarantees access to fresh, updated data for improved business process efficiency.

{% hint style="success" %}
The API that allows this type of action is located in the **Report** group of the **V2** version of **Swagger**.

`/api/v2/rest/application/{application}/report/{id}`
{% endhint %}

## Prerequisites

To execute the API, you need to have:

* **DAC Access Token (** plese see the documentation to generate the [**DAC Token**](../authentication.md#generate-token)**)**

In Swagger, we notice that the API also requires two additional parameter.

<figure><img src="../../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

* **Application**: Application ID (OWNER)
* **id**: Report ID (OBJECT\_ID)

{% hint style="success" %}
You can retrieve **application ID** (**owner**) information from the metadataInfo property of any object in DAC .

To retrieve the **report ID** (**object\_id**), you need to view the metadataInfo property related to the report .

![](<../../../../.gitbook/assets/image (69).png>)
{% endhint %}



## **Step 1. View Report**

The API we’re going to configure will read the data of the report displayed below.

<figure><img src="../../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

## **Step 2. Configure API on Postman**

Access Postman and configure the API.

<figure><img src="../../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

1. Insert API URL `/api/v2/rest/application/{application}/report/{id}.`Replace parameters with object IDs.
2. Inset Headers:
   1. Authorization: `Bearer <Access_Token>`
   2. Accept: `Application/json`
3. Send API.

## **Step 3. API result**&#x20;

This is the result of the API in JSON format. It includes information such as the report's ID, name, and whether it is writable. Additionally, it contains details about the report's structure, including its columns and rows. Each row contains cells representing different data points, and each cell has properties such as type, subtype, value, and visibility.&#x20;

{% code fullWidth="false" %}
```json
{
    "id": "567713782940342",
    "description": "",
    "name": "Plant 001",
    "writable": false,
    "rows": [
        {
            "row": 0,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "H",
                    "subType": "He",
                    "value": "Plant",
                    "idValue": "Plant_Id_DS",
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "H",
                    "subType": "He",
                    "value": "Active Flag",
                    "idValue": "Active_Flag",
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "H",
                    "subType": "He",
                    "value": "Line",
                    "idValue": "PO_Line_Id1",
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "H",
                    "subType": "He",
                    "value": "Minutes",
                    "idValue": "Stop_Duration",
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "C",
                    "subType": "F",
                    "value": "Stop Counter",
                    "idValue": "Stop_Count_Sum",
                    "colSpan": 1,
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 1,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE A",
                    "idValue": "4",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "4.00",
                    "idValue": "4.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "1",
                    "idValue": "1",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 2,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 2,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 2,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE A",
                    "idValue": "4",
                    "rowSpan": 2,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "10.00",
                    "idValue": "10.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "2",
                    "idValue": "2",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 3,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 3,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 3,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE A",
                    "idValue": "4",
                    "rowSpan": 3,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "20.00",
                    "idValue": "20.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "2",
                    "idValue": "2",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 4,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 4,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 4,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE A",
                    "idValue": "4",
                    "rowSpan": 4,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "25.00",
                    "idValue": "25.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "1",
                    "idValue": "1",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 5,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 5,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 5,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE B",
                    "idValue": "5",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "4.00",
                    "idValue": "4.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "1",
                    "idValue": "1",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 6,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 6,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 6,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE B",
                    "idValue": "5",
                    "rowSpan": 2,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "10.00",
                    "idValue": "10.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "1",
                    "idValue": "1",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 7,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 7,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 7,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE B",
                    "idValue": "5",
                    "rowSpan": 3,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "15.00",
                    "idValue": "15.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "1",
                    "idValue": "1",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 8,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 8,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 8,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE B",
                    "idValue": "5",
                    "rowSpan": 4,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "25.00",
                    "idValue": "25.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "1",
                    "idValue": "1",
                    "visible": true,
                    "readOnly": true
                }
            ]
        },
        {
            "row": 9,
            "visible": true,
            "readOnly": true,
            "drillThrough": [],
            "cells": [
                {
                    "column": 0,
                    "type": "R",
                    "subType": "D",
                    "value": "CR",
                    "idValue": "CR",
                    "rowSpan": 9,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 1,
                    "type": "R",
                    "subType": "D",
                    "value": "1",
                    "idValue": "1",
                    "rowSpan": 9,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 2,
                    "type": "R",
                    "subType": "D",
                    "value": "LINE B",
                    "idValue": "5",
                    "rowSpan": 5,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 3,
                    "type": "R",
                    "subType": "D",
                    "value": "30.00",
                    "idValue": "30.00",
                    "rowSpan": 1,
                    "visible": true,
                    "readOnly": true
                },
                {
                    "column": 4,
                    "type": "B",
                    "subType": "B",
                    "value": "2",
                    "idValue": "2",
                    "visible": true,
                    "readOnly": true
                }
            ]
        }
    ],
    "drillThrough": [],
    "properties": {
        "reportColsDefinition": "[{\"coldef_Plant_Id_DS\":[{\"reportColName\":\"Plant_Id_DS\"},{\"reportColVisibility\":\"1\"},{\"reportColsType\":\"String/Text\"},{\"datePattern\":\"yyyy-MM-dd HH:mm:ss.SSS\"},{\"reportColsKey\":\"1\"},{\"reportColsMandatory\":\"1\"},{\"reportColsReadOnly\":\"1\"},{\"reportColInputType\":[{\"reportColsMainId\":\"567713782940342\"},{\"reportColInputDT\":\"Number\"},{\"reportColInputListType\":\"From report\"},{\"reportAssociated\":\"-1\"},{\"reportColInputListId\":\"\"},{\"reportColInputListDs\":\"\"},{\"reportColInputListBinding\":[]},{\"reportColDependsOn\":\"\"},{\"reportColInputListValues\":\"\"},{\"reportColTextMxL\":\"0\"},{\"reportColTextMnL\":\"0\"},{\"reportColTextRgx\":\"\"},{\"reportColNumMin\":\"\"},{\"reportColNumMax\":\"\"}]},{\"reportColInputListDefault\":[\"\"]},{\"reportColsIndex\":\"0\"},{\"reportColsAutoIncrement\":\"0\"}]},{\"coldef_Active_Flag\":[{\"reportColName\":\"Active_Flag\"},{\"reportColVisibility\":\"1\"},{\"reportColsType\":\"Number\"},{\"datePattern\":\"yyyy-MM-dd HH:mm:ss.SSS\"},{\"reportColsKey\":\"1\"},{\"reportColsMandatory\":\"1\"},{\"reportColsReadOnly\":\"1\"},{\"reportColInputType\":[{\"reportColsMainId\":\"567713782940342\"},{\"reportColInputDT\":\"Number\"},{\"reportColInputListType\":\"From report\"},{\"reportAssociated\":\"-1\"},{\"reportColInputListId\":\"\"},{\"reportColInputListDs\":\"\"},{\"reportColInputListBinding\":[]},{\"reportColDependsOn\":\"\"},{\"reportColInputListValues\":\"\"},{\"reportColTextMxL\":\"0\"},{\"reportColTextMnL\":\"0\"},{\"reportColTextRgx\":\"\"},{\"reportColNumMin\":\"\"},{\"reportColNumMax\":\"\"}]},{\"reportColInputListDefault\":[\"\"]},{\"reportColsIndex\":\"1\"},{\"reportColsAutoIncrement\":\"0\"}]},{\"coldef_PO_Line_Id1\":[{\"reportColName\":\"PO_Line_Id1\"},{\"reportColVisibility\":\"1\"},{\"reportColsType\":\"String/Text\"},{\"datePattern\":\"yyyy-MM-dd HH:mm:ss.SSS\"},{\"reportColsKey\":\"1\"},{\"reportColsMandatory\":\"1\"},{\"reportColsReadOnly\":\"1\"},{\"reportColInputType\":[{\"reportColsMainId\":\"567713782940342\"},{\"reportColInputDT\":\"Number\"},{\"reportColInputListType\":\"From report\"},{\"reportAssociated\":\"-1\"},{\"reportColInputListId\":\"\"},{\"reportColInputListDs\":\"\"},{\"reportColInputListBinding\":[]},{\"reportColDependsOn\":\"\"},{\"reportColInputListValues\":\"\"},{\"reportColTextMxL\":\"0\"},{\"reportColTextMnL\":\"0\"},{\"reportColTextRgx\":\"\"},{\"reportColNumMin\":\"\"},{\"reportColNumMax\":\"\"}]},{\"reportColInputListDefault\":[\"\"]},{\"reportColsIndex\":\"2\"},{\"reportColsAutoIncrement\":\"0\"}]},{\"coldef_Stop_Duration\":[{\"reportColName\":\"Stop_Duration\"},{\"reportColVisibility\":\"1\"},{\"reportColsType\":\"Number\"},{\"datePattern\":\"yyyy-MM-dd HH:mm:ss.SSS\"},{\"reportColsKey\":\"1\"},{\"reportColsMandatory\":\"1\"},{\"reportColsReadOnly\":\"1\"},{\"reportColInputType\":[{\"reportColsMainId\":\"567713782940342\"},{\"reportColInputDT\":\"Number\"},{\"reportColInputListType\":\"From report\"},{\"reportAssociated\":\"-1\"},{\"reportColInputListId\":\"\"},{\"reportColInputListDs\":\"\"},{\"reportColInputListBinding\":[]},{\"reportColDependsOn\":\"\"},{\"reportColInputListValues\":\"\"},{\"reportColTextMxL\":\"0\"},{\"reportColTextMnL\":\"0\"},{\"reportColTextRgx\":\"\"},{\"reportColNumMin\":\"\"},{\"reportColNumMax\":\"\"}]},{\"reportColInputListDefault\":[\"\"]},{\"reportColsIndex\":\"3\"},{\"reportColsAutoIncrement\":\"0\"}]},{\"coldef_Stop_Count_Sum\":[{\"reportColName\":\"Stop_Count_Sum\"},{\"reportColVisibility\":\"1\"},{\"reportColsType\":\"Number\"},{\"datePattern\":\"yyyy-MM-dd HH:mm:ss.SSS\"},{\"reportColsKey\":\"0\"},{\"reportColsMandatory\":\"0\"},{\"reportColsReadOnly\":\"1\"},{\"reportColInputType\":[{\"reportColsMainId\":\"567713782940342\"},{\"reportColInputDT\":\"Number\"},{\"reportColInputListType\":\"From report\"},{\"reportAssociated\":\"-1\"},{\"reportColInputListId\":\"\"},{\"reportColInputListDs\":\"\"},{\"reportColInputListBinding\":[]},{\"reportColDependsOn\":\"\"},{\"reportColInputListValues\":\"\"},{\"reportColTextMxL\":\"0\"},{\"reportColTextMnL\":\"0\"},{\"reportColTextRgx\":\"\"},{\"reportColNumMin\":\"\"},{\"reportColNumMax\":\"\"}]},{\"reportColInputListDefault\":[\"\"]},{\"reportColsIndex\":\"4\"},{\"reportColsAutoIncrement\":\"0\"}]}]",
        "reportEditingGrants": "ENABLE:ALL;",
        "data-deletion-message": "",
        "task-enabled": "false",
        "discussion-enabled": "false"
    }
}
```
{% endcode %}
