# Example 2

In this example we will create an API that invokes snippet 8348 passing parameters through a second snippet 8349. The Execution Result will be written in DAC's log.

**Snippet 8348**

```java
package snippet;

import it.decisyon.ext.program.*;
import it.decisyon.ext.program.context.ExtProgramOutputContextEnum;
import it.decisyon.ext.program.context.IExtProgramExecutionContext;
import it.decisyon.ext.sdk.PASSWORD_TYPE;
import it.decisyon.ext.sdk.SdkEnvironment;
import it.decisyon.ext.sdk.api.IIndicatorSDK;
import it.decisyon.ext.sdk.api.INotificationMailSDK;
import it.decisyon.ext.sdk.impl.SdkPersistence;
import it.decisyon.ext.sdk.impl.SdkWinged;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;
import java.util.*;
public class Snippet implements ExtIDecisyonProgram {

    private IIndicatorSDK indicator;
    private SdkPersistence sdkPersistence = null;
    private SdkWinged sdkWinged = null;

    private INotificationMailSDK notification;

    public void execute(IExtProgramExecutionContext context) throws Exception {
    
        String key1Value = context.getAttribute("?key1?").toString();
        String key2Value = context.getAttribute("?key2?").toString();
        
        String result = "{\"key1\":\"" + key1Value + "\"," + "\"key2\":\"" + key2Value + "\"}";
        
        context.setResultAttribute("PROGRAM_RESULT", result);
    }
    /* 
     * This main may be used for testing and debugging. 
     * It creates a context for simulating the parameters passing
     * from external caller. 
     */
    public static void main(String[] args) throws Exception {

        String user = "<username>";
        String passwordCrypt = "Iug57RA7wspVsuNdS0G7cQ==";
        String owner = "J3FFGSC";
        String url = "jdbc:postgresql://<host>:5432/documentation?currentSchema=appcomposer_md";
        String dbType = "POSTGRESQL";

        /* It set up a Decisyon environment for testing */
        SdkEnvironment sdk = new SdkEnvironment(user, passwordCrypt, owner, url, dbType);

        /* Create a fake context setting up the mode in which the password has been passed through (CRYPT or DECRYPT) */
        IExtProgramExecutionContext context = sdk.createContext(PASSWORD_TYPE.CRYPT);

        /* Some programs receive parameters from the outside (from a mashboard, for example) that have to be elaborated. */
        /* For testing and debugging, it possible to simulate this behaviour setting the parameters to the context. */
        context.setAttribute("parameterName", "value");

        Snippet workFile = new Snippet();
        workFile.execute(context);
    }
}
```

The code below shows the code of the snippet in which the association between variables and the parameters coming from the API is made.

```java
public void execute(IExtProgramExecutionContext context) throws Exception {
        
        String key1Value = context.getAttribute("?key1?").toString();
        String key2Value = context.getAttribute("?key2?").toString();
        
        String result = "{\"key1\":\"" + key1Value + "\"," + "\"key2\":\"" + key2Value + "\"}";
        
        context.setResultAttribute("PROGRAM_RESULT", result);
```

`key1Value` the parameter value `? Key1?` sent by API request

`key2Value` the parameter value `? Key1?` sent by API request

`result` the variable will be valorized concatenating the contained values of the parameters

This is the snippet that will be called from the API by passing in the call of the API the OBJECT\_ID of the snippet

<br>

<figure><img src="../../../../.gitbook/assets/image (916).png" alt=""><figcaption></figcaption></figure>

&#x20;**Snippet 8349**

