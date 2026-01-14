---
title: "add_policy_schedule_retention"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy_schedule_retention.html"
last_updated: "7/9/2025"
product_version: "10.0.0.232"
---


In this article

You can instruct Veeam Backup for AWS to start the backup policy automatically according to a specific backup schedule. The backup schedule defines how often data of the instances added to the backup policy will be backed up.

|  |
| --- |
| Important |
| If you have selected a standard or an archive backup repository with immutability settings enabled at [step 5](add_policy_target_settings_backups.md) of the wizard, you must configure at least one schedule for the backup policy. |

To help you implement a comprehensive backup strategy, Veeam Backup for AWS allows you to create schedules of the following types:

* [Daily](schedule_daily.md) — the backup policy will create restore points repeatedly throughout a day on specific days.
* [Weekly](schedule_weekly.md) — the backup policy will create restore points once a day on specific days.
* [Monthly](schedule_monthly.md) — the backup policy will create restore points once a month on a specific day.
* [Yearly](schedule_yearly.md) — the backup policy will create restore points once a year on a specific day.

Combining multiple schedule types together allows you to retain restore points for longer periods of time  — for more information, see [Enabling Harmonized Scheduling](harmonized_scheduling.md). Combining multiple schedule types together also allows you to archive backups — for more information, see [Enabling Backup Archiving](backup_archiving.md).

|  |
| --- |
| Note |
| If you do not specify a backup schedule for the backup policy, you will need to start it manually to create EC2 instance snapshots and backups. For information on how to start backup policies, see [Starting and Stopping Policies](policies_start_stop.md). |

Page updated 7/9/2025

Page content applies to build 10.0.0.232
