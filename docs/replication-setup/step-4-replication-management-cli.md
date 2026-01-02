---
title: Step 4 – Replication Management Using CLI
description: Manage publications, subscriptions, and replication operations using the serverconfig CLI
---

## Overview

Helyx provides a command-line tool called `serverconfig` to manage all
replication-related operations. This includes creating publications and
subscriptions, managing replicated tables, monitoring status, and performing
administrative actions.

This step covers the most commonly used `serverconfig` commands.

---

## Common `serverconfig` Commands

| Action | Command |
|------|--------|
| Create publication | `serverconfig -createpub -s publication.config -tables tablelist.config` |
| Create subscription | `serverconfig -createsub -s subscription.config -pub publication.config` |
| Add tables to publication | `serverconfig -addtabletopub -s publication.config -tables tablelist.config` |
| Trigger ad-hoc snapshot | `serverconfig -adhocsnapshot -s publication.config -tables table1,table2` |
| Monitor publication status | `serverconfig -status -pub -s publication.config` |
| Monitor subscription status | `serverconfig -status -sub -s subscription.config` |
| Remove publication | `serverconfig -remove -pub -s publication.config` |
| Remove subscription | `serverconfig -remove -sub -s subscription.config` |
| Remove table from replication | `serverconfig -removetablefromrepl -s publication.config -tables table1,table2` |
| Encrypt password | `serverconfig -encryptPassword -s publication.config` |
| List connectors | `serverconfig -listconnectors -s publication.config` |
| List tasks | `serverconfig -listtask -s publication.config` |
| View lag statistics | `serverconfig -lagstat -s subscription.config` |
| List replicated tables | `serverconfig -tablelist -s publication.config` |

---

## Notes

- Ensure the corresponding configuration file exists before executing commands.
- Commands should be run from the Helyx installation directory.
- Administrative privileges may be required for certain operations.

---

## Next Step

Proceed to **Step 5 – Validation and Monitoring**.
