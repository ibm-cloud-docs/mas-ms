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

# Self-Service Portal
{: #ssp}

**Note: This section is under construction**

## Access Management Tool
{: #access-management-tool}

The Access Management Tool is a self-service tool, located in the IBM IoT Saas Self-Service Portal, where users can manage access to their MAS-MS environments.

IBM IoT Saas Self-Service Portal URL: 

https://devops.maximo.com

## Access Management Tool Overview
{: #access-management-overview}

User Roles

The Access Management Tool supports two user roles - standard users and manager users. Manager users have elevated accesses to manage the tool for their customer.

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

List View

The List View page is the homepage of the Access Management Tool. This is where you can view the user accounts you have access to. Manager users can view user accounts that have access to the customer they are managing from this page. Standard users can view their user account from this page.

Person Information

The Person Information tab contains user account details. These details include the user’s IBMid, name, email address, role, and customer(s) they have access to. This tab will also contain the customer a user is managing if they are a manager user.

Manage Access

The Manage Access tab contains the user account’s existing and pending accesses. Access records are filtered by selecting the asset in the Assets table. Once selected, accesses for the selected asset can be seen in the Specific Access in the Environment table below. In addition to viewing accesses, users can submit access requests for their user account from this tab. Go to the How to Submit an Access Request wiki to read more about requesting accesses.

Access Approvals

The Access Approvals tab is where manager users review access requests submitted for the customer they are managing. This tab is only accessible through the manager user’s account. Go to the How to Approve/Reject an Access Request wiki to read more about reviewing access requests.

## Obtaining Access to the Access Management Tool
{: #obtaining-access-to-am-tool}

Follow the steps below to obtain access to the Access Management Tool.

1. Create an IBMid

An IBMid is required to login to the Access Management Tool. To create an IBMid click [here](https://myibm.ibm.com){: external}

2. Request Access

A user managing the customer you want access to must add you to the tool. Contact one of the manager users to request they add you to the Access Management Tool. If you do not know who the manager users are for a specific customer, submit a [support case](https://www.ibm.mysupport){: external} requesting this information.

3. Navigate to the Access Management Tool

Navigate to the Access Management Tool by logging into the IBM IoT Saas Self-Service Portal with your IBMid. Once logged in, select Security > Access Management from the navigation menu.

## How to Remove a User's Access
{: #remove-user-access-am-tool}

Manager users in the Access Management tool are able to remove a user’s access under the customer they are managing. 

Follow these steps to remove a user’s access if your user role is Manager.

1. Sign into the Self Service Portal: https://devops.maximo.com

2. Navigate to the Access Management application.
![SSP-AM-Remove-User-1](images/SSP-AM-Remove-User-1.png "SSP-AM-Remove-User-1"){: caption="Figure 1. Access Management Application" caption-side="bottom"}

3. Select the user’s IBM ID from the List View that you want to remove the access from.
![SSP-AM-Remove-User-2](images/SSP-AM-Remove-User-2.png "SSP-AM-Remove-User-2"){: caption="Figure 2. Select User ID" caption-side="bottom"}

4. Select the user’s Manage Access tab to view their existing accesses.
![SSP-AM-Remove-User-3](images/SSP-AM-Remove-User-3.png "SSP-AM-Remove-User-3"){: caption="Figure 3. Manage Access Tab" caption-side="bottom"}

5. Select the asset from the Assets table that the access is linked to. This will populate all existing and pending accesses for the asset in the Specific Access in the Environment table below.
![SSP-AM-Remove-User-4](images/SSP-AM-Remove-User-4.png "SSP-AM-Remove-User-4"){: caption="Figure 4. Select Asset" caption-side="bottom"}

6. Select the “>” icon next to the access you want to remove. This will show the access details and actions that can be run against the access.
![SSP-AM-Remove-User-5](images/SSP-AM-Remove-User-5.png "SSP-AM-Remove-User-5"){: caption="Figure 5. Select Arrow Icon" caption-side="bottom"}

7. Select the “Remove Access” button to initiate the access removal process. The access status will be updated to “PENDING REMOVAL”.
![SSP-AM-Remove-User-6](images/SSP-AM-Remove-User-6.png "SSP-AM-Remove-User-6"){: caption="Figure 6. Remove Access" caption-side="bottom"}
![SSP-AM-Remove-User-7](images/SSP-AM-Remove-User-7.png "SSP-AM-Remove-User-7"){: caption="Figure 7. Pending Removal" caption-side="bottom"}

8. The status of the access will be updated to “REMOVED” once the access removal process is completed.
![SSP-AM-Remove-User-8](images/SSP-AM-Remove-User-8.png "SSP-AM-Remove-User-8"){: caption="Figure 8. Status Removed" caption-side="bottom"}