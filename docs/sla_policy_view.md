---
title: "sla_policy_view"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/sla_policy_view.html"
last_updated: "12/1/2025"
product_version: "10.0.0.232"
---


In this article

After you create an SLA-based backup policy, Veeam Backup for AWS displays this policy on the SLA-Based Policies page

|  |
| --- |
| Tip |
| By default, Veeam Backup for AWS applies the Daily filtering condition to the created policies. Therefore, the page displays the status of average SLA compliance ratio for all EC2 instances protected by these policies according to the daily schedule. To switch between the filtering conditions, click Reporting SLA. |

Each policy is described with the following set of properties:

* Priority — the priority of the policy.
* Policy — the name of the policy.
* Description — the reference information on the policy.
* Snapshot SLA — the most recent SLA compliance ratio calculated for all snapshots produced by the policy.
* Snapshot Replica SLA — the most recent SLA compliance ratio calculated for all snapshot replicas produced by the policy.
* Backup SLA — the most recent SLA compliance ratio calculated for all backups produced by the policy.
* Archive SLA — the most recent SLA compliance ratio calculated for all archived backups produced by the policy.

|  |
| --- |
| Note |
| The displayed status of the SLA compliance ratio is based on the snapshot and backup schedules configured while creating the SLA template that is assigned to the SLA-based backup policy:   * Not configured — no schedule is configured in the SLA template. * Not available — a schedule is configured in the SLA template but the SLA compliance ratio has not yet been calculated. * SLA Met/SLA Missed — the SLA compliance ratio has been calculated based on the schedule settings configured in the SLA template. |

To see how the SLA compliance ratio has been changing over a specific period (daily, monthly or weekly) for each EC2 instance protected by the policy, click the link in the Snapshot SLA, Snapshot Replica SLA, Backup SLA or Archive SLA column. For more information, see [Monitoring SLA-Based Policy Performance](sla_monitoring.md).

[![Viewing SLA-Based Policy Details](images/view_sla_policy_details.webp)](images/view_sla_policy_details.webp "Viewing SLA-Based Policy Details")

In This Section

[How Veeam Backup for AWS Estimates SLA Compliance](sla_calculation.md)

Page updated 12/1/2025

Page content applies to build 10.0.0.232
