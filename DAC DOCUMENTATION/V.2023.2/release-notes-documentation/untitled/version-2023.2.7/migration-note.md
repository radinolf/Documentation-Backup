# Migration Note

## Link Control in PDF Export Configurations for Security

In order to address a vulnerability issue, a check has been introduced on all links used when configuring the export of a report in PDF format.

Now, only links to resources with protocols and hosts certified by the application are loaded. Otherwise, an error message about security breaches is displayed in place of the resource in the exported PDF.&#x20;

All links to resources currently used in the configurations of the headers, footers, and descriptions properties relating to the report PDF export must necessarily be included in the deployment property "`appcomposer.security.whitelist`" in order to be loaded correctly.

To enable check for links used in the PDF export configuration, the property "`appcomposer.security.pdf.whitelist.enabled`” must be set to `true`; default value are `false`.

Here an extract of the YAML to be used for configuring the protection of PDF export

{% code overflow="wrap" %}
```yaml
application: 
  properties: 
    appcomposer.security.pdf.whitelist.enabled: "true"
    #WHen the whitelist is enabled, only the URL in the below property could be used to add extra resources in the PDF Export
    appcomposer.security.whitelist: "https://<my-domain>.com" 
```
{% endcode %}
