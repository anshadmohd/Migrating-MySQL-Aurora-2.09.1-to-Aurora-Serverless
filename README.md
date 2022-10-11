# Migrating-MySQL-Aurora-2.09.1-to-Aurora-Serverless
steps for Migrating MySQL Aurora(2.09.1) to Aurora Serverless

* We have Aurora MySQL 2.0.9 (compatible with MySQL 5.7). We want to migrate it to serverless. 
To do that,
* Upgrade the engine type to Aurora 3.0.2(compatible with MySQL 8.0) with the snapshot of the old cluster.

* Take a snapshot of the new cluster and restore it with a serverless instance type.

Steps:

1.Upgrade the existing cluster(mysql_aurora.2.09.1) to Aurora MySQL 3.02.0
  > Take the snapshot of existing cluster
  
  > Restore the snapshot
  
  > Select Aurora MySQL 3.02.0

  > Select instance class of existing cluster
  
2.Upgrade into serveless
  > Take the snapshot of upgraded cluster 
  > Restore the snapshot 
  > Select the instance class as v2serverless.
  > Select the same capacity range as our previous instance type.

# Note: Rollback failure

> Rollback after failure to upgrade from MySQL 5.7 to 8.0
When you upgrade a DB instance from MySQL version 5.7 to MySQL version 8.0, the upgrade can fail. In particular, it can fail if the data dictionary contains incompatibilities that weren't captured by the prechecks. In this case, the database fails to start up successfully in the new MySQL 8.0 version. At this point, Amazon RDS rolls back the changes performed for the upgrade. After the rollback, the MySQL DB instance is running MySQL version 5.7. When an upgrade fails and is rolled back, Amazon RDS generates an event with the event ID RDS-EVENT-0188.
