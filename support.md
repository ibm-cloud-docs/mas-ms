---

copyright:
  years: 2015, 2020
lastupdated: "2023-07-31"

subcollection: mas-ms

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:attention: .attention}
{:external: target="_blank" .external}

# Support
{: #support}

Support for MAS Dedicated can be obtained by submitting a support case through the [IBM support portal](https://www.ibm.com/mysupport){: external}. You must have an [IBMid](https://myibm.ibm.com){: external} and be [registered for support](/docs/mas-ms?topic=mas-ms-getting-started-with-ibm-maximo-application-suite-dedicated#how-to-register-for-mas-support) before you can [create a case](/docs/mas-ms?topic=mas-ms-getting-started-with-ibm-maximo-application-suite-dedicated#how-to-create-a-case). Cases are reviewed based on the severity level assigned. Please see table below for further details.

Before submitting a case, check to see if your issue can be addressed using the [Self Service Portal (SSP)](/docs/mas-ms?topic=mas-ms-ssp#supported-requests). If a case/ticket is submitted to execute a request that is available on the Self Service Portal, the case will be rejected and closed. Customers can open a case if their job fails in the Self Service Portal. Be sure to include detail of the failed job in the case. Please note as more Self Service features are added to the Self Service Portal, the expectation is that customers will use this functionality in lieu of submitting individual support cases.


| Case Severity Level | Description | Response Time Objective | Response Time Coverage |
| -------------- | -------------- | -------------- | -------------- |
| 1 | Critical Business Impact/Service Down: Business critical functionality is inoperable or critical interface has failed. This should be used for Production environments only and indicates an inability to access services resulting in a critical impact on operations. | Within 1 hour | 24x7 |
| 2 | Significant business impact: A service, business feature, or function of the service is severely restricted in its use, or you are in jeopardy of missing business deadlines. | Within 2 business hours | Monday – Friday business hours |
| 3 | Minor business impact: The service or functionality is usable and the issue does not represent a critical impact on operations. | Within 4 business hours | Monday – Friday business hours |
| 4 | Minimal business impact: An inquiry or non-technical request. | Within 1 business day | Monday – Friday business hours |
{: caption="IBM Support Case Severity Levels and Response Time" caption-side="bottom"}

**Off Shift Weekend/Holiday Support** (Severity 1 Only)

If you require support between the hours of Friday 8pm to Sunday 6pm US Eastern Time (and Christmas Day and New Years Day) for a Severity 1 case, the following steps are required:

1. Log a new case using the IBM Support Community and set the Severity to 1 (only if not related to an existing Sev1). Provide as much detail as possible, including the business impact and confirm it is a production system issue.
2. Call your local IBM Support Center ([click here for IBM Directory of worldwide contacts](https://www.ibm.com/planetwide)) and request to speak to the duty engineer.

Failure to follow this process results in no support during off-shift hours.
{: note}

**Response Time Objective** describes IBM's goals only and do not represent a guarantee of performance.

**Business Hours** reflect normal country business hours in your time zone. For example, 8:00 AM to 5:00 PM in North America or 9:00 AM to 6:00 PM in some parts of Asia and Europe, Monday through Friday, excluding weekends and national or statutory holidays.

For further details, please refer to the [IBM Support Guide](https://www.ibm.com/support/pages/node/6443339){: external}

## MAS-Dedicated Environment Route URLs
{: #environment-route-urls}

MAS Application Suite Instance:

`https://main.home.INSTANCE_NAME.suite.maximo.com/`

Admin:

`https://maxinst.manage.INSTANCE_NAME.suite.maximo.com/toolsapi`

INSTANCE_NAME = Your environment instance identifier found in your Welcome Letter.

Once an environment has been provisioned, the URL can not be changed.
{: note}

## Database Support and Access
{: #database-support}

IBM Maximo Application Suite Dedicated supports DB2 as the database for the Suite.  Clients who wish to directly access their data can with the following restrictions or procedures:

* Direct access to the production database is not allowed.  If a client wishes to access production data, they must order a data replica and a read only user can be created against this replica.  This replica is near real time so it will mirror the production data.

* SSL Connection can be done using JDBC or ODBC.  IBM is not responsible for any tool a client selects to make this connection with and it will be the client responsibility to troubleshoot issues connecting their chosen tool to the database. Non-SSL connections are not allowed.

Please note, if a client has been granted write access to a database, and there are issues with data, the SRE team will only restore the database back to the last version.  SRE personnel will not troubleshoot queries or data issues in these databases.

The Access Management Tool located on the Self Service Portal (SSP) should be used to request and/or remove Database Access Acounts. Please see link below for further information:

https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-ssp#access-management-overview

It is the client's responsibility to ensure once database access is no longer required for a user, they remove that user's access using the SSP.
{: note}

## Summary of MAS-Dedicated Database Access Rules & Guidelines
{: #mas-dedicated-database-access-rules-summary}

| Database Task | Non-PROD | PROD |
| -------------- | -------------- | -------------- |
| Direct Read Access | Yes | Not Allowed (only allowed if secondary DB ordered) |
| Direct Write Access | Yes | Not Allowed |
| Create/Update Access for Triggers | Not Allowed | Not Allowed |
| Create/Update Access for Procedures | Not Allowed | Not Allowed |
| Run Explain Plan | Not Allowed | Not Allowed |
| Create/Update Tables/Columns | Maximo DB Configuration App (UI) | Maximo DB Configuration App (UI) |
| Create/Update Access for Indexes | Maximo DB Configuration App (UI) | Maximo DB Configuration App (UI) |
| Create/Update Access for Sequences | Maximo DB Configuration App (UI) | Maximo DB Configuration App (UI) |
| Run SQL Scripts | Not Allowed | Yes | See guidelines below |
| Run DBC Scripts | Not Allowed | Not Allowed |
{: caption="MAS-Dedicated Database Access Rules & Guidelines" caption-side="bottom"}

## Best Practices for Configuring Maximo Databases and Migrating Changes
{: #configuring-maximo-database}

The Maximo Database Configuration Application should be used for making database configuration changes. For further details, please see link below:

https://www.ibm.com/support/pages/best-practice-configuring-your-maximo-database

Migration Manager should be used for migrating changes from one environment to another (for example from DEV to TEST). For further details, please see link below:

https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=content-migration

The above processes have all validation built in, which reduces the chances of failure.
{: note}

## Running SQL Scripts in Production
{: #running-sql-scripts}

For production environments, the IBM SRE team highly discourages requests to run sql scripts with insert/update/delete statement(s). These are considered high risk and can break overall data integrity. SRE will only execute statements that have been tested by the client on their non-production environments.  Every effort should be made to use [automation scripts](https://www.ibm.com/docs/en/maximo-manage/continuous-delivery?topic=scripts-automation){: external} or standard tools through the Maximo front end rather than altering data directly. If a SQL script of this type is required, clients can request this via [IBM case ticket](https://www.ibm.com/mysupport){: external}, with sql script attached along with business justification as to why its needed and why changing from Maximo front end is not possible. There is a 3 day lead time for SQL scripts. The case needs to include:

* SQL Script (as an attachment)
* Design or description of what the script is doing to the data
* Business justification of why the script is required
* Technical justification of why the script's commands cannot be done via Maximo front end using DB configuration
* Request to take full offline backup of target database prior to running script

SQL Script Limitations:

* SQL scripts cannot be run in Non-Production environments.
* DBC Scripts are not allowed in any environment.
* Backups will be done in offline mode which will require target site to be down / unavailable. Backups can take several hours based on database size.
* IBM SRE team is not responsible for script not working, script corrections and any issues that arise during or after sql execution. If issues arise, IBM SRE can only restore from backup.
* Any outages caused by the execution of the script and time to recover will not be counted as an SLA breach.

## How to Access IBM COS (Cloud Object Storage) Buckets
{: #access-cos-buckets}

* To access IBM COS bucket you have to configure Rclone. Rclone is the utility via which you can access IBM COS bucket(s) and upload/download the content.

* To configure Rclone please use steps below. You will need this information while configuring Rclone.

* A separate Rclone config is needed for each bucket as the access credentials for each bucket are unique.

* Some buckets are read-only which means you can only download data from that bucket while some are read/write meaning you can upload and download data.

All Custfile bucket data will be purged automatically by IBM SRE when it is 15 days old and Log bucket data when it is 30 days old.
{: note}

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
3. Enter "5" for Storage (IBM COS)
4. Enter "10" for Provider (IBMCOS)
5. Press Enter for env_auth (false)
6. Enter access_key_id from above
7. Enter secret_access_key for secret_access_key
8. Press Enter for region
9. Choose a number for the region defined in your Welcome Letter - Example: Enter 9 (US Region East Endpoint / us-east) for endpoint
10. Choose a number for the region defined in your Welcome Letter - Example: Enter 5 (US East Region Standard / us-east-standard) for location_constraint
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
{: caption="Common IBM COS (Cloud Object Storage) Commands" caption-side="bottom"}

## Accessing Server Logs for Maximo Manage
{: #accessing-server-logs}

Below are the steps required to upload server bundle logs from your log location on WebSphere Application Server Liberty.

Make the following API request:

* POST:  https://hostname/maximo/api/service/logging?action=wsmethod:submitUploadLogRequest

* Header:  Provide the API key in the header of the request

* Body:  The body is empty

The API request creates an entry in the LOGREQUEST table of the Maximo Manage database for each server bundle. A continuously running cron task uploads the compressed log files to your S3 storage location when the table is updated. The name of each file contains the source location and the timestamp of when the command started to run.  You will have a Bucket for Logs.  This bucket name will be defined in your Welcome Letter.

* Maximo Manage API Documentation - https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=applications-integration-apis

How to use the new Tools API with Maximo Application Suite:

https://www.ibm.com/support/pages/node/6519816?myns=swgother&mynp=OCSSRHPA&mync=E&cm_sp=swgother-

## ODBC Connectivity
{: #odbc-connectivity}

Connecting to the MAS Manage database using a DB2 ODBC Driver

* Download the ODBC driver for your DB2 Version using the link below. The ODBC driver should match with the DB2 database version on Cloud. If you do not know your DB2 version, please submit a case asking for this information.

https://www.ibm.com/support/pages/db2-odbc-cli-driver-download-and-installation-information

* After you download the correct driver follow the steps in the applicable **Installation** section

Lastly open the ODBC data source administration and select the above installed driver. Enter the username and password in the Data Source section and add below parameters in the Advance Setting:

- Database
- Hostname
- Port
- Security - SSL
- SSLServerCertificate <- Path of the your database certificate which we have provided to make the ssl connection

Pleae note ODBC driver setup and configuration with your specific tool is not support by IBM. The above information is provided for reference purposes only.

## Integration
{: #integration}

### Server Folder Access
{: #integration-server-folder-access}

In your welcome letter you will receive details on a bucket for customer files.  Use that bucket to upload all files you would like the Maximo Manage server to have access to.  The path for that directory will be /MeaGlobalDirs

* Flat File Consumer directory:         /MeaGlobalDirs
* Migration Manager Target directory:   /MeaGlobalDirs

All integrations are done through API Keys. See link below for further details.

https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=applications-integration-framework-overview

### Maximo Manage Queues
{: #integration-maximo-manage-queues}

The MAS Manage environments use Event Streams (IBM Kaftka) topics for integration. The event stream setup will be completed by the IBM MAS-Dedicated SRE provisioning team.

* EndPoints will need to be configured to use the event stream topics (client responsibility to make necessary changes)
* Cron activation will need to be enabled by the customer

Maximo Manage - Moving from JMS to Kafka:

https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=applications-integration-apache-kafka

### Administrative Utilities (API Calls)
{: #admin-util-api-calls}

You can run script commands for several key utilities by using API requests. The script commands can run the integrity checker utilities, start and stop the Maximo® Manage pods, download log files or a list of log files, and upload logs to Simple Storage Service (S3) Cloud Object Storage.

* More details can be found at: https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=reference-apis-administrative-utilities

| Description | API Call Example |
| -------------- | -------------- |
| Generate the integrity checker log | POST https://**Adminurl**/toolsapi/toolservice/icheckerreport |
| Get an integrity checker log | GET https://**Adminurl**/toolsapi/toolservice/toolslog?logfile=name of report from icheckerreport request |
| Get a list of all tools logs | GET https://**Adminurl**/toolsapi/toolservice/toolslog |
| Run the integrity checker utility | POST https://**Adminurl**/toolsapi/toolservice/icheckerrepair |
| Upload logs from Maximo Manage pods to S3 Cloud Object Storage | POST https://**ManageInstanceHostname**/maximo/api/service/logging?action=wsmethod:submitUploadLogRequest |
| Stop the Maximo Manage pods | POST http://**Adminurl**/toolsapi/toolservice/managestop |
| Start the Maximo Manage pods | POST http://**Adminurl**/toolsapi/toolservice/managestart |
{: caption="Sample API Calls" caption-side="bottom"}

The **Adminurl** will be defined in the Welcome Letter.

Note: The above API calls are only available in the non-production environments. The only call which is available for Prod environment is Upload logs from Maximo Manage pods to S3 Cloud Object Storage.

### Exporting and Importing File-based Data in Maximo Manage
{: #file-based-data}

See link below for further information on Exporting and Importing File-based Data in Maximo Manage:

https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=applications-exporting-importing-file-based-data

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
https://www.ibm.com/docs/en/mas-cd/continuous-delivery?topic=configuring-users-identity

MAS SAML Authentication:
https://www.ibm.com/docs/en/mas-cd/continuous-delivery?topic=authentication-methods#configuring-authentication__saml-authentication__title__1

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

Note: typically a site-to-site VPN is required to make a connection from the MAS-Dedicated environment to your LDAP server.

Additional details on LDAP user registry synchronization can be found here:
https://www.ibm.com/docs/en/mas-cd/continuous-delivery?topic=identity-ldap-user-registry-synchronization

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
2. Case description: Please configure our MAS-Dedicated environment to use the following SMTP server:

* SMTP hostname
* SMTP Port
* SMTP user
* SMTP password
* SMTP SSL Certificate (if using SMTP over SSL / port 465)
* Sender Address (the email address that MAS should send FROM / as)

Once this case and details are received, we generate and send 3 DNS records for you to add to your DNS server to complete the outbound email configuration.

## Site-to-Site IPsec VPN
{: #site-to-site-vpn}

A Site-to-Site IPsec VPN can be configured between the IBM Cloud environment and a customer site or third party location. This type of VPN establishes a persistent tunnel between the two sites. Site-to-Site VPNs are not configured by default. The setup and configuration of a Site-to-Site VPN can be complex and will require both IBM and the customer's network SMEs to work together. Initial VPN settings and shared parameters must first be agreed upon by both parties. Source and destination IPs must then be determined along with the type and direction of traffic. The tunnel must be stood up, along with routing, IP Address NATing, and applicable firewall rules on both sides. VPNs can take 2-4 weeks to design, setup, test and validate (from start to finish). Proper time should be allowed for a VPN build when planning integrations or services will that depend on it for connectivity. MAS-Dedicated customers must specifically request a VPN by submitting a case to the IBM Support Community.

* Note: Only one case is needed for VPN setup and can cover configuration for multiple environments (DEV, TEST, PROD, etc).
* Note: It is important to bear in mind a VPN may not necessarily be needed to establish certain types of connectivity. Some integration types can run over HTTPS and/or rclone and may not require a VPN.
* Note: Currently MAS on AWS does not support NAT at MAS side in Site-to-Site VPN

## Maximo Mobile
{: #maximo-mobile}

For questions related to use of Maximo Mobile in MAS-Dedicated Manage, please refer to the link below.
https://www.ibm.com/docs/en/mas-cd/maximo-manage/continuous-delivery?topic=managing-using-maximo-mobile

Once on the resulting page, select the desired version of Maximo Mobile from the drop-down 'Change version' in the top left corner.
