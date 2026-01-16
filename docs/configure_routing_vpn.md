---
title: "configure_routing_vpn"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/configure_routing_vpn.html"
last_updated: "10/10/2025"
product_version: "10.0.0.232"
---


In this article

To allow the backup appliance to access the customer gateway and to automatically propagate Site-to-Site VPN routes, enable route propagation in the route table associated with a subnet of the appliance VPC:

1. In the Amazon VPC console, navigate to Virtual Private Cloud > Route Tables.
2. In the Route tables list, choose the necessary route table and click Actions > Edit Route Propagation.
3. In the Edit route propagation wizard, select the Enable check box and click Save.

Page updated 10/10/2025

Page content applies to build 10.0.0.232
