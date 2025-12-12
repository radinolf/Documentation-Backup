# Known issues

#### Exception during query validation of a sql report <a href="#exception-during-query-validation-of-a-sql-report" id="exception-during-query-validation-of-a-sql-report"></a>

On postgresql environment system shows an exception during query validation of a sql report, this happens because %metadata\_schema% is translated with . and db has a name with “-“ character.

<figure><img src="../../../.gitbook/assets/image (733).png" alt=""><figcaption></figcaption></figure>



### Known issue about extSubscribeEvent

The previous extSubscribeEvent javascript API no longer works since version 2022.1.0 due to a known bug.\
you need to replace the old API extSubscribeEvent with the new API DECISYON.page.subscribeEvent (event, (payload)) where the exception is raised.
