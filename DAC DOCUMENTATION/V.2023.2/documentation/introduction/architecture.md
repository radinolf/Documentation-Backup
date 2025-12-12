# 🆕 Architecture

## Introduction

App Composer is built on a microservice architecture, which allows for greater scalability, flexibility, and resilience in building and executing applications.&#x20;

The platform consists of several independent microservices, each with a specific role and responsibility. Usually each service manage its own persistency on a relational database.&#x20;

<figure><img src="../../.gitbook/assets/image (1762).png" alt=""><figcaption></figcaption></figure>

**Design Studio** is a thick client used to configure the Applications to run in the AppComposer

**MD** is a Postgres instance containing all the setting and configurations

**Decisyon AppComposer (DAC)** is the service through which users can access the Applications for monitoring, reporting, and analysis functions of company data in a collaborative environment.

**OIDC** is a User Authentication Service, OpenID Connect compliant

**HUB** is a Message Broker that all services use to exchange events.

**TimeTurner** is a service to trigger actions on schedule.

**Dumbella** is a service to execute integration jobs.

## Technology stack

* Container based architecture
* Java 17+ / JEE platform
* Spring Framework 2.x
* Angular, HTML 5 and CSS 3
* REST API with JSON payload
* Cloud agnostics
* Deploy on-premise or in cloud
