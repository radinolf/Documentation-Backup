# How consume the response of a POST request in a DAC page

In this example we will see how to how consume the response of a POST request in a DAC page.

In this example the invoked API search a country by name and, if the country exists, returns a JSON with detailed information about the country itself. In the page we will display the response code and body of the HTTP request.

The API used is the following:

`https://restcountries.com/v3.1/name/{name}`

The parameter “name” will be the parameter of the request and the value will input by the user from a page “text field” widget.

### **Overview of the final result** <a href="#overview-of-the-final-result" id="overview-of-the-final-result"></a>

Let's see in detail the final result of the page.

![](<../../../.gitbook/assets/image (892).png>)

The page consists of four widgets . When the API request is executed the **Execute button** the value input in the ' **Enter the Country to use in the API' field** will be passed to the API via the Name parameter “[_**https://restcountries.com/v3.1/name/{name}**_](https://restcountries.com/v3.1/name/%7Bname%7D)”.

The two **API fields BOBY RESPONSE** and **API RESPONE STATUS** will show the API response, in JSON format, and the status of the response. See image below.

![](<../../../.gitbook/assets/image (136).png>)

&#x20;

### **How to Configure API** <a href="#how-to-configure-api" id="how-to-configure-api"></a>

To create a new API you use the RunTime Rest API Client under the Administration section.

&#x20;

![](<../../../.gitbook/assets/image (548).png>)

&#x20;

{% hint style="info" %}
Remember that to use the Rest API Client you must be an Administrator. Rest API Client LINK
{% endhint %}

In these example a new API named Retrive Capita has been created and the API explained above has been passed in the GET field:[_**https://restcountries.com/v3.1/name/{name}**_](https://restcountries.com/v3.1/name/%7Bname%7D)”.

### **How to build the page** <a href="#how-to-build-the-page" id="how-to-build-the-page"></a>

Below we can see which are the widgets with which the page was built.

&#x20;

![](<../../../.gitbook/assets/image (440).png>)

### **How to configure the widgets.** <a href="#how-to-configure-the-widgets." id="how-to-configure-the-widgets."></a>

In this part of the example we will analyze how to configure the main properties for each widget .

&#x20;

#### **Widget - TextField** <a href="#widget-textfield" id="widget-textfield"></a>

&#x20;

![](<../../../.gitbook/assets/image (433).png>)

**Wdg-textfile :** this widget allows us to insert the country name on page.

**Base Name:** It used to compose the parameters to import and Export in the page. In this example is named _country_

#### **Widget - Text Area** <a href="#widget-text-area" id="widget-text-area"></a>

&#x20;

![](<../../../.gitbook/assets/image (695).png>)

The Text Area widget will display the API result in JSON format. In this widget we are going to set the parameter name from the param base name property .

* **param base name:** get\_country\_Response\_Body

{% hint style="info" %}
In order for the response to be displayed in Json del'API the parameter must be configured as follows: _ParamName_ **\_Response\_Body**. Where Response\_Body is a fixed part and must NEVER change while ParamName can be changed.


{% endhint %}

&#x20;

#### **Widget - Text Field** <a href="#widget-text-field" id="widget-text-field"></a>

&#x20;

![](<../../../.gitbook/assets/image (506).png>)

The Text Field widget will display the API response status . In this widget we are going to set the parameter name from the param base name property .

**param base name:** get\_country\_Response\_Status

{% hint style="info" %}
For the response status to be displayed, the parameter must be configured as follows: _ParamName_ **\_Response\_Status** . Where \_ **Response\_Status** is a fixed part and must NEVER change while ParamName can be changed.
{% endhint %}

&#x20;

#### **Widget - Execute Button**  <a href="#widget-execute-button" id="widget-execute-button"></a>

![](<../../../.gitbook/assets/image (195).png>)

The main properties that we are going to configure for this widget are available under the execution group of the Object folder.

&#x20;

![](<../../../.gitbook/assets/image (45).png>)

* **execution-type:** Select REST\_API
  * **api-alias:** select the Api created previously from the drop-down menu (Get Country Details)
  * **api-params-mapping:** identify the mapping of the parameters used by the API REST with the parameters of the Page. in This case the mapping is between the Execute object and Text Fiels

![](<../../../.gitbook/assets/image (775).png>)



*   **mandatory-params:** through this property we will go to it enable the execution of the query only if all the parameters there are valued

    * **parameters** : select the parameter that must be valued for the execution associated to the button to be started. In this example the parameter is Country (define in the Widget TextField)



![](<../../../.gitbook/assets/image (515).png>)

* **javaScript-code-before** Define the javascript code to be run before the execution. In this example two functions are used that will export the API response and status values to the page, stored in the RetriveCapital\_Respomse\_Body and RetriveCapital\_Respomse\_Status parameters ( see Text Field and Text Area Widget definitions )

![](<../../../.gitbook/assets/image (924).png>)
