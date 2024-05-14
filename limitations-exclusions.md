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

# Limitations & Exclusions
{: #limitations-exclusions}

Maximo Application Suite Dedicated is implemented using a defined set of technologies and operates within a security profile designed to ensure our client's data is secure and the applications operate efficiently and effectively.  As a result of the decisions made regarding technologies and to meet the high security standards, there are differences between what is available using the Dedicated Services and what a client could do if they hosted and operated the Suite themselves.

The following items are not included or allowed in the Maximo Application Suite Dedicated offering:

## Access
{: #access}

Clients will not have access to the operating system, file system, Red Hat OpenShift or overall system administration of the Suite.  DBAdmin access or direct updating of the database is not allowed.

## MAS Administrator Functions
{: #mas-administrator-functions}

Direct access to the clusters is not available.  Changes required must be submitted using an IBM support case system and the IBM SRE team will execute.

## Databases
{: #databases}

The following are database limitations of the MAS-Dedicated offering:

* Only DB2 is supported.  Oracle and SQLServer are not supported.  Conversion services are available.

* If converting from Oracle to DB2, Oracle compatibility mode is not supported.

* DB2 Text Search is not supported.

* Running SQL statements (update/insert/delete) directly on databases is not allowed and IBM SRE team will not be able to execute those statements for you. DBC scripts are not allowed. Customers must carry out these changes using the UI via different means for example using Automation scripts or MIF. For further details on use of automation scripts, please see document below:

https://ibm-maximo-dev.github.io/maximo-autoscript-documentation/introduction/whatisautoscript

* SQL Scripts can be run on Production databases on an exception-only basis. Please see [Running SQL Scripts in Production](/docs/mas-ms?topic=mas-ms-support#running-sql-scripts) for details.

## Manage Application
{: #manage-application}

No Java extensions are supported.  It is assumed the Manage auomation scripting capability will be used for these types of extensions.  Existing Maximo customers who have Java extensions will need to move these functions into automation scripts within the application. See link above for further details

## LA Fixes
{: #la-fixes}

LA (Limited Availability) aka "one off" or "hot" fixes are the customer's responsibility to manage. Please see [Maintenance](/docs/mas-ms?topic=mas-ms-maintenance#lafixes) section for details.

## 3rd Party Applications
{: #3rd-party-applications}

MAS-Dedicated and MAS-MS offer limited support of customer owned third party applications in the IBM cloud environment.

* Third party applications must be considered "Add-On" or complimentary components necessary to the operation of Maximo
* Customer must provide all required media and licensing for third party products
* Stand alone third party applications (those with no connectivity or interaction with Maximo) are not supported
* It should be assumed that IBM SRE has no awareness or expertise in using or managing customer owned third party applications
* Third party applications must be small footprint (enterprise level applications are not supported within Maximo Cloud environments)
* All proposed third party applications must be reviewed and approved by the IBM SRE management team prior to contract approval
* A Third Party Application Vendor Questionnaire must be completed for review by the IBM SRE team. See Attachments tab below.

## AppConnect
{: #mas-app-connect}

AppConnect is included as an entitlement with the Maximo Application Suite, but the Dedicated Service does not implement or support this within the MAS-Dedicated environment.  The client is responsible for implementing AppConnect or beginning with version MAS v8.7, AppConnect SaaS will be supported.
