---
title: Step 6 - Use CLI Tool
---
Use CLI Tool for Starting Replication between servers

## Overview

In this step, replication between the source and destination servers is started
and managed using the Helyx CLI tools.

These operations allow you to control publications and subscriptions, monitor
replication health, and perform maintenance tasks during the replication lifecycle.

---

## Replication Actions and Descriptions

| Action | Description |
|------|-------------|
| Create publication | Creates a logical publication on the source database using `publication.config` and tables defined in `tablelist.config`. |
| Create subscription | Sets up the destination (sink) connector using `subscription.config` and links it to Kafka topics created by the publication. |
| Add tables to publication | Adds new tables to an existing publication so that changes in those tables start replicating. |
| Trigger ad-hoc snapshot | Triggers a one-time snapshot for specified tables. Useful for re-syncing data. |
| Monitor publication status | Displays the current status of the publication connector (running, paused, failed, etc.). |
| Monitor subscription status | Shows the running status of the subscription connector and its associated tasks. |
| Remove publication | Stops and completely removes the publication configuration from the source. |
| Remove subscription | Stops and deletes the subscription configuration on the destination side. |
| Remove table from replication | Removes selected tables from the active replication setup. |
| List connectors | Lists all Kafka connectors currently running on the Connect cluster. |
| List tasks | Displays connector task IDs along with their current state (running, paused, failed). |
| View lag statistics | Shows replication lag metrics to monitor delay between source and destination. |
| List replicated tables | Lists all tables currently configured for replication in the source configuration. |

---

## Operational Notes

- Ensure services configured in **Step 1** are running before starting replication.
- Always verify connector status after creating publications or subscriptions.
- Monitor lag statistics regularly to detect performance or network issues.

---

## Completion

Replication setup is now complete.

You can continue to use the CLI commands described in this step to:
- Monitor replication health
- Add or remove tables
- Perform controlled re-synchronization
- Manage ongoing replication operations
