# Comparison with MongoDB 

Percona Backup for MongoDB is a fully supported community backup solution that can perform cluster-wide consistent backups in MongoDB. The following table compares the Percona Backup for MongoDB with the MongoDB backup solutions

| Feature name | Percona Backup for MongoDB | MongoDB Community `mongodump` | MongoDB Enterprise | MongoDB Atlas |
| -------------| -------------------------- | ----------- | ----------------- | --------------- 
|Open source backup | Yes | No	| No | No 
| Binary database export (logical backup) | Yes | Yes | Yes | Yes 
| Built-in point-in-time recovery support |	Yes | No | Yes | Yes
| Physical backup |	Yes	| No | Yes | Yes
| Incremental backup (physical) | Yes |	No |Yes | Yes
| Backup management interfaces	| Percona Backup for MongoDB (CLI) <br> PMM <br> mongodump / mongorestore (CLI) | - <br> - <br> mongodump / mongorestore (CLI) | Ops Manager <br> Cloud Manager <br> mongodump / mongorestore (CLI) | Atlas backups <br> mongodump / mongorestore (CLI)
| Sharded cluster restores supported | Yes | No | Yes |	Yes