## Task 4: Configure Anti-Phishing and Safe Links Policies

### Estimated Duration: 30 Minutes

## Overview

In this task, you will create a custom Anti-Phishing policy and Safe Links policy to enhance protection against malicious emails and phishing links. You will also simulate a phishing email and verify alerts and detections.

1. On the **Microsoft Defender portal**, go to **Email & collaboration (1)** > **Policies & rules (2)** and selct **Threat Policies**. Under **Policies**, select **Anti-phishing (3)**.

   ![](./media/rd_day1_ex2_t2_1.png)

1. On the **Anti-phishing** page, click **Create (1)** to begin a new policy.

   ![](./media/rd_day1_ex2_t2_2.png)

1. Enter the name **Anti-Phish (1)** and click **Next (2)**.

   ![](./media/rd_day1_ex2_t2_3.png)

1. Under **Users, groups, and domains**, add the user **ODL User (1)** and click **Next (2)**.

   ![](./media/rd_day1_ex2_t2_4.png)

1. Set the **Phishing email threshold** to **4 - Most Aggressive** to enable maximum protection.

   ![](./media/rd_day1_ex2_t2_5.png)

1. Under **Trusted senders and domains**, check the following options:

    - **Enable mailbox intelligence (1)**
    - **Enable Intelligence for impersonation protection (2)**
    - **Enable spoof intelligence (3)**  
    - Then click **Next (4)**. 
     
      ![](./media/rd_day1_ex2_t2_6.png)

1. Under **Message actions**, configure the following and click **Next (5)**.

   - If Mailbox Intelligence detects an impersonated user:  
     **Move the message to the recipients’ Junk Email folders (1)**
   - For spoof messages with DMARC policy = quarantine:  
     **Move to Junk Email (2)**
   - For spoof messages with DMARC policy = reject:  
     **Quarantine the message (3)**
   - For spoof detection by spoof intelligence:  
     **Move to Junk Email (4)**  

      ![](./media/rd_day1_ex2_t2_7.png)

1. Back on the **Threat policies** page, go to **Email & collaboration (1)** > **Policies & rules (2)**, then select **Safe Links (3)**.

   ![](./media/rd_day1_ex2_t2_8.png)

1. Enter the policy name **Anti-Safe (1)** and click **Next (2)**.

   ![](./media/rd_day1_ex2_t2_9.png)

1. Under **Users and domains**, add the user **ODL_User (1)** and click **Next (2)**.

    ![](./media/rd_day1_ex2_t2_10.png)

1. In **URL & click protection settings**, ensure all checkboxes are enabled, including:

    - Email Safe Links
    - URL scanning
    - Teams and Office 365 apps protection
    - Click tracking  

    Then click **Next**.

    ![](./media/rd_day1_ex2_t2_11.png)

1. Navigate to **Email & collaboration (1)** > **Policies & rules (2)** > **Alert policy (3)**.

    ![](./media/rd_day1_ex2_t2_12.png)

1. On the **Alert policy** page, click **+ New Alert Policy**.

    ![](./media/rd_day1_ex2_t2_13.png)

1. Enter the following details:
    
    - **Name (1):** Alert-Safe  
    - **Severity (2):** High  
    - **Category (3):** Threat management  
      
      Click **Next (4)**.

      ![](./media/rd_day1_ex2_t2_14.png)

1. For the activity condition, configure the following and click **Next (4)**.

    - **Activity (1):** Detected malware in an email message  
    - **Mail direction (2):** Inbound  
    - **Trigger (3):** Every time an activity matches the rule  

      ![](./media/rd_day1_ex2_t2_15.png)

1. Add the recipient's email address **(1)** and click **Next (2)**.

    ![](./media/rd_day1_ex2_t2_16.png)

1. Review the alert settings, choose **Yes, turn it on right away (1)**, and click **Submit (2)**.

    ![](./media/rd_day1_ex2_t2_17.png)

   > **Note:** Your alert policy is now active and will trigger if matching activity is detected.

1. Send a test email with sample malicious links to simulate a threat:
    
    - **(1)** https://www.amtso.org/check-desktop-phishing-page/  
    - **(2)** https://malware.wicar.org/data/eicar.com.txt  
    - Click **Send (3)** to deliver the email.

      ![](./media/rd_day1_ex2_t2_18.png)

1. Navigate to **Email & collaboration (1)** > **Explorer (2)** and locate the test email **Test-safe (3)**.

   ![](./media/rd_day1_ex2_t2_19.png)

1. Click **Open email entity (1)** and verify that:
    
   - **Original location:** Quarantine  
   - **Delivery action:** Blocked  
   - **Detection technologies:** URL malicious reputation, Mixed analysis detection  

      ![](./media/rd_day1_ex2_t2_20.png)

1. Finally, go to **Investigation & response (1)** > **Incidents (2)**. Select the alert incident **Alert-Link (3)** and click on the incident name **(4)** to investigate further.

   ![](./media/rd_day1_ex2_t2_21.png)

   >  Dive deep into the incident: review alerts, evidence, entities involved, and the automated investigation trail.

   >  You’ve now created an alert policy, triggered it with test emails, and followed the investigation trail using Defender XDR.

## Review

In this lab, you have completed the following tasks:

- Configured custom Anti-Phishing and Safe Links policies to enhance threat protection.
- Created an alert policy and validated it by simulating a phishing and malware email.

### You have successfully completed the lab. Click on **Next >>** to proceed with the next Lab.

![](./media/rd_gs_1_9.png)
