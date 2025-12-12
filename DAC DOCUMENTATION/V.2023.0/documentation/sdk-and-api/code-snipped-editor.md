---
description: >-
  DAC has a module that allows users to create Java code snippets using DAC
  objects.
---

# Code Snippet

DAC has a module that allows users to create Java code snippets using DAC objects.

With a few lines of code, you can create code snippets that allow you to use DAC objects, such as reports, notifications, alerts, etc.

These code snippets are developed in the _Eclipse_ environment, and are then saved in DAC as **Code Snippet** objects; these are then used in DAC in several ways:

* as **Listener**, configured on the application, to which the Code Snippet objects are associated (for the _configuration see Application properties_).

Listeners receive messages in the form of HTTP requests that they then process, according to the code snippet. Messages can be sent from DAC, for management from any system that can send a query in HTTP mode. The format for the HTTP query is:

```url
http://<host>:<port>/<weburl>/cassiopeaWeb/misc/http/httpReceiver.jsp.cas?
revent=1&csUsrn=<user>&csPass=<password>[&parameter=value]
```

The parameters of the HTTP query will be available as attributes in context of the execution of the _Code Snippet._ In `[& parameteri=valuei]` you can add the parameters necessary for executing the Code Snippet.

* associated with **command** buttons on the mashboard
* when setting schedules with the _Scheduler_ module

The module used to create code snippets is **Code Snippet editor**, which can be accessed from the **Application** menu ite&#x6D;**:**

![](<../../.gitbook/assets/0 (13).png>)

A Code Snippet can be created in one of two ways:

* creating a Blank Code Snippet
* creating a Code Snippet from a default template.

A few possible uses for Code Snippets are suggested in DAC default templates, and are described in the code of the template itself.

After selecting one of the default templates, or a new _blank_ code snippet, you access the development environment (Eclipse) where you can make changes to the code snippet. JAVA 6 is the version used for the code snippet.

With the _**auto-save-on-edit**_ property, changes made to the code in the development environment are automatically saved. When Eclipse is closed, the Code Snippet object automatically closes too, with all the changes made in the development environment.

