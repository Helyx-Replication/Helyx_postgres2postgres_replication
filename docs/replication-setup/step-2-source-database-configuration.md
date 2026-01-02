---
title: Step 2 – Source Database Configuration
description: Configure PostgreSQL or EDB source database for Helyx replication
---

## Overview

In this step, the source PostgreSQL or EDB database is prepared for replication.
This includes creating a dedicated Helyx database user, granting required
privileges, and configuring the publication settings.

---

## Create Helyx User on Source Database

To allow Helyelyx to perform logical replication, a dedicated database role
and schema must be created on the source database.

Execute the following SQL commands as a superuser or database administrator.

### Create Replication Role

```sql
CREATE ROLE helyx
WITH LOGIN REPLICATION PASSWORD 'password';
