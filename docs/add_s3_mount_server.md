---
title: "Step 7. Specify Mount Server Settings"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/add_s3_mount_server.html"
last_updated: "2/2/2026"
product_version: "10.0.0.232"
---

# Step 7. Specify Mount Server Settings


At the Mount Servers step of the wizard, you can specify settings for the [mount servers](https://helpcenter.veeam.com/docs/vbr/userguide/mount_server.html?ver=13) that will be used for Instant Recovery, guest OS file restore and application item restore. By default, Veeam Backup & Replication automatically chooses the servers that meet the [system requirements](https://helpcenter.veeam.com/docs/vbr/userguide/system_requirements.html?ver=13#mount) from your backup infrastructure.

If Veeam Backup & Replication fails to choose a mount server automatically or you want to specify a server manually, do the following:

1. To perform restore operations with Windows-based VMs, select the necessary server from the Windows mount server list. For a server to be displayed in the list of available servers, it must be added to the backup infrastructure as described in Veeam Backup & Replication User Guide, section [Adding Microsoft Windows Servers](https://helpcenter.veeam.com/docs/vbr/userguide/add_windows_server_console.html?ver=13). If you have not added the server to Veeam Backup & Replication beforehand, you can do it without closing the Add External Repository wizard. To do that, click Add and complete the New Windows Server wizard.
2. To perform restore operations with Linux-based VMs, select the necessary server from the Linux mount server list. For a server to be displayed in the list of available servers, it must be added to the backup infrastructure as described in Veeam Backup & Replication User Guide, section [Adding Linux Servers](https://helpcenter.veeam.com/docs/vbr/userguide/add_linux_server_console.html?ver=13). If you have not added the necessary server to Veeam Backup & Replication beforehand, you can do it without closing the Add External Repository wizard. To do that, click Add and complete the New Linux Server wizard.
3. To perform Instant Recovery or scan backups with SureBackup in VMware vSphere environments, click Configure settings. In the Mount Server Settings window, do the following:

1. Select the Enable vPower NFS service on the mount server check box to make the backup repository accessible by the [Veeam vPower NFS Service](https://helpcenter.veeam.com/docs/vbr/userguide/vpower_nfs_service.html?ver=13).

|  |
| --- |
| Important |
| It is not recommended that you enable Microsoft Windows NFS services on the same VM that runs Veeam vPower NFS Service. Otherwise, both services may fail to work properly. |

1. Click Ports to customize network ports used by the Veeam vPower NFS Service. By default, Veeam vPower NFS Service uses port 1058 to mount the vPower NFS datastore to the ESXi host and port 2049 to connect to the target NFS share.
2. In the Instant recovery write cache folder field, specify a folder that will be used for storing cache files.

![Step 7. Specify Mount Server Settings](images/add_s3_mount_server.webp "Add Amazon S3 repository - S3 endpoint")

Related Topics

* [Verifying Backups](verify_backups.md)
* [Instant Recovery](instant_recovery.md)
* [Performing Guest OS File Restore](guest_file_recovery.md)
* [Performing Application Item Restore](application_items_restore.md)