{% hint style="info" %}
The **Janino** compiler is used to compile this Java code. Not all the features of the Java programming language are implemented by the Janino compiler. For a list of the limitations, please visit this site [http://janino-compiler.github.io/janino/](http://janino-compiler.github.io/janino/).
{% endhint %}



## Return Parameters of a Code Snippet Invoked via REST

While implementing a code snippet invoked via REST, three attributes are available which assist a response result.

* **PROGRAM\_RESULT:** JAVA object that the code snippet may return as result of the invocation. For example, you can populate a JAVA object which will count the response.
* **PROGRAM\_ERROR:** JAVA object useful for capturing any error information in case the code snippet fails to execute.
* **HTTP\_STATUS**: lets you set the code of the http response invoked via REST. The parameter is optional.

For the default response states, the methods of invocation and the format of the response, refer to the REST API Documentation.

The PROGRAM\_RESULT and PROGRAM\_ERROR objects are included in the serialized response in JSON format through the google/gson library.

In order to display the fields in the objects, it is necessary to use the @Expose note

Below are some application examples.

### **Example of Using the PROGRAM\_ERROR and HTTP\_STATUS Parameter**

{% code lineNumbers="true" %}
```java
package com.decisyon.devEnv;
import it.decisyon.ext.program.ExtIDecisyonProgram;
import it.decisyon.ext.program.context.ExtProgramOutputContextEnum;
import it.decisyon.ext.program.context.IExtProgramExecutionContext;
import it.decisyon.ext.sdk.api.INotificationMailSDK;
import it.decisyon.ext.sdk.impl.SdkPersistence;
import it.decisyon.ext.sdk.impl.SdkWinged;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;
import java.util.HashMap;
import java.util.Map;
/**
 * Sample program of an empty template.
 * The class implements the execute method of the ExtIDecisyonProgram object that takes
 * a context as a parameter.
 */
public class WorkFile implements ExtIDecisyonProgram {
    private SdkPersistence sdkPersistence = null;
    private SdkWinged sdkWinged = null;
    private INotificationMailSDK notification;
    public void execute(IExtProgramExecutionContext context) throws Exception {
        ExtLoggerSDK.debug("Program Start");
        // program param error
        Map < String, Object > error = new HashMap < String, Object > ();
        error.put("myError", "errValue");
        error.put("myErrorDetail", "errDetail");
        error.put("myErrorOther", "errOther");
        context.setResultAttribute(ExtProgramOutputContextEnum.PROGRAM_ERROR.name(), error);
        context.setResultAttribute(ExtProgramOutputContextEnum.HTTP_STATUS.name(), new Integer(1007));
        ExtLoggerSDK.debug("Program End");
    }
}
```
{% endcode %}



**Example of PROGRAM\_RESULT**

{% code lineNumbers="true" %}
```java
package com.decisyon.devEnv;
import it.decisyon.ext.program.ExtIDecisyonProgram;
import it.decisyon.ext.program.context.ExtProgramOutputContextEnum;
import it.decisyon.ext.program.context.IExtProgramExecutionContext;
import it.decisyon.ext.sdk.api.INotificationMailSDK;
import it.decisyon.ext.sdk.impl.SdkPersistence;
import it.decisyon.ext.sdk.impl.SdkWinged;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;
import java.util.HashMap;
import java.util.Map;
/**
 * Sample program of an empty template.
 * The class implements the execute method of the ExtIDecisyonProgram object that takes
 * a context as a parameter.
 */
public class WorkFile implements ExtIDecisyonProgram {
    private SdkPersistence sdkPersistence = null;
    private SdkWinged sdkWinged = null;
    private INotificationMailSDK notification;
    public void execute(IExtProgramExecutionContext context) throws Exception {
        ExtLoggerSDK.debug("Program Start");
        // param program result
        Map < String, Object > result = new HashMap < String, Object > ();
        result.put("myAttribute", "myValue");
        context.setResultAttribute(ExtProgramOutputContextEnum.PROGRAM_RESULT.name(), result);
        ExtLoggerSDK.debug("Program End");
    }
}
```
{% endcode %}





### Example of PROGRAM\_RESULT and PROGRAM\_ERROR

{% code lineNumbers="true" %}
```java
package com.decisyon.devEnv;
import it.decisyon.ext.program.ExtIDecisyonProgram;
import it.decisyon.ext.program.context.ExtProgramOutputContextEnum;
import it.decisyon.ext.program.context.IExtProgramExecutionContext;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;
import java.util.HashMap;
import java.util.Map;
/**
 * Sample program of an empty template.
 * The class implements the execute method of the ExtIDecisyonProgram object that takes
 * a context as a parameter.
 */
public class WorkFile implements ExtIDecisyonProgram {
    public void execute(IExtProgramExecutionContext context) throws Exception {
        ExtLoggerSDK.debug("Program Start");
        //parameters return as result of the program execution
        Map < String, Object > result = new HashMap < String, Object > ();
        result.put("myAttribute", "myValue");
        context.setResultAttribute(ExtProgramOutputContextEnum.PROGRAM_RESULT.name(), result);
        // param program error
        Map < String, Object > error = new HashMap < String, Object > ();
        error.put("myError", "errValue");
        error.put("myErrorDetail", "errDetail");
        error.put("myErrorOther", "errOther");
        context.setResultAttribute(ExtProgramOutputContextEnum.PROGRAM_ERROR.name(), error);
        ExtLoggerSDK.debug("Program End");
    }
```
{% endcode %}





### Example of Program Result that returns a custom Java object

{% code lineNumbers="true" %}
```java
import it.decisyon.ext.program.context.ExtProgramOutputContextEnum;
import it.decisyon.ext.program.context.IExtProgramExecutionContext;
import it.decisyon.ext.sdk.api.INotificationMailSDK;
import it.decisyon.ext.sdk.impl.SdkPersistence;
import it.decisyon.ext.sdk.impl.SdkWinged;
import it.decisyon.ext.sdk.impl.logger.ExtLoggerSDK;
import java.util.HashMap;
import java.util.Map;
import com.google.gson.annotations.Expose;
/**
 * Sample program of an empty template.
 * The class implements the execute method of the ExtIDecisyonProgram object that takes
 * a context as a parameter.
 */
public class WorkFile implements ExtIDecisyonProgram {
    private SdkPersistence sdkPersistence = null;
    private SdkWinged sdkWinged = null;
    private INotificationMailSDK notification;
    public void execute(IExtProgramExecutionContext context) throws Exception {
        ExtLoggerSDK.debug("Program Start");
        // Program result
        TestBean1 tb1 = new TestBean1();
        context.setResultAttribute(ExtProgramOutputContextEnum.PROGRAM_RESULT.name(), tb1);
        ExtLoggerSDK.debug("Program End");
    }
    private class TestBean1 {
        @Expose
        private String attr1;
        @Expose
        private Integer attr2;
        @Expose
        private Boolean attr3;
        @Expose
        private Map < String, TestBean2 > attr4;
        public TestBean1() {
            this.attr1 = "this is a test text";
            this.attr2 = 12;
            this.attr3 = true;
            this.attr4 = new HashMap < String, TestBean2 > ();
            this.attr4.put("key1", new TestBean2("1", 1 L));
            this.attr4.put("key2", new TestBean2("2", 2 L));
            this.attr4.put("key3", new TestBean2("3", 3 L));
        }
    }
    private class TestBean2 {
        @Expose
        private String field1;
        @Expose
        private Long field2;
        public TestBean2(String field1, Long field2) {
            this.field1 = field1;
            this.field2 = field2;
        }
    }
}
```
{% endcode %}



## Blank Code Snippet

The **New** item allows you to create a blank code snippet whose code contains the **WorkFile** class, with the following methods:

* **execute**, which receives the context and contains the code for the operations executed by the object _Program_
* **main,** executed during testing/debugging; this calls the execute method, to which the metadata context, appropriately created, is transferred

![](<../../.gitbook/assets/1 (16).png>)

The code begins by importing DAC object classes.

## Default Templates

To create a Code Snippet from a default template, right-click after positioning the cursor on the _Root_ item.

![](<../../.gitbook/assets/2 (25).png>)

The Template item produces a list of available templates. When one of the templates is selected, a Code Snippet is created whose code, like that of a blank code snippet, includes the WorkFile class, with the main and execute methods: the latter includes the operations that will be executed by the Code Snippet object and are described in the comments of the code itself.

## Accessing the Development Environment

The development environment is accessed through the button, which opens **Eclipse** on the class associated with the _Code Snippet_ object.

In this environment you can change and save the class. When Eclipse is closed, the modified Java class will be shown in the _Code Snippet._

![](<../../.gitbook/assets/3 (28).png>)

The command button ![](<../../.gitbook/assets/4 (16).png>) allows you to restore Eclipse default configurations (such as Java or DAC libraries)

By clicking the ![](<../../.gitbook/assets/5 (9).png>) button, you can restore the initial Workspace situation, deleting any files and folders, and leaving the Java class associated with the _Code Snippet_ unchanged.
