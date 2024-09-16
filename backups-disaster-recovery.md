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

# Backups and Disaster Recovery
{: #backups-and-disaster-recovery}

## Application Backups
{: #application-backups}

Data used by applications within the Maximo Application Suite portfolio are backed up according to the following:

All backups are encrypted. Communication between applications, backup scripts the storage layer and DB services are perfromed via secure transport and accessed only via private endpoints that are offered by the service. Production backups are performed once a day. Backups are stored in a separate IBM Cloud data center location.

## System Configuration Backups
{: #system-configuration-backups}

Maximo Application Suite utilizes different components to deliver the applications to clients.  Each of these services are backed up using the appropriate backup tool for that component.  In general, all component backups:

* are encrypted
* are taken daily
* are stored in a separate data center
* are saved for 30 days

## Database Backup Retention
{: #database-backup-retention}

Database backups will be retained for the standard duration of 14 days for Production environments and 7 days for Non-Production environments. In scenarios where the customer would like to retain a backup for longer than the standard duration outlined, the IBM SRE team will perform a database backup and save it to the COS bucket. It will then be the responsibility of the customer to download and maintain these backups. If a restore using one of these downloaded backups is required, the customer will need to upload the backup back to the COS bucket and open a case specifying which backup to use and for which environment they would like the restore.

## Restore
{: #restore}

Restore requests must be submitted via case (ticket) through the IBM Support Community Portal.  The expected turn around time will depend on the severity and the size of the restore required.  Generally for non-production systems, expect 1 - 3 days for a restore to happen. Database restore can only be done to one of the previous daily backups (cannot restore to point in time).

## Disaster Recovery
{: #disaster-recovery}

In the event of a DR issue with the Maximo Application Suite Dedicated Service offering for a specific customer, IBM's focus will be in the following order:

1. Recover the existing infrastructure in place
2. Recover within the same IBM Cloud data center to a new infrastructure
3. Recover to a secondary IBM Cloud data center

In the event a disaster is declared, the base parameters are:

Recovery Time Objective (RTO)  - 72 hours
Recovery Point Objective (RPO) - 24 hours

RTO is the longest possible time needed to make the application available.
RPO is the longest possible time since data was last backed up.

These are Service Level Objectives (SLO's) and not Service Level Agreements.

## Business Continuity
{: #business-continuity}

For information on IBM business continuity, please refer to IBM's Business Continuity Management Position Paper. It is IBM Confidential and can be shared under a non-disclosure agreement.  Please note only IBM personnel can access the link below.  If required, please contact your IBM Sales person or Customer Success Manager.

https://w3.ibm.com/w3publisher/global-bcm/education/copy-of-faq
