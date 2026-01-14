---
title: "add_policy_schedule_retention_redshift_serverless"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_policy_schedule_retention_redshift_serverless.html"
last_updated: "7/7/2025"
product_version: "10.0.0.232"
---


In this article

You can instruct Veeam Backup for AWS to start the backup policy automatically according to a specific backup schedule. The backup schedule defines how often data of the namespaces added to the backup policy must be backed up.

To help you implement a comprehensive backup strategy, Veeam Backup for AWS allows you to create schedules of the following types:

* [Daily](schedule_daily_redshift_serverless.md) — the backup policy will create restore points repeatedly throughout a day on specific days.
* [Weekly](schedule_weekly_reshift_serverless.md) — the backup policy will create restore points once a day on specific days.
* [Monthly](schedule_monthly_redshift_serverless.md) — the backup policy will create restore points once a month on a specific day.

* [Yearly](schedule_yearly_redshift_serverless.md) — the backup policy will create restore points once a year on a specific day.

Combining multiple schedule types together allows you to retain restore points for longer periods of time. For more information, see [Enabling Harmonized Scheduling](harmonized_scheduling_redshift_serverless.md).

|  |
| --- |
| Note |
| If you do not specify the backup schedule, after you configure the backup policy, you will need to start it manually to create Redshift Serverless namespaces backups. For information on how to start backup policies, see [Starting and Stopping Policies](policies_start_stop.md). |

Page updated 7/7/2025

Page content applies to build 10.0.0.232
