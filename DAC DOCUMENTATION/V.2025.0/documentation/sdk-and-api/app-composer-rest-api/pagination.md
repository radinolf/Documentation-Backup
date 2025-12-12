# Pagination

## Introduction

Pagination in API is a mechanism used to divide large datasets into more manageable blocks called **pages**. This allows developers to retrieve data in smaller chunks instead of receiving the entire dataset in a single request.&#x20;



<img src="../../../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">

Pagination for DAC APIs is a keyset-based pagination, where you specify sorting and page size to retrieve results based on an orderable key.

Some DAC APIs allow you to set pagination. When accessing the Swagger documentation, if pagination is available, you will find a section called "**Paginable**" at the bottom, which indicates the required values to correctly paginate the data returned by the API.

<figure><img src="../../../.gitbook/assets/image (2060).png" alt=""><figcaption></figcaption></figure>

For instance, the configuration below indicates that the request will returns 2 elements from page number 2 (page numbering begins at 0).

```json
{
"page":1,
"size":2,
"sort":[
    "string"
    ]
}
```

## Pagination settings

In the diagram below we can see how the parameters interact in the pagination of an API.

Below the diagram illustrating how to configure pagination parameters to display a specific data set (`size`) on a designated page (`page`) while maintaining sorting (`sort`).&#x20;



<figure><img src="../../../.gitbook/assets/image (202).png" alt=""><figcaption></figcaption></figure>

<img src="../../../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">

#### **Set of Data**  &#x20;

Array = \["A", "B", "C", "D", "E", "F", "G"];

#### **Pagination settings**    &#x20;

```json
{ 
     "page": 1, 
     "size": 4, 
      "sort": [ "string,ASC" ] 
}
```

{% hint style="success" %}
The value "string" can be replaced with a specific field of the JSON on which the data will be sorted. Please see the details in the section [Sort](pagination.md#sort).
{% endhint %}



#### **Subdivision of Data**

<figure><img src="../../../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

Subdivision of Data (**size= 4**) per page. The total number of pages is 2

#### **Resut**&#x20;

<figure><img src="../../../.gitbook/assets/image (192).png" alt=""><figcaption></figcaption></figure>

The result are the value presents in the page 1 (page=1)

{% hint style="success" %}
For further details regarding the **total number** of pages and **total elements** in the JSON file, and to understand how to interpret the JSON data correctly, we invite you to refer to the dedicated section in the document [Format of Respponse](format-of-response.md).
{% endhint %}

## Detail of the parameters

Now let's look closely at what each variable contains.

### Size

The `size` parameter is crucial during pagination as it determines the number of items displayed per page. This parameter specifies how many elements (or results) will be shown in a single page.

For example if you set `size=4` it means you want to display up to 4 elements per page.

<figure><img src="../../../.gitbook/assets/image (2071).png" alt="" width="333"><figcaption></figcaption></figure>

### **Page**

The `page` parameter indicates the page number of the items you want to display.&#x20;

For example, if you set `page=1` you are requesting to display the results of the second page.

<figure><img src="../../../.gitbook/assets/image (2075).png" alt="" width="348"><figcaption></figcaption></figure>

{% hint style="info" %}
The page numbering in the DAC API responses starts from 0 instead of 1.

You can also learn about both the elements and the pages consulted in the variables in the JSON file. For more details click [here](format-of-response.md).
{% endhint %}

### **Sort**

This parameter allows you to sort the results based on a specific criterion. By default, the value is set to \["string"] to sort the results based on a string. The value "string" can be replaced with a specific field of the JSON on which the data will be sorted. The sort parameter can also accept the values "DESC" for descending order (from highest to lowest) and "ASC" for ascending order (from lowest to highest).



The JSON example shown below contains a simple data structure represented by an array of objects, each with a "Name"  and "code" field that has different values.

```json
[
    {
        "Name": "A",
        "code": "001"
    },
    {
        "Name": "B",
        "code": "002"
    },
    {
        "Name": "C",
        "code": "003"
    },
    {
        "Name": "D",
        "code": "004"
    }
]
```

#### Example of ascending ordering (ASC)

We sort the data by the "Name" field in ascending alphabetical order. The sort parameter will be set to "ASC".

```json

{ 
     "page": 0, 
     "size": 4, 
      "sort": [ "Name,ASC" ] 
}
```

After sorting, the array will remain in the same order, as the data is already sorted alphabetically:

<figure><img src="../../../.gitbook/assets/image (2084).png" alt="" width="427"><figcaption></figcaption></figure>

#### Example of descending ordering (DESC)

Se invece volessimo ordinare i dati in ordine alfabetico decrescente, imposteremmo il parametro di ordinamento su "DESC":

If we want sort the data by the "Name" field in descending alphabetical order. The sort parameter will be set to "DESC".

```json
{ 
     "page": 0, 
     "size": 4, 
      "sort": [ "Name,DESC" ] 
}
```

After sorting, the array will be rearranged as follows:

<figure><img src="../../../.gitbook/assets/image (2083).png" alt="" width="410"><figcaption></figcaption></figure>

