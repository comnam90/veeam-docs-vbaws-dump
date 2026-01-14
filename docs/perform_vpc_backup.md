---
title: "perform_vpc_backup"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/perform_vpc_backup.html"
last_updated: "12/15/2025"
product_version: "10.0.0.232"
---


In this article

To protect the Amazon VPC configuration and settings, Veeam Backup for AWS  comes with a preconfigured VPC Configuration Backup policy. With this policy, you can protect VPC configurations of AWS Regions in your AWS accounts or AWS Organizations.

The VPC Configuration Backup policy is disabled by default. To start protecting your Amazon VPC configuration, [edit backup policy settings](policies_edit_vpc.md) and [enable the policy](policies_disable_enable_vpc.md).

|  |
| --- |
| Important |
| Veeam Backup for AWS does not support backup of the following VPC configuration components: VPC Traffic Mirroring, AWS Network Firewall, Route 53 Resolver DNS Firewall, AWS Verified Access, VPC Flow Logs, carrier gateways, customer IP pools, transit gateway policy tables, and core networks in route tables. |

In This Section

* [Editing VPC Backup Policy](policies_edit_vpc.md)
* [Enabling and Disabling VPC Configuration Backup Policy](policies_disable_enable_vpc.md)
* [Starting and Stopping VPC Configuration Backup Policy](policies_start_stop_vpc.md)

Page updated 12/15/2025

Page content applies to build 10.0.0.232
