---
title: Step 3 – Destination Database Configuration
description: Configure PostgreSQL or EDB destination database for Helyx replication
---

## Overview

In this step, the destination PostgreSQL or EDB database is prepared to receive
replicated data. This includes creating the Helyx database user, granting
required privileges on target schemas, and configuring the subscription
settings.

---

## Create Helyx User on Destination Database

To allow Helyx to write replicated data to the destination database, a dedicated
database role and schema must be created.

Execute the following commands as a database administrator.

### Create Replication Role

```sql
CREATE ROLE helyx
WITH LOGIN REPLICATION PASSWORD 'password';
