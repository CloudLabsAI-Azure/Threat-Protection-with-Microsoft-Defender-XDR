# Exercise 1: Configuring Threat Policies and Simulating Attacks in Microsoft Defender for Office 365

## Overview

In this exercise, you will configure threat protection policies in Microsoft Defender for Office 365 and use the Attack Simulator to mimic phishing and malware attacks. You will then explore how to analyze these simulated threats using Threat Explorer and real-time detections, gaining insights into how Defender identifies, tracks, and helps mitigate threats within your Office 365 environment.

## Objectives

- Task 1: Configure Threat Policies in Microsoft Defender for Office 365 
- Task 2: Simulate Phishing and Malware Attacks Using Attack Simulator 
- Task 3: Analyze Threats with Threat Explorer and Real-Time Detections 

## Task 1: Configure Threat Policies in Microsoft Defender for Office 365

### Enable Microsoft Defender for Cloud

1. Go to the [Azure Portal](https://portal.azure.com), and search for **Microsoft Defender for Cloud**.

2. When prompted, click **Enable** to activate Defender CSPM.

   ![](./media/gg-1-1.png)  
   ![](./media/gg-1-2.png)
   > **Note:** If you don’t see the pop-up prompt, simply continue and follow the lab guide steps as shown below.

> ✅ This enables advanced posture capabilities like attack path analysis and permissions management.

---

### Enable Defender Plans and Verify Protection

1. In **Microsoft Defender for Cloud**, navigate to **Inventory** and check if **Defender for Cloud** is **Off** for any resources.

   ![](./media/gg-1-2-1.png)

2. Go to **Environment settings** > select your subscription.

   ![](./media/gg-1-3.png)

3. Under **Defender plans**, turn on:

   - Foundational CSPM  
   - Defender CSPM  
   - Servers (under CWP)  

   Then click **Save**.

   ![](./media/gg-1-4.png)

4. Return to **Inventory** and confirm Defender is now set to **On**.

   ![](./media/gg-1-5.png)

> ✅ Your Defender protection is now active for all supported workloads.

---

### Configure Threat Protection Policies

1. Open the [Microsoft 365 Defender Portal](https://security.microsoft.com)

2. Navigate to:  
   **Email & collaboration** → **Policies & rules** → **Threat policies**

   ![](./media/gg-2-1.png)

---

### Apply Standard Protection Policies

1. Select **Standard Protection**, then click **Manage protection settings**.

2. In each section, choose **Specific recipients** and assign your lab user (e.g., `ODL_User@...`).

   ![](./media/gg-2-2.png)  
   ![](./media/gg-2-3.png)

3. Select **Turn on the policy when finished**, then review and confirm the settings.

   ![](./media/gg-2-4-1.png)

> 🔐 Standard protection includes Safe Attachments, Safe Links, and anti-phishing controls.

---

### Apply Strict Protection for High-Risk Users

1. On the protection profile page, go to **Strict Protection** and click **Manage protection settings**.

   ![](./media/gg-2-6.png)

2. Like before, assign your lab user under **Specific recipients** for both Exchange and Defender for Office 365.

   ![](./media/gg-2-7.png)  
   ![](./media/gg-2-8.png)

3. Configure impersonation protection:

   - Add key email addresses to monitor  
   - Add domains (e.g., `www.officenced.com`) that need protection

   ![](./media/gg-2-3-1.png)  
   ![](./media/gg-2-3-2.png)

4. Complete the wizard and confirm the configuration.

---

### Confirm Policy Activation

1. Once setup is complete, verify that:

   - **Standard protection is on**  
   - **Strict protection is on** for selected users

   ![](./media/gg-2-11.png)

> ✅ Your threat policies are now fully configured with layered protection for both general and high-risk users.

## Task 2: Simulate Phishing and Malware Attacks Using Attack Simulator

In this task, you'll simulate phishing and malware attacks using Microsoft Defender's built-in **Attack Simulation Training**. These simulations help you evaluate user vulnerability and response to social engineering techniques.

---

### Launch a Credential Harvest Simulation

1. In [Microsoft 365 Defender Portal](https://security.microsoft.com), go to:  
   **Email & collaboration** → **Attack simulation training**

2. Click **Launch your own simulation**.

   ![](./media/gg-3-1.png)

3. Select **Launch a single simulation** and click **Continue**.

   ![](./media/gg-4-1.png)

4. On the **Select technique** screen, choose **Credential Harvest** and click **Next**.

   ![](./media/gg-4-2.png)

5. Name your simulation (e.g., `Test1`) and proceed.

   ![](./media/gg-4-3.png)

6. Select a payload such as **Expense report sharing**, then click **Next**.

   ![](./media/gg-4-4.png)

7. Add your lab user as the target recipient.

   ![](./media/gg-4-5.png)  
   ![](./media/gg-4-6.png)

8. Use default training settings:  
   - Training assignment: **Assign training for me**  
   - Due in: **7 days after simulation ends**

   ![](./media/gg-4-7.png)  
   ![](./media/gg-4-8.png)

9. Choose a landing page template and continue.

   ![](./media/gg-4-9.png)

10. Set **End-user notification** to *Microsoft default notification*.  
    Confirm:
    - Positive reinforcement: **During simulation**  
    - Training reminder: **Weekly**

    ![](./media/gg-4-10.png)

11. Launch immediately and set the simulation to end after 2 days.

    ![](./media/gg-4-11.png)

12. Review details and click **Submit** to start the simulation.

    ![](./media/gg-4-12.png)

13. After confirmation, click **Done**.

    ![](./media/gg-4-13.png)

14. You’ll see the simulation listed as **In progress**.

    ![](./media/gg-5-1.png)

> ✅ You've successfully launched a phishing simulation that will track user interaction and response.

---

### Launch a Malware Attachment Simulation

1. From the Attack simulation dashboard, launch another simulation.

2. Choose **Malware Attachment** as the technique.

   ![](./media/gg-5-2.png)

3. Name the simulation (e.g., `Test2`) and click **Next**.

   ![](./media/gg-5-3.png)

4. Select a payload like **HR notification on update of contract**.

   ![](./media/gkk-1-1.png)

5. Repeat the notification and training steps:
   - Use Microsoft defaults  
   - Deliver during simulation  
   - Weekly reminders

   ![](./media/gg-4-10.png)

6. Set simulation launch to immediate and duration to 2 days.

   ![](./media/gg-4-11.png)

7. Review the summary and submit.

   ![](./media/gg-5-6.png)

8. Confirm the simulation has been scheduled successfully.

   ![](./media/gg-5-7.png)

> 🛡️ This test mimics malware-laden email attachments and assesses user interaction with potentially harmful files.

## Task 3: Analyze Threats with Threat Explorer and Real-Time Detections

In this task, you’ll analyze the simulated phishing attack launched in Task 2. You’ll explore user interactions, examine click telemetry in Threat Explorer, and review simulation impact to assess compromise.

> ⚠️ Since this was a simulation, detailed threat data such as malware indicators or incident correlation is not available.

---

### Review Phishing Email in Outlook

Open the lab user’s mailbox and locate the email titled:

**"File inloop Expenses Report.xlsx Has Been Shared with ODL_User"**

![](./media/gp-1-1.png)

Clicking **Open** simulates a phishing link click and may trigger a credential submission event.

![](./media/gp-1-2.png)

> ✅ Interaction with this email will reflect in both the simulation report and Threat Explorer.

---

### Track Clicks in Threat Explorer

Go to **Microsoft 365 Defender Portal** →  
**Email & collaboration** → **Explorer**

![](./media/gp-1-3.png)

Use the **URL clicks** tab to filter results by recipient and timeframe.

![](./media/gp-1-4.png)

Click on the suspicious entry to review detailed telemetry.

![](./media/gp-1-4-1.png)

The full malicious URL is displayed, along with metadata and click status.

![](./media/gp-1-5.png)

> 🔍 This confirms that the user interacted with the phishing URL used in the simulation.

---

### View Simulation Report

Go to **Attack simulation training** → **Simulations**

Select the simulation titled `Test1`.

![](./media/gp-1-6.png)

The report indicates that **100% of users were compromised**, and **0% reported** the attack.

![](./media/gp-1-7.png)

> ✅ This visibility helps admins evaluate how users responded to social engineering attacks.

---

### Review User Activity

Select the compromised user from the simulation details.

![](./media/gp-2-1.png)

You’ll see all activity captured during the simulation:

- Clicked message link  
- Read message  
- Supplied credentials

![](./media/gp-2-2.png)

> 🛡️ Defender provides granular insight into user behavior during the simulated threat.

---

### Explore Message Trace and Alert Data

In **Threat Explorer**, you can also trace the attack flow:

- Email origin and delivery  
- Phishing payload  
- Policy actions applied (if any)

![](./media/gp2-3.png)  
![](./media/gp2-4.png)

To investigate further, click on related alerts or campaign details.

![](./media/gp2-5.png)

> ✅ Threat Explorer enables deep-dive analysis even for simulated campaigns.





## Review

1. In this exercise, you learnt how to configure threat policies and simulate phishing and malware attacks using Microsoft Defender for Office 365.

1. You also learnt to analyze threats in real time using Threat Explorer, helping understand how Defender detects and responds to email-based threats.

## Click Next to Continue
