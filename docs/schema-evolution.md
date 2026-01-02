# Start & Monitor

### Start the Publication

```bash
./serverconfig -createpub -s publication.config -tables tablelist.config
```
### Start the Subscription
```bash
./serverconfig -createsub -s subscription.config -pub publication.config
```
### Monitor Status
```bash
serverconfig -status -pub -s publication.config
```
```bash
serverconfig -status -sub -s subscription.config
```

## Final Checklist

- ✅ sync-manager, broker, Connect, Schema Registry running
- ✅ Source publication.config configured
- ✅ Destination subscription.config configured
- ✅ Grants applied to source and destination DBs
- ✅ Topics appearing in Kafka
- ✅ Messages flowing to sink
