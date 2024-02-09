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

# Maintenance
{: #maintenance}

## Infrastructure Deployment Options
{: #deployment-options}

The IBM MAS Cloud Service supports two infrastructure deployment options: _Dedicated Cluster_ and _Shared Cluster_. Both require Capacity Unit, Virtual Processor Core and Gigabyte entitlements. The difference between the two options is how the Cloud Service is provisioned, deployed and maintained. In both scenarios the client is provided separate MAS Applications and database instances for each environment (for example PROD, TEST, DEV) on IBM Cloud - but the underlying infrastructure will differ according to the deployment type ordered.

**Dedicated Cluster Deployment** (MAS-Dedicated)

In a Dedicated Cluster Deployment, clients maintain their own individual MAS Applications and database instances. Each MAS Client environment (PROD, TEST, DEV) resides on it's own dedicated Red Hat OpenShift Cluster. Red Hat OpenShift clusters are not shared. IBM determines, schedules and communicates when upgrades will occur. Customer initiated deferrals are permitted.

**Shared Cluster Deployment** (MAS-MS aka "Managed Service")

In a Shared Cluster Deployment, clients maintain their own individual MAS Applications and database instances, but these reside on one or more _shared_ Red Hat OpenShift Clusters (along with other customers). Clients choosing the Shared Cluster deployment must follow the software upgrade schedule (determined by IBM SRE). In this scenario, IBM schedules and communicates when upgrades will occur. Customer intiated deferrals are **not** permitted.

Clients who purchased MAS-MS (Managed Service) or were quoted prior to December 2022 are _Shared Cluster_ deployment.  Clients who were quoted and purchased off that quote after January 2023 are _Dedicated Cluster_ deployment.  If you are not sure which deployment option you have please contact your IBM sales person, CSM or open a support ticket.
{: note}

## Maintenance Windows
{: #maintenance-windows}

Maintenance windows for production environments are scheduled over the weekend (Saturday 00:00 UTC -> Sunday 24:00 UTC).
Non-Production environment maintenance is scheduled on weekdays (Monday 00:00 UTC -> Friday 24:00 UTC).
There may be exceptions, in which case Customers will be notified in advance.

The IBM SRE team proactively notifies customers at least 5 business days prior to any Non-Production maintenance and 10 business days prior to any Production maintenance via email using the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center).

It is important all customers subscribe in order to receive CCC maintenance notifications.
{: note}

Environments are usually not available to users during maintenance windows, but the following maintenance categories may be applied:

- **Outage** - systems will not be available to users for the duration of the scheduled window
- **Low Impact** - users may experience a brief period of intermittent connectivity (up to 15 mins) during the scheduled window
- **Medium Impact** - users may experience a period of intermittent connectivity (30 mins to 1 hour) during the scheduled window
- **No Outage** - maintenance will be performed, but it will not impact users

## Change Freeze Period
{: #change-freeze-period}

The Change Freeze period for year end 2024 is December 18th, 2024 through January 3rd, 2025. Systems are available to users and all standard automated processes such as database backups continue as normal during the change freeze period.  Coordinated changes to environments such as application upgrades are not available during this time.  The IBM SRE team does not schedule maintenance during the change freeze period.

## Upgrade Rules, Policy and Plans
{: #upgrade-rules}

Starting March 1st, 2024 all MAS-Dedicated and MAS-MS customers will be assigned an upgrade date and time and recieve MAS 8.11 upgrade notifications. Customers can also request the upgrade via case ticket [case ticket](https://support.ibm.com). If you wish to upgrade to v8.11, submit a case ticket requesting the upgrade, along with the target environment URL(s). IBM SRE will then put you in a queue to receive the upgrade.

It should be noted that IBM SRE initially determines the date, start time and duration for the upgrade your environment(s), based on our available resources and the overall schedule. IBM SRE will then send you an upgrade notification with those details via the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center).

Shared Cluster (MAS-MS) customers are not allowed to defer or re-schedule upgrades. Dedicated Cluster custonmers (MAS-Dedicated) can submit deferral date(s) for consideration.
{: #note}

Please also note the IBM SRE Change / Freeze period of December 18th, 2024 to January 3rd, 2025. MAS Upgrades will not be scheduled or performed during this timeframe.
{: note}

## LA Fixes
{: #lafixes}

During the Manage upgrade process all LA (Limited Availability) aka "one off" or "hot" Fixes applied to a customer's environment will be removed. It is assumed the upgrade or fixpack contains the LA Fix. It is the customer's responsibility to retest and revalidate all functionality after an upgrade.  If an issue is found, the customer should [open an IBM support case](https://www.ibm.com/mysupport){: external} with the product support team to troubleshoot.  If a new LA Fix is required, this would need to be requested through the support case.  LA Fix approvals by the SRE team will be determined on a case-by-case basis.

## Patch Releases
{: #patch-releases}

The following guidelines apply to Maximo Application Suite patch releases:
* Minor patches are available 1 week (5 business days) after General Availability (GA)
* Minor patch releases are designated at the last digits in the version. For example Maximo 8.10.0.X, where 'X' is the patch release
* Patch releases for MAS or any Apps have to be requested via an [IBM support case](https://www.ibm.com/mysupport){: external}
* 1 week of advance notice is needed in ticket for Patch release update
* If Patch contains security fixes or any security fix available, IBM SRE team will apply fixes as soon as they are available. No exceptions.

## Shared Cluster Deployment Customers
{: #shared-cluster-upgrades}

Shared Cluster Upgrade Policy

The following guidelines apply to MAS-MS (Shared Cluster) release schedule:
* Starting with v8.10, all MAS releases are Long Term Support (LTS) Releases
* MAS-MS comes out on the first Tuesday 30 days after MAS (GA) release.
* For example, MAS 8.10 (GA) will be released by IBM on 3/28/2023 and MAS-MS 8.10 on 5/2/2023
* The release of MAS-MS can be delayed beyond 30 days due to holidays and freeze periods. For example MAS 8.9 was released on 11/22/2022 and MAS-Dedicated will be 1/17/2023

| MAS Version | MAS (GA) Release Date | MAS-MS Release Date |
| -------------- | -------------- | -------------- |
| 8.11 | 9/26/23 | 10/31/23 <sup>1,2</sup>|
{: caption="Table 1. MAS-MS Release Planning" caption-side="bottom"}

<sup>1</sup> After 10/31/23 – v8.11 available, will be pushed out direclyto customerect
must open ticket to request upgrade<br>
<sup>2</sup> Please note change / freeze period in effect 12/16/23 – 1/2/24

Planning Guidelines - Shared Cluster

The following guidelines apply to planning upgrades for MAS-MS (Shared) cluster deployments:
* Upgrade schedules are set by IBM & communicated via [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center)
* Upgrade schedules are non-negotiable for MAS-MS (Shared Cluster) deployments.
* All client stakeholders must register to receive CCC notifications & communications
* IBM will share long-range anticipated upgrade windows upon request via ticket
* Timing is subject to change at IBM’s sole discretion based on software availability & other factors

Non-Production Upgrades

* Clients will be notified via CCC at least 5 business days prior to non-production environment upgrades
* All non-production environments will be upgraded concurrently, without exception.
* Non-Production environments are upgraded during weekdays.

Production Upgrades

* Production environments will be upgraded no earlier than 4 weeks after the non-production upgrade
* Some requests (e.g. data back-flow) are unavailable between Non-Production & Production upgrades
* Clients will be notified via CCC at least 10 business days prior to the Production environment upgrade
* The Production environment will be upgraded on schedule; deferal requests permitted
* Production environments are upgraded on weekends

Notes:

Upgrades of both prod or non-prod cannot requested to be done earlier or deferred to later for any reason, such as:
* We have training scheduled on planned maintenance window
* We are in critical stage of implementation phase and env cannot be touched
* We have a golive coming up and system cannot be touched
* We have an executive demo
* Non-prod upgrade broke a business functionality that is critical to the business, so Prod cannot be updated until the bug is fixed
* We need upgrade soon, because the new release has feature we need asap

## Dedicated Cluster Deployment Customers
{: #dedicated-cluster-upgrades}

Dedicated Cluster Upgrade Policy

The following guidelines apply to MAS-Dedicated (Dedicated Cluster) release schedule:
* Starting with v8.10, all MAS releases are Long Term Support (LTS) Releases
* MAS-Dedicated comes out on the first Tuesday 30 days after MAS (GA) release.
* For example, MAS 8.10 (GA) will be released by IBM on 3/28/2023 and MAS-Dedicated 8.10 on 5/2/2023
* The release of MAS-Dedicated can be delayed beyond 30 days due to holidays and freeze periods. For example MAS 8.9 was released on 11/22/2022 and MAS Dedicated will be 1/17/2023

| MAS Version | MAS (GA) Release Date | MAS-Dedicated Release Date |
| -------------- | -------------- | -------------- |
| 8.10 | 3/28/23 | 5/2/23 |
| 8.11 | 9/26/23 | 10/31/23 <sup>1,2</sup>|
{: caption="Table 1. MAS-Dedicated Release Planning" caption-side="bottom"}

<sup>1</sup> After 10/31/23 – v8.11 available, customer must open ticket to request upgrade<br>
<sup>2</sup> Please note change / freeze period in effect 12/16/23 – 1/2/24

Planning Guidelines

The following guidelines apply to planning for MAS upgrades:
* Clients must remain on a supported version.  This means either be on n or n-1 or a Long Term Support version.  For example once 8.13 is released, 8.11 is no longer in support so a customer will need to be on 8.12 before 8.13 is released.
* Long Term Support (LTS) releases are designated by development.  8.10 has been designated as a Long Term Support release.  LTS releases are supported for up to three years.  No new functionality will be delivered on this release, but fixes and security patches will be available and delivered to clients on LTS releases.
* Supporting Software such as Openshift and DB2 are on separate release schedules.  These will be updated according the support policies of those teams.  LTS releases will be updated to support newer versions of the supporting software.  This means even if on a LTS release over the three years, there will still be a need to upgrade some elements.

Within these parameters:
* Clients can request specific dates for upgrading their environments.  Clients on an LTS release can remain on that release for the time it is supported.
* Non production environments will be done during the week
* Production environments are typically done over the weekend
* Clients can determine the length of time between upgrading non production and production assuming the production upgrade happens prior to the existing version being out of support.
* Clients must request via a ticket the dates.
* Clients on non Long Term Support versions will be notified via Client Communication Center (CCC) with proposed dates to ensure clients remain in support. Clients can defer, but only within the window to stay on a supported version.
* All client stakeholders must register to receive CCC notifications & communications
* IBM will share long-range anticipated upgrade windows upon request via ticket

Non-Production Upgrades
* Client must request upgrades via [IBM support case](https://www.ibm.com/mysupport){: external} including the target environment and suggested dates when upgrades can occur
* Non-Production environments are upgraded during weekdays.

Production Upgrades
* Production environments will be upgraded no earlier than 4 weeks after the non-production upgrade
* Some requests (e.g. data back-flow) are unavailable between non-production & Production upgrades
* Production environments are upgraded on weekends

## Post Maintenance Customer Testing / Validation
{: #post-upgrade-customer-testing-validation}

After completion of maintenance windows or upgrades by the SRE team, it will be the customer's responsibility to perform regression testing and validate that the application is working as expected. The IBM SRE team do not have front end application access to customer environmentd. Customers are required to check general applicaton functionality and any business critical components. Additionally, any customer specific integrations (JMS) or custom configurations (automation scripts, applications, etc) will need to be validated as well.

## Emergency Maintenance
{: #emergency-maintenance}

In exceptional cases such as critical security patching, the The IBM Maximo Application Suite Dedicated Services team may need to schedule unplanned emergency maintenance outages outside of a Planned Maintenance window for Production systems.  The IBM Maximo Application Suite Dedicated team will provide as much advanced notice as possible, however depending on criticality of the security patch, 5-10 business days notice may not be possible. Emergency Maintenance will be communicated via the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center).

See below slidedeck for more information on upgrades, Continuous Delivery and Long Term Support

[MAS Continuous Delivery and Long Term Support Presentation](https://ibm.box.com/shared/static/xqn8znqlk69p8glipsxbxg9suxli643i.pptx){: external download="MAS CD and LTS Support Models.pptx"}
