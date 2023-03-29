---

copyright:
  years: 2015, 2023
lastupdated: "2023-03-23"

subcollection: mas-ms

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Self-Service Portal
{: #ssp}

The purpose of the Self-Service Portal is to empower our clients to execute selected services in both production and non-production environments. These pre-selected tasks can be run immediately or scheduled for a future time.

The Self-Service Portal is comprised of two main parts, the Access Management Tool for administering Access Requests, and the Self-Service Automation for submitting Service Requests to run against assets.

This portal is available to all IBM Maximo Application Suite – Managed Service and Maximo Application Suite – Dedicated Customers.

Use the following links to find more information:

[Obtaining Access to the Self-Service Automation](#obtaining-access-to-self-service-automation)

[Supported Request Types](#supported-requests)

[Submitting Requests](#submitting-requests)

[Reviewing Request Results](#reviewing-request-results)

[What to do in the event of a failure](#what-to-do-for-failure)

[Access Management](#access-management-overview)

You can access the self-service portal here:
https://devops.maximo.com

## Obtaining Access To Self-Service Automation
{: #obtaining-access-to-self-service-automation}

You must have access to the Access Management tool in the Self-Service Portal before obtaining access to Self-Service Automation. If you do not have access to the Access Management tool please see [Obtaining Access to the Access Management Tool](#obtaining-access-to-the-access-management-tool).

In order to obtain access to Self-Service Automation in the Self-Service Portal follow the steps below.

1. Sign into the portal at https://devops.maximo.com and Navigate to Security > Access Management in the toolbar.

![AMT-Sign-On](images/SSP-AMT-Sign-On.png "AMT-Sign-On"){: caption=""}

2. Select your IBMid from the list.

![AMT-Sign-On](images/SSP-AMT-Select-ID.png "AMT-Sign-On"){: caption=""}

3. Navigate to the Manage Access tab.

![AMT-Sign-On](images/SSP-AMT-Manage-Tab.png "AMT-Sign-On"){: caption=""}

4. Add an asset to the Assets table that you would like to request an access for.

Requesting Self-Service Automation access to one asset will grant Self-Service Automation access to all assets assigned to your customer. It is not necessary to request access for each asset you wish to run requests against.
{: note}

![AMT-Sign-On](images/SSP-AMT-Add-Asset.png "AMT-Sign-On"){: caption=""}

5. Add Self-Service Portal access to the Specific Access in the Environment table and enter a reason for the access request in the Justification section.

"Self-Service Portal" access equates to Self-Service Automation access in the Self-Service Portal.
{: note}

![AMT-Sign-On](images/SSP-AMT-Request-SSP.png "AMT-Sign-On"){: caption=""}

6. Save the record.

You have successfully submitted an access request for Self-Service Automation access! You will receive an email notification when your access request is reviewed and granted.

### Supported Requests
{: #supported-requests}

Currently Service Requests are only supported in non-production environments.
{: note}

#### Start Asset Management Application
{: #start-asset-management-application}

This task can be used to start the Maximo Manage application for the target environment.

#### Stop Asset Management Application
{: #stop-asset-management-application}

This task can be used to stop the Maximo Manage application for the target environment.

#### Restart Asset Management Application
{: #restart-asset-management-application}

This task can be used to restart the Maximo Manage application for the target environment.

#### Run ConfigDB
{: #run-configdb}

This task can be used to apply all pending database configuration changes for the target environment. The task stops the Maximo Manage application, runs the Maximo ConfigDB process, then restarts the Maximo Manage application.

This task could take several hours to complete depending on the types of changes being made and how much data resides in the database tables being modified. Additionally, access to the database will be limited during the execution of this task to users belonging to restricted access groups.
{: note}

#### Run REORG and RUNSTATS
{: #run-reorg-and-runstats}

This task will execute one of the following operations on the target environment depending on the option chosen.

`Runstats only` operation to improve SQL performance. This option updates statistics in the system catalog about tables, view, and indexes. DB2’s query optimizer uses these statistics to improve query performance.

`Offine reorganization` of tablespaces along with runstats operation for the target asset to improve SQL performance and reclaim fragmented disk space.

The environment will be unavailable during the execution of this task, and depending on the size of the database, this task may take up to several hours complete.

`Online reorganization` of tablespaces along with runstats operation for the target asset to improve SQL performance and reclaim fragmented disk space. The environment is not stopped for this option.

Most cases require only the Runstats operation. Reorganization of tablespaces need only be run if a significant amount of data has been deleted from the database since the last tablespace reorganization.
{: note}

#### Run MAS MustGather and upload to ECuRep
{: #run-mas-mustgather}

This task will collect application logs from the target environment and upload the logs to the ECuRep (IBM Support) server.

### Submitting a Service Request
{: #submitting-requests}

Currently Service Requests are only supported in non-production environments.
{: note}

1. Using your IBMid, sign-on to the portal (https://devops.maximo.com)

2. Click on New Service Request

![SSP-Sign-On](images/SSP-New-Request.png "SSP-Sign-On"){: caption=""}

3. Select the requested start time (if it is for the future). If you have not changed your timezone, the selection will be for UTC. Click the Calendar icon below the text field "Requested Start" and select the time and date you would like the job to start.

![SSP-Start-Time](images/SSP-SR-Start-Time.png "SSP-Start-Time"){: caption=""}

4. Select the environment to run the action against by clicking on the magnifying glass next to the "Target Environment" field. Select the environment from the pop-up list.

![SSP-Select-Asset](images/SSP-Select-Asset.png "SSP-Select-Asset"){: caption=""}

5. Select the action you would like to take by clicking on the magnifying glass next to the "Requested Action" field. Select the action from the pop-up list. Fill in any required information for the chosen action.

If you select a production asset then the pop-up list will be empty.
{: note}

![SSP-Select-Action](images/SSP-Select-Action.png "SSP-Select-Action"){: caption=""}

6. Click Save. And then Click the Queue Request button.

If the request is not Queued it will remain in New state and will not be run.
{: note}

![SSP-Queue-Request](images/SSP-Queue-Request.png "SSP-Queue-Request"){: caption=""}

7. Request will move to INPROG State once the request has been picked up to be executed by the tool.

Once a request has been picked up by the tool for processing the task cannot be stopped.
{: note}

### Reviewing Service Request Results
{: #reviewing-request-results}

1. Open the Service Requests App

![SSP-Open-SR-App](images/SSP-Open-SR-App.png "SSP-Open-SR-App"){: caption=""}

2. Find your service request and open it.

![SSP-Select-SR](images/SSP-Select-SR.png "SSP-Select-SR"){: caption=""}

In each of the fields including Service Request, Asset, Status you can enter filter criteria.  If you just want to display all requests just hit the "Enter" key.  Using your mouse, click on the desired service request number.

3. Click the log tab and review the log information.

![SSP-View-SR-Logs](images/SSP-View-SR-Logs.png "SSP-View-SR-Logs"){: caption=""}

### In the event of a failure
{: #what-to-do-for-failure}

Detailed log information surrounding the failure will be available in the log tab of the service request.  In the event the failure is not due to a problem with the data submitted with the required, you should engage the operations team by opening a case. Use the following links for more information.  Please include a request to complete the action required, as well documenting that this action was attempted via the self-service portal.

[Requesting Support for IBM Maximo Application Suite](https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-getting-started-with-ibm-maximo-application-suite-dedicated#how-to-register-for-mas-support)

[How To Create A Case](https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-getting-started-with-ibm-maximo-application-suite-dedicated#how-to-create-a-case)

Requests will be handled per the Service Description for non-production environments.  Issues with the portal are handled on the same service description.

[Service Descriptions and SLA](https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-services#service-description)

## Access Management Tool
{: #access-management-tool}

The Access Management Tool is a self-service tool, located in the IBM IoT Saas Self-Service Portal, where users can manage access to their MAS-Dedicated environments.

IBM IoT Saas Self-Service Portal URL:

https://devops.maximo.com

## Access Management Tool Overview
{: #access-management-overview}

### User Roles
{: #access-management-user-roles}

The Access Management Tool supports two user roles - standard users and manager users. Manager users have elevated accesses to manage the tool for their customer.

![SSP-AM-Overview-User-Roles](images/SSP-AM-Overview-User-Roles.png "SSP-AM-Overview-User-Roles"){: caption=""}

Manager User

A manager user is a user in the Access Management Tool with a role assignment of MANAGER. Manager user responsibilities include:

* Adding/removing users to the tool.
* Granting users access to the customer they are managing.
* Reviewing access requests.
* Viewing, modifying, and removing user accesses.
* Standard user responsibilities.

Standard User

A standard user is a user in the Access Management Tool with a role assignment of STD_USER. Standard user responsibilities include:

* Submitting access requests.
* Viewing, modifying, and removing their accesses.
* Deactivating their user account.

### Views & Tabs
{: #access-management-views-tabs}

List View

The List View page is the homepage of the Access Management Tool. This is where you can view the user accounts you have access to. Manager users can view user accounts that have access to the customer they are managing from this page. Standard users can view their user account from this page.

![SSP-AM-Overview-List-View](images/SSP-AM-Overview-List-View.png "SSP-AM-Overview-List-View"){: caption=""}

Person Information Tab

The Person Information tab contains user account details. These details include the user’s IBMid, name, email address, role, and customer(s) they have access to. This tab will also contain the customer a user is managing if they are a manager user.

![SSP-AM-Overview-Person-Info-Tab](images/SSP-AM-Overview-Person-Info-Tab.png "SSP-AM-Overview-Person-Info-Tab"){: caption=""}

Manage Access Tab

The Manage Access tab contains the user account’s existing and pending accesses. Access records are filtered by selecting the asset in the Assets table. Once selected, accesses for the selected asset can be seen in the Specific Access in the Environment table. In addition to viewing accesses, users can submit access requests for their user account from this tab.

![SSP-AM-Overview-Manage-Access-Tab](images/SSP-AM-Overview-Manage-Access-Tab.png "SSP-AM-Overview-Manage-Access-Tab"){: caption=""}

Access Approvals Tab

The Access Approvals tab is where manager users review access requests submitted for the customer they are managing. This tab is only accessible through the manager user’s account. Go to [How to Approve/Reject an Access Request](#approve-reject-access-am-tool) to read more about reviewing access requests.

![SSP-AM-Overview-Access-Approvals-Tab](images/SSP-AM-Overview-Access-Approvals-Tab.png "SSP-AM-Overview-Access-Approvals-Tab"){: caption=""}

## Obtaining Access to the Access Management Tool
{: #obtaining-access-to-am-tool}

Follow the steps below to obtain access to the Access Management Tool.

1. Create an IBMid

    An IBMid is required to login to the Access Management Tool. To create an IBMid click [here](https://myibm.ibm.com){: external}

2. Request Access

    A user managing the customer you want access to must add you to the tool. Contact one of your manager users to request they add you to the Access Management Tool. If you do not know who the manager users are for your account, submit a [support case](https://www.ibm.com/mysupport){: external} requesting this information.

    If you are new customer and manager users were not created for your account during the onboarding process, you must submit a [support case](https://www.ibm.com/mysupport){: external} designating at least two (2) managers for your account (1 primary, 1 backup). The case must include the email address and first and last name for each of the users. All email adresses must be associated with an [IBMid](https://myibm.ibm.com){: external}.
    {: note}

3. Navigate to the Access Management Tool

    Navigate to the Access Management Tool by logging into the [IBM IoT Saas Self-Service Portal](https://devops.maximo.com){: external} with your IBMid. Once logged in, select **Security** > **Access Management** from the navigation menu.

## Supported Access Requests
{: #suported-access-requests}

The Access Management Tool provides the ability for users to request and manage accesses to their MAS-Dedicated environments. The table below describes the accesses users can request. The table will be updated as new accesses are supported.

| Access Type | Summary |
| -------------- | -------------- |
| Self-Service Portal | Grants a user access to submit service requests through the Self-Service Automation for the customer the access request’s asset is linked to. For more information on Self-Service Automation access navigate to the [Self-Service Automation page](#obtaining-access-to-self-service-automation)|
| Client Communications Center | Obtain access to the Client Communications Center Dashboard for your organization and subscribe to email notifications.  \n For more information on the Client Communications Center, navigate to the [Client Communications Center](/docs/mas-ms?topic=mas-dedicated-client-communications-center) page.   \n For details on how to request Client Communications Center access, see [How to Request Client Communications Center Access](#how-to-request-ccc-access)|
| Create Database Service Account | Creates a database service account on the asset the access request is linked to. This account should be used for integration (i.e. used by a program not by a user). \n Database accounts requested for non-production assets will be granted read/write access to the primary database server. Accounts for production assets (not yet available) will be granted read only access on the standby database server. \n The database password and the required SSL certificate information will be populated on the Access record when the account is created. \n **Note:** Database service account passwords expire every 365 days. Passwords can be reset through the Access Management Tool. \n For details on how to request a Database Service Account, see [How to Request a Database Service Account](#how-to-request-database-service-account)|
| Create Database User Account | Creates a database user account on the asset the access request is linked to. \n Database accounts requested for non-production assets will be granted read/write access to the primary database server. Accounts for production assets (not yet available) will be granted read only access on the standby database server. \n The database password and the required SSL certificate information will be populated on the Access record when the account is created. \n **Note:** Database user account passwords expire every 90 days. Passwords can be reset through the Access Management Tool. \n For details on how to request a Database User Account, see [How to Request a Database User Account](#how-to-request-ccc-access)|
| Reset Database Account Password | Issues a request to reset the password for the selected Database User or Service Account. The new password will be made available in the access record when the request is completed. Additionally the Database SSL certificate information will be refreshed to ensure it is current with that is on the system. \n For details on how to Reset a Database Account Password, see [How to Reset a Database Account Password](#how-to-reset-database-password)|
| MAS Object Storage File Access | Not yet available. \n For details on how to request MAS Object Storage File access, see [How to Request MAS Object Storage File Access](#how-to-request-cos-file-access)|
| MAS Object Storage Log Access | Not yet available. \n For details on how to request MAS Object Storage Log access, see [How to Request MAS Object Storage Log Access](#how-to-request-ccc-access)|
{: caption="Table 1. Supported Access Requests" caption-side="bottom"}

### How to Request CCC Access
{: #how-to-request-ccc-access}

Follow the steps below to request access to the Client Communications Center Dashboard for your organization. For more information on the Client Communications Center, navigate to the [Client Communications Center](/docs/mas-ms?topic=mas-ms-client-communications-center) page.

1.	Sign into the Self-Service Portal with your IBMid:

    https://devops.maximo.com

    If you are unable to login to the Self-Service Portal please see [Obtaining Access to the Access Management Tool](#obtaining-access-to-am-tool)

2.	Navigate to the Access Management Tool by selecting **Security** > **Access Management** from the applications menu.

    ![MAS-MS-CCC-Access-1](images/MAS-MS-CCC-Access-1.png "MAS-MS-CCC-Access-1"){: caption=""}

3.	Select your IBMid from the list of users.

    ![MAS-MS-CCC-Access-2](images/MAS-MS-CCC-Access-2.png "MAS-MS-CCC-Access-2"){: caption=""}

4.	Select the **Manage Access** tab.

    ![MAS-MS-CCC-Access-3](images/MAS-MS-CCC-Access-3.png "MAS-MS-CCC-Access-3"){: caption=""}

5.	Add an asset to the **Assets** table by selecting the “New Row” button.

    ![MAS-MS-CCC-Access-4](images/MAS-MS-CCC-Access-4.png "MAS-MS-CCC-Access-4"){: caption=""}

6.	Select the search icon to bring up a list of assets you have access to.

If the asset you want to submit an access request for is not viewable in the asset list, you do not have access to the asset’s organization. To obtain access, contact the access manager for the organization. If you do not know who the access manager is, you may submit a support case [here](https://www.ibm.com/mysupport){: external} to request this information.
{: note}

    ![MAS-MS-CCC-Access-5](images/MAS-MS-CCC-Access-5.png "MAS-MS-CCC-Access-5"){: caption=""}

7.	Select an asset from the list for the organization you want to request Client Communications Center access to. Obtaining Client Communications Center access to one asset will grant you communications access to all assets for that organization.

    ![MAS-MS-CCC-Access-6](images/MAS-MS-CCC-Access-6.png "MAS-MS-CCC-Access-6"){: caption=""}

8.	Click on the row in the **Assets** table of the asset you just added. This will link the asset to the access requested in the next step.

    ![MAS-MS-CCC-Access-7](images/MAS-MS-CCC-Access-7.png "MAS-MS-CCC-Access-7"){: caption=""}

9.	Begin the access request process by selecting the “New Row” button under the **Specific Access in the Environment** table.

    ![MAS-MS-CCC-Access-8](images/MAS-MS-CCC-Access-8.png "MAS-MS-CCC-Access-8"){: caption=""}

10.	Select the search icon to bring up the list of accesses to choose from.

    ![MAS-MS-CCC-Access-9](images/MAS-MS-CCC-Access-9.png "MAS-MS-CCC-Access-9"){: caption=""}

11.	Select the access type “Client Communication Center” from the list.

    ![MAS-MS-CCC-Access-10](images/MAS-MS-CCC-Access-10.png "MAS-MS-CCC-Access-10"){: caption=""}

12.	Once selected, a warning message will popup indicating that you only need to request Client Communications Center access for one asset per organization and that you will be automatically subscribed to email notifications for that organization. You can unsubscribe at any time by following the unsubscribe option located in the notification emails. Click “OK” to continue.

    ![MAS-MS-CCC-Access-11](images/MAS-MS-CCC-Access-11.png "MAS-MS-CCC-Access-11"){: caption=""}

13.	Enter a reason for requesting Client Communications Center access in the **Justification** field.

    ![MAS-MS-CCC-Access-12](images/MAS-MS-CCC-Access-12.png "MAS-MS-CCC-Access-12"){: caption=""}

14.	Save the record to submit the access request. You will receive an email notification when your access request has been approved.

    ![MAS-MS-CCC-Access-13](images/MAS-MS-CCC-Access-13.png "MAS-MS-CCC-Access-13"){: caption=""}

### How to Request a Database Service Account
{: #how-to-request-database-service-account}

Follow the steps below to request a Database Service Account.

1.	Sign into the Self-Service Portal with your IBMid:

    https://devops.maximo.com

    If you are unable to login to the Self-Service Portal please see [Obtaining Access to the Access Management Tool](#obtaining-access-to-am-tool)

2.	Navigate to the Access Management Tool by selecting **Security** > **Access Management** from the applications menu.

    ![MAS-MS-CCC-Access-1](images/MAS-MS-CCC-Access-1.png "MAS-MS-CCC-Access-1"){: caption=""}

3.	Select your IBMid from the list of users.

    ![MAS-MS-CCC-Access-2](images/MAS-MS-CCC-Access-2.png "MAS-MS-CCC-Access-2"){: caption=""}

4.	Select the **Manage Access** tab.

    ![MAS-MS-CCC-Access-3](images/MAS-MS-CCC-Access-3.png "MAS-MS-CCC-Access-3"){: caption=""}

5.	Add an asset to the **Assets** table by selecting the “New Row” button.

    ![MAS-MS-CCC-Access-4](images/MAS-MS-CCC-Access-4.png "MAS-MS-CCC-Access-4"){: caption=""}

6.	Select the search icon to bring up a list of assets you have access to.

If the asset you want to submit an access request for is not viewable in the asset list, you do not have access to the asset’s organization. To obtain access, contact the access manager for the organization. If you do not know who the access manager is, you may submit a support case [here](https://www.ibm.com/mysupport){: external} to request this information.
{: note}

    ![MAS-MS-CCC-Access-5](images/MAS-MS-CCC-Access-5.png "MAS-MS-CCC-Access-5"){: caption=""}

7.	Select an asset from the list for the organization you want to request Client Communications Center access to. Obtaining Client Communications Center access to one asset will grant you communications access to all assets for that organization.

    ![MAS-MS-CCC-Access-6](images/MAS-MS-CCC-Access-6.png "MAS-MS-CCC-Access-6"){: caption=""}

8.	Click on the row in the **Assets** table of the asset you just added. This will link the asset to the access requested in the next step.

    ![MAS-MS-CCC-Access-7](images/MAS-MS-CCC-Access-7.png "MAS-MS-CCC-Access-7"){: caption=""}

9.	Begin the access request process by selecting the “New Row” button under the **Specific Access in the Environment** table.

    ![MAS-MS-CCC-Access-8](images/MAS-MS-CCC-Access-8.png "MAS-MS-CCC-Access-8"){: caption=""}

10.	Select the search icon to bring up the list of accesses to choose from.

    ![MAS-MS-CCC-Access-9](images/MAS-MS-CCC-Access-9.png "MAS-MS-CCC-Access-9"){: caption=""}

11.	Select the access type “Create Database Service Account” from the list.

    ![MAS-MS-CCC-Access-10](images/SSP-AMT-DB-SVC-ACT.png "MAS-MS-CCC-Access-10"){: caption=""}

12.	Enter a reason for requesting the Database Service Account in the **Justification** field and an account id in the **Database Account ID** field. Make sure to comply with the naming restrictions.

    ![MAS-MS-CCC-Access-12](images/SSP-AMT-DB-Svc-Detail.png "MAS-MS-CCC-Access-12"){: caption=""}

13.	Save the record to submit the access request. You will receive an email notification when your access request has been approved and the account has been created.

    ![MAS-MS-CCC-Access-13](images/MAS-MS-CCC-Access-13.png "MAS-MS-CCC-Access-13"){: caption=""}

14. Once the account has been created you can return to the access record to retrieve the database password and SSL Certificate information. Use the **Show Database Password** and **Show SSL Certificate** checkboxes to display/hide the information.

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-Details-Hidden.png "MAS-MS-CCC-Access-13"){: caption=""}

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-Details-Display.png "MAS-MS-CCC-Access-13"){: caption=""}

### How to Request a Database User Account
{: #how-to-request-database-user-account}

Follow the steps below to request access to the Client Communications Center Dashboard for your organization. For more information on the Client Communications Center, navigate to the [Client Communications Center](/docs/mas-ms?topic=mas-ms-client-communications-center) page.

1.	Sign into the Self-Service Portal with your IBMid:

    https://devops.maximo.com

    If you are unable to login to the Self-Service Portal please see [Obtaining Access to the Access Management Tool](#obtaining-access-to-am-tool)

2.	Navigate to the Access Management Tool by selecting **Security** > **Access Management** from the applications menu.

    ![MAS-MS-CCC-Access-1](images/MAS-MS-CCC-Access-1.png "MAS-MS-CCC-Access-1"){: caption=""}

3.	Select your IBMid from the list of users.

    ![MAS-MS-CCC-Access-2](images/MAS-MS-CCC-Access-2.png "MAS-MS-CCC-Access-2"){: caption=""}

4.	Select the **Manage Access** tab.

    ![MAS-MS-CCC-Access-3](images/MAS-MS-CCC-Access-3.png "MAS-MS-CCC-Access-3"){: caption=""}

5.	Add an asset to the **Assets** table by selecting the “New Row” button.

    ![MAS-MS-CCC-Access-4](images/MAS-MS-CCC-Access-4.png "MAS-MS-CCC-Access-4"){: caption=""}

6.	Select the search icon to bring up a list of assets you have access to.

If the asset you want to submit an access request for is not viewable in the asset list, you do not have access to the asset’s organization. To obtain access, contact the access manager for the organization. If you do not know who the access manager is, you may submit a support case [here](https://www.ibm.com/mysupport){: external} to request this information.
{: note}

    ![MAS-MS-CCC-Access-5](images/MAS-MS-CCC-Access-5.png "MAS-MS-CCC-Access-5"){: caption=""}

7.	Select an asset from the list for the organization you want to request Client Communications Center access to. Obtaining Client Communications Center access to one asset will grant you communications access to all assets for that organization.

    ![MAS-MS-CCC-Access-6](images/MAS-MS-CCC-Access-6.png "MAS-MS-CCC-Access-6"){: caption=""}

8.	Click on the row in the **Assets** table of the asset you just added. This will link the asset to the access requested in the next step.

    ![MAS-MS-CCC-Access-7](images/MAS-MS-CCC-Access-7.png "MAS-MS-CCC-Access-7"){: caption=""}

9.	Begin the access request process by selecting the “New Row” button under the **Specific Access in the Environment** table.

    ![MAS-MS-CCC-Access-8](images/MAS-MS-CCC-Access-8.png "MAS-MS-CCC-Access-8"){: caption=""}

10.	Select the search icon to bring up the list of accesses to choose from.

    ![MAS-MS-CCC-Access-9](images/MAS-MS-CCC-Access-9.png "MAS-MS-CCC-Access-9"){: caption=""}

11.	Select the access type “Database User Account” from the list.

    ![MAS-MS-CCC-Access-10](images/SSP-AMT-DB-User-Act.png "MAS-MS-CCC-Access-10"){: caption=""}

12.	Enter a reason for requesting the Database Service Account in the **Justification** field. The Database Account ID will be populated for you.

    ![MAS-MS-CCC-Access-12](images/SSP-AMT-DB-User-Detail.png "MAS-MS-CCC-Access-12"){: caption=""}

13.	Save the record to submit the access request. You will receive an email notification when your access request has been approved and the account has been created.

    ![MAS-MS-CCC-Access-13](images/MAS-MS-CCC-Access-13.png "MAS-MS-CCC-Access-13"){: caption=""}

14. Once the account has been created you can return to the access record to retrieve the database password and SSL Certificate information. Use the **Show Database Password** and **Show SSL Certificate** checkboxes to display/hide the information.

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-Details-Hidden.png "MAS-MS-CCC-Access-13"){: caption=""}

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-Details-Display.png "MAS-MS-CCC-Access-13"){: caption=""}


### How to Reset a Database Account Password
{: #how-to-reset-database-password}

Follow the steps below to request access to the Client Communications Center Dashboard for your organization. For more information on the Client Communications Center, navigate to the [Client Communications Center](/docs/mas-ms?topic=mas-ms-client-communications-center) page.

1.	Sign into the Self-Service Portal with your IBMid:

    https://devops.maximo.com

    If you are unable to login to the Self-Service Portal please see [Obtaining Access to the Access Management Tool](#obtaining-access-to-am-tool)

2.	Navigate to the Access Management Tool by selecting **Security** > **Access Management** from the applications menu.

    ![MAS-MS-CCC-Access-1](images/MAS-MS-CCC-Access-1.png "MAS-MS-CCC-Access-1"){: caption=""}

3.	Select your IBMid from the list of users.

    ![MAS-MS-CCC-Access-2](images/MAS-MS-CCC-Access-2.png "MAS-MS-CCC-Access-2"){: caption=""}

4.	Select the **Manage Access** tab.

    ![MAS-MS-CCC-Access-3](images/MAS-MS-CCC-Access-3.png "MAS-MS-CCC-Access-3"){: caption=""}

5.	Select the asset in the **Assets** table associated with the Database Account you wish to reset the password for.

    ![MAS-MS-CCC-Access-4](images/MAS-MS-CCC-Access-4.png "MAS-MS-CCC-Access-4"){: caption=""}

6. Select the twistie(>) to the left of the Databae Account you wish to reset the password for. This will show the access details and actions that can be run against the access.

    ![MAS-MS-CCC-Access-5](images/SSP-AMT-Select-DB-Act.png "MAS-MS-CCC-Access-5"){: caption=""}

7.	You can provide a new password in the **New Database Password** field, or leave it blank to have one generated.

    ![MAS-MS-CCC-Access-5](images/SSP-AMT-DB-New-Pwd.png "MAS-MS-CCC-Access-5"){: caption=""}

8.	Submit the request by pressing the **Reset Database Password** button. No Manager approval is required for this. You will receive an email notification when the password has been reset.

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-PW-Reset.png "MAS-MS-CCC-Access-13"){: caption=""}

9. Once the reset is complete you can return to the access record to retrieve the database password and SSL Certificate information. Use the **Show Database Password** and **Show SSL Certificate** checkboxes to display/hide the information.

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-Details-Hidden.png "MAS-MS-CCC-Access-13"){: caption=""}

    ![MAS-MS-CCC-Access-13](images/SSP-AMT-DB-Details-Display.png "MAS-MS-CCC-Access-13"){: caption=""}


### How to Request MAS Object Storage File Access
{: #how-to-request-cos-file-access}

Procedure will be documented when function is released.

### How to Request MAS Object Storage Log Access
{: #how-to-request-cos-log-access}

Procedure will be documented when function is released.

## How to Remove a User's Access
{: #remove-user-access-am-tool}

Users in the Access Management tool are able to remove accesses that they have. Manager users are able to remove accesses for all users under the customer they are managing.

Follow these steps to remove a user’s access.

1. Sign into the Self-Service Portal:

    https://devops.maximo.com

2. Navigate to the Access Management application.

    ![SSP-AM-Remove-User-1](images/SSP-AM-Remove-User-1.png "SSP-AM-Remove-User-1"){: caption=""}

3. Select your IBMid, or if a Manager the user’s IBMid, from the List View that you want to remove the access from.

    ![SSP-AM-Remove-User-2](images/SSP-AM-Remove-User-2.png "SSP-AM-Remove-User-2"){: caption=""}

    ![SSP-AM-Remove-User-2](images/SSP-AM-Remove-User-2.png "SSP-AM-Remove-User-2"){: caption=""}

4. Select the user’s Manage Access tab to view their existing accesses.

    ![SSP-AM-Remove-User-3](images/SSP-AM-Remove-User-3.png "SSP-AM-Remove-User-3"){: caption=""}

5. Select the asset from the Assets table that the access is linked to. This will populate all existing and pending accesses for the asset in the Specific Access in the Environment table below.

    ![SSP-AM-Remove-User-4](images/SSP-AM-Remove-User-4.png "SSP-AM-Remove-User-4"){: caption=""}

6. Select the “>” icon next to the access you want to remove. This will show the access details and actions that can be run against the access.

    ![SSP-AM-Remove-User-5](images/SSP-AM-Remove-User-5.png "SSP-AM-Remove-User-5"){: caption=""}

7. Select the “Remove Access” button to initiate the access removal process. The access status will be updated to “PENDING REMOVAL”.

    ![SSP-AM-Remove-User-6](images/SSP-AM-Remove-User-6.png "SSP-AM-Remove-User-6"){: caption=""}

    ![SSP-AM-Remove-User-7](images/SSP-AM-Remove-User-7.png "SSP-AM-Remove-User-7"){: caption=""}

    ![SSP-AM-Remove-User-7](images/SSP-AM-Remove-User-7.png "SSP-AM-Remove-User-7"){: caption=""}

8. The status of the access will be updated to “REMOVED” once the access removal process is completed.

    ![SSP-AM-Remove-User-8](images/SSP-AM-Remove-User-8.png "SSP-AM-Remove-User-8"){: caption=""}

## How to Grant a User Access to a Customer
{: #grant-user-access-customer-am-tool}

Managers in the Access Management application are able to grant existing users access to the customer they are managing. This process is similar to adding a new user to the Access Management tool. Once a user is granted access to a customer they can submit access requests for that customer. All access requests must be approved by a Manager User for that customer before they are granted.

Follow these steps to grant a user access to the customer you are assigned to manage.

1. Sign into the Self-Service Portal: https://devops.maximo.com

2. Navigate to the Access Management tool.

    ![SSP-AM-Grant-User-Customer-1](images/SSP-AM-Grant-User-Customer-1.png "SSP-AM-Grant-User-Customer-1"){: caption=""}

3. Click on the Plus (+) icon.

    ![SSP-AM-Grant-User-Customer-2](images/SSP-AM-Grant-User-Customer-2.png "SSP-AM-Grant-User-Customer-2"){: caption=""}

4. Enter the following information for the user you are granting customer access to. During this process a question mark (?) icon will pop up in the IBMid field.

If a question mark icon does not pop up in the IBMid field, the user does not exist yet. Follow the steps in the [How to Create a New User](#create-new-user-am-tool) document to create the new user. The process of creating a new user will also grant the user access to the customer you are managing.
{: note}

    | Value | Description |
    | -------------- | -------------- |
    | IBMid | The user's IBMid (email address) |
    | First Name | The user's First Name |
    | Last Name | The user's Last Name |
    {: caption=""}

     ![SSP-AM-Grant-User-Customer-3](images/SSP-AM-Grant-User-Customer-3.png "SSP-AM-Grant-User-Customer-3"){: caption=""}

5. Select the question mark (?) icon. A message will pop up asking if you want to grant the user access to the customer you are managing. Select “Yes”.

    ![SSP-AM-Grant-User-Customer-4](images/SSP-AM-Grant-User-Customer-4.png "SSP-AM-Grant-User-Customer-4"){: caption=""}

6.  Return to the List View without saving.

    ![SSP-AM-Grant-User-Customer-5](images/SSP-AM-Grant-User-Customer-5.png "SSP-AM-Grant-User-Customer-5"){: caption=""}

7. The user should now be viewable in your List View and have access to the customer you are managing.

If the user is not viewable in your List View refresh the page.
{: note}

    ![SSP-AM-Grant-User-Customer-6](images/SSP-AM-Grant-User-Customer-6.png "SSP-AM-Grant-User-Customer-6"){: caption=""}

    ![SSP-AM-Grant-User-Customer-7](images/SSP-AM-Grant-User-Customer-7.png "SSP-AM-Grant-User-Customer-7"){: caption=""}

## How to Remove a User's Access to a Customer
{: #remove-user-access-customer-am-tool}

Manager users in the Access Management tool are able to remove a user’s access to submit access requests for a customer. In addition, all existing accesses linked to the customer will be removed. If the user does not have access to submit access requests for other customers, their account will be deactivated.

Manager user’s can only remove the customer they are managing from a user’s Customer Access List.
{: note}

Follow these steps to remove the user’s accesses if your user role is Manager.

1. Sign into the Self-Service Portal: https://devops.maximo.com

2. Navigate to the Access Management application.

    ![SSP-AM-Remove-User-Customer-1](images/SSP-AM-Remove-User-Customer-1.png "SSP-AM-Remove-User-Customer-1"){: caption=""}

3. Select the user’s IBMid from the List View that you want to remove the accesses from.

    ![SSP-AM-Remove-User-Customer-2](images/SSP-AM-Remove-User-Customer-2.png "SSP-AM-Remove-User-Customer-2"){: caption=""}

4. In the Customer Access List table, select the delete icon next to the customer row you want to remove the user’s access to.

    ![SSP-AM-Remove-User-Customer-3](images/SSP-AM-Remove-User-Customer-3.png "SSP-AM-Remove-User-Customer-3"){: caption=""}

5. A warning message will pop-up indicating that removing the user’s access to the customer will also remove all accesses under the customer for the user. If you are removing the last customer in the user’s Customer Access List, their account will be deactivated. If you want to continue with the removal process, select “Yes”.

    ![SSP-AM-Remove-User-Customer-4](images/SSP-AM-Remove-User-Customer-4.png "SSP-AM-Remove-User-Customer-4"){: caption=""}

6. Save the record and return to the List View.

The user will not be viewable in the List View because they no longer have access to the customer you are managing.
{: note}

    ![SSP-AM-Remove-User-Customer-5](images/SSP-AM-Remove-User-Customer-5.png "SSP-AM-Remove-User-Customer-5"){: caption=""}

## How to Create a New User
{: #create-new-user-am-tool}

Managers in the Access Management application are able to create new users. These users can be another Manager or Standard User. When the new user is created they are granted access to submit access requests for the customer the Manager user is managing.

Only users that will be responsible for approving/rejecting access requests should be assigned the Manager role.
{: note}

Follow these steps to create a new user if your user role is Manager.

1. Sign into the Self-Service Portal: https://devops.maximo.com

2. Navigate to the Access Management application.

    ![SSP-AM-Create-User-1](images/SSP-AM-Create-User-1.png "SSP-AM-Create-User-1"){: caption=""}

3. Click on the "New Access" icon (Plus sign) to create a new user.

    ![SSP-AM-Create-User-2](images/SSP-AM-Create-User-2.png "SSP-AM-Create-User-2"){: caption=""}

4. Enter the requested information for the new user in the following order:

    | Value | Description |
    | -------------- | -------------- |
    | IBMid | The user's IBMid (email address). The new user's IBMid. This will be the new user's username when they login to the Self-Service Portal.  \n If the user does not have an IBMid, they can create one [here](https://myibm.ibm.com){: external}) |
    | First Name | The user's First Name |
    | Last Name | The user's Last Name |
    | Primary Email | The email for contacting the new user. This is where the new user will receive initial login instructions for the Self-Service Portal. |
    | Role | The role for the new user:  \n STD_USER = Standard User  \n MANAGER = Manager |
    | Managing Customer | ** This will be set to the customer you are assigned to manage if the user role is set to "MANAGER". |
    | Customer Access List | ** A row will be added to this list with the customer you are assigned to manage once the user is activated. |
    {: caption=""}

    ![SSP-AM-Create-User-3](images/SSP-AM-Create-User-3.png "SSP-AM-Create-User-3"){: caption=""}

5. Save the record.

    ![SSP-AM-Create-User-4](images/SSP-AM-Create-User-4.png "SSP-AM-Create-User-4"){: caption=""}

6. The new user will be created once the backend processing is completed. You will know the new user was successfully created when the user status changes to "ACTIVE". The new user will receive an email with instructions on how to login to the Self-Service Portal once their user is activated.

## How to Approve / Reject an Access Request
{: #approve-reject-access-am-tool}

Managers in the Access Management application are responsible for approving/rejecting access requests submitted by users assigned to their customer/vendor. Managers will receive an email when a user with their customer/vendor assignment submits an access request.

Follow these steps to review an access request if your user role is Manager.

1. Sign into the Self-Service Portal: https://devops.maximo.com

2. Navigate to the Access Management application by selecting the drop down menu in the top left of the window and selecting **Security** → **Access Management**. The initial screen will show a list of users that you have access to manage and process access requests for.

    ![SSP-AM-Approve-Reject-Access-1](images/SSP-AM-Approve-Reject-Access-1.png "SSP-AM-Approve-Reject-Access-1"){: caption=""}

3. Select your IBMid from the list and proceed to the "Access Approvals" tab. There you will see a table with all the access requests that you can process.

    ![SSP-AM-Approve-Reject-Access-2](images/SSP-AM-Approve-Reject-Access-2.png "SSP-AM-Approve-Reject-Access-2"){: caption=""}

4. Open the details on the request you want to process by choosing the twistie (>) to the left of the user.

    ![SSP-AM-Approve-Reject-Access-3](images/SSP-AM-Approve-Reject-Access-3.png "SSP-AM-Approve-Reject-Access-3"){: caption=""}

5. Select the Disposition for the request (APPROVED, REJECTED). If the Disposition is REJECTED comments are required for reason why request was denied.

6. Once you have processed all the requests you intend to, select the "Save" icon near the upper left part of the console to start the back end processing of the requests. The requestors will be notified by email if their request has been rejected or when the processing is complete and they have been granted the requested access.

    ![SSP-AM-Approve-Reject-Access-4](images/SSP-AM-Approve-Reject-Access-4.png "SSP-AM-Approve-Reject-Access-4"){: caption=""}

## Access Re-Validation
{: #access-revalidation-am-tool}

Continued business need (CBN) for accesses provided through the IoT SaaS Self-Service portal access management tool must be validated annually.

The re-validation process is run on an annual basis for all users, so it is possible that you will be notified of the need to re-validate less than a year after access is granted. You will receive an email when validation is required. Until that time the “Re-validate CBN” button will not be available on the “Manage Access” tab as indicated below.
{: note}

When notified of the need to re-validate, follow these steps to review your current accesses and re-validate your need to keep them.

1. Sign into the Self-Service Portal: https://devops.maximo.com

2. Navigate to the Access Management application by selecting the drop down menu in the top left of the window and selecting Security → Access Management.

    ![SSP-AM-Access-Revalidation-1](images/SSP-AM-Access-Revalidation-1.png "SSP-AM-Access-Revalidation-1"){: caption=""}

3. Select your IBMid from the list and proceed to the "Manage Access" tab. There you will see tables with all the assets and associated accesses. Remove any accesses you no longer have a business need for and press the “Save” button.

    ![SSP-AM-Access-Revalidation-2](images/SSP-AM-Access-Revalidation-2.png "SSP-AM-Access-Revalidation-2"){: caption=""}

4. Press the “Re-validate CBN” button to validate your continued need for the remaining accesses.

    ![SSP-AM-Access-Revalidation-3](images/SSP-AM-Access-Revalidation-3.png "SSP-AM-Access-Revalidation-3"){: caption=""}

5. The "Re-validate CBN" button should be removed from the panel (indicating successful validation).
