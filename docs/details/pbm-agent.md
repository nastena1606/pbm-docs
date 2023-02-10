# pbm-agent

A `pbm-agent` is a process that runs backup, restore, delete and other operations available with Percona Backup for MongoDB.

A `pbm-agent` instance must run on each `mongod` instance. This includes replica set nodes that are currently secondaries and config server replica set nodes in a sharded cluster.

An operation is triggered when the `pbm` CLI makes an update to the [PBM Control collection](#pbm-control-collections). All `pbm-agents` monitor changes to the PBM control collections but only one `pbm-agent` in each replica set will be elected to execute an operation. The elections are done by a random choice among secondary nodes. If no secondary nodes respond, then the `pbm-agent` on the primary node is elected for an operation.

The elected `pbm-agent` acquires a lock for an operation. This prevents mutually exclusive operations like backup and restore to be executed simultaneously.

When the operation is complete, the `pbm-agent` releases the lock and updates the PBM control collections.