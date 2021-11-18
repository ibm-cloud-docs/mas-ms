---

copyright:
  years: 2015, 2020
lastupdated: "2020-11-12"

subcollection: mas-ms

---

{:shortdesc: .shortdesc}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Services

## Scope of Services

IBM Maximo Application Suite Managed Service (MAS-MS) is an offering supported by IBM's Cloud Delivery Services and Development Operations team. IBM has been hosting Maximo systems for over 12 years and has deep experience provisioning and supporting Maximo on IBM Cloud. The Managed Services team is solely focused on Maximo Application Suite delivery, providing expert IT administration for both infrastructure and operations and support for customers through the IBM Support Community Portal. Customers interact with the IBM Managed Services team members via case creation, interaction and followup. Team members are based out of Canada, the United States, Brazil, Ireland, India, China and Australia. MAS-MS is a subscription based hosting service exclusively offered on the IBM Cloud platform. The diagram below shows the general scope of MAS-MS:


![Enter image alt text right here.](images/MAS-MS-Scope-of-Services.jpg "MAS-MS Scope of Services"){: caption="Figure 1. MAS-MS Scope of Services" caption-side="bottom"}

## Service Description
Please see link below to the current Service Description for Maximo Application Suite Managed Service. Please check this link regularly as it is updated periodically and the current service description takes precedent.

https://www.ibm.com/support/customer/csol/terms/internal?id=i126-8819&lc=en#detail-document

## Service Level Agreement
The Service Level Agreement (SLA) for MAS-MS is described in Section 3 of the service description document (above).

SLA Summary for Maximo Application Suite Managed Service (MAS-MS):

99.9 % Availability (production)

SLA does not include planned or emergency maintenance windows. For details on the maintenance window schedule, see Maintenance & Outage Calendar

SLA applies to production environments only

Availability credits for availability of less than 99.9%

## Operations

IBM Maximo Application Suite Managed Service includes:

- System Administration and ongoing Security Compliance to meet IBM internal (ITSS) standards
- MAS Environment provisioning including sizing, product installation, configuration and deployment
- Ongoing maintenance including Application, Middleware and O/S upgrades, updates, patches and fixes
- Ongoing environment and database monitoring, logging & tuning
- 24 x 7 system administration support on call
- 24 x 7 support and monitoring for systems and applications
- ITIL managed operations (Service Request, Incident, Problem and Change management)
- Disaster Recovery and Backup / Restore support & services

## Support - General

Technical support for the cloud service is available as part of the customer's subscription period.

IBM Maximo Application Suite Managed Service customers receive support coverage 24 hours per day, 7 days per week, 365 days per year. This includes IBM Support Community Portal access, comprehensive backup and restore, system monitoring and patching.
24x7 emergency on-call support is available for Severity 1 or system down incidents. This is reserved for production outages where the application is unavailable or service has been severely degraded. IBM leverages an automated alert system integrated with our case ticketing system to provide timely customer response to Sev1 issues.

## Data Center Locations

Maximo Application Suite Managed Service is currently offered from the following IBM Cloud data center locations (regions).

North America:

Washington, DC, US
Dallas, TX US

Europe:

Amsterdam, Netherlands
Frankfurt, Germany

## Operations Support Locations

IBM's MAS-MS support personnel are located across the globe in the following countries:

United States
Canada
Brazil
United Kingdom
Ireland
China
India
Australia

## IBM Support Guides

An IBM Support Guide for Maximo Application Suite is available. See link below. The guide contains information such as Contact Information, Hours of Operation, Severity Level Guidelines & Response Time Objectives and Issue Escalation

https://www.ibm.com/support/home/pages/support-guide/?product=4558485

## Provisioning - Process

Important:

Customers must purchase (or own) App Points for MAS prior to (or in conjunction with) ordering the IBM Managed Service. The managed service provides IBM Cloud based hosting, product installation, operation, maintenance and support for MAS.

The provisioning process is invoked when a client has placed an order using MAS-MS part numbers. There are three (3) part numbers:

D02QTZX - Capacity
D02QUZX  - Data
D02QWZX - VPC (Virtual Processor Core)

For details, per see Part Numbers and Order consideration

Each client is provisioned in an environment that is separate and distinct from other clients.  The provisioning is done to meet the specific customer requirements for a specific order.  This means there is no pre-provisioning done and client environment provisioning begins when an order is placed. 

The provisioning process has several steps, most of them automated, but some that require a manual update(s) to complete.  The time frame to complete a new provisioning will depend on several factors including:
 
- the size of the order
- the order complexity
- the number of orders in the queue ahead of the order

In general, allow for at least 1 week for provisioning to be completed.

The provisioning itself can be broken down into a number of steps:
 
- Order validation
- Information gathering
- Initial provisioning of MAS base environment
- Provisioning of the individual MAS products the clients has requested
- Internal IBM verification of the provisioned environments
- Welcome letter sent to the client / designated contacts indicating provisioning is complete

## Provisioning - Order Validation

Once an order has been placed, the initial step is to validate the order and the information submitted.  This includes checking the part numbers, ensuring the provisioning form has been completed, performing IBM internal financial checks and setting up the order to be provisioned.  In general this can take 1 to 2 days to complete.

Once this is complete, the order is sent to the IBM MAS Managed Services Provisioning Team to begin the provisioning of the order.

## Provisioning - Information Gathering

Once the order has been placed into the provisioning queue, additional information needs to be validated and gathered.  This includes preparing the final architecture for the order; specifying the infrastructure needed to meet the order requirements; ensuring requested URL(s) are valid and available; detailed review of the order to ensure completeness; meeting or clarifying specific items with the sales person or client as required and setting up the provisioning parameters.

This step can take a few hours to several days depending on the initial quality and completeness of the information.  Critical information that is needed includes:
 
- products that to be deployed (not all products will be deployed by default).
- anticipated sizing information for each product - this can be based on users, I/O or other metrics specific to each product
- URL's being requested
- Languages required
- Add On and/or Industry Solutions required
- location of the majority of users to determine optimal placement of the Suite in the proper IBM Cloud data center

If this information is missing or incorrect it can cause delays in the provisioning process while this information is being confirmed.

## Provisioning - Initial Provisioning

The initial provisioning covers several key aspects of the Maximo Application Suite deployment.

The base architecture is finalized regarding the size and number of OpenShift clusters needed.  The provisioning of all based components and configuration is performed and the initial DNS registration for the Maximo Application Suite done.  A temporary license file is installed.  The client will need to supply the final license file (described below).

## Provisioning of the Individual Products

At this point, the products the client has selected is provisioned based on the sizing parameters that were specified.  This includes deploying the appropriate containers within OpenShift and configuring the products to be available to the client.  This includes the application, database, any network configuration required, DNS registrations and set up of client administration users. 

At this stage, all operational configuration is finalized including ensuring backups are configured properly, monitoring in place and security scans completed.  Alerting is configured and the sites added to the MAS-MS escalation process.

## Final Verification of the Provisioning

A final review of the install is done to ensure what has been deployed meets the order and the additional information gathered.  At this point, the order is marked complete.

Welcome Letter sent to the client

A welcome letter is then sent to the client which will include the URL's to access each environments, usernames and instructions on how to supply the license file the customer would have received when they purchased the Maximo Application Suite product.

The letter will contain similar instructions to below:

Some IBM products require license keys to use them. The IBM License Key Center is an online software license key delivery tool that provides easy access to your license keys 24 hours a day, 7 days a week. 

How to log in

To access your license keys:
Please click here to create your Password
Once you have created your password click on the Attempt to Login link.
Select the link to log into the License Key Center.
Select Continue to navigate to the IBM Rational License Key Center.
Log into the License Key Center using your email address as your ID and your password.
If you do not create your password and log in within 72 hours of receiving this e-mail, you will need to request a new email by clicking  here

Once the client has logged in and obtained their license key, this must be sent to the MAS MS Provisioning team who will install it in the customer instance.