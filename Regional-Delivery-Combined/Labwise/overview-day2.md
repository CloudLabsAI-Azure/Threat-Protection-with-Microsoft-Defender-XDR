# Hands-on Labs – Day 02

## Manage SaaS Threats and Identity Protection with Microsoft Defender XDR

### Estimated Duration: 4 Hours

## Overview

In this lab, you will extend Microsoft Defender XDR capabilities to protect against SaaS application threats, identity-based attacks, and advanced adversary techniques. You will begin by connecting and onboarding a Microsoft 365 SaaS application to Microsoft Defender for Cloud Apps, enabling auditing, session control, and file monitoring. You will then configure session policies to block risky behaviors such as downloading executable files from non-compliant devices.

Next, you will enable App Governance to assess OAuth applications, create custom detection policies to flag high-privilege apps with unverified publishers, and investigate resulting incidents. You will also work with activity logs and alert investigations to create custom detection policies for suspicious file downloads. Moving deeper into identity protection, you will deploy Microsoft Defender for Identity sensors on domain controllers, simulate lateral movement attacks using Mimikatz, and review alerts and containment actions triggered by Defender. Finally, you will integrate Defender for Identity with Microsoft Sentinel, review Automated Investigation and Response (AIR) capabilities, and automate threat response using Power Automate and Sentinel playbooks.

## Objective

In **Day-2** of this workshop you will learn how to:

- Connect and Onboard a SaaS App to Microsoft Defender for Cloud Apps  
- Configure Session Policies to Monitor and Block Risky Behavior  
- Implement App Governance and Risk Detection for OAuth Apps  
- Investigate Alerts and Create Custom Detection Policies  
- Deploy Microsoft Defender for Identity Sensor on Domain Controllers  
- Simulate and Detect Lateral Movement Attacks  
- Investigate Identity-Based Threats and User Timelines  
- Integrate Defender for Identity with Microsoft 365 Defender Portal  
- Review Automated Investigation and Response (AIR) for Identity Threats  
- Automate Response with Power Automate and Microsoft Sentinel  

## Prerequisites

Participants should have:

- Familiarity with Microsoft 365 security services and identity protection concepts.  
- Understanding of Microsoft Defender for Cloud Apps, Defender for Identity, and Sentinel.  
- Access to the lab-provided Microsoft 365 tenant, Azure portal, and domain controller VM.  
- Basic knowledge of OAuth application security, lateral movement attacks, and automation workflows.  
- Awareness of Conditional Access, App Governance, and Power Automate integrations.  

## Explanation of Components

- **Microsoft Defender for Cloud Apps**: Provides visibility, control, and threat protection for SaaS applications with session policies, discovery, and app governance.  
- **Conditional Access App Control**: Extends Microsoft Entra Conditional Access to monitor and control user sessions in SaaS apps in real time.  
- **App Governance**: Detects risky OAuth apps by analyzing permissions, publishers, and unusual activity.  
- **Detection Policies**: Custom rules that identify high-risk behaviors such as unauthorized file downloads or malicious app activity.  
- **Microsoft Defender for Identity**: Monitors Active Directory domain controllers to detect suspicious activity and lateral movement techniques.  
- **Lateral Movement Simulation**: Use of tools like Mimikatz to simulate credential theft and observe automated containment by Defender.  
- **User Timelines**: Unified view of user activity and associated alerts for investigating identity-based threats.  
- **Microsoft Sentinel Integration**: Centralizes visibility by ingesting Defender for Identity and Defender XDR alerts into Sentinel for advanced investigation.  
- **Automated Investigation and Response (AIR)**: Pre-configured workflows that remediate threats automatically at the identity and device level.  
- **Power Automate and Sentinel Playbooks**: Low-code automation tools to log, notify, and respond to security incidents in real time.  

Now, click on **Next** from the lower right corner to move on to the first lab.  

![Start Your Azure Journey](../media/rd_gs_1_9.png)

### Happy learning!
