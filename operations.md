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
| Run SQL script in Production | 3 Days |
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

## Client Requests for RCA
{: #client-request-rca}

RCA (Root Cause Analysis)

For Severity 1 incidents, IBM SRE and the Incident Response Team (IRT) have a primary goal to restore service and remediate any disruption as soon as possible. Addressing the symptoms of an issue can often be sufficient enough to successfully restore service, but the underlying root cause may not have been identified during this process due to time constraints. A Root Cause Analysis (RCA) can be requested by customers for further analysis to help identify the underlying cause. As part of this process,  the client and/or their implementer may be required to review specific configurations within the Maximo or TRIRIGA application. Root Cause Analysis can include specific actions to prevent the same issue occurring again in the future. This detail will be given back to the client in the case itself, or in an associated child case if opened separately. Unlike an Incident Report, an RCA is not a separate document and doesn't include a summary of the primary issue or timeline of significant activity during the event. The original case will already have this detail captured.

Under what type of circumstances an RCA can be requested

* RCA's are only provided for production environments
* RCA's are provided for Severity 1 incidents that are outside of the agreed SLA (99.9% availability for the Production environment)
* RCA’s are not provided for single/isolated incidents
* RCA's can be provided for frequently recurring issues in production that have a significant impact on your business

How to request an RCA

* If the case in which the incident occurred is still open, customers can request a Root Cause Analysis as an entry within the case itself.
* If the case in which the incident occurred is closed, a new case should be opened by the customer specifically requesting an RCA. It should include the original case number of the incident.
* For example: "Request for RCA on TS00001111"

RCA lead times

An RCA can take between 5 to 10 business days to be completed. RCA detail will be provided in the applicable case.

## IBM Support Guides
{: #ibm-support-guides}

An IBM Support Guide for Maximo Application Suite is available. See link below. The guide contains information such as Contact Information, Hours of Operation, Severity Level Guidelines and Response Time Objectives and Issue Escalation:

https://www.ibm.com/support/pages/node/733923

## Project Implementation Guidelines
{: #project-implementation-guildelines}

### Planning
{: #planning}

#### 1.1 Implementation Types
{: #mas-implementation-types}

There are generally two types of implementation scenarios when working with IBM SRE on a large implementation of MAS:

New Implementation

In this scenario, MAS is implemented from an "out of the box" build. Data is usually migrated manually into "net new" MAS environment(s) by the customer or system implementor. Changes and customizations are made directly in the MAS environment itself or migrated manually from one or more standalone environment(s). This type of implementation typically does not require a statement of work with the customer or IBM internal DoU (Document of Understanding) with IBM SRE, as the level of effort on the SRE side usually falls under IBM's standard MAS support services.

Migration to IBM Cloud or AWS

In this scenario, an existing on-premise or non-IBM Cloud production Maximo v7 environment is migrated and upgraded to MAS on the IBM Cloud or AWS. This type of scenario requires a separate purchase of a migration part number as well as some analysis to ensure the correct level of IBM SRE effort is captured. It usually involves one or more test migrations and a live cutover. IBM SRE services related to a cloud migration effort are not included as part of IBM's standard MAS Dedicated or MAS-MS subscription. Please see Maximo Migration to Cloud Services for further details:

https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-migration-from-maximo-saas-flex-or-on-premise

It is important to identify your implementation type and work with IBM SRE and Expert Services as necessary to insure all SRE related work for the project has been considered and reviewed.

Note: Net-new MAS implementations typically do not require a DoU or SOW from IBM Expert Services; migration efforts from on-premise typically require a DoU and/or SOW.

#### 1.2  MAS Order Considerations
{: #mas-order-considerations}

The following section contains items that should be reviewed and considered prior to MAS orders or Statements of Work being finalized and submitted.

#### 1.2.1  Provisioning Form
{: #mas-order-form}

It is important to confirm your IBM Salesperson has properly completed a provisioning form for the MAS order. This form contains important information as it relates to the project. Make sure the information on the form is accurate in order to prevent the possibility of re-work by IBM SRE after customer environments are provisioned. This can cause unnecessary project delays. Provisioning information to review:

Contacts

These are the contacts that will receive the Welcome Kit when the environments are first provisioned. Be sure all proper contacts have been identified, including any key members from the implementation team (IBM Expert Services, GBS or 3rd party)

Preferred Data Center Location

This is the IBM Cloud or AWS data center location where the environments will be provisioned and will serve as the primary data center. See the Architecture section for a list of currently supported locations. Be sure this location is correct and in line with the customer's expectations an nearest to the majority of their end users.

Environment URL names

These are the URL names that will be setup for each provisioned environment (PROD, DEV, TEST, etc). Customers can define a specific sub-domian level name for each environment URL. Be sure these are correct and in line with customer expectations and overall project plan.

IBM MAS example domain names for a company called ACME might be:

Production URL example : `https://main.home.ACME.suite.maximo.com`

Non-Production URL example: `https://main.home.ACME-DEV.suite.maximo.com`

Note: environment names, once specified, cannot be altered without re-provisioning. This will incurr additional costs. In addtion, no provisioning can take place until URLs have been specificed.

Languages

Be sure any languages that need to be installed in the environments (other than English) are identified.

Contact your IBM salesperson or the IBM CDS Project Office: SaaSIOTPPO/Dallas/IBM to obtain a current copy of the provisioning form for your customer.

#### 1.2.2  Component Verification
{: #mas-component-verification}

It is important to check with your IBM salesperson to insure all necessary products and components have been included in the customer MAS order. This will help eliminate the need for re-work by the IBM SRE team after the initial environments have been provisioned and avoid unnecesssary delays. Examples of MAS items or components that may be overlooked on an order include:

Number of Environments:

The correct number and type of environments. Two (2) environments are provided by default on MAS orders: (PROD and TEST). Additional environments can be provisioned at an added cost. PROD environments are sized to support the total number of concurrent or authorized users specified on the order.

Sizing:

All PROD and NON-PROD environment sizing is specified on the SQO order. Clients are required to specify the sizing (Dev, extra small, small, medium, large). Environments are not designed or sized for load testing activities.

Have all applicable Industry Solutions and add-on components (Scheduler, SAP or Oracle Connector, Health, Aviation, etc) been ordered?

Will a replicated copy of the PROD database be needed for offline reporting or data extraction purposes? If yes, an add-on reporting database should be included on the order.

Further details on MAS components can be found in the Service Description for the offering.

#### 1.3  Statement of Work (SOW) or Contract Considerations
{: #mas-sow-considerations}

The following contains items that should be included and considered in any Statement of Work or Contract that involves the use of IBM MAS environments

#### 1.3.1  Project Plan and Project Schedule
{: #mas-project-plan-schedule}

The following are items that should be considered for the project plan and schedule. IBM SRE has found these are often overlooked and should be reviewed and considered. Please note SRE is not ultimately responsible for establishing your project's plan and schedule, but can and should be consulted.

The Project Management Plan should include, but not be limited to the following:

- Client (or designate) is responsible for the Project Manager role
- Identification of Project Team and Roles for client, business partner(s), and IBM
- Scope statement that clearly defines what IBM SRE needs to do
- Quality Management Plan that includes the Test Plan with all testing activities, Configuration Management Plan to maintain environments, and methodology (i.e. Waterfall vs. Agile)
- Performance Load Testing (IBM SRE can assist but is not responsible)
- Communication Plan that outlines how information will be disseminated
- Risk Management Plan that identifies risks and plan for managing them
- The Project Schedule should include:
- Project non-working days/times that are agreed by client, business partner(s), and IBM
- Onboarding activities
- Resources and lead times for all appropriate IBM SRE requests (please see lead times):

https://cloud.ibm.com/docs/mas-ms?topic=mas-ms-operations#sre-task-lead-times

- Steps for Production dry run(s)
- IT-mandated freeze period(s)
- Go Live Deployment Period(s)

#### 1.3.2  Infrastructure based deliverables
{: #mas-infrastructure-deliverables}

IBM GBS, Expert Services or other 3rd party services projects that leverage IBM Cloud or AWS based MAS environments should avoid including infrastructure based deliverables in any contract or statement of work. This would include promising deliverables of the following nature:

- Infrastructure diagrams or design documents
- Network Diagrams
- Clustering Diagrams
- Hardware sizing and resource allocations (Cores, Memory, Storage)
- Listing of O/S, Middleware or other specific Software Versions
- IT security documents or diagrams
- Installation checklists or certifications

In the IBM MAS-Dedicated model, the IT stack is the responsibility and domain of the IBM SRE team. IBM's MAS architecture is based on best practices and empirical experience supporting a large existing customer base. With a MAS subscription, the responsibility of IBM SRE is to deliver the application in accordance with the customer's MAS subscription terms and Service Level Agreement (SLA). IBM is not obligated to provide technical details of the infrastructure used to meet it's subscription commitments. As a result, specific infrastructure based deliverables should be avoided in consulting services contracts. Technical details regarding customer infrastructure can, in some cases, be provided by the SRE team depending on the nature of the request.

### Provisioning
{: #provisioning}

Be sure both you an your customer are aware of IBM SRE provisioning lead times and have scheduled accordingly. Make sure the customer's MAS environments are ordered and will be available prior to any scheduled meetings or on-site engagements that require access to the environments. IBM's objective is to provision MAS environments within 1-2 weeks of their corresponding sales order being placed, approved and fully processed. The overall amount of time can vary depending on the size (user license) of the environment(s), total number of environments needed (for example DEV, TEST, PROD), number and type of industry solutions within each environment, number & type of add-on components such as Maximo Anywhere, availability of resources in the target data center location, and amount of orders in the queue.

### Onboarding & Implementation
{: #onboarding-implementation}

#### 3.1  Onboarding Roles
{: #onboarding-roles}

The following onboarding roles should be defined:

* Client Business Leader - provides formal sign off of completed phases
* Project Implementer - Top level contact of the Implementor (GBS, Partner, 3rd Party)
* Project Manager - usually provided by the Implementor
* IBM SRE - provides environment support via case tickets
* Client IT Team - obtains support for MAS environments by submitting case tickets

#### 3.2  Traps
{: #traps}

The following are common "traps" that can occur in MAS implementation projects.

* Not allocating time to test any potential product issues found
* Report Developer Access
* Planning & Organizing VPN configuration to support integration(s)
* Inability to submit case tickets (see IBM SRE Services Support)
* Not engaging the IBM SRE team early, esp regarding networking (see section 3.6 below 'Back End Access')
* Not planning or coordinating a detailed go live plan and schedule
* Not planning for post-go live maintenance
* Not allocating time or resources for performance load testing

#### 3.3  Welcome Kit
{: #welcome-kit}

When the MAS environments are provisioned and ready, the customer contacts on the order's Provisioning Form will receive a Welcome Kit from IBM with full details on accessing their environments. Customers will be provided a URL for each environment and will be able to login as the masadmin (Maximo) user. Customers are responsible for setting up additional users and security groups within each environment

#### 3.4  On Boarding Meeting
{: #onboarding-meeting}

IBM will schedule and provide an on-boarding meeting. This meeting serves as a brief introduction to IBM SRE services and covers the following details:

* Contacts, Support and Administration
* Client Environments (how to access)
* Support (How to get Help)
* Roles & Responsibilities
* Tools & Access Control
* Helpful Links

If you do not receive an invite for an onboarding meeting, please contact: cdsonboarding@ibmserviceengage.com

#### 3.5  Case Ticket Submission
{: #case-ticket-submission}

At the onset of the project, Project manager(s) should determine who from their implementation team will be responsible for submitting case tickets to IBM. A single portal (https://www.ibm.com/mysupport) is used to establish cases for both MAS environment related issues and product specific issues. It is generally advisable to have a limited number of individuals that can submit cases in order to prevent ticket duplication and better manage updates, followup and closure. Specific instructions on how to establish access to the IBM Support Community for case ticket submission can be found in the IBM SRE Services Support section.

#### 3.6  Back End Access
{: #back-end-access}

Certain types of special back end access are usually needed at the beginning of projects for developers and/or consultants. It's important to note that this type of access can only be configured after environments have been provisioned and are accessible. Access of this type must be requested via case ticket submission

Common back-end access types for most MAS projects are:

* VPN

This is particularly important if integrations, data migration or custom reports are part of the implementation.

* Direct Database Access

This is usually required for report developers and those who need to run SQL statements against the database. Which users will need access? What kind of access is needed? Note: read/write access is allowed on non-production environments; read-only allowed on production environments if a database replica is ordered and configured.

* COS (Cloud Object Storage) access

This is typically used for files transfers to/from MAS, file based integrations and Application Server log file access. Who will need it?

IBM recommends first determining who from the implementation team will need each of the above. Create and submit a single case for each access type. Within the case list each user who require that specific type of access.

#### 3.7  Support Request (Case) Lead Times
{: #support-case-lead-times}

IBM SRE has specific lead times established based on the type of request being submitted. Lead times can vary based on number of cases in the queue and the complexity or level of effort of the specific request. It is important to consider standard lead times when planning your project and delivery commitments. For details please see Request Lead Times

#### 3.8  Report Customization
{: #report-customization}

If custom reporting is part of the implementation, please see access section above.

#### 3.9  SAML and/or LDAP Authentication
{: #saml-ladp-authentication}

MAS supports Single Sign On (SSO). This can only be configured after environments have been initially provisioned. Further detail on how to initiate this configuration process with the IBM SRE support team can be found under Single Sign On (SSO) and SAML Authentication

#### 3.10  Roles & Responsibilities
{: #roles-responsibilities}

Roles & Responsibilities for IBM SRE, Customers, Implementors and other parties are described in the Environment Management & Responsibilities section. This includes a RACI that details each level of responsibility (Responsible Accountable, Consulted, Informed) for specific tasks. It is important to review the applicable RACI and make sure all project team members agree to and understand their individual roles.

### Go Live & Steady State Support
{: #go-live-support}

It is important to determine and clearly communicate any critical phases or go live support periods in your project schedule to the IBM SRE team as early as possible. The IBM SRE support team needs to be aware of these phases as specific SRE resources (DBA, Network, Firewall, Sys Admin) will need to be lined up in advance.  Typically implemention teams would have a detailed go live task list to support this and a "dry run" of the go live cutover activities is often performed in advance to validate the task list and timings. For guidelines on notifying IBM SRE, see Requesting Off Hours & Weekend Support

It is important to determine how ownership and support will transition once the go live has been successfully completed and the system migrates to steady state. The IBM Support Community portal will be the primary means of communication for any MAS or product related issues.

5.1 Steady State Roles

* Client Business Owner
* IBM SRE
* Client IT Team
* Additional Steady State teams as specified by the client
