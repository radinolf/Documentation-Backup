# New Feature

**DACXX-1120**: Added support for uploading customer-specific HTTPS certificates. Below are the properties to configure the certificates. For more information, consult the Installation Guide.

<details>

<summary>View the properties</summary>

### **Properties**&#x20;

* **`config_ssl_custom_enabled:`** set to true for enabling the custom certificates
* **`config_ssl_custom_bundle_name:`** the name of the bundle containing the certificate or the truststore.

The certificate or the truststore is injected in the application using the SpringBoot's SslBundles.

Following examples of extracts of two values.yaml files for both Pages and AppComposer:

### **PEM Ceritificate**

* Assuming the PEM certificate is stored in a secret
* Assuming the name of the secret is "certificate-secret"
* Assuming the name of the certificate within the secret is "client.pem"

### Application

properties:&#x20;

* `config_ssl_custom_enabled: true config_ssl_custom_bundle_name: client`
* `spring_ssl_bundle_pem_client_truststore_certificate: "classpath:client.pem"`

```
volumeMounts:
- name: certificate-store
  mountPath: "/opt/pages/BOOT-INF/classes/client.pem"
  subPath: client.pem
  readOnly: true
volumes:
- name: certificate-store
  secret:
    secretName: certificate-secret
```

### **TRUSTORE (JKS)**

* Assuming the truststore in stored in a secret
* Assuming the name of the secret is "certificate-secret"
* Assuming the name of the certificate within the secret is "truststore.jks"

### application:

&#x20;secrets:&#x20;

* properties:  spring\_ssl\_bundle\_jks\_client\_truststore\_password: "changeit"&#x20;
* properties: config\_ssl\_custom\_enabled: true&#x20;
* config\_ssl\_custom\_bundle\_name: client
* spring\_ssl\_bundle\_jks\_client\_truststore\_location: "classpath:truststore.jks"

```
volumeMounts:
- name: certificate-store
  mountPath: "/opt/pages/BOOT-INF/classes/truststore.jks"
  subPath: truststore.jks
  readOnly: true
volumes:
- name: certificate-store
  secret:
    secretName: certificate-secret
```

</details>

**DACXX-958**: Following an issue regarding the inconsistent handling of the numeric parameter in the JS API **sendMultiParamsChanged** vs **sendParamChanged**, a new APIs has been introduced:

*   **DECISYON.page.setParam(param);**

    Export a parameter in the format `[{name, value}]`. The value can be an array of string or numeric values or a single string or numeric value. The values are always sent without quotes. The function also allows you to force or remove single quotes by setting the parameter `singleQuotes` to `true` or `false`.
*   **DECISYON.page.setParams(params);**

    Export a list of parameters in the format \[{name, value}]. The value can be an array of string or numeric values or a single string or numeric value. The values are always sent without quotes. The function also allows you to force or remove single quotes by setting the parameter `singleQuotes` to `true` or `false`.
* Increased API LEVEL VERSION to 2.5.0 for AppComposer and Pages. For more details see the [API Changelog](https://dac-documentation-1.gitbook.io/dac-api)
