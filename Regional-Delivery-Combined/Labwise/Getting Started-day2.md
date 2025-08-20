# Hands-on Labs – Day 02
## Implement Threat Protection with Microsoft Defender XDR solutions

## Overview

In this lab, you will advance your threat protection capabilities by integrating Microsoft Defender for Cloud Apps, Microsoft Defender for Identity, Microsoft Sentinel, and Power Automate. You’ll start by connecting and onboarding SaaS applications to Defender for Cloud Apps and configuring session policies to detect and block risky user behaviors. Then, you’ll implement App Governance to identify high-risk OAuth applications and create custom detection policies for suspicious activity. You’ll deploy Defender for Identity sensors to domain controllers, simulate and detect identity-based attacks such as Pass-the-Hash and DC Sync, and analyze threat timelines. Finally, you’ll implement automated investigation and response (AIR) for identity threats and build incident response workflows using Microsoft Sentinel and Power Automate.

## Objectives

- Onboard SaaS applications and configure session policies using Microsoft Defender for Cloud Apps.
- Implement App Governance to detect high-risk OAuth apps and create custom detection policies.
- Deploy Microsoft Defender for Identity sensors and investigate identity-based threats and lateral movement attacks.
- Integrate Defender for Identity with Microsoft Defender XDR and analyze user timelines.
- Implement automated investigation and response (AIR) for identity threats.
- Build incident response workflows using Microsoft Sentinel and Power Automate.

## Prerequisites

Participants should have:

- Familiarity with Microsoft 365 security and compliance capabilities.
- Understanding of Microsoft Defender for Endpoint and Defender for Cloud Apps.
- Access to the lab-provided Microsoft 365 tenant and administrative permissions.
- Basic knowledge of Conditional Access, SaaS onboarding, and security policy configuration.
- Awareness of Shadow IT risks, OAuth application security, and file governance.
- Basic knowledge of KQL, incident management, and security policy configuration.
- Awareness of attack techniques, threat hunting, and incident response.

## Explanation of Components

* **Microsoft Defender for Cloud Apps**: A cloud access security broker (CASB) that provides visibility, control, and protection for SaaS applications.
* **Cloud Discovery**: A feature that collects and analyzes app usage data to detect unsanctioned or high-risk apps in the organization.
* **Snapshot Reports**: Manually uploaded log files from firewalls or proxies that generate a one-time analysis of discovered apps.
* **Conditional Access App Control**: Integration with Microsoft Entra Conditional Access to control and monitor sessions for connected cloud apps.
* **File Monitoring**: Capability to track file activity, classify sensitive content, and enforce data protection policies in connected apps.
* **Session Policies**: Real-time controls applied to user sessions, such as blocking downloads or restricting access based on device compliance.
* **App Governance**: Advanced monitoring for OAuth applications to detect risky permissions, unverified publishers, and unusual activity.
* **Detection Policies**: Custom rules to automatically identify and respond to high-risk behaviors or configurations in cloud apps.
* **Microsoft Defender XDR**: An integrated security suite for detecting, investigating, and responding to threats across endpoints, identities, email, and cloud apps.
* **Microsoft Sentinel**: A cloud-native SIEM and SOAR solution for proactive threat detection, hunting, and automated response.
* **Attack Simulation**: Hands-on steps to simulate persistence (registry modification) and command-and-control (DNS queries) attacks.
* **Analytics Rules**: Custom rules in Sentinel to detect suspicious activity and generate incidents.
* **Threat Hunting**: Building and running KQL queries to proactively search for threats and bookmark notable findings.
* **Incident Investigation**: Reviewing incidents, mapping entities, and analyzing evidence in Defender and Sentinel.
* **Mitigation**: Managing incidents and alerts, applying security recommendations, and restoring data for deeper analysis.

Now, click on **Next** from the lower right corner to move on to the next page.
 
  ![Start Your Azure Journey](../media/rd_gs_1_9.png)

### Happy learning!
