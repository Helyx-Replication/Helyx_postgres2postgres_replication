---
title: Step 1 – Service Setup
description: Configure and start required Helyx replication services
---

## Overview

Before configuring database-level replication, all required Helyx services
must be properly configured and running.

This step ensures that the core services required for replication are started
in the correct order.

---

## Required Services

The following services must be configured and started:

1. Sync Manager Service  
2. Broker Service  
3. Schema Registry Service  
4. Connect Service  

---

## 1. Sync Manager Service

Start the Sync Manager service using the following command:

```bash
./configservice -start sync-manager
```
This service coordinates internal replication workflows.

## 2. Broker Service

**Configuration**

Edit the following file:
```bash
/var/lib/helyx/server.properties
```

Set the listener configuration:
```bash
listeners=PLAINTEXT://<your.server.ip>:9092
```

Replace **your.server.ip** with the IP address of the server where Helyx is running.

**Start the Service**
```bash
./configservice -start broker
```

## 3. Schema Registry Service
**Configuration**

Edit the Schema Registry configuration file :
```properties
/var/lib/helyx/plugins/confluent-7.5.0/etc/schema-registry/schema-registry.properties
```

Ensure the following properties are set :
```properties
kafkastore.bootstrap.servers=PLAINTEXT://<your.server.ip>:9092
listeners=http://0.0.0.0:8081
```

Replace __your.server.ip__ with the Helyx server IP address.

**Start the Service**

```bash
./configservice -start schemaregistry
```

## 4. Connect Service

**Configuration**

Edit the Connect distributed configuration file:

/var/lib/helyx/config/connect-distributed.properties


Set the following properties:
```properties
bootstrap.servers=<your.server.ip>:9092

key.converter.schema.registry.url=http://<your.server.ip>:8081
value.converter.schema.registry.url=http://<your.server.ip>:8081
```
**Start the Service**
```bash
./connectservice -start connect
```
**Verification**

Ensure all services are running before proceeding to the next step.