```java
package snippet;

import it.decisyon.ext.program.*;
import it.decisyon.ext.program.context.IExtProgramExecutionContext;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;
import it.decisyon.ext.sdk.PASSWORD_TYPE;
import it.decisyon.ext.sdk.SdkEnvironment;
import it.decisyon.ext.sdk.impl.restapi.ExtRestApiExecutionResult;

import static it.decisyon.ext.sdk.impl.restapi.ExtRestApiDefinerSDK.givenRestApi;

/**
 *   Simple Code Snippet to call a REST API.
 * It is possible to call a REST API using its alias.
 * It is possible to map the value of any parameters defined in the REST API with constant values or parameters present in the execution context of the Code Snippet
 * It is possible to run the REST API and map the result in the execution context of the Code Snippet and in the 'executionResult' object.
 * It is possible to log the result of the execution.
 */
public class Snippet implements ExtIDecisyonProgram {

    private ExtRestApiExecutionResult response = new ExtRestApiExecutionResult();

	public void execute(IExtProgramExecutionContext context) throws Exception {
		ExtLoggerSDK.debug("Code Snippet started");


		givenRestApi()
			.withAlias("Program")
			.withParam("par1")
			.mappedToValue("Texas")
			.withParam("par2")
			.mappedToValue("California")
			.withParam("par3")
			.mappedToValue("Italy")
			.then()
			.execute()
			.and()
			.saveResponseTo(response)
			.and()
			.exposeResponseTo(context)
			.and()
			.log(context);

		ExtLoggerSDK.debug("Code Snippet ended");
	}
	
	/** 
	* This main may be used for testing and debugging. 
	* It creates a context for simulating the parameters passing
	* from external caller. 
	*/	
	public static void main(String[] args) throws Exception{ 

        String user = "<username>";
        String passwordCrypt = "<crypted password>";
        String owner = "J3FFGSC";
        String url = "jdbc:postgresql://<host>:5432/documentation?currentSchema=appcomposer_md";
        String dbType = "POSTGRESQL";

        	/* It set up a Decisyon environment for testing */
     	   SdkEnvironment sdk = new SdkEnvironment(user, passwordCrypt, owner, url, dbType);

     	   /* Create a fake context setting up the mode in which the password has been passed through (CRYPT or DECRYPT) */
    	   IExtProgramExecutionContext context = sdk.createContext(PASSWORD_TYPE.CRYPT);

    	   /* Some programs receive parameters from the outside (from a mashboard, for example) that have to be elaborated. */
    	   /* For testing and debugging, it possible to simulate this behaviour setting the parameters to the context. */
    	   context.setAttribute("parameterName", "value");

    	   Snippet workFile = new Snippet();
    	   workFile.execute(context);
    	}
}

```

In the snippet we have 4 parameters ( `par1, par2,par 3`) where the first three parameters are passed the names of some States. This snippet will pass its parameters to snippet 8348

**API Configuration**

Now let's see how to configure the API

{% tabs %}
{% tab title="HEADERS" %}
<figure><img src="../../../../.gitbook/assets/image (1188).png" alt=""><figcaption></figcaption></figure>

Select the Get method and insert the end point URL

{% code overflow="wrap" %}
```http
https://<application url>/api/rest/application/J3FFGSC/program/programID/body?key1={{par1}}&key2={{par2}}&key2={{par3}}
```
{% endcode %}

Configure the **HEADER** of API:

| Key           | Value                       |
| ------------- | --------------------------- |
| Authorization | Bearer %DAC\_ACCESS\_TOKEN% |
| Accept        | application/json            |
| Content-Type  | application/json            |
{% endtab %}

{% tab title="TEST PARAMETERS" %}
<figure><img src="../../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="336">KEY</th><th width="157.33333333333331">VALUE</th></tr></thead><tbody><tr><td>par1</td><td>Texas</td></tr><tr><td>par2</td><td>California</td></tr><tr><td>par3</td><td>Italy</td></tr></tbody></table>
{% endtab %}

{% tab title="RESPONSE" %}
<figure><img src="../../../../.gitbook/assets/image (1427).png" alt=""><figcaption></figcaption></figure>

After running the API we can view the call response.
{% endtab %}
{% endtabs %}



Let’s see in detail how the API call is structured.

* recall the 8348 snippet by passing the unique ID of the program (`531686559275158`).
* Key 1 is associated to the value par 1&#x20;
* Key 2 is associated to the value par 2
* Key 3 is associated to the value par 3

The result in the log is as follows.

```
https://<application url>/api/rest/application/J3FFGSC/program/531686559275158/body?key1=Texas&key2=California&key2=Italy
```





<br>
