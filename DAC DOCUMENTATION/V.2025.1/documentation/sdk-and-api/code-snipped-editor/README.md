---
description: >-
  DAC has a module that allows users to create Java code snippets using DAC
  objects.
---

# Code Snippet

## Introduction to Snippets  <a href="#what-is-a-snippet-ok" id="what-is-a-snippet-ok"></a>

**Snippets** are small, customizable pieces of Java code that extend the functionality of App Composer.&#x20;

They provide application developers with the flexibility to add custom logic to the applications without modifying the platform.

Snippets can be triggered in different ways: through widgets in the page, such as execute buttons or via REST API. This capability allows developers to integrate more complex logic, connect external systems or automate tasks within App Composer.

By leveraging snippets, app. developers can solve specific application needs while maintaining a high degree of control and customization in how the flow and the process are executed.&#x20;

The editor used to create the snippets of code is the **Code Snippet Editor**, accessible from the menu item **Application.**

<figure><img src="https://1992103909-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2Fdac-documentatin-home%2F-MifFsBi8ofIITvYfugw%2F-MifFzR5UTNiIt4YejeZ%2F0.png?generation=1630665964560949&#x26;alt=media" alt=""><figcaption></figcaption></figure>

A snippet of code can be created starting from a snippet of code empty.

After selecting a new blank code snippet, you can open the IDE[^1] environment (Eclipse) where you can write your code.

## Creating Snippet  <a href="#creating-and-using-a-snippet" id="creating-and-using-a-snippet"></a>

When creating a new snippet, DAC provides a predefined script designed to be extended with additional features, such as sending email notifications or interacting with data persistence. Thanks to its structure, it allows for easy expansion to meet specific use cases.&#x20;

Developers can add logs or implement further business logic to support more complex use cases.

<figure><img src="../../../.gitbook/assets/image (2253).png" alt=""><figcaption></figcaption></figure>

The provided template is an example of a blank program with an execution method that is used within the DAC framework. In the example Snippet, it creates a class called **`Snippet`**, which implements the **`ExtIDecisyonProgram`**&#x69;nterface.

**1.Imports**\
The code imports several classes and interfaces from the Decisyon SDK, including:

* **`it.decisyon.ext.program.*`** and **`context.IExtProgramExecutionContext`**: These allow the creation of executable programs that can be integrated into Decisyon.
* **`ExtLoggerSDK`**: Provides logging capabilities.

**2. Snippet Class**\
The **`Snippet`** class implements the **`ExtIDecisyonProgram`** interface, so it must provide a definition for the **`execute`** method that accepts a context (**`IExtProgramExecutionContext`**).

```java
javaCopia codicepublic class Snippet implements ExtIDecisyonProgram { 
    private SdkPersistence sdkPersistence = null;
    private SdkWinged sdkWinged = null;
    private INotificationMailSDK notification;

    public void execute(IExtProgramExecutionContext context) throws Exception { 
        ExtLoggerSDK.debug("Program creation");
    }
}
```

* **Variables**: Some variables are declared, like `sdkPersistence`, `sdkWinged`, and `notification`, though they are not used in the body of the **`execute`** method (they might be used in future extensions).
* **`execute` Method**: This method is mandatory as defined by the **`ExtIDecisyonProgram`** interface. It currently performs only a logging operation ("Program creation") but can be extended to include custom logic.

**3. Main Method**\
The **`main`** method is used only for testing and debugging. It sets up a simulated execution environment and invokes the **`execute`** method with a context.

```java
javaCopia codicepublic static void main(String[] args) throws Exception { 
    String user          = "User";
    String passwordCrypt = "passwordCrypt";
    String owner         = "owner";
    String url           = "url";
    String dbType        = "dbType";

    /* Set up the Decisyon environment for testing */
    SdkEnvironment sdk = new SdkEnvironment(user, passwordCrypt, owner, url, dbType);

    /* Create a fake context setting up the mode in which the password has been passed through */
    IExtProgramExecutionContext context = sdk.createContext(PASSWORD_TYPE.CRYPT);

    /* Simulate external parameters being passed */
    context.setAttribute("parameterName", "value");

    Snippet workFile = new Snippet();
    workFile.execute(context);
}
```

