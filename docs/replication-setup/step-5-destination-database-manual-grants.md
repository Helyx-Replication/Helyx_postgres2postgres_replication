---
title: Step 5 – Destination Database Manual Grants
description: Manually grant required privileges on the destination database for Helyx replication
---

## Overview

In some environments, database privileges must be granted manually due to
security or compliance requirements.

This step describes the SQL commands required to manually configure the
destination database so that Helyx can apply replicated changes successfully.

---

## Execute on Destination Database

Run the following commands on the **destination PostgreSQL or EDB database**
as a database administrator.

---

## Create Helyx Role and Schema

```sql
CREATE ROLE helyx
WITH LOGIN PASSWORD '<password>';

## Grant Schema Privileges

For each schema being replicated, replace <schema_name> with the actual
schema name and execute the following commands.

Grant Schema Privileges

For each schema being replicated, replace <schema_name> with the actual
schema name and execute the following commands.

GRANT USAGE ON SCHEMA <schema_name> TO helyx;

GRANT SELECT, INSERT, UPDATE, DELETE
ON ALL TABLES IN SCHEMA <schema_name>
TO helyx;

GRANT CREATE ON SCHEMA <schema_name> TO helyx;

ALTER SCHEMA <schema_name> OWNER TO helyx;

Grant Default Privileges

To ensure future tables and sequences are accessible to Helyx, configure
default privileges as shown below.

ALTER DEFAULT PRIVILEGES IN SCHEMA <schema_name>
GRANT ALL ON TABLES TO helyx;

ALTER DEFAULT PRIVILEGES IN SCHEMA <schema_name>
GRANT USAGE ON SEQUENCES TO helyx;

ALTER DEFAULT PRIVILEGES IN SCHEMA <schema_name>
GRANT SELECT, INSERT, UPDATE, DELETE ON TABLES TO helyx;

Important Note

Note:
The helyx username and password must be identical on both the source
and destination databases for replication to function correctly.