# Example 1: Using DAC ENV within the SMTP Server

## Introduction

In this example we shows how to use DAC ENV within the SMTP Server configuration to manage email notification settings efficiently.

### **Step 1: Define DAC ENVs**

Define the following DAC ENVs that contains the connection parameter of the SMTP server in the App Composer pod.

<figure><img src="../../../.gitbook/assets/image (289).png" alt=""><figcaption></figcaption></figure>

### **Step 2 : Ceate DAC ENV**

Set u the DAC ENV on your client: if you are using Design Studio on a Microsoft Windows client, you need to create environment variables.

{% tabs %}
{% tab title="Windows Batch" %}
Example for windows CMD

```
//Set environment variables with specified values
setx DAC_ENV_EMAIL_SMTP_SERVER "Email_smtp_server"
setx DAC_ENV_MAIL_USERNAME "Mail_Username"
```
{% endtab %}

{% tab title="Power Shell" %}
```
# Set environment variables with specified values for the current Windows user
DAC_ENV_EMAIL_SMTP_SERVER "Email_smtp_server"
setx DAC_ENV_MAIL_USERNAME "Mail_Username"
[Environment]::SetEnvironmentVariable("DAC_ENV_EMAIL_SMTP_SERVER", "Email_smtp_server", [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("DAC_ENV_MAIL_USERNAME", "Mail_Username", [System.EnvironmentVariableTarget]::User)
```
{% endtab %}
{% endtabs %}

### **Step 3: Create SMTP server**

In Design Studio, create an SMTP server using the DAC ENV for the following properties:

* host-name
* mail-sender-mail
* smtp-username
* smtp-password

<figure><img src="../../../.gitbook/assets/image (290).png" alt=""><figcaption></figcaption></figure>

### **Step 4: Conntection test**

Click the “Connection Test” button: if if works, you will receive a test email.

<figure><img src="../../../.gitbook/assets/image (292).png" alt=""><figcaption></figcaption></figure>
