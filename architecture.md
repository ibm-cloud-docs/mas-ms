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

# Architecture
{: #architecture}

## Cloud Architecture
{: #cloud-architecture}

Maximo Application Suite (MAS) is a feature rich suite of applications delivered using key IBM and Red Hat technologies. The MAS Dedicated Service delivers this functionality on the IBM Cloud platform.

IBM Cloud - YouTube Videos

Inside the heart of an IBM Cloud Data Center:

https://www.youtube.com/watch?v=HkIJTyjE4zo

Do you have a cloud designed for data?

https://www.youtube.com/watch?v=TrbQbM_xtBw

Further information on IBM Cloud Data Centers:

https://www.ibm.com/cloud/data-centers

## Network Architecture
{: #network-architecture}

IBM Cloud has a unique Triple Network architecture.  Every server provisioned in the IBM Cloud has 3 distinct networks:

* Public Network: Two network interfaces are dedicated to the public network.  This network serves as the internet facing network for the server.  IBM MAS-Dedicated uses this network as the way for external clients to access the application. This network is also secured by a firewall pair managed by the IBM SRE team.

* Private Network: Two network interfaces are dedicated to the private network.  This network serves as a secure private network dedicated to IBM Cloud.  IBM Cloud uses this network for secure server to server communication as well as data center to data center communications.  This network has no access to the internet.

* Management Network: One network interface is dedicated to the Management network.  This secure out-of-band network is accessible via an IBM managed VPN.  It is used by IBM Cloud staff for maintenance and administration purposes such as firmware updates, OS reloads, power-cycle or other IPMI functions like keyboard, video, mouse control (KVM over IP).

For the MAS Dedicated Service each client is provisioned with their own application instance and dedicated namespace(s).  The IBM MAS-Dedicated team will provision and configure all necessary underlying infrastructure and components.

IBM Cloud Data Centers are SOC compliant and have full hardware redundancy implemented for all servers. All data centers have an N1 redundant power and cooling infrastructure, including backup power generators. All servers have redundant power supplies, NICs and use SAN based RAID storage.

The following diagrams show a high level overview of the architecture for each individual client instance.

![MAS-Dedicated Shared Architecture](images/MAS-Dedicated-Shared-Cluster.png "MAS-Dedicated Shared Architecture"){: caption="MAS-Dedicated / MS Shared Cluster Architecture on IBM CLoud" caption-side="bottom"}

![MAS-Dedicated Non-Shared Architecture](images/MAS-Dedicated-Non-Shared-Cluster.png "MAS-Dedicated Non-Shared Architecture"){: caption="MAS-Dedicated / MS Non-Shared Cluster Architecture on IBM CLoud" caption-side="bottom"}

## MAS-Dedicated Architecture Highlights
{: #mas-dedicated-highlights}

* MAS MS customers are required to have two (2) environments provisioned by default: (1) PROD and (1) NON-PROD
* All clients will be provisioned in their own application instance using dedicated namespace(s)
* IT Administration for the PROD and NON-PROD environments is solely managed by IBM's MAS-Dedicated operations team
* Clients can access PROD and NON-PROD systems via browser based URL
* MAS-Dedicated is an internet based offering that runs over HTTPS. There is no private cloud or direct connect option for MAS-Dedicated
* Clients are provided application administrator access for all applications ordered
* All servers are Red Hat Linux O/S
* Maximo Manage databases are IBM DB2. Oracle and MS SQLServer are not supported.

## MAS-Dedicated Monitoring
{: #mas-dedicated-monitoring}

Monitoring tasks performed

IBM SRE carries out the following types of monitoring to evaluate the health status of our MAS on cloud production instances and set up proactive alerts and notifications for timely identification and response to critical issues.

System and infrastructure monitoring
* Use of Instana and OpenShift storage metrics through Prometheus. Monitor the entire Kubernetes Eco-System from Nodes and Pods to Containers and Applications - for ALL K8s Distributions. This type of monitoring ensures that the infrastructure supporting our application is stable and operating optimally.

Application monitoring
* Instana APM and custom metrics exposed through Prometheus helps monitor and analyze the performance and behavior of our application in real time. Monitor logs using LogDNA in real time to troubleshoot issues and obtain insights into application.

Synthetic monitoring
* Performs availability checks on customer site URLs for each individual Application of MAS - core, manage, health, predict, monitor, MVI, and IoT.

These monitoring tasks enable IBM SRE to proactively identify issues, perfrom efficient troubleshooting, and continuously optimize our infrastructure to ensure the smooth operation of
MAS on the cloud.

## MAS-Dedicated Integrations
{: #mas-dedicated-integrations}

IBM Maximo Application Suite Dedicated Service supports integration to / from external systems. There are different options available to provide secure integration connections such as SSL, VPN, and Cloud Object Storage integration. HTTPS (SSL) is the standard encryption method and is supported for XML based interfaces using HTTP Post and Web Service endpoints. In addition, the REST API is available over HTTPS. All these integration methods can also be implemented with authentication. Cloud Object Storage is available for integrations that require file based transfers. A Site-to-Site IPsec VPN Tunnel can also be established between the client network and the IBM cloud environment using IBM's firewall in order to support other integration transport methods.

 Integration options include, but are not limited to:

* Support for synchronous and asynchronous exchange of data with applications within the Suite
* Use of common protocols and format such as Web Services, HTTP, JMS, REST, OSLC, XML, JSON, XML and .csv files, DB tables
* Support of Create, Replace, Update, Delete and Query operation
* Support for customizing integration processing using Processing Rules and Scripting

For the MS-Manage Application:

* Maximo integration message generation and delivery based on application object events
* Support for implementation (batch) data loading
* Pre-defined (75+) interface components provided along with applications to configure new interfaces
* Support for customizing integration processing using Processing Rules and Scripting

For file based integrations, an AWS S3 Cloud Object Storage location will be allocated for each order. **One API Key** will be generated for the client to use to move files in and out of the location. Additional keys can be ordered. To initiate this process, customers must work with salesrep in placing the order.

One Site-to-Site VPN is included in the order.  To initiate the creation of this VPN, customers must submit a support case.  At this time, the VPN is only available for LDAP integrations.

For clients wanting to use App Connect or File integration for other applications within the suite:

- AppConnect is included as an entitlement with the Maximo Application Suite, but the Dedicated Service does not implement or support this within the MAS-Dedicated environment.  The client is responsible for implementing AppConnect or beginning with version MAS v8.7, AppConnect SaaS will be supported.

- For clients wanting file integrations with applications other than Manage, this needs to be discussed with the Sales team and an appropriate solution implemented.  COS is only included for the Manage application in the Dedicated Service.

## MAS-Dedicated Bundles
{: #mas-dedicated-bundles}

The following table shows the distribution of workload across worker nodes.  This is based on the T-Shirt sizes on the [Maximo Application Suite Dedicated T-Shirt Calculator v6](https://ibm.box.com/shared/static/aydqzy5in7coc0995vfcctyhg55ic4ar.xlsm){: external download="MAS-Dedicated-Tshirt-Calculator-v6.xls"} and will be the setup based on the selected size of the sites. For Development and Extra Small, all workloads (UI, MIF, RPT, CRON) go through the same (2) base worker nodes. For Small, Medium and Large, the workloads are distributed through specific worker nodes as per the below table. If a client needs a different configuration, please contact your sales representative.

| T-Shirt Size | Max Concurrent Users | Base | UI | MIF | RPT | CRON | VPC on Order |
| ------------ | -------------------- | ---- | -- | --- | --- | ---- | ------------ |
| Development | | 2 | | | | | 4 |
| Extra Small | 50 | 2 | | | | | 4 |
| Small | 100 | | 2 | 1 | 1 | 1 | 8 |
| Medium | 250 | | 6 | 2 | 2 | 1 | 24 |
| Large | 500 | | 12 | 3 | 2 | 2 | 48 |
{: caption="MAS-Dedicated Bundles" caption-side="bottom"}
