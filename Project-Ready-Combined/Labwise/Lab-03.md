# Lab 3: Analyze Threats with Threat Explorer and Real-Time Detections

## Overview

In this lab, you will leverage Microsoft Defender for Office 365 to investigate simulated phishing and malware scenarios using Threat Explorer and real-time detection features. You will interact with simulation emails, report suspicious messages, and analyze security events. The lab guides you through reviewing phishing and malware simulation results, investigating user actions such as credential submission and URL clicks, and assessing user risk based on simulation outcomes.

> **⚠ Important Usage Guidance:** Microsoft Defender for Office 365 may take some time to load certain results or complete specific labs from the backend. This is expected behavior. If the data does not appear after a couple of refresh attempts, proceed with the next lab and return later to check the results.

1. Open a new tab, navigate to https://outlook.office.com, sign in with the lab user’s credentials, and access the mailbox.

   > **Note:** If the **Your privacy matters** pop-up appears, click **Continue** to proceed.

   ![](./media/combi_g_c_8.png)

1. In the mailbox, select the **phishing simulation email (1)** and click the **link (2)** provided in the message body to proceed.

   ![](./media/combi_g_c_9.png)

1. On the **Sign in** page, type any random email address (1) and click **Next (2)**.

   ![](./media/combi_g_c_11.png)

1. On the **Enter password** page, type any random password (1) and click **Sign in (2)**.

   ![](./media/combi_g_c_12.png)

1. After submitting the fake credentials, the phishing simulation results page will appear indicating that you were phished. Review the message and proceed as instructed in the lab.

   ![](./media/combi_g_c_10.png)

   > Note: This activity simulates a phishing attack and triggers credential submission logs.

1. A training assignment email is also generated for users who fall for the phishing simulation. In the mailbox, open the **Training assignment notification** email and review the details.

   ![](./media/combi_g_c_13.png)

1. In the mailbox, select the malware attachment simulation email to view its contents.

   ![](./media/combi_g_c_14.png)

1. With the malware attachment simulation email open, click the **More actions (1)** menu, select **Report (2)**, and then click **Report phishing (3)**.

   ![](./media/combi_g_c_15.png)

1. In the **Report phishing** confirmation dialog, click **Report** to submit the phishing report.

   ![](./media/combi_g_c_16.png)

1. After reporting the phishing email, a confirmation message will be sent to your mailbox. Open the **Thank you for reporting a phish!** email to review the acknowledgment.

   ![](./media/combi_g_c_17.png)

1. On the **Explorer (1)** page under **Email & collaboration**, select **All email (2)** from the available filters.

   - Click on the **Top URLs (3)** tab.
   - Review the list of **URLs** that were blocked, junked, or delivered.

      ![](./media/iss-fix-3.png)

      > **Note:** Sometimes the Microsoft Defender portal can take 1–2 hours for initial backend data to load. If refreshing the page doesn’t display results, check back later.

      > **Note:** If no data appears after waiting and refreshing, skip ahead to step 14 to continue with the lab.

2. Select one of the listed URLs to open its details page.

   - Review the **Threat intelligence verdict** and **active alerts** associated with the URL.
   - Expand **Domain Details** to check the registrant and domain information.

      ![](./media/iss-fix-4.png)

1. In the **Microsoft Defender portal**, do the following:

   - Select **Email & collaboration (1)** from the left navigation pane.
   - Click **Attack simulation training (2)**.
   - Navigate to the **Simulations (3)** tab.
   - Locate and select the simulation named **Test1 (4)** from the list.

      ![](./media/rd_day1_ex2_t1_12.png)

1. View the simulation report to observe the results.  
   In this example, 100% of users were compromised and 0% reported the phishing attempt.

   ![](./media/rd_day1_ex2_t1_13.png)

1. Click the **Affected user** to view detailed actions taken during the simulation such as reading the email, clicking the link, and submitting credentials.

   ![](./media/rd_day1_ex2_t1_14.png)

   > Note: This data helps evaluate user behavior and identify high-risk individuals.

1. Navigate back to the **Simulations** tab, select the simulation named **Test2**, and view the report details for the malware attachment simulation.

## Review

In this lab, you have completed the following:

- Explored phishing and malware simulation emails in the user mailbox.  
- Reported a phishing simulation email and verified the acknowledgment response.  
- Investigated URL click events using **Threat Explorer** to review detailed security data.  
- Analyzed simulation reports to assess user actions and identify high-risk users. 

## You have successfully completed the lab. Click on Next to Continue

  ![Start Your Azure Journey](./media/rd_gs_1_9.png)
