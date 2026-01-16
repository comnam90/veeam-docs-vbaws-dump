---
title: "instant_recovery"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/instant_recovery.html"
last_updated: "8/8/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup & Replication allows you to use the Instant Recovery feature to restore EC2 instances from image-level backups to VMware vSphere and Microsoft Hyper-V environments, and to Nutanix AHV clusters. For more information, see the [Veeam Backup & Replication User Guide](https://helpcenter.veeam.com/docs/vbr/userguide/instant_recovery.html?ver=13) and [Veeam Backup for Nutanix AHV User Guide](https://helpcenter.veeam.com/docs/vbahv/userguide/instant_recovery_ahv.html?ver=8), section Instant Recovery.

|  |
| --- |
| Important |
| Instant Recovery can be performed only using backup files stored in standard backup repositories for which you have specified access keys of an IAM user whose permissions are used to access the repositories. To learn how to specify credentials for the repositories, see sections [Creating New Repositories](add_s3_account.md) and [Connecting to Existing Appliances](connect_appliance_repo.md). |

Before you start the restore operation, make sure to add to the backup infrastructure a vCenter Server, a Microsoft Hyper-V server or a Nutanix AHV cluster that will manage restored EC2 instances, as described in the Veeam Backup & Replication User Guide, section [Adding VMware vSphere Servers](https://helpcenter.veeam.com/docs/vbr/userguide/add_vmware_server.html?ver=13), [Adding Microsoft Hyper-V Servers](https://helpcenter.veeam.com/docs/vbr/userguide/add_hyperv_server.html?ver=13) or [Adding Nutanix AHV Cluster](https://helpcenter.veeam.com/docs/vbahv/userguide/add_ahv_cluster.html?ver=50).

To perform Instant Recovery, do the following:

1. In the Veeam Backup & Replication console, open the Home view.
2. Navigate to Backups > External Repository.
3. Expand the backup policy that protects an EC2 instance that you want to recover, select the necessary EC2 instance and click Instant Recovery on the ribbon.
4. Select VMware vSphere, Microsoft Hyper-V or Nutanix AHV.

1. Depending on the selected Instant Recovery option, complete the Instant Recovery wizard as described in the Veeam Backup & Replication User Guide, section [Performing Instant Recovery of Workloads to VMware vSphere VMs](https://helpcenter.veeam.com/docs/vbr/userguide/instant_recovery_vms_vm.html?ver=13), [Performing Instant Recovery of Workloads to Hyper-V VMs](https://helpcenter.veeam.com/docs/vbr/userguide/ir_workloads_hv.html?ver=13) or [Performing Instant Recovery of Workloads to Nutanix AHV](https://helpcenter.veeam.com/docs/vbahv/userguide/ir_workloads_ahv.html?ver=8).

[![Instant Recovery to VMware vSphere, vSphere or to Nutanix AHV](images/instant_recovery.webp)](images/instant_recovery.webp "Instant Recovery to VMware vSphere, vSphere or to Nutanix AHV")

Page updated 8/8/2025

Page content applies to build 10.0.0.232
