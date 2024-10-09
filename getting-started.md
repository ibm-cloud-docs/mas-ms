---

copyright:
  years: 2015, 2020
lastupdated: "2023-07-31"

subcollection: mas-ms

content-type: tutorial
completion-time: 10m

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:attention: .attention}
{:external: target="_blank" .external}
{ :toc-completion-time="10m"}

# Getting started with IBM Maximo Application Suite Dedicated
{: #getting-started-with-ibm-maximo-application-suite-dedicated}
{: toc-content-type="tutorial"}
{: toc-completion-time="10m"}

![MAS Dedicated Site Banner](images/MAS-MS-Site-Banner.jpg "MAS-Dedicated Site Banner"){: caption=""}

On January 23rd 2024, IBM announced the end of marketing for the Maximo Application Suite Dedicated offering (this includes customers who originally purchased MAS Managed Services before it was renamed MAS Dedicated). The official announcement can be found in the link below.
{: .attention}

[End of marketing of IBM Maximo Application Suite Dedicated and IBM TRIRIGA Application Suite Managed Service - IBM Documentation](https://www.ibm.com/docs/en/announcements/mas-dedicated-tas-managed-service-saas-eom)

What does this mean for MAS Dedicated customers?

IBM updates its offering portfolio from time to time to reflect market directions and corporate strategy.  As IBM continues to focus on market driven SaaS delivery of our products, new MAS SaaS options have been released that will meet the needs of most of our MAS Dedicated customers, allowing us to consolidate these offerings.  As we move forward, IBM will be assisting customers in moving to these new SaaS offerings or advising on other alternatives if needed.

Customers on existing MAS Dedicated contracts will have them fulfilled at the current terms, conditions, and availability through the length of those contracts.   While the contract is in force, customers will be able to expand their usage to take advantage of other applications in the suite or increase their usage of currently installed applications, however, MAS Dedicated purchases will not be available to new customers.

For more information and clarification of how this announcement affects you, please refer to [this presentation](https://ibm.box.com/shared/static/upx33sinwuk7jjne3x8734j4n4qp3koq.pdf){: external download="MAS-Dedicated-EOM.pdf"} or contact your Sales Representative or Customer Success Manager.  As customers approach their contract end date, they should work with their Sales Representative and Customer Success Manager to discuss alternatives available to them, and plan for the transition.

## About
{: #about}

Maximo Application Suite Dedicated (MAS-Dedicated) provides IBM managed provisioning, installation, configuration, operational support, security, maintenance and administration of Maximo Application Suite for customers on the IBM Cloud and AWS platforms. MAS-Dedicated combines key IBM technologies: Red Hat Open Shift, IBM Cloud Pak for Data and IBM Watson - into a focused MAS services solution, allowing customers to make implementation of product functionality & features a priority.

Please note the Maximo Application Suite Managed Services was renamed MAS Dedicated in December 2022.  Client who purchased MAS Managed Services will remain on the Shared Cluster deployment option (see [Maintenance](/docs/mas-ms?topic=mas-ms-maintenance) page for details and differences between shared cluster deployment option and the dedicated cluster deployment option).  Clients on the shared cluster can contract their sales representative to discuss the upgrade to the dedicated service if needed.

## Before you begin
{: #before-you-begin}

Before you can use Maximo Application Suite Dedicated, environments must first be ordered and provisioned by the IBM MAS-Dedicated operations team. To obtain more information about the MAS-Dedicated offering and available options, please contact your IBM Salesperson or an Authorized IBM Partner. If you do not have an IBM Saleperson or Authorized reseller, please complete and submit the consultation form (link below). An IBM representative will be in contact with you.

https://www.ibm.com/products/maximo?schedulerform=

## Part Numbers and Order Considerations
{: #part-numbers-and-order-considerations}

This section details the part numbers and considerations when placing an order for Maximo Application Suite Dedicated.

Before submitting an order, the following should be considered to ensure the order is 'right sized' and will meet the requirements of the client.

Customers must purchase (or own) App Points for MAS prior to (or in conjunction with) ordering MAS Dedicated. The dedicated service provides IBM Cloud or AWS based hosting, product installation, operation and maintenance.
{: attention}

Information should be gathered about the potential usage of the suite, including which applications will be required, how many users on each application and the primary usage of the applications.

There are three (3) MAS-Dedicated part numbers:

* D02QTZX - Capacity
* D02QUZX - Data
* D02QWZX - VPC (Virtual Processor Core)

For additional information, please contact Mike Cookson:

michael.cookson@ibm.com

519-932-3511

## Welcome Letter
{: #welcome-letter}

When your MAS-Dedicated environments have been provisioned, you will receive a Welcome Letter from the IBM MAS-Dedicated Operations team. This letter will contain:

* The URLs of each environment that have been provisioned
* The username, corresponding email and password for each environment
* Information on how to activate your environment(s)
* Information on how to access your environment logs
* Information on downloading IBM Watson Studio and Watson Machine Learning (if applicable)

## How to Create an IBMid
{: #how-to-create-an-ibmid}

Note: If you already have an IBMid, please proceed to [How to Register for Maximo Application Suite Support](#how-to-register-for-mas-support)


1. To create an IBMid, click on the following link:
    https://myibm.ibm.com

2. Click **Create an IBMid**

    ![MAS-MS-IBMid-Click-Create](images/MAS-MS-IBMid-Click-Create.png "MAS-MS-IBMid-Click-Create"){: caption="Create IBMid" caption-side="bottom"}

3. Enter the applicable information (you will need to provide a valid email address) and click **Next**

    ![MAS-MS-IBMid-Enter-Applicable-Information](images/MAS-MS-IBMid-Enter-Applicable-Information.png "MAS-MS-IBMid-Enter-Applicable-Information"){: caption="IBMid - Enter Applicable Information" caption-side="bottom"}

4. Upon submission, a confirmation code will be sent from `ibmacct@iam.ibm.com` to the email address you provided

    ![MAS-MS-IBMid-Confirmation-Code](images/MAS-MS-IBMid-Confirmation-Code.png "MAS-MS-IBMid-Confirmation-Code"){: caption="MAS-Dedicated IBMid Confirmation Code" caption-side="bottom"}

5. Open your email and copy & paste the 7 digit confirmation code (Verification token).
    Click **Create Account** to activate your IBMid

    ![MAS-MS-IBMid-Confirmation-Code-Email](images/MAS-MS-IBMid-Confirmation-Code-Email.png "MAS-MS-IBMid-Confirmation-Code-Email"){: caption="MAS-Dedicated IBMid Confirmation Code Email" caption-side="bottom"}

    ![MAS-MS-IBMid-Create-Account](images/MAS-MS-IBMid-Create-Account.png "MAS-MS-IBMid-Create-Account"){: caption="MAS-Dedicated IBMid Create Account" caption-side="bottom"}

6. Accept IBM Account Privacy notification by clicking **Proceed**

    ![MAS-MS-IBMid-Privacy](images/MAS-MS-IBMid-Privacy.png "MAS-MS-IBMid-Privacy.png"){: caption="MAS-Dedicated IBMid Privacy Notification" caption-side="bottom"}

7. Your new IBMid will be created and registration completed:

    ![MAS-MS-IBMid-Ready](images/MAS-MS-IBMid-Ready.png "MAS-MS-IBMid-Ready"){: caption="MAS-Dedicated IBMid Ready" caption-side="bottom"}

    ![MAS-MS-IBMid-Activated](images/MAS-MS-IBMid-Activated.png "MAS-MS-IBMid-Activated.png"){: caption="MAS-Dedicated IBMid Activated" caption-side="bottom"}

After verification/creation of your IBMid has been completed, proceed to the next section [How to Register for MAS Support Services](#how-to-register-for-mas-support)

## How to Register for MAS Support
{: #how-to-register-for-mas-support}

Maximo Application Suite Support covers support for both the Application and your MAS-Dedicated environments.

1. Visit the following link:

    https://www.ibm.com/mysupport/s/supportaccess

2. Log in using your IBMid:

    Note: if you don't have an IBMid, please reference the following link: [How to Create an IBMid](#how-to-create-an-ibmid)

    ![MAS-MS-Register-IBMid-Login](images/MAS-MS-Register-IBMid-Login.png "MAS-MS-Register-IBMid-Login"){: caption="MAS-Dedicated Register IBMid Login" caption-side="bottom"}

3. Privacy Statement may appear. If it does, click **I consent**

    ![MAS-MS-Register-Privacy](images/MAS-MS-Register-Privacy.png "MAS-MS-Register-Privacy"){: caption="MAS-Dedicated Register Privacy" caption-side="bottom"}

4. After entering your IBMid & password, the following page will be displayed.
    Click on the Request access button:

    ![MAS-MS-Register-Request-Access](images/MAS-MS-Register-Request-Access.png "MAS-MS-Register-Request-Access"){: caption="MAS-Dedciated  Register Request Access" caption-side="bottom"}

5. The following dialog box will appear:

    ![MAS-MS-Register-Request-Access-Dialog](images/MAS-MS-Register-Request-Access-Dialog.png "MAS-MS-Register-Request-Access-Dialog.png"){: caption="MAS-Dedicated Request Access Dialog" caption-side="bottom"}

6. Be sure the I consent checkbox is checked, then type **Maximo Application Suite on Cloud** in the Product field.
    Select **Maximo Application Suite on Cloud** from the drop down list and click **Submit**

    ![MAS-MS-Register-Select-Product](images/MAS-MS-Register-Select-Product.png "MAS-MS-Register-Select-Product"){: caption="MAS-Dedicated Select Product" caption-side="bottom"}

7. If you are not already registered for Maximo Application Suite on Cloud support, the following screen will appear.
    Complete the applicable information. Ensure Client / account name is populated and click **Submit**

    ![MAS-MS-Register-Enter-Customer-Number](images/MAS-MS-Register-Enter-Customer-Number.png "MAS-MS-Register-Enter-Customer-Number"){: caption="MAS-Dedicated Enter Customer Number" caption-side="bottom"}

8. The following dialog will appear. Click **Close**

    ![MAS-MS-Register-Request-Sent](images/MAS-MS-Register-Request-Sent.png "MAS-MS-Register-Request-Sent"){: caption="MAS-Dedicated Request Sent" caption-side="bottom"}

9. An email notification will be sent confirming your request:

    ![MAS-MS-Register-Request-Sent-Confirm](images/MAS-MS-Register-Request-Sent-Confirm.png "MAS-MS-Register-Request-Sent-Confirm"){: caption="MAS-Dedicated Request Sent Confirmation" caption-side="bottom"}

    Note:
    Once you request has been submitted, please be patient. It will take some time (up to 24 hours) for IBM to review and approve your request.

    To confirm your access, login with your IBMid to the Support Access page:

    https://www.ibm.com/mysupport/s/supportaccess

    You should see your product access with a Status of ‘Approved’ under your ACCOUNT:

    ![MAS-MS-Register-Request-Approved](images/MAS-MS-Register-Request-Approved.png "MAS-MS-Register-Request-Approved"){: caption="MAS-Dedicated Request Approved" caption-side="bottom"}

    If you need support, see the next section **How to Create a Case**

## How to Create a Case
{: #how-to-create-a-case}

This section describes how to create a case for Maximo Application Suite Dedicated (MAS-Dedicated)

1. Access the IBM Support Community:

    https://www.ibm.com/mysupport

2. Click the **Open a case** button on top right of page.

3. Sign in with valid IBMid:

    Please note:  If you do not have an IBMid, or your IBMid has not been registered with a valid product and customer account, go to the following link(s):

    [How to Create An IBMid](#how-to-create-an-ibmid)

    [Register for Maximo Application Suite Support](#how-to-register-for-mas-support)

4. On the following page, populate all required (*) fields ensuring **Maximo Application Suite on Cloud** is selected for Product and click on the **Submit Case** button

5. Case Creation will be confirmed and case number referenced:

    Note: Cases are (9) digit numbers preceded with “TS”

    You will also receive an email confirming the Case #

6. Click *Back to all cases* (in the upper left hand corner) or go to https://www.ibm.com/mysupport/s/my-cases to see a full list of your cases.

## How to set password and login to MAS
{: #how-to-set-password}

You will need to set a temporary password and then change it when you first login to your MAS-Dedicated environment(s).

1. Navigate to your MAS-Dedicated login URL and enter your username (sent via Welcome Letter in the username file) and click **Continue**.

    ![MAS-MS-Password-Change-1](images/MAS-MS-Password-Change-1.png "MAS-MS-Password-Change-1"){: caption="MAS Login Screen" caption-side="bottom"}

2. Click on **Forgot password?** option in below screen.

    ![MAS-MS-Password-Change-2](images/MAS-MS-Password-Change-2.png "MAS-MS-Password-Change-2"){: caption="MAS Login Screen" caption-side="bottom"}

3. A confirmation code will be sent to your e-mail address. Enter the code contained in your email and click **Continue**

    ![MAS-MS-Password-Change-3](images/MAS-MS-Password-Change-3.png "MAS-MS-Password-Change-3"){: caption="MAS Login Code Confirmation" caption-side="bottom"}

4. The email with the confirmation code will look similar to below.

    ![MAS-MS-Password-Change-4](images/MAS-MS-Password-Change-4.png "MAS-MS-Password-Change-4"){: caption="MAS Login Code Email" caption-side="bottom"}

5. After the code is enter in the above screen with the code you received over an email, you will see below screen asking for the password. You will receive the temporary password (again via email).

    ![MAS-MS-Password-Change-5](images/MAS-MS-Password-Change-5.png "MAS-MS-Password-Change-5"){: caption="MAS Login Temp Password" caption-side="bottom"}

6. Email with the temporary password will look similar to below.

     ![MAS-MS-Password-Change-6](images/MAS-MS-Password-Change-6.png "MAS-MS-Password-Change-6"){: caption="MAS Login Temp Password email" caption-side="bottom"}

7. Enter the temporary password you received via email in the below screen and you will be able to login to MAS.

    ![MAS-MS-Password-Change-7](images/MAS-MS-Password-Change-7.png "MAS-MS-Password-Change-7"){: caption="MAS Login Temp Password" caption-side="bottom"}

8. After you login to MAS, change your password by clicking **Manage profile** under Profile in the right top hand corner.

    ![MAS-MS-Password-Change-8](images/MAS-MS-Password-Change-8.png "MAS-MS-Password-Change-8"){: caption="MAS Login Manage Profile" caption-side="bottom"}

9. Select **Change password** to change your password. Enter the temporary password and then set your new password.

    ![MAS-MS-Password-Change-9](images/MAS-MS-Password-Change-9.png "MAS-MS-Password-Change-9"){: caption="MAS Login Set Password" caption-side="bottom"}


## How to activate your environments
{: #how-to-activate-your-environments}

To complete the activation of your Maximo Application Suite Dedicated environment(s), you must first generate and download Maximo Application Suite license keys and provide them to the IBM MAS-Dedicated Operations team via case ticket. Your license keys will then be applied to your MAS-Dedicated environments to activate them. You will need to generate one (1) license key file per environment (for example one license key for PROD and one license key for TEST). IBM License Key Center login information and credentials are provided in a separate License Key Center welcome letter for your organization. You will receive separate letters for each environment.

For further information on the IBM License Key Center, see the link below:

https://www.ibm.com/support/pages/ibm-support-licensing-start-page

To acquire your license keys:
1. Locate your IBM License Key Center Welcome Letter(s)
2. Login to the [IBM License Key Center](https://licensing.subscribenet.com/control/ibmr/login) using the credentials provided in the License Key Center Welcome Letter
3. Select your company name
4. Select the IBM AppPoints product line
5. Select the IBM MAXIMO APPLICATION SUITE license key name
6. Select the product or sales order for which to create the license key
7. Enter the number of keys to generate. These correspond to the AppPoints that are allocated to the license key
8. Provide the following Maximo Application Suite license server parameters. These are provided in your welcome letter:

    | Parameter | Value (Example) |
    | -------------- | -------------- |
    | Version | IBM Maximo Application Suite App Point License |
    | Configuration | Single License Server |
    | Host ID Type | Ethernet Address (Windows, Linux, UNIX or Solaris) |
    | Host ID | 99999xxx9x99 |
    | Hostname | customerinstancename-rlks-0.rlks |
    | Port | 27000 |
    | Description | Environment Name |
    {: caption="MAS-Dedicated License Key Parameter Examples" caption-side="bottom"}

9. Download your license key(s)
10. Open a case using the IBM Support Portal and upload the license key files to IBM by clicking the following link:

    https://www.ibm.com/mysupport/s/?language=en_US

    Note: to open a case, you must have an IBMid and have registered for Maximo Application Suite Support. After IBM receives your support case and attached license key(s), your environment will be activated and the case updated.

For further information on AppPoints, see the link below:

https://www.ibm.com/docs/en/mas-cd/continuous-delivery?topic=overview-apppoints


## Next steps
{: #next-steps}

1. Specify two (2) users in your organization to be your account managers and have them created in the [Access Management Tool](/docs/mas-ms?topic=mas-ms-ssp#obtaining-access-to-am-tool) via [IBM case ticket](https://www.ibm.com/mysupport){: external}.

2. Designate member(s) of your staff to subscribe to the [Client Communications Center (CCC)](/docs/mas-ms?topic=mas-ms-client-communications-center) in order to receive important information and notifications regarding your environment(s):

    https://status.suite.maximo.com

3. Add additional users to your account, login to Maximo Application Suite, click the administration icon in the menu bar, and select Administration > Users.

4. Refer to the Reference section for further information on MAS-Dedicated operations and support, maintenance, security and the additional topics.

5. For further details on IBM Maximo Application Suite, please refer to IBM Maximo Application Suite documentation:

    https://www.ibm.com/docs/en/mas

6. To get help and support for your Maximo Application Suite Dedicated, see the IBM support guide on IBM.com:

    https://www.ibm.com/support/pages/node/733923

7. Before using your new environment, please be sure to complete the Maximo Application Suite Dedicated onboarding training for administration tasks. There is no cost for this online training. Your team can reference and retake this training as a refresher as often as needed. See link below.

    https://learn.ibm.com/course/view.php?id=16174
