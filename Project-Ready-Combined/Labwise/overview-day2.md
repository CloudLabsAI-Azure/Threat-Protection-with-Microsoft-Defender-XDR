# Hands-on Labs – Day 2

# Manage SaaS Threats and Advanced Detection with Microsoft Defender for Cloud Apps

### Estimated Duration: 4 Hours

## Overview

In this lab, you will work with Microsoft Defender for Cloud Apps to configure cloud discovery, onboard SaaS applications, and apply advanced detection policies. You will start by enabling Cloud Discovery integration with Microsoft Defender for Endpoint, uploading and analyzing snapshot reports, and identifying unsanctioned applications to address Shadow IT risks. You will then connect and onboard a Microsoft 365 SaaS app, configure Conditional Access App Control, and enable file monitoring for sensitive data protection.

Next, you will implement session policies to control risky behavior, such as blocking downloads of executable files from non-compliant devices. You will also enable App Governance to monitor OAuth applications, create custom detection policies to identify high-risk apps with unverified publishers, and investigate resulting alerts and incidents. By the end, you will have hands-on experience in detecting, analyzing, and controlling risky cloud application behavior in a Microsoft 365 environment.

## Objectives

By the end of this lab, you will be able to:

- **Enable Cloud Discovery Integration**: Connect Microsoft Defender for Endpoint with Defender for Cloud Apps to collect app usage data.
- **Analyze Shadow IT**: Review snapshot reports to identify high-risk, unsanctioned, and unapproved applications.
- **Onboard SaaS Applications**: Connect Microsoft 365 to Defender for Cloud Apps and configure Conditional Access App Control policies.
- **Enable File Monitoring**: Track and protect sensitive files in connected cloud applications.
- **Configure Session Policies**: Block risky file downloads from specific cloud apps and enforce session control.
- **Implement App Governance**: Enable governance logging, assess OAuth app permissions, and create detection policies for high-risk apps.
- **Investigate Incidents**: Review triggered policies, violations, and incidents in Microsoft Defender for Cloud Apps.

## Prerequisites

Participants should have:

- Familiarity with Microsoft 365 security and compliance capabilities.
- Understanding of Microsoft Defender for Endpoint and Defender for Cloud Apps.
- Access to the lab-provided Microsoft 365 tenant and administrative permissions.
- Basic knowledge of Conditional Access, SaaS onboarding, and security policy configuration.
- Awareness of Shadow IT risks, OAuth application security, and file governance.

## Explanation of Components

- **Microsoft Defender for Cloud Apps**: A cloud access security broker (CASB) that provides visibility, control, and protection for SaaS applications.
- **Cloud Discovery**: A feature that collects and analyzes app usage data to detect unsanctioned or high-risk apps in the organization.
- **Snapshot Reports**: Manually uploaded log files from firewalls or proxies that generate a one-time analysis of discovered apps.
- **Conditional Access App Control**: Integration with Microsoft Entra Conditional Access to control and monitor sessions for connected cloud apps.
- **File Monitoring**: Capability to track file activity, classify sensitive content, and enforce data protection policies in connected apps.
- **Session Policies**: Real-time controls applied to user sessions, such as blocking downloads or restricting access based on device compliance.
- **App Governance**: Advanced monitoring for OAuth applications to detect risky permissions, unverified publishers, and unusual activity.
- **Detection Policies**: Custom rules to automatically identify and respond to high-risk behaviors or configurations in cloud apps.

