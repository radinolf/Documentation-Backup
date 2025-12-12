# Enhancement

* **DACXX-1132**: In the cockpit service, introduced the `web.url` property and used it as `post_logout_redirect_uri` in the logout flow.
* **DACXX-1154**: Changed the calculation of `post_logout_redirect_uri` in the logout flow AppComposer and Cockpit. The DecisyonWebUrl property value is now used as `post_logout_redirect_uri`
* **D4C-10347**: AppComposer and Pages are now automatically added to the REST Client whitelist. To enable automatic whitelisting for Pages, ensure the **`appcomposer.pages.url`** property is correctly set. When using AppComposer's Helm chart, this property must be defined under the **properties** attribute as **`appcomposer_pages_url`**.

