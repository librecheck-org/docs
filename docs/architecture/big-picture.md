---
sidebar_position: 1
---

# Big picture

```mermaid
architecture-beta
    group api(cloud)[API]
    
    service db(database)[Postgres] in api
    service s3(disk)[S3 storage] in api
    service queue(disk)[Message queue] in api
    service server(server)[Server] in api

    group field(internet)[Field]

    service field-app(server)[Field app] in field

    group customer(internet)[Customer]

    service integration-svc(server)[Integration service] in customer
    service customer-svc(server)[Customer services] in customer

    db:L -- R:server
    s3:T -- B:server
    queue:T -- B:server

    server:L -- R:field-app
    server:L -- R:integration-svc
    
    integration-svc:L -- R:customer-svc
    
```

## Field app

Mobile app (PWA) which can be used by field inspectors to:

- Fill a checklist submission
- Create or update a checklist definition

All operations should also be performed when internet connection is not available. Operations performed when offline are stored on the device and are sent to the server as soon as an internet connection is available.