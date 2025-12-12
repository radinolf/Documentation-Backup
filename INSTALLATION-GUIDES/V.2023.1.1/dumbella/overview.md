# Overview

Dumbella is an optional service in the stack and it is responsible of executing ETL jobs built with Talend Open Studio.

Dumbella runs in the stack in coordination with the App Composer service, on which it depends on. It doesn't have its own UI because it's a back-end only service and it exposes REST API to interact with it.
