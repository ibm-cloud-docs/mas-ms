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

# Operations
{: #operations}

## Service Components
{: #service-components}

IBM Maximo Application Suite Dedicated includes:

* System Administration and ongoing Security Compliance to meet IBM internal (ITSS) standards
* MAS Environment provisioning including sizing, product installation, configuration and deployment
* Ongoing maintenance including Application, Middleware and O/S upgrades, updates, patches and fixes
* Ongoing environment and database monitoring, logging & tuning
* 24 x 7 system administration support on call
* 24 x 7 support and monitoring for systems and applications
* ITIL managed operations (Service Request, Incident, Problem and Change management)
* Disaster Recovery and Backup / Restore support & services

## Technical Support
{: #technical-support}

Technical support for the cloud service is available as part of the customer's subscription period.

IBM Maximo Application Suite Dedicated customers receive support coverage 24 hours per day, 7 days per week, 365 days per year. This includes IBM Support Community Portal access, comprehensive backup and restore, system monitoring and patching.
24x7 emergency on-call support is available for Severity 1 or system down incidents. This is reserved for production outages where the application is unavailable or service has been severely degraded. IBM leverages an automated alert system integrated with our case ticketing system to provide timely customer response to Sev1 issues.

Please follow this link for Severity and Repsonse guidelines from the IBM Global Support Team:

https://www.ibm.com/support/pages/node/738881

## Data Center Locations
{: #data-center-locations}

Maximo Application Suite Dedicated is currently offered from the following IBM Cloud data center locations (regions).

North America:

* Washington, DC, US
* Dallas, TX, US
* Toronto, Canada

Europe:

* Frankfurt, Germany
* London, UK

Asia Pacific:

* Sydney, Australia

## Operations Support Locations
{: #operations-support-locations}

IBM's MAS-Dedicated support personnel are located across the globe in the following countries:

* United States
* Canada
* Brazil
* United Kingdom
* Ireland
* China
* India
* Australia

## Roles & Responsibilities Matrix (RACI)
{: #roles-responsibilities-matrix-raci}

The RACI defines IBM and customer responsibilities in the delivery and management of the Maximo Application Suite Dedicated environment.

MAS-Dedicated RACI Spreadsheet (excel download):

[MAS-Dedicated RACI Spreadsheet](https://ibm.box.com/shared/static/6rvwdbyu8uwx2qb85ovpf2btilbqnyg0.xlsx){: external download="MAS-Dedicated-RACI.xlsx"}

## IBM SRE Task Lead Times
{: #sre-task-lead-times}

The following table lists the expected lead time for the IBM SRE team (CDS) to complete certain types of tasks based on the initial case or service request response date. Lead times are in business days and are approximate.

| IBM SRE Task | Duration |
| -------------- | -------------- |
| VPN Setup | 15 Days |
| Root Cause Analysis | 10 Days |
| Apply Patch | 5 Days | 
| Backflow (Refresh) Database | 3 Days |
| On Demand Backup and Restore | 3 Days |
| Environment Migration (Database and Doclinks) | 3 Days |
| Maximo Configdb Request | 2 Days |
| SSO/LDAP setup | 2 Days |
| Cloud Object Storage (COS) Setup | 2 Days |
| Adding Additional JMS Queues | 2 Days |
| Access to CP4D | 1 Day |
| Log Request | 1 Day |
| Application Server Restarts | 1 Day |
{: caption="Table 1. MAS-Dedicated IBM SRE Lead Times" caption-side="bottom"}

## Incident Management and RCA Process
{: #incident-management-and-rca-process}

The IBM SRE team has monitoring in place for all sites and infrastructure under our control.  These are designed to allow the SRE team to pro-actively respond to service impacting or service threatening events or conditions.  When a site is unavailable, or there are infrastructure issues leading to monitor alerts, an incident record is automatically generated within our Incident Management System.

At the same time, for production environments, a SRE Incident Response Team (IRT) provides 24/7 critical outage support. The goal of IRT is to ensure our customer's applications are running when they should, and to provide effective and timely customer communication during availability incidents or Severity 1 cases during off hours. IRT is sometimes referred to as the "on call" team.

Please note IRT is not considered standard support. It is for emergency and Sev1 cases only. Please see our Support & Operations section for standard support details and hours of operation. 

How is the IBM SRE Incident Response Team (IRT) organized?

The IRT is organized into a 2-person rotating schedule on 8-hour cycles over 7 days. This means that there are two IRT members for each 8 hour period: a Client Communicator and a First Responder. IBM SRE uses a region based “follow the sun” support model. The IRT schedule is maintained and updated by IBM on a regular basis.

Client Communicator

* The Client Communicator (CC) is responsible for ensuring that any customer affected by a Severity 1 incident or alert is receiving prompt and frequent communication regarding the status of their incident. This resource does not necessarily have technical skills or access to investigate / act upon systems that are failing. The CC may also be expected to triage requests that do not fall within the definition of Severity 1 and communicate with the customer regarding these issues.

First Responder

* The First Responder (FR) is a technical role that requires access to systems that may be in a failed or failing state, as well as the skills required to understand what can be done to recover affected environment(s). It may not be possible for the FR to correct all problems and he/she should be equipped to escalate issues to specific individuals for resolution if necessary. The FR remains focused on incident resolution at all times and is not expected to communicate directly with customers; they remain in regular contact with the Client Communicator on duty. It is important to note that the First Responder is precisely that, the first responder - he/she is not solely responsible for solving every incident.

The first responder will respond to alerts and off hours Severity 1 cases to:

* Determine the impact of the alert or case
* Determine the cause of the alert or case 
* Initiate corrective action if appropriate
* Alert the Client Communicator if escalation is determined necessary.

The IBM first responder’s priority will be to restore service.  The IBM client communicator is notified if there are any challenges to restoring service.  The IBM client communicator will lead the recovery activities and escalate to any personnel required to resolve the issue, while also ensuring that continuous communication is maintained with the customer throughout the length of the incident.

Escalation Manager / Discipline Team Members
Additional support for IRT members is provided by an Escalation Manager as well as dedicated Database and Network discipline team members. These specific SRE individuals are assigned to the IRT schedule to also provide coverage. 

## IBM Support Guides
{: #ibm-support-guides}

An IBM Support Guide for Maximo Application Suite is available. See link below. The guide contains information such as Contact Information, Hours of Operation, Severity Level Guidelines and Response Time Objectives and Issue Escalation

https://www.ibm.com/support/pages/node/733923

## Project Implementation Guidelines
{: #project-implementation-guildelines}

Please Note: This section is under construction

### Project Implementation FAQs
{: #faqs}

### Planning
{: #planning}

### Provisioning
{: #provisioning}

### Onboarding & Implementation
{: #onboarding-implementation}

### Go Live & Steady State Support
{: #go-live-support}