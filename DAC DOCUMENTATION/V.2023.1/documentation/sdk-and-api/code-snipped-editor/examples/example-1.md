# Example 1

In this example you will create a simple snippet executed by an execute button widget. The snippet doesn't execute any complex task, it will be used mostly to show to a snippet can be used in App Composer.&#x20;

The Java class **Interrupted Exception** below, makes the program wait for 10 seconds before printing the message "Done waiting!"



{% code title="Interrupted Exception" overflow="wrap" lineNumbers="true" %}
```java
InterruptedException {
        int secondsToWait = 10;

        ExtLoggerSDK.debug("Waiting for " + secondsToWait + " seconds...");

        // Convert seconds to milliseconds
        long millisecondsToWait = secondsToWait * 1000;

        // Pause the execution for the specified number of milliseconds
        Thread.sleep(millisecondsToWait);

        ExtLoggerSDK.debug("Done waiting!");
```
{% endcode %}

* `int secondsToWait = 10;` An integer variable named `secondsToWait` is declared and assigned the value 10. This variable represents the number of seconds the program will wait.
* `ExtLoggerSDK.debug("Waiting for " + secondsToWait + " seconds...");` The message "Waiting for X seconds..." is printed to the Log, where X is the value stored in the `secondsToWait` variable.
* `long millisecondsToWait = secondsToWait * 1000;` A long variable named `millisecondsToWait` is declared and assigned the value obtained by multiplying `secondsToWait` by 1000. This operation converts the number of seconds to milliseconds.
* `Thread.sleep(millisecondsToWait);` This statement pauses the program's execution for the number of milliseconds specified in the `millisecondsToWait` variable. In this case, the program is paused for 10 seconds.
* `ExtLoggerSDK.debug("Done waiting!");` The message "Done waiting!" is printed in the log file to indicate that the waiting period is over.

Now let’s copy the code, at the top, in the  DAC’s Snippet.

Open the **Snippet Code Editor** from the Design Studio, creates a **new Snippet Code** and selects the **auto-save-on-edit** property to automatic save the file.

<figure><img src="../../../../.gitbook/assets/image (1353).png" alt=""><figcaption></figcaption></figure>

Insert inside the template the class **InterruptedException**, as shown in figure. Then save the Snippet.

<figure><img src="../../../../.gitbook/assets/image (600).png" alt=""><figcaption></figcaption></figure>

Now create a page with a widget Execute Button to which associate the snippet just created.

<figure><img src="../../../../.gitbook/assets/image (632).png" alt=""><figcaption></figcaption></figure>

Open the page from web and click on the button. You will notice that the button is running as the spinner appears: after 10 seconds (set in the snippet), the execution stops.

<figure><img src="../../../../.gitbook/assets/image (597).png" alt=""><figcaption></figcaption></figure>

Now download the Log from the web administration page:

<figure><img src="../../../../.gitbook/assets/image (1362).png" alt=""><figcaption></figcaption></figure>

You will notice that when the snippet is executed, the log file print the string _`Waiting for 10 seconds...`_ comes printed . After 10 seconds the _`Done Waiting!`_ string is printed in the log.





