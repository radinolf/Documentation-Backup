# Keycloak Installation Guide

## Configuring App Composer with Keycloak <a href="#configuring-app-composer-with-keycloak" id="configuring-app-composer-with-keycloak"></a>

Environment variables configuring App Composer to work with Keycloak as IODC Server

oc.realm=appcomposer\
client.id=appcomposer\
client.secret=3a95e29c-7909-425c-a165-c875f39cf91a\
oc.authorizationEndpoint=[\<keycloak\_url>/auth/realms/${oc.realm}/protocol/openid-connect/auth](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/auth)\
oc.tokenEndpoint=[\<keycloak\_url>](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/auth)[/auth/realms/${oc.realm}/protocol/openid-connect/token](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/token)\
oc.userInfoEndpoint=[\<keycloak\_url>/auth/realms/${oc.realm}/protocol/openid-connect/userinfo](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/userinfo)\
oc.loginRedirectUri=[\<dac\_url>/index.cas](http://localhost:8080/index.cas)\
oc.checkTokenEndpoint=[\<keycloak\_url>/auth/realms/${oc.realm}/protocol/openid-connect/token/introspect](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/token/introspect)\
oc.jwkEndpoint=[\<keycloak\_url>/auth/realms/${oc.realm}/protocol/openid-connect/certs](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/certs)\
oc.logoutEndpoint=[\<keycloak\_url>/auth/realms/${oc.realm}/protocol/openid-connect/logout?redirect\_uri=%LOGOUT\_REDIRECT\_URI%](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/logout?redirect_uri=%25LOGOUT_REDIRECT_URI%25)\
oc.userIdentifierClaim=sub uaa.url=[\<keycloak\_url>/auth](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/logout?redirect_uri=%25LOGOUT_REDIRECT_URI%25)[/admin/realms](http://localhost:8084/auth/realms/$%7Boc.realm%7D/protocol/openid-connect/logout?redirect_uri=%25LOGOUT_REDIRECT_URI%25)<br>
