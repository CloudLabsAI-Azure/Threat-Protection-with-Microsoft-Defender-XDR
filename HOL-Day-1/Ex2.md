# Exercise 2: Threat Investigation and Security Posture Management with Microsoft Defender

## Overview

In this exercise, you will investigate and remediate security incidents using Microsoft Defender XDR, gaining hands-on experience with incident timelines and response actions. You will also configure anti-phishing and Safe Links policies to protect users from malicious emails and links. Finally, you will implement and monitor security posture settings in Defender for Office 365 to ensure ongoing protection and compliance across your organization.

## Objectives

- Task 1: Investigate and remediate Incidents in Microsoft Defender XDR  
- Task 2: Configure Anti-Phishing and Safe Links Policies

---

## Task 1: Investigate and Remediate Incidents in Microsoft Defender XDR

In this task, you’ll investigate a phishing email, take appropriate actions, submit it to Microsoft for review, and monitor the automated investigation and alerts triggered in Microsoft Defender XDR.

### Send a Phishing Email

Use Outlook or another email client to send a test phishing message with suspicious links to your lab user.

![](./media/g25-1.png)

### Locate the Suspicious Email in Threat Explorer

Go to the [Microsoft 365 Defender Portal](https://security.microsoft.com)  
Navigate to:  
**Email & collaboration** → **Explorer**  
Find and click the suspicious message titled **Test Phishing**.

![](./media/g25-2.png)

> ⚠️ It may take 2–3 minutes after the phishing email is delivered for it to appear in Threat Explorer.

### Take Action on the Email

Click the message to view its details, then click **Take action** to initiate response actions.

![](./media/g25-3.png)

### Configure Response Actions

- Enable **Show all response actions**  
- Choose **Move to Junk**  
- Submit to Microsoft for review:
  - Select **I've confirmed it's a threat**
  - Choose **Phish** as the category  
- Enable **Initiate automated investigation**

Click **Next** to continue.

![](./media/g25-4.png)

### Choose Target Entities

Set a name like `report-phish` and confirm impacted users and actions.

![](./media/g25-5.png)

### View Triggered Alert

Navigate to:  
**Incidents & alerts** → **Alerts**  
Look for the alert titled **Administrative action submitted by an Administrator**.

![](./media/g25-6.png)

### Manage and Classify the Alert

Click the alert to open details, then click **Manage alert**.

![](./media/g25-7.png)

In the Manage alert pane:  
- Set **Status** to `In progress`  
- Assign to your lab user  
- Set **Classification** to `True positive – Phishing`  
- Click **Save**

![](./media/g25-8.png)

### View the Automated Investigation

Go to:  
**Email & collaboration** → **Investigations**  
Click on the newly triggered investigation linked to your phishing test.

![](./media/g25-9.png)

### Analyze the Investigation Graph

Review the investigation graph showing the alert path, analyzed entities, and final result.

![](./media/g25-10.png)

> ⏳ **Note:** It may take **10–15 minutes** for the automated investigation to complete and display results.

> ✅ You've successfully investigated and responded to a phishing incident using Microsoft Defender XDR.

---

## Task 2: Configure Anti-Phishing and Safe Links Policies

---

### Open Anti-Phishing Policies

Go to the [Microsoft 365 Defender Portal](https://security.microsoft.com)  
Navigate to:  
**Email & collaboration** → **Policies & rules** → **Threat policies**  
Click on **Anti-phishing** under the Policies section.

![](./media/g25-11.png)

### Create a New Anti-Phishing Policy

Click **+ Create** to start configuring a custom anti-phishing policy.

![](./media/g25-12.png)

### Name the Policy

Enter a name such as `Anti-Phish` and click **Next**.

![](./media/g25-13.png)

### Assign Users to the Policy

Add your lab user under **Users**, then click **Next**.

![](./media/g25-14.png)

### Configure Threshold and Protection

Set **Phishing email threshold** to `4 - Most Aggressive` for strict detection.  
(Other impersonation settings can be skipped for now.)

![](./media/g25-15.png)

### Enable Intelligence and Spoof Protection

Enable all recommended options under trusted senders and spoofing intelligence:  
- ✅ Enable mailbox intelligence  
- ✅ Enable impersonation intelligence  
- ✅ Enable spoof intelligence  

Click **Next** to continue.

![](./media/g25-16.png)

### Configure Message Actions

Set the following actions for detected spoofing and impersonation:
- Move impersonated messages to **Junk Email**
- Honor DMARC policies:
  - If `p=quarantine` → move to Junk
  - If `p=reject` → quarantine
  - If spoof intelligence triggers → move to Junk

Click **Next** to continue.

![](./media/g25-17.png)

### Open Safe Links Policies

Go to:  
**Email & collaboration** → **Policies & rules** → **Threat policies**  
Click on **Safe Links** under the Policies section.

![](./media/g25-18.png)

### Create a New Safe Links Policy

Click **+ Create**, name the policy (e.g., `Anti-Safe`), then click **Next**.

![](./media/g25-19.png)

### Assign Users to the Policy

Add your lab user (e.g., `ODL_User 1777538`) under **Users** and proceed.

![](./media/g25-20.png)

### Configure URL & Click Protection

Enable all recommended protection settings:
- ✅ Real-time URL scanning  
- ✅ Safe Links for email, Teams, and Office apps  
- ✅ Track user clicks  
- ✅ Wait for URL scanning before delivery  

Click **Next**.

![](./media/g25-21.png)


### Configure an Alert Policy

Go to **Email & collaboration** → **Policies & rules** → **Alert policy**.

![](./media/tbh-1-1.png)

Click **+ New Alert Policy**.

![](./media/tbh-1-2.png)

Fill in the following details:
- **Name**: `Alert-Safe`
- **Severity**: `High`
- **Category**: `Threat management`

Click **Next**.

![](./media/tbh-1-3.png)

Set the alert logic:
- **Activity**: `Detected malware in an email message`
- **Mail direction**: `Inbound`
- **Trigger**: `Every time an activity matches the rule`

Click **Next**.

![](./media/tbh-1-4.png)

Add the email recipient to get notified about the alert.

Click **Next**.

![](./media/tbh-1-5.png)

Enable the alert immediately and click **Submit** to create the policy.

![](./media/tbh-1-6.png)

---

### Simulate a Malicious Email

Send an email to the lab user with the following links:

- [https://www.amtso.org/check-desktop-phishing-page/](https://www.amtso.org/check-desktop-phishing-page/)
- [https://malware.wicar.org/data/eicar.com.txt](https://malware.wicar.org/data/eicar.com.txt)

> 🧪 These are safe test links designed to simulate phishing and malware detection.

![](./media/tbh-1-7.png)

---

### Investigate the Email in Explorer

Go to:  
**Email & collaboration** → **Explorer**  
Locate the **Test-safe** email.

![](./media/tbh-1-8.png)

Click **Open email entity** to inspect the detection and delivery information.

Check details like quarantine status and detection technologies used.

![](./media/tbh-1-9.png)

---

### Explore the Alert Incident

Navigate to:  
**Investigation & response** → **Incidents**

Open the incident titled **Alert-Link**.

![](./media/tbh-1-10.png)

> 🔍 Dive deep into the incident: review alerts, evidence, entities involved, and the automated investigation trail.

> ✅ You’ve now created an alert policy, triggered it with test emails, and followed the investigation trail using Defender XDR.

---

## Review

1. In this exercise, you learnt how to investigate and respond to security incidents using Microsoft Defender XDR.  
2. You also configured anti-phishing and Safe Links policies and monitored Defender for Office 365 to strengthen overall security posture.

## 🎉 Congratulations! You have successfully completed the Lab.
