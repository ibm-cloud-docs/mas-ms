---

copyright:
  years: 2015, 2020
lastupdated: "2023-02-02"

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

# Migration from Maximo SaaS Flex or On-Premise
{: #migration-from-maximo-saas-flex-or-on-premise}

## Migration of Maximo to Dedicated (MAS-Dedicated)
{: #migration-of-maximo-to-mas-dedicated}

This page covers migration of an existing Maximo application, either on the IBM Maximo EAM SaaS Flex offering or a client-managed installation to Maximo Application Suite Dedicated (MAS-Dedicated). This document focuses on the MAS Manage (Maximo EAM) application.  There are two paths that can be followed:

1. Migration of client from the IBM Maximo EAM SaaS Flex offering
2. Migration of client from an on-premise or 3rd party Cloud provider

The steps are similar for both, but the responsibilities vary as to which team is responsible for some of the tasks. This diagram represents a high-level overview of the migration path to MAS MS:

![MAS-Migration-Steps](/images/MAS-Migration-Steps.png){: caption="Figure 1. MAS Migration Steps"}

## Planning
{: #planning}

The planning stage is driven by the customer and covers the internal processes and approvals needed for the migration project.  This step requires collaboration with IBM to understand the complexity of the migration, timeframes, level of effort, and personnel needed to perform the migration.  In this step the customer determines if they have the necessary expertise and capacity internally to perform the migration or engage IBM GBS, IBM Expert Services or a Business Partner to perform this work.

## Pre-Conditions
{: #pre-conditions}

There are several preconditions that need to be met in order to migrate to the new MAS-Dedicated offering:

- [ ] A new Maximo Application Suite Dedicated (MAS-Dedicated) contract is in place.
- [ ] The source version of Maximo must be v7.6.1.2 or greater. For SaaS Flex (IBM hosted) clients, the technical upgrade is performed by the IBM SRE Team as
   - part of the SaaS Flex offering per normal upgrade procedures. For on-premise clients, the technical upgrade is the responsibility of the client or business
   - partner.
- [ ] The source database export is DB2 (the supported DB2 version depends on the timing of the migration).
- [ ] The MAS database timezone for each instance will be set to UTC when provisioned. This cannot be changed.
- [ ] Customer has run Maximo v7.6 Integrity Checker on source database and resolved all errors prior to sending to IBM.
- [ ] All items to be migrated are identified. For SaaS Flex (IBM hosted) clients this is a shared responsibility; for on-premise the customer is responsible.
- [ ] All custom java classes arre remediated and removed. Java classes can be replaced with automation scripts. See link for further information:

    https://ibm-maximo-dev.github.io/maximo-autoscript-documentation/introduction/whatisautoscript/

- [ ] Database conversion tools won't address stored queries, relationships or reports. Ensure these are converted and tested on v7.6 before migrating to MAS.
- [ ] TEXT Search is not supported in MAS. All fields should be converted from TEXT search to another value (WILDCARD, EXACT, or NONE).
- [ ] Each user account can have only (1) primary email address.
- [ ] Each user account can have only (1) primary phone number.
- [ ] The user account added for the mxe.int.dfltuser property must have complete user application and related object access inside Manage for user
   - syncronization to work after migration.
- [ ] Maximo Object Structure Tables and Data Dictionary Tables must be aligned before sending the database to IBM. See link below for further information:

    https://www.ibm.com/support/pages/bmxaa7733e-error-loading-object-structure-or-generating-schema

- [ ] Insure maxtable and maxintobjdetail are updated properly before sending the database to IBM. See link below for further information:

    https://www.ibm.com/support/pages/error-initializing-micservicebmxaa7733e-after-applying-fix-pack-7505

- [ ] MaxSequence should be aligned before sending database to IBM. See link below for further information:

    https://www.ibm.com/support/pages/integrity-checker-sequence-not-setup-correctly

## Initial Set Up
{: #initial-set-up}

The initial set up includes several components including:

* Creation of the target MAS Dedicated environment
* Identification of all components that need to be migrated (database, code, attachments)
* Final documentation of the integration's and any initial set-up that can be done (including VPN's)

The goal of this step is to ensure all components are in place so the first test can begin.

| Task | IBM | Client (or Designate) |
| -------------- | -------------- | -------------- |
| Deploy MAS in selected data center | X | |
| Install Applications | X | |
| Perform initial configuration | X | |
| Identify SaaS Flex site for data to use in initial test | | X |
| Identify all components that need to be migrated (attachments, custom reports) | | X |
| Begin VPN Set up (optional) | X | X |
| Remediation of JAVA class files to Automation Script(s) | | X |
| Configure any integrations in MAS | | X |
{: caption="Table 1. Initial Setup Responsibilities" caption-side="bottom"}

## Test 1
{: #test-1}

Test 1 executes all of the steps required to move a customer from the SaaS Flex (or on-premise) implementation to the MAS Dedicated offering.  Data is exported from the source system, transferred to the Dedicated Service location and loaded into the new database instance.  Configuration is completed for integration's and any technical remediation performed for the technology differences.  Next the client tests to ensure all business flows are performing as expected.  Issues identified are then resolved until the testing is complete.

## Test 2
{: #test-2}

This is similar to test 1, except the focus is ensuring all steps are documented and accurate timings taken for the final migration of production.  This is a dress rehearsal for the go live as well as to ensure all issues identified in the first test have been resolved.  This test should take place close to the final cut-over date (within a few weeks).

## Live on MAS-Dedicated
{: #live-on-mas-dedicated}

The final execution of the steps in the scheduled migration window.  Once complete, the customer is now live on the Dedicated Service offering.

## Post Live MAS-Dedicated Activities
{: #post-live-mas-dedicated-activities}

This is the support for customers after the go live.  Any new issue is investigated and resolved and then the client moves to steady state.

## Roles and Responsibilities
{: #roles-and-responsibilities}

Both IBM and the client have critical roles in the successful transition to the Maximo Application Suite Dedicated offering. These responsibilities are summarized in the attached spreadsheet below (MAS-Dedicated Migration Swimlanes).  At a high level, IBM is responsible for the technical components of the migration and the client would be responsible for ensuring business processes are working, custom and unique features of their implementation are identified, and updates to integration's and accounted for in the plan.

If the source database is being converted from another platform (for example Oracle or SQLServer) it is the customers responsibility to perform validation of the converted DB2 database and correct any issues identified before providing to the SRE team for import into the target MAS-Dedicated environment.

IBM and the customer share the responsibility to ensure the appropriate personnel are available to meet the agreed project plan.

## Additional Notes
{: #migration-additional-notes}

## Database Backup Image/Export
{: #migration-backup-image}

The IBM SRE team would prefer a database backup image provided the image is from the same database version as you are running in MAS-Dedicated.  We can accept/use an export done using (db2move/db2look). We would like you to send the export as well as backup image if possible.  The database backup image and export files should be uploaded to the following IBM Cloud COS bucket. The bucket detail and its connection detail will be send via welcome letter.

Bucket name: masms-XX-X-XXX-XXXXX-"InstanceName"-XX-XXX-cust-files

## Doclink and Attachment Files
{: #migration-doclink-attachment-files}

Doclink and Attachment Files should be uploaded to the following IBM Cloud COS bucket. Please upload your doclinks directory with all required subfolders The structure of these files and directories will be maintained when copied to the Manage server location.

Bucket name: masms-XX-X-XXX-XXXXX-"InstanceName"-XX-XXX-cust-files

Note:

The DOCINFO path within the Manage database will need to be updated to /doclinks/"folderStructure"/...  It is the customer's responsibility to change all the references. The IBM SRE team prefers customers to carry out this database change and then take the database export so that the database IBM will restore will have this change already.

## Overview Documents
{: #migration-overview-documents}

High-level overviews of the different migration considerations can be found in the attached documents.

Spreadsheet with MAS-Dedicated Migration Swimlanes (Roles and Responsibilities):

[MAS-Dedicated Spreadsheet with Roles and Responsibilities](https://www.ibm.com/support/pages/system/files/inline-files/Swimlanes-v3_0.xlsx){: external download="MAS-Dedicated-Migration-Swimlanes-v3_0.xlsx"}

Presentation of MS-Dedicated Migration Steps:

[MAS-Dedicated Presentation of Migration Steps](https://ibm.box.com/shared/static/e2e9i3dir373gdzm8kwdvpzqgfi83uvp.pptx){: external download="MAS-Dedicated Presentation of Migration Steps February 2023"}

MS-Dedicated Migration Questionaire:

[MAS-Dedicated Migration Questionaire](https://ibm.box.com/shared/static/plkrslw49s5ugr6qnf04g0p1atnujtpr.xls){: external download="IBM-Dedicated-Dedicated-Migration-Questionaire.xls"}
