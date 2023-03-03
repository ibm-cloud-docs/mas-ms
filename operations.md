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

IBM Maximo Application Suite Dedicated customers receive support coverage 24 hours per day, 7 days per week, 365 days per year. This includes IBM Support Community Portal access, comprehensive backup and restore, system monitoring and patching. 24x7 emergency on-call support is available for Severity 1 or system down incidents. This is reserved for production outages where the application is unavailable or service has been severely degraded. IBM leverages an automated alert system integrated with our case ticketing system to provide timely customer response to Sev1 issues.

Please follow [this link](https://www.ibm.com/support/pages/node/738881) for Severity and Repsonse guidelines from the IBM Global Support Team.

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

An IBM Support Guide for Maximo Application Suite is available. See link below. The guide contains information such as Contact Information, Hours of Operation, Severity Level Guidelines and Response Time Objectives and Issue Escalation:

https://www.ibm.com/support/pages/node/733923

## Project Implementation Guidelines
{: #project-implementation-guildelines}

Please Note: This section is under construction

### Planning
{: #planning}

#### 1.1 Implementation Types

There are generally two types of implementation scenarios when working with IBM SRE on a large implementation of MAS:

New Implementation

In this scenario, MAS is implemented from an "out of the box" build. Data is usually migrated manually into "net new" MAS environment(s) by the customer or system implementor. Changes and customizations are made directly in the MAS environment itself or migrated manually from one or more standalone environment(s). This type of implementation typically does not require a statement of work with the customer or IBM internal DoU (Document of Understanding) with IBM SRE, as the level of effort on the SRE side usually falls under IBM's standard MAS support services.

Migration to IBM Cloud or AWS

In this scenario, an existing on-premise or non-IBM Cloud production Maximo v7 environment is migrated and upgraded to MAS on the IBM Cloud or AWS. This type of scenario requires a separate purchase of a migration part number as well as some analysis to ensure the correct level of IBM SRE effort is captured. It usually involves one or more test migrations and a live cutover. IBM SRE services related to a cloud migration effort are not included as part of IBM's standard MAS Dedicated or MAS-MS subscription. Please see Maximo Migration to Cloud Services for further details:

https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-migration-from-maximo-saas-flex-or-on-premise

It is important to identify your implementation type and work with IBM SRE and Expert Services as necessary to insure all SRE related work for the project has been considered and reviewed.

Note: Net-new MAS implementations typically do not require a DoU or SOW from IBM Expert Services; migration efforts from on-premise typically require a DoU and/or SOW.

#### 1.2  MAS Order Considerations

The following section contains items that should be reviewed and considered prior to MAS orders or Statements of Work being finalized and submitted.

#### 1.2.1  Provisioning Form

It is important to confirm your IBM Salesperson has properly completed a provisioning form for the MAS order. This form contains important information as it relates to the project. Make sure the information on the form is accurate in order to prevent the possibility of re-work by IBM SRE after customer environments are provisioned. This can cause unnecessary project delays. Provisioning information to review:

Contacts
These are the contacts that will receive the Welcome Kit when the environments are first provisioned. Be sure all proper contacts have been identified, including any key members from the implementation team (IBM Expert Services, GBS or 3rd party)

Preferred Data Center Location
This is the IBM Cloud or AWS data center location where the environments will be provisioned and will serve as the primary data center. See the Architecture section for a list of currently supported locations. Be sure this location is correct and in line with the customer's expectations an nearest to the majority of their end users.

Environment URL names
These are the URL names that will be setup for each provisioned environment (PROD, DEV, TEST, etc). Customers can define a specific sub-domian level name for each environment URL. Be sure these are correct and in line with customer expectations and overall project plan.

IBM MAS example domain names for a company called ACME might be:

`https://main.home.ACME.suite.maximo.com`

`https://main.home.ACME-DEV.suite.maximo.com`

Languages
Be sure any languages that need to be installed in the environments (other than English) are identified.

Contact your IBM salesperson or the IBM CDS Project Office: SaaSIOTPPO/Dallas/IBM to obtain a current copy of the provisioning form for your customer.

#### 1.2.2  Component Verification

It is important to check with your IBM salesperson to insure all necessary products and components have been included in the customer MAS order. This will help eliminate the need for re-work by the IBM SRE team after the initial environments have been provisioned and avoid unnecesssary delays. Examples of MAS items or components that may be overlooked on an order include:

Number of Environments:

The correct number and type of environments. Two (2) environments are provided by default on MAS orders: (PROD and TEST). Additional environments can be provisioned at an added cost. PROD environments are sized to support the total number of concurrent or authorized users specified on the order.

Add-on Capacity:

All NON-PROD environments will support up to 30 concurrent users by default. If more than 30 concurrent users need to be supported in any NON-PROD environment, add-on capacity should be included on the order. For example, will a performance load testing environment be required for this project? This is typically an environment that is identical to (or mimics) the production environment. If yes, one or more non-production capacity add-ons will need to be included on the order. Standard NON-PROD environments are not designed or sized for load testing activities.

Have all applicable Industry Solutions and add-on components (Scheduler, SAP or Oracle Connector, Health, Aviation, etc) been ordered?

Will a replicated copy of the PROD database be needed for offline reporting or data extraction purposes? If yes, an add-on reporting database should be included on the order

Further details on MAS components can be found in the Service Descriptions for each offering.

If you are an IBMer and would like a copy of a customer's current MAS order from the EngageSupport database, please contact the IBM SRE Project Office: SaaSIOTPPO/Dallas/IBM. If you are a customer or business partner, please contact an IBM SRE team member and this information can be provided

#### 1.3  Statement of Work (SOW) or Contract Considerations

The following contains items that should be included and considered in any Statement of Work or Contract that involves the use of IBM MAS environments

#### 1.3.1  Project Plan and Project Schedule

The following are items that should be considered for the project plan and schedule. IBM SRE has found these are often overlooked and should be reviewed and considered. Please note SRE is not ultimately responsible for establishing your project's plan and schedule, but can and should be consulted.

The Project Management Plan should include, but not be limited to the following:

- Identification of Project Team and Roles for client, business partner(s), and IBM
- Scope statement that clearly defines what IBM SRE needs to do
- Quality Management Plan that includes the Test Plan with all testing activities, Configuration Management Plan to maintain environments, and methodology (i.e. Waterfall vs. Agile)
- Performance Load Testing
- Communication Plan that outlines how information will be disseminated
- Risk Management Plan that identifies risks and plan for managing them
- The Project Schedule should include:
- Project non-working days/times that are agreed by client, business partner(s), and IBM
- Onboarding activities
- Resources and lead times for all appropriate IBM SRE requests
- Steps for Production dry run(s)
- IT-mandated freeze period(s)
- Go Live Deployment Period(s)
- A sample project plan for migration to Maximo MAS can be found on the Attachments tab below.

#### 1.3.2  Infrastructure based deliverables

IBM GBS, Expert Services or other 3rd party services projects that leverage IBM Cloud or AWS based MAS environments should avoid including infrastructure based deliverables in any contract or statement of work. This would include promising deliverables of the following nature:

- Infrastructure diagrams or design documents
- Network Diagrams
- Clustering Diagrams
- Hardware sizing and resource allocations (Cores, Memory, Storage)
- Listing of O/S, Middleware or other specific Software Versions
- IT security documents or diagrams

Installation checklists or certifications

In the IBM MAS Dedicated model, the IT stack is the responsibility and domain of the IBM SRE team. IBM's MAS architecture is based on best practices and empirical experience supporting a large existing customer base. With a MAS subscription, the responsibility of IBM SRE is to deliver the application in accordance with the customer's MAS subscription terms and Service Level Agreement (SLA). IBM is not obligated to provide technical details of the infrastructure used to meet it's subscription commitments. As a result, specific infrastructure based deliverables should be avoided in consulting services contracts. Technical details regarding customer infrastructure can, in some cases, be provided by the SRE team depending on the nature of the request. Please see slide below that shows the IBM MAS model. It is consistent with most public MAS models. It is important customers understand the nature of Software as a Service delivery.

### Provisioning
{: #provisioning}

This section is under construction

### Onboarding & Implementation
{: #onboarding-implementation}

This section is under construction

### Go Live & Steady State Support
{: #go-live-support}

This section is under construction

## Upgrade Rules, Policy and Plans
{: #upgrade-rules}

### MAS Dedicated Release Planning
{: #mas-release-planning}


* MAS Dedicated comes out on the first Tuesday 30 days after MAS (GA) release. 

* For example, MAS 8.10 (GA) will be released by IBM on 3/28/2023 and MAS Dedicated 8.10 on 5/2/2023

* The release of MAS Dedicated can be delayed beyond 30 days due to holidays and freeze periods. For example MAS 8.9 was released on 11/22/2022 and MAS Dedicated will be 1/17/2023

| Version | MAS Release | MAS Dedicated Release | Approx Upgrade Window |
| -------------- | -------------- | -------------- | -------------- |
| 8.9 | 1/22/22 | 1/17/23 | Mid March to June |
| 8.10 | 3/28/23 | 5/2/23 | Late June to September |
| 8.11 | 7/25/23 | 8/29/23 | Late Oct to Jan |
| 8.12 | 11/21/23 | 1/9/24 | TBD |
{: caption="Table 1. MAS-Dedicated Release Planning" caption-side="bottom"}

### Planning Guidelines
{: #mas-planning-guidelines}


* Upgrade schedules are set by IBM & communicated via Client Communications Center (CCC)
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

### Patch Upgrades
{: #mas-patch-upgrades}


* Patch upgrade for MAS or any Apps have to be requested via IBM suppport case
* 1 week of advance notice is needed in ticket for Patch upgrade
* If Patch contains security fixes or any security fix available, IBM SRE team will apply fix as soon as its available. No exceptions.
