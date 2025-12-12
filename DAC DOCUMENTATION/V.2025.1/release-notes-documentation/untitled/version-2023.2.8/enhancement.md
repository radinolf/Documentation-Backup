# Enhancement

#### Compatibility with NextGEN IDMS <a href="#compatibility-with-nextgen-idms" id="compatibility-with-nextgen-idms"></a>

Compatibility with NextGEN IDMS. AppComposer 2023.2.x has been modified to work with the latest version of Schneider IDMS. The values.yaml property `oc.checkTokenEndpoint`, previously used to verify the token validity of the user session, has been removed and now the `/userinfo` endpoint is used for the same purpose.&#x20;

A new property, `oc.scope`, has been introduced to specify the IDMS required scopes in authentication requests. In IDMS the scope must be configured as "`openid,email,profile`".&#x20;

Helm Chart must be migrated accordingly to these changes

#### Creation Times for the Time Dimension <a href="#creation-times-for-the-time-dimension" id="creation-times-for-the-time-dimension"></a>

After solving a bug related to the creation of the Time dimension (D4C-9454), an optimization of the process has been implemented. This modification now allows for a significant reduction in the time required to create the TIME dimension, enabling the operation to be completed in a significantly shorter time compared to previous versions.
