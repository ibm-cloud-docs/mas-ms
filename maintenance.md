---

copyright:
  years: 2015, 2020
lastupdated: "2022-07-19"

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

## 2023 Maintenance Windows
{: #2021-maintenance-windows}

Maintenance Windows generally apply to production environments only.

Standard maintenance times for PROD environments are planned and scheduled for weekend timeframes.  The maintenance duration can range from 4 to 40 hours on Saturday and/or Sunday depending on the scope of work being performed.  All updates are first applied to non-production sites for clients to validate and then production later. Exact dates are communicated through the Client Communication Center.

The IBM Maximo Application Suite Managed Services team may choose to use all, some, or none of the planned maintenance windows and will proactively notify customers 5-10 days prior to any outage that will be taken.

Systems are not available to users during maintenance windows.

Non-Production systems may be scheduled for maintenance during the week, 1- 2 weeks prior to planned maintenance on Production systems to allow additional time for testing.

Change Freeze period for year end 2022 is December 17, 2022 through January 2, 2023
Systems are available to users and all standard automated processes such as database backups continue as normal during the change freeze period.  Coordinated changes to environments like application upgrades as an example are not available during this time.  The IBM Maximo Application Suite Managed Services team also does not schedule any maintenance during the change freeze period. 

## Upgrade Policy
{: #upgrade-policy}

Application and MAS component Upgrades are on a defined schedule based on the Maximo Application Suite release schedule and complexity of the upgrade.  It is expected customers will be upgraded to the current version within 6 months of release.  Upgrades will be deployed first to test and then scheduled for production.  The test window length will depend on the size and complexity of the change and will be communicated through the Customer Communications Center as soon as it is available.

## Post Upgrade Customer Testing / Validation
{: #post-upgrade-customer-testing-validation}

After completion of an upgrade by the SRE team, it will be the customer's responsibility to perform regression testing and validate that the application is working as expected. Customers are required to check general applicaton functionality and any business critical components. Additionally, any customer specific integrations (JMS) or custom configurations (automation scripts, applications, etc) will need to be validated as well.

## Emergency Maintenance
{: #emergency-maintenance}

In exceptional cases such as critical security patching, the The IBM Maximo Application Suite Managed Services team may need to schedule unplanned emergency maintenance outages outside of a Planned Maintenance window for Production systems.  The IBM Maximo Application Suite Managed Services team will provide as much advanced notice as possible, however depending on criticality of the security patch, 5-10 business days notice may not be possible.

## Exception / Deferral Maintenance Requests
{: #exception-deferral-maintenance-requests}

All customer environments are managed to several internal and external security and compliance standards. IBM initiated planned maintenance is governed by these standards. For this reason, exceptions or deferral requests are **not available**. There are **no exceptions**.


