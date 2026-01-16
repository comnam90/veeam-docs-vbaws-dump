---
title: "repositories_add_s3endpoint"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/repositories_add_s3endpoint.html"
last_updated: "8/20/2025"
product_version: "10.0.0.232"
---


In this article

[This step applies only if you have enabled the [private network deployment](enable_private_network_deployment.md) functionality]

At the Settings step of the wizard, specify an S3 interface endpoint that will be used to communicate with the Amazon S3 service.

For an S3 interface endpoint to be displayed in the Interface VPC endpoint list, it must be created in the Amazon VPC console for all subnets to which the worker instances will be connected, as described in section [Configuring Private Networks](configuring_private_networks.md#private_network).

|  |
| --- |
| Important |
| S3 gateway endpoints are not supported when using the private network deployment functionality. |

[![Specifying Repository Settings](images/repo_add_specify_endpoint.webp)](images/repo_add_specify_endpoint.webp "Specifying Repository Settings")

Page updated 8/20/2025

Page content applies to build 10.0.0.232