* **Variables**: Some sample variables, such as `user`, `passwordCrypt`, `owner`, `url`, and `dbType`, simulate the configuration parameters for the SDK environment.
* **SDK Environment**: Creates an instance of the Decisyon SDK environment, which simulates an execution context with credentials and database connections.
* **Execution Context**: The **`IExtProgramExecutionContext`** is configured to pass simulated parameters, with the option to choose whether passwords should be encrypted or decrypted (**`PASSWORD_TYPE.CRYPT`**).
* **Simulating Parameters**: For testing and debugging purposes, it is possible to simulate the reception of external parameters (e.g., from a dashboard) by setting an attribute in the context.

### Full snippet&#x20;

<pre class="language-javascript" data-full-width="true"><code class="lang-javascript">package snippet; 
<strong>
</strong>import it.decisyon.ext.program.*; 
import it.decisyon.ext.program.context.IExtProgramExecutionContext; 
import it.decisyon.ext.sdk.PASSWORD_TYPE;
import it.decisyon.ext.sdk.SdkEnvironment;
import it.decisyon.ext.sdk.api.INotificationMailSDK;
import it.decisyon.ext.sdk.impl.SdkPersistence; 
import it.decisyon.ext.sdk.impl.SdkWinged;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;

 
/**
 *  Sample program of an empty template.
 *  The class implements the execute method of the ExtIDecisyonProgram object that takes
 *  a context as a parameter.
 */
public class Snippet implements ExtIDecisyonProgram { 
	
	private SdkPersistence sdkPersistence = null;
	private SdkWinged sdkWinged = null;
	
	private INotificationMailSDK notification;

	public void execute(IExtProgramExecutionContext context) throws Exception { 
		ExtLoggerSDK.debug("Program creation");
	}
	
