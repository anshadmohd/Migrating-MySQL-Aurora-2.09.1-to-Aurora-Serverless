# Migrating-MySQL-Aurora-2.09.1-to-Aurora-Serverless
steps for Migrating MySQL Aurora(2.09.1) to Aurora Serverless

* We have Aurora MySQL 2.0.9 (compatible with MySQL 5.7). We want to migrate it to serverless. 
To do that,
* Upgrade the engine type to Aurora 3.0.2(compatible with MySQL 8.0) with the snapshot of the old cluster.

Take a snapshot of the new cluster and restore it with a serverless instance type.

Steps:

1.Upgrade the existing cluster(mysql_aurora.2.09.1) to Aurora MySQL 3.02.0
  > Take the snapshot of existing cluster
  
  > Restore the snapshot
  
  > Select Aurora MySQL 3.02.0
