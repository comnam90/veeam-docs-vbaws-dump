---
title: "Before You Begin"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_sla_based_policy_byb.html"
last_updated: "3/12/2026"
product_version: "10.0.0.232"
---

# Before You Begin


Before you protect EC2 instances, consider the following:

* Veeam Backup for AWS prioritizes SLA-based backup policies over schedule-based backup policies. If an EC2 instance is included into both a schedule-based and an SLA-based backup policy, it will be processed by the SLA-based backup policy only.

* Veeam Backup for AWS protects only EC2 instances that run in VPCs. EC2-Classic instances are not supported. For more information, see [this Veeam KB article](https://www.veeam.com/kb3147).

When Veeam Backup for AWS backs up EC2 instances with IPv6 addresses assigned, it does not save the addresses. That is why when you restore these instances, IP addresses are assigned according to the settings specified in AWS for the subnet to which the restored instances will be connected.

* Veeam Backup for AWS may fail to create image-level backups of EC2 instances with [product codes](https://docs.aws.amazon.com/marketplace/latest/userguide/ami-getting-started.html#ami-product-codes) if the AMIs that were used to deploy the instances do not support the type of worker instances deployed for the backup operation. To work around the issue, modify the worker profile to choose another instance type, as described in section [Managing Worker Profiles](worker_profiles.md).

* [Applies only to image-level backups and file-level recovery from cloud-native snapshots] Veeam Backup for AWS does not support creating image-level backups and restoring EC2 instances with [product codes](https://docs.aws.amazon.com/marketplace/latest/userguide/ami-getting-started.html#ami-product-codes) that have vendor restrictions preventing root EBS volumes from being attached to worker instances as secondary volumes. To learn how Veeam Backup for AWS performs EC2 backup, see [Protecting EC2 Instances](backup_hiw_ec2.md).

* Veeam Backup for AWS does not support creating cloud-native snapshots and image-level backups for arm64-based EC2 instances if these instances were deployed from AMIs containing [product codes](https://docs.aws.amazon.com/marketplace/latest/userguide/ami-getting-started.html#ami-product-codes).

* Since Veeam Backup for AWS runs retention sessions for SLA-based backup policies as soon as it finalizes the backup window in all protected regions, it is recommended that you estimate how long it may take for Veeam Backup for AWS to complete a retention session first, and then configure a backup window. Otherwise, Veeam Backup for AWS will not be able to run retention sessions, and obsolete data will not be removed from the configuration database and backup repositories.


