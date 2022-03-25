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

## MAS-MS Environment Route URLs
{: #environment-route-urls}

MAS Application Suite Instance:

`https://main.home.INSTANCE_NAME.suite.maximo.com/`

Admin:

`https://maxinst.manage.INSTANCE_NAME.suite.maximo.com/toolsapi`
 
INSTANCE_NAME = Your environment instance identifier found in your Welcome Letter.

## Database Support and Access
{: #database-support}

IBM Maximo Application Suite Managed Services supports DB2 as the database for the Suite.  Clients who wish to directly access their data can with the following restrictions or procedures:

* Direct access to the production database is not allowed.  If a client wishes to access production data, they must order a data replica and a read only user can be created against this replica.  This replica is near real time so it will mirror the production data.

* Read only users can be requested for non-production databases.

* Read / Write users can be requested for development databases.

* Connection is currently JDBC only.

Please note, if a client has been granted write access to a database, and there are issues with data, the SRE team will only restore the database back to the last version.  SRE personnel will not troubleshoot queries or data issues in these databases. 

A support case must be submitted listing the names and emails of the users needing access.  
One ticket is required for each database.

It is the client's responsibility to ensure once access is no longer required for a user, a support case is submitted to have the IBM SRE team remove that user's access.

## How to Access IBM COS (Cloud Object Storage) Buckets
{: #access-cos-buckets}

* To access IBM COS bucket you have to configure Rclone. Rclone is the utility via which you can access IBM COS bucket(s) and upload/download the content.

* To configure Rclone please use steps below. You will need this information while configuring Rclone. 

* A separate Rclone config is needed for each bucket as the access credentials for each bucket are unique.

* Some buckets are read-only which means you can only download data from that bucket while some are read/write meaning you can upload and download data. 

The below steps can only be performed by the client once they have received their Welcome Letter.

### Rclone Config for COS file Upload and Download - Step-by-Step Guide
{: #configure-rclone}

### Pre-requisite Steps:
{: #rclone-pre-req-steps}

1. Installation of Rclone - https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-rclone
2. Your Welcome Letter from the MAS MS Provision Team with the following details:
* Public Endpoint (ie. s3.us-east.cloud-object-storage.appdomain.cloud ==> us-east or s3.eu-de.cloud-object-storage.appdomain.cloud ==> eu-de)
* Access_key_id
* Secret_access_key
* Bucket Name

### Terminal Steps:
{: #rclone-terminal-steps}

1. Run rclone config and select n for a new remote
2. Enter a name for the configuration
3. Enter "4" for Storage (IBM COS)
4. Enter "6" for Provider (IBMCOS)
5. Press Enter for env_auth (false)
6. Enter access_key_id from above
7. Enter secret_access_key for secret_access_key
8. Press Enter for region
9. Enter 9 (US Region East Endpoint / us-east) or 23 (EU Region DE Endpoint / eu-de) for endpoint
10. Enter 5 (US East Region Standard / us-east-standard) or 13 (EU Cross Region Standard / eu-standard) for location_constraint
11. Hit Enter for acl (This will take the default value).
12. Enter No for "Edit advanced config?": You will see the details of your newly created configuration
13. Enter Yes for y/e/d: You will see your Current Remotes configuration list
14. Enter q for e/n/d/r/c/s/q to Quit config
15. After you successfully completed above steps you will have the RemoteName (The one you have just created).

### Common Commands to Upload/Download data to and from COS
{: #common-cos-commands}

| Description | Command Example |
| -------------- | -------------- |
| List contents of a bucket | rclone ls RemoteName:newbucket |
| Copy a file from local to remote (COS) | rclone copy /Users/file.txt RemoteName:bucketname |
| Copy a file from remote (COS) to local | rclone copy RemoteName:bucketname /Users/Documents/ |
| rclone sync | rclone sync source:path dest:path |
{: caption="Table 1. Common IBM COS (Cloud Object Storage) Commands" caption-side="bottom"} 

## Accessing Server Logs for Maximo Manage
{: #accessing-server-logs}

Below are the steps required to upload server bundle logs from your log location on WebSphere Application Server Liberty.

Make the following API request: 

* POST:  https://hostname/maximo/api/service/logging?action=wsmethod:submitUploadLogRequest 

* Header:  Provide the API key in the header of the request

* Body:  The body is empty

The API request creates an entry in the LOGREQUEST table of the Maximo Manage database for each server bundle. A continuously running cron task uploads the compressed log files to your S3 storage location when the table is updated. The name of each file contains the source location and the timestamp of when the command started to run.  You will have a Bucket for Logs.  This bucket name will be defined in your Welcome Letter.

* Maximo Manage API Documentation - https://www.ibm.com/docs/en/maximo-manage/8.1.0?topic=suite-apis-administrative-utilities

## Integration
{: #integration}

### Server Folder Access
{: #integration-server-folder-access}

In your welcome letter you will receive details on a bucket for customer files.  Use that bucket to upload all files you would like the Maximo Manage server to have access to.  The path for that directory will be /MeaGlobalDirs

* Flat File Consumer directory:         /MeaGlobalDirs
* Migration Manager Target directory:   /MeaGlobalDirs/MigrationManager

All integrations are done through API Keys. See link below for further details.

https://www.ibm.com/docs/en/maximo-manage/8.1.0?topic=applications-integration-framework-overview

### Maximo Manage Queues
{: #integration-maximo-manage-queues}

The MAS environments use Kafka queues as JMS queues are not configured. If your MAS order indicates you will be using integrations then all of the Kafka setup will be completed by the IBM MAS-MS SRE provisioning team.

* EndPoints will need to be configured to use the Kafka queues
* Cron activation will need to be enabled by the customer

* Maximo Manage Kafka Documentation - https://www.ibm.com/docs/en/maximo-manage/8.1.0?topic=applications-integration-by-using-apache-kafka

### Administrative Utilities (API Calls)
{: #admin-util-api-calls)}

You can run script commands for several key utilities by using API requests. The script commands can run the integrity checker utilities, start and stop the Maximo® Manage pods, download log files or a list of log files, and upload logs to Simple Storage Service (S3) Cloud Object Storage.
 
* More details can be found at: https://www.ibm.com/docs/en/maximo-manage/8.1.0?topic=suite-apis-administrative-utilities

| Description | API Call Example |
| -------------- | -------------- |
| Generate the integrity checker log | POST https://**Adminurl**/toolsapi/toolservice/icheckerreport |
| Get an integrity checker log | GET https://**Adminurl**/toolsapi/toolservice/toolslog?logfile=name of report from icheckerreport request |
| Get a list of all tools logs | GET https://**Adminurl**/toolsapi/toolservice/toolslog |
| Run the integrity checker utility | POST https://**Adminurl**/toolsapi/toolservice/icheckerrepair |
| Upload logs from Maximo Manage pods to S3 Cloud Object Storage | POST https://**ManageInstanceHostname**/maximo/api/service/logging?action=wsmethod:submitUploadLogRequest |
| Stop the Maximo Manage pods | POST http://**Adminurl**/toolsapi/toolservice/managestop |
| Start the Maximo Manage pods | POST http://**Adminurl**/toolsapi/toolservice/managestart |
{: caption="Table 1. Sample API Calls" caption-side="bottom"}

The **Adminurl** will be defined in the Welcome Letter.
 
Note: The above API calls are only available in the non-production environments. The only call which is available for Prod environment is Upload logs from Maximo Manage pods to S3 Cloud Object Storage.

## SAML SSO Configuration
{: #saml-sso-config}

The first step of the configuration is for the MAS SRE team to create the SAML Service Provider Information metadata file. For this setup the customer will need to provide the the User Identifier (Name ID) format. Below are the possible options for Name ID's.

* email: 'urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress',
* customize: formatMessage(messages.nameIDFormatCustomize),
* encrypted: 'urn:oasis:names:tc:SAML:2.0:nameid-format:encrypted',
* entity: 'urn:oasis:names:tc:SAML:2.0:nameid-format:entity',
* kerberos: 'urn:oasis:names:tc:SAML:2.0:nameid-format:kerberos',
* persistent: 'urn:oasis:names:tc:SAML:1.1:nameid-format:persistent',
* unspecified: 'urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified',
* windowsDomainQualifiedName:'urn:oasis:names:tc:SAML:1.1:nameid-format:WindowsDomainQualifiedName',
* x509SubjectName: 'urn:oasis:names:tc:SAML:1.1:nameid-format:X509SubjectName',

Note: When creating a case requesting your SAML SSO setup please include one of the above User Identifiers in the case details.  

MAS User and Identity Details:
https://www.ibm.com/docs/en/mas85/8.5.0?topic=administering-configuring-suite#users-id-section

MAS SAML Authentication:
https://www.ibm.com/docs/en/mas86/8.6.0?topic=administering-configuring-suite#sa

## LDAP user registry synchronization
{: #ldap-registry-sync}

User registry synchronization simplifies Maximo Application Suite user management by synchronizing users and groups between an LDAP server and your local Maximo Application Suite user registry. To initiate the LDAP Authentication setup you will need to submit a case to the IBM Support Community with the following details.
 
Configuration parameters
 
LDAP domain attributes:
* URL – ldaps://hostname:port
* Bind DN
* Bind Password
* Base DN
* User ID map
 
User synchronization:
* User Base DN
* User ID map
* User filter
 
Group synchronization:
* Group Base DN
* Group filter
* Group ID map
* Group member ID map
 
Other:
* Synchronization schedule
* Identity provider
* Default permissions
 
Note: typically a site-to-site VPN is required to make a connection from the MAS-MS environment to your LDAP server.
 
Additional details on LDAP user registry synchronization can be found here:
https://www.ibm.com/docs/en/mas86/8.6.0?topic=access-administering-ldap-user-registry-synchronization 

## SMTP Setup
{: #smtp-setup}

### MAS SMTP Configuration
{: #mas-smtp-config}

To enable outbound emails from your Maximo Application Suite Manage environment from the provided SMTP relay, you must raise an IBM Support case to configure SMTP Domain Authentication. Completing this configuration will allow you to send email from hosted Manage environment as your %CUSTOMERNAME% domain email addresses. If you plan to use your own SMTP host, this process will not apply.

In the case, please include:

* Case title: SMTP / outbound email activation
* Case description: Please initiate domain authentication for customerdomain.com. This domain should align with the email addresses used in Manage. Please provide contact details / email address of a person who has access to add DNS records for the domain(s) you specify. With these details the IBM SRE Team can generate the DKIM / Domain Authentication records which will be sent to the contact you specify (which has access to add DNS records). Once said contact adds the DNS records, the IBM SRE team will then need to perform a lookup / validation to ensure these records are intact. Once validated, customer will be able to send email as email addresses from the domain(s) specified.
* Note: If SendGrid DKIM records already exist in the DNS server in question, please let the IBM SRE team know so they can generate a unique DKIM selector.

### Customer Managed SMTP Configuration
{: #customer-smtp-config}

If you plan to use your own SMTP server instead of the provided MAS SMTP relay, you must raise an IBM Support case.

In the case, please include:

1. Case title: SMTP / outbound email activation
2. Case description: Please configure our MAS-MS environment to use the following SMTP server:

* SMTP hostname
* SMTP Port
* SMTP user
* SMTP password
* SMTP SSL Certificate (if using SMTP over SSL / port 465)
* Sender Address (the email address that MAS should send FROM / as)

Once this case and details are received, we generate and send 3 DNS records for you to add to your DNS server to complete the outbound email configuration.

## Site-to-Site IPsec VPN
{: #site-to-site-vpn}
 
A Site-to-Site IPsec VPN can be configured between the IBM Cloud environment and a customer site or third party location. This type of VPN establishes a persistent tunnel between the two sites. Site-to-Site VPNs are not configured by default. The setup and configuration of a Site-to-Site VPN can be complex and will require both IBM and the customer's network SMEs to work together. Initial VPN settings and shared parameters must first be agreed upon by both parties. Source and destination IPs must then be determined along with the type and direction of traffic. The tunnel must be stood up, along with routing, IP Address NATing, and applicable firewall rules on both sides. VPNs can take 2-4 weeks to design, setup, test and validate (from start to finish). Proper time should be allowed for a VPN build when planning integrations or services will that depend on it for connectivity. MAS-MS customers must specifically request a VPN by submitting a case to the IBM Support Community.

* Note: Only one case is needed for VPN setup and can cover configuration for multiple environments (DEV, TEST, PROD, etc).
* Note: It is important to bear in mind a VPN may not necessarily be needed to establish certain types of connectivity. Some integration types can run over HTTPS and/or SFTP and may not require a VPN.

## Maximo Mobile
{: #maximo-mobile}

For questions related to use of Maximo Mobile in MAS-MS Manage, please refer to the links below:

* Maximo Manage Version 8.2 - https://www.ibm.com/docs/en/maximo-manage/8.2.0?topic=managing-maximo-mobile
* Maximo Manage Version 8.1 - https://www.ibm.com/docs/en/maximo-manage/8.1.0?topic=managing-maximo-mobile

## Self-Service Portal
{: #ssp}

A Self Service Portal (SSP) for MAS Managed Service (MAS-MS) is not available at this time and is under construction.