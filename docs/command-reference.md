---
title: Command Reference
---
Common serverconfig CLI commands for managing Helyx replication

### Create Publication
```bash
serverconfig -createpub -s publication.config -tables tablelist.config
```
### Create Subscription
```bash
serverconfig -createsub -s subscription.config -pub publication.config
```

### Add Tables to Publication
```bash
serverconfig -addtabletopub -s publication.config -tables tablelist.config
```

### Trigger Ad-hoc Snapshot
```bash
serverconfig -adhocsnapshot -s publication.config -tables table1,table2
```
### Monitor Publication Status
```bash
serverconfig -status -pub -s publication.config
```

### Monitor Subscription Status
```bash
serverconfig -status -sub -s subscription.config
```

### Remove Publication
```bash
serverconfig -remove -pub -s publication.config
```

### Remove Subscription
```bash
serverconfig -remove -sub -s subscription.config
```

### Remove Table from Replication
```bash
serverconfig -removetablefromrepl -s publication.config -tables table1,table2
```

### Encrypt Database Password
```bash
serverconfig -encryptPassword -s publication.config
```

### List Connectors
```bash
serverconfig -listconnectors -s publication.config
```

### List Tasks
```bash
serverconfig -listtask -s publication.config
```

### View Replication Lag
```bash
serverconfig -lagstat -s subscription.config
```

### List Replicated Tables
```bash
serverconfig -tablelist -s publication.config
```