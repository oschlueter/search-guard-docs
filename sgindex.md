<!---
Copryight 2016 floragunn GmbH
-->

# Managing the Search Guard index

## Index name

Beginning with Search Guard 2.x.x.6, you can configure the name of the Search Guard index itself. This is only necessary in very special cases. If you have configured a Search Guard index name other than `searchguard`, you must configure this name via the `-i` switch.

## Replica shards

If the Search Guard index is created for the first time, the number of replica shards is determined automatically and is set to the number of nodes - 1. This means that a primary or replica shard of the Search Guard index is available on all nodes.

If you add or remove nodes, you can use the `-us` switch to set the number of replica shards manually. Usually, you want to set this to the number of data nodes - 1. This switch does not change any configuration settings.

If you want Search Guard to manage the number of replica shards automatically, you can enable and disable the replica auto-expand feature by using the `-era` and `-dra` switches. If this is enabled, Search Guard will monitor the cluster topology, and set the number of replica shards automatically whenever a node joins or leaves the cluster.

You read more about Search Guard and replica shards [in this blog post](https://floragunn.com/search-guard-index-replica-shards/).

Note that the `-us`, `-era` and `-dra` only work if there is an existing Search Guard index.