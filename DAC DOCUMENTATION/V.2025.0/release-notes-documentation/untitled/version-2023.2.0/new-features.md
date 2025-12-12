# New Features

The migration to Angular has brought a series of improvements that have significantly enriched the user experience. Among the introduced innovations, some features have proven to be particularly useful during navigation within the application.

Below some of the improvements introduced but for more details we invite you to view the document [What’s](../version-2022.2.2/whats-new.md)[ new](../version-2022.2.2/whats-new.md).

## Search the page navigation

A new search tool has been introduced to find specific pages within the page tree.

<figure><img src="../../../.gitbook/assets/image (1893).png" alt=""><figcaption></figcaption></figure>

## Cropping the Image in the User Profile

With the migration to Angular, there have been changes to the user profile, including the introduction of the image cropping feature.Now users have the option to further customize their profile picture by cropping the image as desired, allowing for a more precise and tailored display to suit their individual needs.

<figure><img src="../../../.gitbook/assets/image (1983).png" alt=""><figcaption></figcaption></figure>

## Total number of users

Now in the User Administration section on the top right is available the total number of users associated with the selected tenant. If you select “All users” from the tenant list, the icon shows the total number of users in the instance.

<figure><img src="../../../.gitbook/assets/image (1952).png" alt=""><figcaption></figcaption></figure>

## App Composer Environment Variables

In the section "**App Composer Environment Variables**" in the page "**General Info**" the value of vaariable is no longer visible, so that any sensitive backend information disclosure is now prevented.

<figure><img src="../../../.gitbook/assets/image (1991).png" alt=""><figcaption></figcaption></figure>

## REST Api Client URL Whitelist&#x20;

Now the DevOps it able to define a set of allowed URLs which can be invoked using the Rest Api Client, so that the invocation of malicious endpoint could be prevented.

Please read the [migration notes](migration-notes.md#rest-api-client-url-whitelist) to get more details about how to correctly configure the whitelist.

## Azure Key Vault service

App Composer now support the cloud services **Azure Key Vault** to store secrets.

{% embed url="https://azure.microsoft.com/en-us/products/key-vault" %}

This service could be used in organizations that require to securly stores key and secret management, which is crucial for data security and protection of digital resources in a cloud or hybrid environment.

Also App Composer Environment Variables could be eventually stored in the external secret manager.&#x20;

When using an external secret manager, you need to properly modify the [HELM chart](https://dac-documentation-1.gitbook.io/installation-guides/helm-chart/decisyon-appcomposer) that is used to deploy App Composer.&#x20;

Please refer to the [installation guide](https://azure.microsoft.com/en-us/products/key-vault) for more information.
