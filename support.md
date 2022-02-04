---

copyright:
  years: 2015, 2020
lastupdated: "2020-11-12"

subcollection: mas-ms

---

{:shortdesc: .shortdesc}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Support
{: #support}

Please note this section is under construction.

## Database Support and Access
{: #database-support}

IBM Maximo Application Suite Managed Services supports DB2 as the database for the Suite.  Clients who wish to directly access their data can with the following restrictions or procedures:

* Direct access to the production database is not allowed.  If a client wishes to access production data, they must order a data replica and a read only user can be created against this replica.  This replica is near real time so it will mirror the production data.

* Read only users can be requested for non-productin databases.

* Read / Write users can be requested for development databases.

A support ticket must be submitted listing the names and emails of the users needing access.  
One ticket is required for each database.

All users created is the client responsibility to ensure once access is no longer required a support ticket created to remove that access.


## Compatibility and Dependencies
{: #compatibility-dependencies}

Please see the following link for the compatibility matrix:

https://www.ibm.com/support/pages/maximo-product-configuration-matrix


## How to Access IBM COS (Cloud Object Storage) Buckets
{: #access-cos-buckets}

* To access IBM COS bucket you have to configure Rclone. Rclone is the utility via which you can access IBM COS bucket and upload/download the content.

* To configure Rclone please use steps below. You will be needing below information while configuring the Rclone. 

* A separate Rclone config is needed for each bucket as the access credentials for each bucket is unique.

* Some buckets are readonly which means you can only download data from that bucket while some are read/write meaning you can upload and download data. 

The below steps can only be performed by the client once they have received their Welcome Letter.

## Rclone Config for COS file Upload and Download - Step-by-Step Guide
{: configure-rclone}

### Pre-req Steps:
{: rclone-pre-req-steps]

1. Installation of Rclone - https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-rclone
2. Your Welcome Letter from the MAS MS Provision Team with the following details. 
  * Public Endpoint (ie. s3.us-east.cloud-object-storage.appdomain.cloud ==> us-east or s3.eu-de.cloud-object-storage.appdomain.cloud ==> eu-de)
  * Access_key_id
  * Secret_access_key
  * Bucket Name

### Terminal Steps:
{: rclone-terminal-steps}

1. Run rclone config and select n for a new remote
2. Enter a name for the configuration
3. Enter "4" for Storage (IBM COS)
4. Enter "6" for Provider (IBMCOS)
5. Press Enter for env_auth (false)
6. Enter access_key_id from above
7. Enter secret_access_key for secret_access_key
8. Press Enter  for region
9. Enter 9 ( US Region East Endpoint / us-east) or 23 (EU Region DE Endpoint / eu-de) for endpoint
10. Enter 5 (US East Region Standard / us-east-standard) or 13 (EU Cross Region Standard / eu-standard) for location_constraint
11. Hit Enter for acl (This will take the default value).
12. Enter No for "Edit advanced config?": You will see the details of your newly created configuration
13. Enter Yes for y/e/d: You will see your Current Remotes configuration list
14. Enter q for e/n/d/r/c/s/q to Quit config
15. After you successfully completed above steps you will have the RemoteName (The one you have just created).

### Common Commands to Upload/Download data to and from COS
{: common-cos-commands}

* List available buckets
  rclone lsd RemoteName:

* List contents of a bucket
  rclone ls RemoteName:newbucket

* Copy a file from local to remote (COS)
  rclone copy /Users/file.txt RemoteName:bucketname

* Copy a file from remote(COS) to local
  rclone copy RemoteName:bucketname /Users/Documents/

* rclone sync
  rclone sync source:path dest:path 

## Development in MAS-MS
{: #development-mas-ms}

## Production vs Non-Production
{: #production-vs-non-production}

## Maximo Mobile
{: #maximo-mobile}

For questions related to use of Maximo Mobile in MAS-MS Manage, please refer to the links below:

* Maximo Manage Version 8.2 - https://www.ibm.com/docs/en/maximo-manage/8.2.0?topic=managing-maximo-mobile
* Maximo Manage Version 8.1 - https://www.ibm.com/docs/en/maximo-manage/8.1.0?topic=managing-maximo-mobile
