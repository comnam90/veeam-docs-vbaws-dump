---
title: "encryption_aws_cmks_creating_snapshots"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/encryption_aws_cmks_creating_snapshots.html"
last_updated: "10/8/2024"
product_version: "10.0.0.232"
---


In this article

The process of creating cloud-native snapshots of an EC2 instance with encrypted EBS volumes and an encrypted RDS instance does not differ from the same process for an instance with unencrypted volumes. The IAM role used to create cloud-native snapshots does not require any additional permissions — Veeam Backup for AWS encrypts these snapshots with the same KMS keys with which the source instance or volume is encrypted.

Page updated 10/8/2024

Page content applies to build 10.0.0.232
