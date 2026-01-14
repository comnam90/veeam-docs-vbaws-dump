---
title: "rescan_repositories"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/rescan_repositories.html"
last_updated: "7/8/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup & Replication periodically rescans standard backup repositories for newly created restore points and metadata — the results of every rescan session are displayed in the History view under the System node. A rescan operation is launched automatically every 24 hours or in the following cases:

* After you add a repository to the backup infrastructure.
* After a backup chain stored in the repository is modified (for example, if a restore point is added or deleted from the chain).

However, you can perform a rescan operation for a repository manually:

1. In the Veeam Backup & Replication console, open the Backup Infrastructure view.
2. Navigate to External Repositories.
3. Select the necessary repository and click Rescan on the ribbon.

Alternatively, you can right-click the repository and select Rescan.

If multiple repositories are present in the backup infrastructure, you can perform the rescan operation for all repositories simultaneously. To do that, right-click the External Repositories node and select Rescan.

[![Rescan Repository](images/rescanning_repository.webp)](images/rescanning_repository.webp "Rescan Repository")

Page updated 7/8/2025

Page content applies to build 10.0.0.232
