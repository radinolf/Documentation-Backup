# New Feature

**DACXX-1873 \[Meetly] AI-powered Meetings**

The Meeting Notes AI Agent automatically captures and transcribes meeting discussions, ensuring that key decisions, action items, and other important details are accurately recorded. It then organizes the content into structured meeting minutes for easy reference and follow-up.

Please see the Migration Notes

<figure><img src="../../../.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

**D4C-9468 Create the new API for the extStartLoading and extStopLoading JS function**

Implemented a new API that deprecates and replaces the following JavaScript functions:

| API to Replace                       | New API                            | Description                                                                                                                                                                               |
| ------------------------------------ | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p></p><p>extStartLoading</p><p></p> | DECISYON.page.removePageLoading(); | <p><br>Hides the page loading indicator. Call this when you’re done; the indicator is removed once no other loadings are active,helping to avoid visual flicker.</p><p></p>             |
| extStopLoading                       | DECISYON.page.addPageLoading();    | <p>Shows a page loading indicator. Call this to display the indicator.<br>It appears only if it isn’t already visible. Remember to hide it by calling removeLoading() when finished.</p> |

**D4C-10625 Migrate loading handling for TabSelector and TabPanel widgets:** Replaced the old loading spinner with the new page loading on tabpanel.





