# Known issues

Welcome to the "Known issues" section of DAC!  On this page, you will find a list of known issues present in the current version of the software. Known issues are situations or unexpected behaviors that have been identified and documented by our development team. These issues may include errors, limitations, or unexpected software behavior under certain circumstances. It is important to consult this list to be aware of any known limitations or issues that may affect the use of the software. If you encounter any of the listed issues, you can find information on any temporary workarounds or future updates that will address the problem. Our development team is continuously working to resolve these issues and provide an improved user experience.

#### Exception during query validation of a sql report <a href="#exception-during-query-validation-of-a-sql-report" id="exception-during-query-validation-of-a-sql-report"></a>

On postgresql environment system shows an exception during query validation of a sql report, this happens because %metadata\_schema% is translated with . and db has a name with “-“ character.

<figure><img src="../../../.gitbook/assets/image (543).png" alt=""><figcaption></figcaption></figure>



### Known issue about extSubscribeEvent

The previous extSubscribeEvent javascript API no longer works since version 2022.1.0 due to a known bug.\
you need to replace the old API extSubscribeEvent with the new API DECISYON.page.subscribeEvent (event, (payload)) where the exception is raised.
