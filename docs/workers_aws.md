---
title: "workers_aws"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/workers_aws.html"
last_updated: "12/4/2025"
product_version: "10.0.0.232"
---


In this article

If you want initial full backups to be processed quickly, it is recommended that you use a larger worker instance profile, and then change it to a smaller profile for incremental backup. You can change worker instance profile settings on a regional basis, so make sure that the worker instance size is appropriate to process the largest workload within the required time.

Each worker instance is deployed as an amzn-linux-v2 image, and the binaries are downloaded from the connected S3 bucket. Instance types of worker instances sizes depend on the total EBS volume size.

| Worker Profile | Default Instance Type | Usage |
| --- | --- | --- |
| Small | c5.large | Processing EBS volumes under 1024 GB (default) |
| Medium | c5.2xlarge | Processing EBS volumes between 1024 GB and 16 TB (default) |
| Large | c5.4xlarge | Processing EBS volumes over 16 TB (default) |
| Archiving | c5.2xlarge | Processing EBS volumes under 6 TB |
| c5.4xlarge | Processing EBS volumes over 6 TB |

For more information on AWS pricing, see [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-on-demand-instances.html).

Related Topics

* [Managing Worker Profiles](https://helpcenter.veeam.com/docs/vbaws/guide/worker_edit_profile.html?ver=70)
* [Solution Architecture](overview.md)

Page updated 12/4/2025

Page content applies to build 10.0.0.232
