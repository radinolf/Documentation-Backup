---
description: >-
  An Application is the means to create a specific IIoT solution. It is possible
  to create one or more applications.
---

# Overview

An **Application** is the means to create a specific IIoT solution. It is possible to create one or more applications; each of these applications can pertain to a different scope, department, project, etc.

For example, if a manufacturing company wants to optimize asset management using DAC, it can create an application that gets data from the asset, obtaining real-time analysis and predicting failures or maintenance. Each application can be built using one or more pages and functionality that can be configured and arranged to deliver data and tools according to the business users’ requirements.

DAC contains an existing demo application that you can use to understand how a simple application is built. Please refer to the Starter Kit to find out more about the Decisyon Reference App.

All the objects of the DAC-DS environment -- dimensions, cubes, metrics, and reports -- are created within an application. The objects of an application cannot be used by another application.

In addition to defining descriptive parameters during the application creation phase, users must associate the data warehouse to which dimensions and cubes will be mapped.

The data warehouse may reside both on the same instance of the Data Model to which it is connected, and on a remote data source.

A DAC application cannot share the objects contained within it: access to those objects is only permitted to users associated with the applications.

Functions are also available to deploy applications, which lets you manage an application on different environments, for example, to manage a production or test application, rather than a development applicationcopy and then synchronize objects belonging to different applications (however, objects created within applications belong exclusively to the applications)
