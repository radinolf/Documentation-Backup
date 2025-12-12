# Example 1: Creating the First Snippet

In this example, you will learn how to create a simple snippet in App Composer and execute it using an execute button widget.&#x20;

The objective is to introduce you to the basic process of creating and associating a snippet with UI elements in App Composer, such as an execute button.&#x20;

This example will demonstrate how to pause execution for a set time (10 seconds) and log messages before and after the waiting period.

## Creating the Snippet in App Composer

1. Open Design Studio and open the Snippet Editor.
2. Create a new snippet and call it "_Example 1 - pause execution_".
3. Copy the code provided below
4. Enable the `auto-save-on-edit` property to automatically save the snippet while editing.
5. Click the **Save** button.

{% code title="Java code to copy in the snippet editor" lineNumbers="true" fullWidth="true" %}
```java
package snippet;

import it.decisyon.ext.program.*; 
import it.decisyon.ext.program.context.IExtProgramExecutionContext; 
import it.decisyon.ext.sdk.PASSWORD_TYPE;
import it.decisyon.ext.sdk.SdkEnvironment;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;

public class Snippet implements ExtIDecisyonProgram {

    // This method contains the logic that will be executed when the snippet is triggered.
    public void execute(IExtProgramExecutionContext context) throws Exception { 
        
        // Set the number of seconds to wait before completing execution.
        int secondsToWait = 10;

        // Log a debug message indicating the start of the wait.
        ExtLoggerSDK.debug("Waiting for " + secondsToWait + " seconds...");

        // Convert the wait time from seconds to milliseconds.
        long millisecondsToWait = secondsToWait * 1000;

        // Pause execution for the specified time (10 seconds in this case).
        Thread.sleep(millisecondsToWait);

        // Log a debug message indicating that the waiting is done.
        ExtLoggerSDK.debug("Done waiting!");
    }

    // This main method can be used for testing the snippet locally.
    public static void main(String[] args) throws Exception{ 

        String user          = "<username>";
        String passwordCrypt = "P1nowleGxt99uDrxwYKklA==";
        String owner         = "THM9DGR";
        String url           = "jdbc:postgresql://<host>:5432/<db_name>?currentSchema=appcomposer_md";
        String dbType        = "POSTGRESQL";

        // Set up a Decisyon environment for testing.
        SdkEnvironment sdk = new SdkEnvironment(user, passwordCrypt, owner, url, dbType);

        // Create a fake context for simulating parameters passed to the snippet.
        IExtProgramExecutionContext context = sdk.createContext(PASSWORD_TYPE.CRYPT);

        // Set some parameters for testing purposes (optional).
        context.setAttribute("parameterName", "value");

        // Instantiate the snippet and execute it with the fake context.
        Snippet workFile = new Snippet();
        workFile.execute(context);
    }
}
```
{% endcode %}

Open the **Snippet Code Editor** from the Design Studio, creates a **new Snippet Code** and selects the **auto-save-on-edit** property to automatic save the file.

<figure><img src="../../../../.gitbook/assets/image (1802).png" alt=""><figcaption></figcaption></figure>

## Associating the Snippet with a Button Widget

After creating and saving the snippet, you'll now create a page in App Composer where an "Execute" button triggers the snippet.

1. Create a New Page In the Design Studio
2. Add an "Execute Button" widget
3. Set the property `execution-type = CODE_SNIPPET`
4. In the property `code-snippet` select the snippet you created
5. Save and publish the page.

<figure><img src="../../../../.gitbook/assets/image (1081).png" alt=""><figcaption></figcaption></figure>

## Test the page

Open the page from web and click on the button. You will notice that the button is running as the spinner appears: after 10 seconds (set in the snippet), the execution stops.

<figure><img src="../../../../.gitbook/assets/image (1046).png" alt=""><figcaption></figcaption></figure>

Now download the Log from the web administration page:

<figure><img src="../../../../.gitbook/assets/image (1811).png" alt=""><figcaption></figcaption></figure>

You will notice that when the snippet is executed, the log file print the string _`Waiting for 10 seconds...`_ comes printed . After 10 seconds the _`Done Waiting!`_ string is printed in the log.





