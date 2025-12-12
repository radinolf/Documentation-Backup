# Migration Note

## &#x20;**\[Meetly] AI-powered Meetings**

To use the **AI-powered Meetings** widget correctly, the following properties must be added during deployment and startup.

```yaml
appcomposer:
  configuration:
    ai:
      enabled: true
spring:
  ai:
    openai:
      api-key: "Insert API Key"
    
```

## Smart Grid

Starting from version 2025.1.0, using the SmartGrid requires installing SmartGrid 17.0.2.

## New API

A new API has been introduced, replacing the following JavaScript functions. Users relying on these functions should migrate to the new API."

| API to Replace                       | New API                            | Description                                                                                                                                                                               |
| ------------------------------------ | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p></p><p>extStartLoading</p><p></p> | DECISYON.page.removePageLoading(); | <p><br>Hides the page loading indicator. Call this when you’re done; the indicator is removed once no other loadings are active,helping to avoid visual flicker.</p><p></p>             |
| extStopLoading                       | DECISYON.page.addPageLoading();    | <p>Shows a page loading indicator. Call this to display the indicator.<br>It appears only if it isn’t already visible. Remember to hide it by calling removeLoading() when finished.</p> |