	/** 
	* This main may be used for testing and debugging. 
	* It creates a context for simulating the parameters passing
	* from external caller. 
	*/	
	public static void main(String[] args) throws Exception{ 

    		String user          = "User";
    		String passwordCrypt = "passwordCrypt";
    		String owner         = "owner";
    		String url           = "url";
    		String dbType        = "dbType";

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

</code></pre>

### Snippet creation  <a href="#creating-and-using-a-snippet" id="creating-and-using-a-snippet"></a>

In the following paragraphs, we will explain how to use and create a snippet in detail. We will explore the following aspects:

1. [**Creating a Snippet:**](./#how-to-create-a-snippet) We will show you the necessary steps to create a new snippet.
2. **Using the snippet in App Composer:** You will see how to use a snippet associating it to a widget[ Execute Button](./#inlineextension-execution-of-a-snippet-through-execute-button). In addition, we will explore the use of the snippet in a [Scheduler](./#inlineextension-use-of-the-snippet-in-a-scheduler) (note that this feature is now deprecated).
3. [**Passage of the parameters in the snippet through demands API**](./#passing-parameters-in-the-snippet-through-rest-api)**:** We will show you how to pass the parameters to the snippet using the API requests.

#### &#x20;How to create a Snippet&#x20;

To create a Snippet it is essential to have installed Eclipse see **Install and configure Eclipse** once you have made sure that Eclipse is installed follow these simple steps:

**Step1** - **New Code Snippet**

<figure><img src="../../../.gitbook/assets/image (779).png" alt=""><figcaption></figcaption></figure>

Open the Snippet Code Editor and create a new Snippet Code from the New button.

In the central panel we have as reference the snippet example of an empty model.

**Step 2** **Open Eclipse**

<figure><img src="../../../.gitbook/assets/image (971).png" alt=""><figcaption></figcaption></figure>

* Select the **Edit** button
* Open **Eclipse** and start the editor

<figure><img src="../../../.gitbook/assets/image (1131).png" alt=""><figcaption></figcaption></figure>

Select the file **Snippet.Java** present under the folder **snippeCode --> src.**

**Step 3- Snippet Code**

<figure><img src="../../../.gitbook/assets/image (899).png" alt=""><figcaption></figcaption></figure>



* Include your java code in the `Snippet.java` file. Make sure to adhere to the correct Java syntax and follow code formatting rules for better readability. Also, remember not to alter the overall structure of the file while inserting the code.
* Click "Save" to confirm the creation of the snippet.

The snippet will be saved in the Eclipse snippet library and you can call it anytime during the development of your project.

With the **auto-save-on-edit** property, changes to the code in the development environment are saved automatically. When Eclipse is closed, the Code Snippet object also closes automatically, with all changes made in the development environment.

## Using a Snippet

### Execute button

To run the snippet via the execution button, simply associate the snippet to the corresponding button.

<figure><img src="../../../.gitbook/assets/image (1540).png" alt=""><figcaption></figcaption></figure>

From the **execution-type** property select **CODE\_SNIPPET** and from the snippet property the snippet created in the Snippet Editor.

### Exporting Parameters in a Page with an Execute Button

To export parameters in a page containing an Execute Button associated with a Snippet, use the following code:

```java
javaCopia codicecontext.setAttribute(
    IExtProgramExecutionContext.EXPORT_PARAM_MAP, 
    Map.of(
        "param1", "val1", 
        "param2", List.of("v1", "v2", ..., "vn"), 
        ..., 
        "paramN", "valN"
    )
);
```

Here’s how it works:

* **`param1` ... `paramN`**: These represent the parameters you want to export.
* Each parameter can be associated with:
  * A single value (e.g., `"val1"`).
  * A list of values (e.g., `List.of("v1", "v2", ..., "vn")`).

If a parameter requires multiple values, you must associate it with a list using `List.of()`.

### **Executing Snippets via API**

Once a snippet is created in App Composer, a REST API endpoint is automatically generated for it. This allows external applications or systems to trigger the snippet easily through an API call. This is particularly useful when third-party systems need to execute custom logic within App Composer without direct interaction with its user interface.

To execute a snippet via the API, authentication is required using either a Bearer token or an API key. This ensures that only authorized users or systems can trigger the snippet.

More information at

{% content-ref url="../app-composer-rest-api/" %}
[app-composer-rest-api](../app-composer-rest-api/)
{% endcontent-ref %}

Here is an example of a REST request that invokes a snippet:

```http
POST /api/rest/application/<owner>/program/<snippet id>/body HTTP/1.1
Host: <host>
Content-Type: application/json
Authorization: Bearer <token>
```

* **\<owner>**: The owner of the application in which the snippet was created.
* **\<snippet\_id>**: The unique identifier of the snippet you want to execute.
* **\<token>**: A valid bearer token for authentication.

You can retrieve the **owner** and **snippet\_id** from the "Metadata Info" panel within the Snippet Editor.

<figure><img src="../../../.gitbook/assets/image (2250).png" alt=""><figcaption></figcaption></figure>

You can also pass custom parameters to the snippet, either as query parameters or in the request body. Here's an example of a POST request with parameters included in the body:

{% code overflow="wrap" %}
```http
POST /api/rest/application/<owner>/program/<snippet id>/body HTTP/1.1
Host: <host>
Content-Type: application/json
Authorization: Bearer <token>
{
	"key1":"value1",
	"key2":"value2"
}
```
{% endcode %}

These key-value pairs will be accessible within the snippet code, allowing you to handle dynamic inputs and customize the behavior of the snippet based on the incoming request.

Within the snippet code, you can define the structure and content of the response body. This allows you to return specific data or results from the snippet execution, making it possible to interact with external systems and exchange information seamlessly. For example, after processing the request, the snippet can return a success message, computed results, or any other relevant output.

## Logs and debug

The result of a snippet is recorded in the DAC Log.

In the folder containing the [Logs ](../../introduction/application/appcomposer/general-info.md#log)downloaded from the web, there is a **Snippet** file that contains and the logs of snippet executions.

<figure><img src="../../../.gitbook/assets/image (1600).png" alt=""><figcaption></figcaption></figure>

In order to write rows in the log file it is necessary to use the following method inside the Snippet

```java
ExtLoggerSDK.debug("<your text>"); 
```

Please see the [Blank Code Snippet](./#blank-code-snippet).

## Limitation and constraints&#x20;

* **Can I import an external library?** No, you cannot import external libraries.&#x20;
* **Should I be aware of how the snippet will be compiled and executed?** No, it is not necessary.&#x20;
* **Must the snippet have specific classes or methods?** (for example, is there a specific way to use the "main")? You need to follow the provided snippet structure.&#x20;
* **Can I use the Spring framework as the developer of the snippet in order to create the code of the snippet?** Yes, you can use the Spring framework as it is included.





[<br>](#user-content-fn-2)[^2] <a href="#install-and-configure-eclipse-ok" id="install-and-configure-eclipse-ok"></a>
---------------------------------------------------------------------------------------------------------------------

[^1]: Integrated Development Environment

[^2]: 
