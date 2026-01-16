---
title: "private_networks_backup_acc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/private_networks_backup_acc.html"
last_updated: "5/31/2024"
product_version: "10.0.0.232"
---


In this article

For Veeam Backup for AWS to be able to deploy worker instances in a private environment in the [backup account](worker_options.md#backup), perform the following steps:

1. [Create VPC interface and S3 interface endpoints for subnets to which worker instances will be connected](create_interface_endpoints.md).
2. [Create a peering connection between VPCs](create_vpc_peering_connection.md).
3. [Add routes to the route tables associated with the subnets of the VPCs](configure_routing_network.md).

[![Private Networks](images/private_networks.webp)](images/private_networks.webp "Private Networks")

Page updated 5/31/2024

Page content applies to build 10.0.0.232
