---
title: "access_backup_appliances"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/access_backup_appliances.html"
last_updated: "4/25/2025"
product_version: "10.0.0.232"
---


In this article

|  |
| --- |
| Note |
| This section provides instructions on steps performed in a third-party application as part of one possible solution. Keep in mind that the instructions may become outdated. For up-to-date instructions, see [AWS Documentation](https://docs.aws.amazon.com/vpn/latest/s2svpn/SetUpVPNConnections.html). |

To allow a Veeam Backup & Replication server to communicate with a backup appliance operating in a [private environment](appliance_in_private.md), you can establish an AWS Site-to-Site VPN (Site-to-Site VPN) connection between the VPC of the appliance and your on-premises network:

1. [Create a customer gateway](create_customer_device.md).
2. [Create a virtual private target gateway and attach the gateway to the VPC](create_target_gateway.md).
3. [Enable route propagation](configure_routing_vpn.md).
4. [Allow inbound traffic to the backup appliance](update_security_group.md).
5. [Create a VPN connection](create_vpn_connection.md).

Page updated 4/25/2025

Page content applies to build 10.0.0.232
