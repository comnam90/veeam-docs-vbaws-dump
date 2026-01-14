---
title: "sla_edit"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/sla_edit.html"
last_updated: "11/28/2025"
product_version: "10.0.0.232"
---


In this article

For each SLA template, you can modify settings configured while creating the template:

1. Switch to the Configuration page.
2. Navigate to Policy Templates > SLA and click Edit.
3. Complete the Edit SLA Template wizard:

1. To provide a new name and description for the template, follow the instructions provided in section [Adding SLA Templates](sla_add_name.md) (step 2).
2. To modify the configured snapshot settings, follow the instructions provided in section [Adding SLA Templates](sla_add_snapshot_settings.md) (step 3).
3. To modify the configured backup settings, follow the instructions provided in section [Adding SLA Templates](sla_add_backup_settings.md) (step 4).
4. To adjust the target SLA value and change the health check schedule for the template, follow the instructions provided in section [Adding SLA Templates](sla_add_general_settings.md) (step 5).
5. At the Summary step of the wizard, review configuration information and click Finish to confirm the changes.

|  |
| --- |
| Tip |
| After you click Finish, Veeam Backup for AWS will update the timestamp in the Last Modified column on the SLA page, regardless of whether you have actually modified the template settings or not. If you want to simply view the configured settings without making any changes, click View Info. |

Note that when you modify snapshot or backup settings for an SLA template or assign another template to an SLA-based backup policy, this affects the SLA compliance ratio retrospectively — meaning that Veeam Backup for AWS recalculates the SLA compliance ratio for these policies. For more information on how Veeam Backup for AWS estimates SLA compliance, see [Viewing SLA-Based Backup Policy Details](sla_calculation.md).

[![Editing SLA Template](images/sla_edit.webp)](images/sla_edit.webp "Editing SLA Template")

Page updated 11/28/2025

Page content applies to build 10.0.0.232
