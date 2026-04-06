#### **Secure Cloud Storage Management using AWS S3 Buckets**



##### Project Overview

This project demonstrates how to create, secure, and manage cloud storage using Amazon S3 buckets through AWS CLI. It covers the complete lifecycle of S3 buckets including creation, applying security measures, and deletion.

##### 

##### Objective

\- To create and manage S3 buckets using AWS CLI  

\- To implement security features for cloud storage  

\- To demonstrate lifecycle management of S3 buckets  



##### Technologies Used

\- Amazon Web Services (AWS)

\- AWS CLI

\- Amazon S3 (Simple Storage Service)



##### Prerequisites

\- AWS Free Tier Account  

\- IAM User with programmatic access  

\- AWS CLI installed and configured  



##### Steps to Execute



1\. Configure AWS CLI

aws configure



2\. Create S3 Buckets

aws s3 mb s3://my-first-s3-bucket-1806

aws s3 mb s3://my-second-s3-bucket-1806



3\. Verify Buckets

aws s3 ls



4\. Block Public Access (Security)

aws s3api put-public-access-block --bucket my-first-s3-bucket-1806 --public-access-block-configuration BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true



5\. Enable Versioning

aws s3api put-bucket-versioning --bucket my-first-s3-bucket-1806 --versioning-configuration Status=Enabled



7\. Delete Second Bucket

aws s3 rb s3://my-second-s3-bucket-1806



8\. Suspend Versioning

aws s3api put-bucket-versioning --bucket my-first-s3-bucket-1806 --versioning-configuration Status=Suspended



9\. Delete First Bucket

aws s3 rb s3://my-first-s3-bucket-1806



10\. Verify Deletion

aws s3 ls



##### Security Features Implemented

Block Public Access

Prevents unauthorized access to S3 buckets

Versioning

Maintains multiple versions of objects for data protection

Server-Side Encryption (AES-256)

Ensures data is stored securely in encrypted format





##### Output



Successfully created two S3 buckets

Applied security configurations

Deleted buckets successfully using AWS CLI



##### Key Concepts

S3 buckets are globally unique

Buckets are private by default

Versioning helps in data recovery

Encryption ensures data security

AWS CLI enables automation of cloud tasks



##### Notes

ACLs are not used as they are disabled by default in modern AWS

Bucket names must be unique globally

Always delete resources to avoid charges



##### Conclusion



This project demonstrates secure cloud storage management using Amazon S3. It shows how to create, secure, and delete storage resources efficiently using AWS CLI while ensuring data protection and access control.

