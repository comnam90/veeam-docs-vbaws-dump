---
title: "how_health_check_works"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/how_health_check_works.html"
last_updated: "9/17/2025"
product_version: "10.0.0.232"
---


In this article

When Veeam Backup for AWS saves a new backup restore point to a backup repository, it calculates CRC values for metadata in the backup chain and saves these values to the chain metadata, together with the instance data. When performing a health check, Veeam Backup for AWS verifies the availability of data blocks and uses the saved values to ensure that the restore points being verified are consistent.

If you have enabled health checks for the backup policy, Veeam Backup for AWS performs the following operations at the day scheduled for a health check to run:

1. As soon as a backup policy session completes successfully, Veeam Backup for AWS starts the health check as a new session. For each restore point in the standard backup chain, Veeam Backup for AWS calculates CRC values for backup metadata and compares them with the CRC values that were previously saved to the restore point. Veeam Backup for AWS also checks whether data blocks that are required to rebuild the restore point are available.

If the backup policy session completes with an error, Veeam Backup for AWS tries to run the backup policy again, taking into account the maximum number of retries specified in the [automatic retry settings](add_policy_retry_notification.md#retry). After the first successful retry (or after the last one out of the maximum number of retries), Veeam Backup for AWS starts the health check.

1. If Veeam Backup for AWS does not detect data inconsistency, the health check session completes successfully. Otherwise, the session completes with an error.

Depending on the detected data inconsistency, Veeam Backup for AWS performs the following operations:

* If the health check detects corrupted metadata in a full or an incremental restore point, Veeam Backup for AWS marks the backup chain as corrupted in the configuration database. During the next backup policy session, Veeam Backup for AWS copies the full instance image, creates a full restore point in the backup repository and starts a new backup chain in the backup repository.

|  |
| --- |
| Note |
| Veeam Backup for AWS does not support metadata check for encrypted backup chains. |

* If the health check detects corrupted disk blocks in a full or an incremental restore point, Veeam Backup for AWS marks the restore point that includes the corrupted data blocks and all subsequent affected incremental restore points as incomplete in the configuration database. During the next backup policy session, Veeam Backup for AWS reads whole data blocks and copies those data blocks that have changed since the previous backup session with corrupted data blocks, and saves these data blocks to the latest restore point that has been created during the current session.

All restore points marked as incomplete will be deleted according to the specified retention policy settings.

Page updated 9/17/2025

Page content applies to build 10.0.0.232
