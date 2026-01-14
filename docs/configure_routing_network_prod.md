---
title: "configure_routing_network_prod"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/configure_routing_network_prod.html"
last_updated: "8/2/2023"
product_version: "10.0.0.232"
---


In this article

If you have created a peering connection between two different VPCs, you must add routes to the route tables associated with the subnets of the accepter and requester VPC to enable private traffic between those VPCs.

To add a route to a route table, do the following:

1. In the VPC console, navigate to Virtual Private Cloud > Route tables, choose the route table and click Actions > Edit routes.
2. Complete the Edit routes wizard:

1. Click Add routes.
2. In the Destination field, specify the range of IPv4 addresses to which the network traffic in the peering connection must be directed.

The IPv4 address range must be specified in the CIDR notation (for example, 12.23.34.0/24).

1. In the Target field, select the Peering Connection option and specify the ID of the peering connection.

To obtain the ID, you can look it up on the Peering connections page in the VPC console.

1. Click Save changes.

Page updated 8/2/2023

Page content applies to build 10.0.0.232
