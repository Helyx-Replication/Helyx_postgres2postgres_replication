---
title: Replication Setup Overview
description: Overview of Helyx PostgreSQL to PostgreSQL replication setup
---

## Overview

Helyx enables **real-time logical replication** between PostgreSQL and EDB
source and destination databases.

The platform supports:
- Same-version replication
- Cross-version replication

Examples:
- PostgreSQL 11 → PostgreSQL 15
- EDB 12 → EDB 14

This section provides a high-level understanding of the replication setup,
required tools, and configuration layout before starting the actual steps.

---

## Replication Target

The goal of the replication setup is to:

- Establish **continuous, low-latency replication**
- Ensure **schema and data consistency**
- Allow **controlled and observable replication operations**
- Support enterprise-grade PostgreSQL and EDB environments

---

## Prerequisites

Before starting the replication setup, ensure the following requirements are met:

### Software Requirements

- Java 11 or later installed
- Helyx replication binaries installed
- PostgreSQL or EDB installed on both source and destination systems
- JDBC drivers bundled with the Helyx binaries

### Required Tools

The following tools must be available:

- `tabletorepl`
- `serverconfig`
- `configservice`

### Database Configuration

On both source and destination PostgreSQL/EDB databases:

- `wal_level` **must** be set to `logical`

Example:

```sql
SHOW wal_level;
