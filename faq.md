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

# FAQs
{: #faq}

1. Does MAS-MS support Java extensions?
    Answer: MAS-MS does not support Javas class extensions. It is recommended to you use automation script(s). See link below for further details.
    https://ibm-maximo-dev.github.io/maximo-autoscript-documentation/introduction/whatisautoscript/
2. Can the customer request DB2 backup for a NON-PROD or PROD environment?
    Answer: Yes, customer can request via [IBM Case ticket](https://www.ibm.com/mysupport){: external}
3. Can the customer request the MAXIMO.EAR file from their a non-prod or prod environment?
    Answer: No, this is not allowed. MAS-MS environments do not allow class file customization.
4. Does MAS-MS support Site to Site VPN?
    Answer: Yes, the request has to come through an IBM case ticket. Please keep in mind this requires the customer’s network team to collaborate with MAS-MS SRE Network team. For turnaround time please refer to [SRE Task Lead Times](/docs/mas-ms?topic=mas-ms-operations#sre-task-lead-times). Click here for details on [Site to Site VPN](/docs/mas-ms?topic=mas-ms-support#site-to-site-vpn)
5. Does MAS-MS allow connection to the database?
    Answer: Yes, but there are restrictions and guildelines. Please refer to [Database Support](/docs/mas-ms?topic=mas-ms-support#database-support)
6. Can customers access Manage log files?
    Answer: Logs files can be accessed from [IBM COS](/docs/mas-ms?topic=mas-ms-support#access-cos-buckets) (Cloud Object Storage) bucket(s) provided to individual customers for each environment.
7. Can we use the HTTP and HTTPS end points to post to applications in the Cloud?
    Answer: Yes, HTTPS only.
8. Can customers execute sql scripts that manipulate data?
    Answer: This is not allowed. If customer needs data correction, it is recommended to perform this from the front end or use automation scripts, to ensure data integrity.
9. How does Single Sign On (SSO) setup work?
    Answer: Customers can request [SSO setup](/docs/mas-ms?topic=mas-ms-support#saml-sso-config) work via [IBM Case ticket](https://www.ibm.com/mysupport){: external}
10. Can customers run dbconfig for NON_PROD and PROD?
    Answer: For NON-PROD, yes, using [API calls](/docs/mas-ms?topic=mas-ms-support#admin-util-api-calls).
11. Can customers use Manage (Maximo) MXLoader?
    Answer: Technically, IBM does not support MXLoader, but customers can use MXLoader outside of the IBM hosted SRE environment and connect to their database via the MIF (Maximo Integration Framework).
12. Does MAS-MS Manage support email, is there one provided out of the box? Can customer configure their own SMTP server?
    Answer: Yes, please refer to [SMTP Setup](/docs/mas-ms?topic=mas-ms-support#smtp-setup). If customer wants to use their own SMTP server, they can open ticket with IBM and provide details.