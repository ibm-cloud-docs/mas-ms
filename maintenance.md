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

## 2023 Maintenance Details
{: #2021-maintenance-details}

Maintenance Windows generally apply to production environments only.

Standard maintenance times for PROD environments are planned and scheduled for weekend timeframes.  The maintenance duration can range from 4 to 48 hours on Saturday and/or Sunday depending on the scope of work being performed.  All updates are first applied to non-production sites for clients to validate and then production later. Exact dates are communicated through the Client Communication Center.

The IBM Maximo Application Suite Dedicated team may choose to use all, some, or none of the planned maintenance windows and will proactively notify customers 5-10 days prior to any outage that will be taken.

Systems are not available to users during maintenance windows.

Non-Production systems may be scheduled for maintenance during the week, 1- 2 weeks prior to planned maintenance on Production systems to allow additional time for testing.

Customers can defer a scheduled maintenance window as long as 2 requirements are met:
1. The patch is considered non-emergency
2. Environment must remain on a supported version

Change Freeze period for year end 2023 is December 16, 2023 through January 2, 2024
Systems are available to users and all standard automated processes such as database backups continue as normal during the change freeze period.  Coordinated changes to environments like application upgrades as an example are not available during this time.  The IBM Maximo Application Suite Dedicated team also does not schedule any maintenance during the change freeze period. 

## Upgrade Policy
{: #upgrade-policy}

Application and MAS component Upgrades are on a defined schedule based on the Maximo Application Suite release schedule and complexity of the upgrade.  It is expected customers will be upgraded to the current version within 6 months of release.  Upgrades will be deployed first to test and then scheduled for production.  The test window length will depend on the size and complexity of the change and will be communicated through the Customer Communications Center as soon as it is available.

## Post Upgrade Customer Testing / Validation
{: #post-upgrade-customer-testing-validation}

After completion of an upgrade by the SRE team, it will be the customer's responsibility to perform regression testing and validate that the application is working as expected. Customers are required to check general applicaton functionality and any business critical components. Additionally, any customer specific integrations (JMS) or custom configurations (automation scripts, applications, etc) will need to be validated as well.

## Emergency Maintenance
{: #emergency-maintenance}

In exceptional cases such as critical security patching, the The IBM Maximo Application Suite Dedicated Services team may need to schedule unplanned emergency maintenance outages outside of a Planned Maintenance window for Production systems.  The IBM Maximo Application Suite Dedicated team will provide as much advanced notice as possible, however depending on criticality of the security patch, 5-10 business days notice may not be possible.

## Deployment Options
{: #deployment-options}

The Cloud Service supports two architectural deployment options, Dedicated Cluster and Shared Cluster, each of which require Capacity Units, Virtual Processor Cores and Gigabyte entitlements. The difference between the two options is how the Cloud Service is deployed and used. For both deployment options, the Client will have their own MAS Applications and their own database schemas. The Cloud Service will be configured based on the deployment option purchased.

* Dedicated Cluster Deployment (Default)

With the Dedicated Cluster deployment, IBM Red Hat OpenShift on IBM Cloud and IBM Cloud Pak for Data are not shared by multiple Production Instances(s) or Non-Production Instance(s) or Clients. Each MAS Client Production Instance and Non-Production Instance will have its own IBM Cloud Services and it will not be shared across Clients.
Clients choosing the Dedicated Cluster deployment will determine when they wish to implement MAS Dedicated software upgrades. The upgrade may be postponed or deferred by the Client. Client will need to communicate to IBM Support if they wish to defer any upgrade. The following exceptions apply:

- Client must always be on a supported version. Client will need to upgrade their current version before it reaches the end of support date.
- Client will always be required to accept critical security patches. IBM alone will determine whether a patch is deemed a critical security patch and the date it will be applied.

* Shared Cluster Deployment (Optional)

In the Shared Cluster deployment, IBM Red Hat OpenShift on IBM Cloud and IBM Cloud Pak for Data will be shared across multiple Production Instance(s) and Non-Production Instance(s) and Clients. Clients choosing the Shared Cluster deployment will be subject to the MAS Dedicated offering software upgrade policy that is set by IBM. IBM will determine and communicate when upgrades will occur, and no deferrals or exceptions will be allowed.


