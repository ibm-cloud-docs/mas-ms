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
{:external: target="_blank" .external}

# Maintenance
{: #maintenance}

## Deployment Options
{: #deployment-options}

The Cloud Service supports two architectural deployment options, Dedicated Cluster and Shared Cluster, each of which require Capacity Units, Virtual Processor Cores and Gigabyte entitlements. The difference between the two options is how the Cloud Service is deployed and used. For both deployment options, the client will have their own MAS Applications and their own database schemas. The Cloud Service will be configured based on the deployment option purchased.

**Dedicated Cluster Deployment** (default)

With the Dedicated Cluster deployment, IBM Red Hat OpenShift on IBM Cloud and IBM Cloud Pak for Data are not shared by multiple Production Instances(s), Non-Production Instance(s) or Clients. Each MAS Client Production Instance and Non-Production Instance will have its own IBM Cloud Services and it will not be shared across clients. Clients choosing the Dedicated Cluster deployment will determine when they wish to implement MAS Dedicated software upgrades. The upgrade may be postponed or deferred by the client. Client will need to communicate to IBM Support if they wish to defer any upgrade. The following exceptions apply:

- Client must always be on a supported version. Client will need to upgrade their current version before it reaches the end of support date.
- Client will always be required to accept critical security patches. IBM alone will determine whether a patch is deemed a critical security patch and the date it will be applied.

**Shared Cluster Deployment** (optional)

In the Shared Cluster deployment, IBM Red Hat OpenShift on IBM Cloud and IBM Cloud Pak for Data will be shared across multiple Production Instance(s) and Non-Production Instance(s) and Clients. Clients choosing the Shared Cluster deployment will be subject to the MAS Dedicated offering software upgrade policy that is set by IBM. IBM will determine and communicate when upgrades will occur, and no deferrals or exceptions will be allowed.

Clients who purchased MAS-MS or were quoted prior to December 2022 are Shared Cluster deployment.  Clients who were quoted and purchased off that quote after January 2023 are Dedicated Cluster deployment.  If you are not sure which deployment option you have please contact your IBM sales person, CSM or open a support ticket.

## 2023 Maintenance Details
{: #2021-maintenance-details}

Standard maintenance times for production environments are planned and scheduled over weekend timeframes.  The maintenance duration can range from 4 to 48 hours on Saturday and/or Sunday depending on the scope of work being performed.  All updates are first applied to non-production environments and then productio. Specific dates are communicated through the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center).

The IBM Maximo Application Suite SRE team may choose to use all, some, or none of the planned maintenance windows and will proactively notify customers 5-10 days prior to any outage that will be taken.

Systems are not available to users during maintenance windows.

Non-Production systems may be scheduled for maintenance during the week, 1- 2 weeks prior to planned maintenance on Production systems to allow additional time for testing.

Change Freeze period for year end 2023 is December 16, 2023 through January 2, 2024
Systems are available to users and all standard automated processes such as database backups continue as normal during the change freeze period.  Coordinated changes to environments like application upgrades as an example are not available during this time.  The IBM Maximo Application Suite Dedicated team also does not schedule any maintenance during the change freeze period.

## Upgrade Rules, Policy and Plans
{: #upgrade-rules}

Application and MAS component Upgrades are on a defined schedule based on the Maximo Application Suite release schedule and complexity of the upgrade.  It is expected customers will be upgraded to the current version within 6 months of release.  Upgrades will be deployed first to test and then scheduled for production.  The test window length will depend on the size and complexity of the change and will be communicated through the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center) as soon as it is available.

## LAFixes
{: #lafixes}

During the Manage upgrade process all LAFixes applied to a customer's environment will be removed.  It is the customer's responsibility to retest and revalidate all functionality after an upgrade.  If an issue is found, the customer should [open a case](https://www.ibm.com/mysupport){: external} with the product support team to troubleshoot.  If a new LAFix is required, this would need to be requested through the support case.  LAFix approvals by the SRE team will be determined on a case-by-case basis.

### Shared Cluster Deployment Customers
{: #shared-cluster-upgrades}

Application and MAS component Upgrades are on a defined schedule based on the Maximo Application Suite release schedule and complexity of the upgrade. It is expected customers will be upgraded to the current version within 6 months of release. Upgrades will be deployed first to test and then scheduled for production. The test window length will depend on the size and complexity of the change and will be communicated through the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center) as soon as it is available.

Shared Cluster Upgrade Policy

The following guidelines apply to MAS-Dedicated (Shared Cluster) release schedule:
* MAS (8.x) GA versions are released twice a year by IBM development (approx)
* MAS Dedicated comes out on the first Tuesday 30 days after MAS (GA) release.
* For example, MAS 8.10 (GA) will be released by IBM on 3/28/2023 and MAS Dedicated 8.10 on 5/2/2023
* The release of MAS Dedicated can be delayed beyond 30 days due to holidays and freeze periods. For example MAS 8.9 was released on 11/22/2022 and MAS Dedicated will be 1/17/2023

| Version | MAS Release | MAS Dedicated Release | Approx Upgrade Window |
| -------------- | -------------- | -------------- | -------------- |
| 8.9 | 1/22/22 | 1/17/23 | Mid March to June |
| 8.10 | 3/28/23 | 5/2/23 | Late June to September |
| 8.11 | 9/29/23 | 10/30/23 | Late Nov to Feb |
| 8.12 | March 2024 | April 2024 | TBD |
{: caption="Table 1. MAS-MS Release Planning" caption-side="bottom"}

Planning Guidelines

The following guidelines apply to planning for MAS upgrades:
* Upgrade schedules are set by IBM & communicated via [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center)
* Upgrade schedules are non-negotiable
* All client stakeholders must register to receive CCC notifications & communications
* IBM will share long-range anticipated upgrade windows upon request via ticket
* Upgrade window information is shared for planning purposes only & is not a commitment
* Timing is subject to change at IBM’s sole discretion based on software availability & other factors

Non-Production Upgrades

* Clients will be notified via CCC at least 5 business days prior to non-production environment upgrades
* All non-production environments will be upgraded concurrently, without exception
* Non Production environments are upgraded during weekdays.

Production Upgrades

* Production environments will be upgraded no earlier than 4 weeks after the non-production upgrade
* Some requests (e.g. data back-flow) are unavailable between non-production & Production upgrades
* Clients will be notified via CCC at least 10 business days prior to the Production environment upgrade
* The Production environment will be upgraded on schedule, without exception
* Production environments are upgraded on weekends

Notes:

* Upgrades of both prod or non-prod cannot requested to be done earlier or deferred to later for any reason, such as:
* We have training scheduled on planned maintenance window
* We are in critical stage of implementation phase and env cannot be touched
* We have a golive coming up and system cannot be touched
* We have an executive demo
* Non-prod upgrade broke a business functionality that is critical to the business, so Prod cannot be updated until the bug is fixed
* We need upgrade soon, because the new release has feature we need asap

Testing:

* SRE team cannot do any front end test such as can a user login check after upgrade
* Customer needs to do smoke test of critical business functionalities

Patch Upgrades

The following guidelines apply to patch upgrades:
* Patch upgrade for MAS or any Apps have to be requested via IBM suppport case
* 1 week of advance notice is needed in ticket for Patch upgrade
* If Patch contains security fixes or any security fix available, IBM SRE team will apply fix as soon as its available. No exceptions.

### Dedicated Cluster Deployment Customers
{: #dedicated-cluster-upgrades}

The following guidelines apply to MAS-Dedicated (Dedicated Cluster) release schedule:
* MAS (8.x) GA versions are released twice a year by IBM development (approx)
* MAS Dedicated comes out on the first Tuesday 30 days after MAS (GA) release.
* For example, MAS 8.10 (GA) will be released by IBM on 3/28/2023 and MAS Dedicated 8.10 on 5/2/2023
* The release of MAS Dedicated can be delayed beyond 30 days due to holidays and freeze periods. For example MAS 8.9 was released on 11/22/2022 and MAS Dedicated will be 1/17/2023

| Version | MAS Release | MAS Dedicated Release | Approx Upgrade Window |
| -------------- | -------------- | -------------- | -------------- |
| 8.9 | 1/22/22 | 1/17/23 | Mid March to June |
| 8.10 | 3/28/23 | 5/2/23 | Late June to September |
| 8.11 | 9/29/23 | 10/30/23 | Late Nov to Feb |
| 8.12 | March 2024 | April 2024 | TBD |
{: caption="Table 1. MAS-Dedicated Release Planning" caption-side="bottom"}

Planning Guidelines
The following guidelines apply to planning for MAS upgrades:
* Clients must remain on a supported version.  This means either be on n or n-1 or a Long Term Support version.  For example once 8.13 is released, 8.11 is no longer in support so a customer will need to be on 8.12 before 8.13 is released.
* Long Term support (LTS) releases are designated by development.  8.10 has been designated as a Long Term Support release.  LTS releases are supported for up to three years.  No new functionality will be delivered on this release, but fixes and security patches will be available and delivered to clients on LTS releases.
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
* Client must request via tickets which environment and the dates upgrades can happen
* Non Production environments are upgraded during weekdays.

Production Upgrades
* Production environments will be upgraded no earlier than 4 weeks after the non-production upgrade
* Some requests (e.g. data back-flow) are unavailable between non-production & Production upgrades
* Production environments are upgraded on weekends

Testing:
* SRE team cannot do any front end test such as can a user login check after upgrade
* Customer needs to do smoke test of critical business functionalities

Patch Upgrades
The following guidelines apply to patch upgrades:
* Patch upgrade for MAS or any Apps have to be requested via IBM support case
* 1 week of advance notice is needed in ticket for Patch upgrade
* If Patch contains security fixes or any security fix available, IBM SRE team will apply fix as soon as its available. No exceptions.

## Post Upgrade Customer Testing / Validation
{: #post-upgrade-customer-testing-validation}

After completion of an upgrade by the SRE team, it will be the customer's responsibility to perform regression testing and validate that the application is working as expected. Customers are required to check general applicaton functionality and any business critical components. Additionally, any customer specific integrations (JMS) or custom configurations (automation scripts, applications, etc) will need to be validated as well.

## Emergency Maintenance
{: #emergency-maintenance}

In exceptional cases such as critical security patching, the The IBM Maximo Application Suite Dedicated Services team may need to schedule unplanned emergency maintenance outages outside of a Planned Maintenance window for Production systems.  The IBM Maximo Application Suite Dedicated team will provide as much advanced notice as possible, however depending on criticality of the security patch, 5-10 business days notice may not be possible. Emergency Maintenance will be communicated via the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center).

See below slidedeck for more information on upgrades, Continuous Delivery and Lon Term Support

[MAS Continuous Delivery and Long Term Support Presentation](https://ibm.box.com/shared/static/xqn8znqlk69p8glipsxbxg9suxli643i.pptx){: external download="MAS CD and LTS Support Models.pptx"}
