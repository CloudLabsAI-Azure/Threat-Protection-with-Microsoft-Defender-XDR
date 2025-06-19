# Threat Protection With XDR

### Overall Estimated Duration: 8 Hours

## Overview

Threat Protection with XDR is a proactive cybersecurity approach that unifies data across multiple security layers—such as endpoints, network, email, and cloud workloads—to detect, analyze, and respond to threats more effectively. XDR integrates diverse security products into a cohesive system, enhancing visibility and automating response actions across the attack surface. By correlating signals from multiple sources, XDR helps security teams to quickly identify and mitigate complex threats, reducing detection and response times while minimizing alert fatigue and improving overall security efficiency.

### Key features of Threat Protection with XDR

- Integration of Security Tools: XDR integrates multiple security tools and technologies such as endpoint security (EPP/EDR), network security, email security, cloud security, and more into a unified platform.
- Centralized Visibility and Analytics: XDR collects and aggregates data from diverse security sources, creating a comprehensive and unified view of the organization's security posture.
- Automated Threat Detection: XDR leverages its analytical capabilities to detect sophisticated threats, including zero-day exploits, malware, ransomware, phishing attacks, and other advanced threats that might evade traditional security measures.
- Contextualized Insights: XDR provides contextualized insights into detected threats, offering detailed information about the attack chain, affected systems, and the severity of the threat.
- Response and Remediation: When a threat is identified, XDR facilitates a swift response by automating threat containment, isolation, and remediation actions.

## Sandbox Scenario
Contoso is a global organization with a complex IT infrastructure that includes a combination of on-premises data centers and cloud-based resources. They are looking to enhance their security posture by deploying Azure Sentinel, Microsoft's cloud-native security information and event management (SIEM), and security orchestration automation and response (SOAR) solutions. Additionally, Contoso aims to onboard its cloud resources and servers to Azure Sentinel to gain better visibility and proactive threat detection and response capabilities.

By implementing a robust log analytics and threat detection program, Contoso aims to proactively identify and mitigate threats, reduce the risk of security breaches, and maintain a strong security posture in an ever-evolving threat landscape. This approach will enable Contoso to stay ahead of potential threats and protect its digital assets effectively.


## Objective

By the end of this lab, you will be able to:

- **Review and explore sentinel workspace** : In this hands-on exercise, you’ll review and explore a Microsoft Sentinel workspace to examine security alerts, incidents, and analytics rules. You'll also explore workbooks and hunting capabilities, gaining insights into effective threat monitoring and response.

- **Integrate Logic App with Threat Protection and XDR** : In this hands-on exercise, integrate Azure Logic Apps with Threat Protection and XDR to automate responses to security alerts. By connecting Logic Apps with XDR, you can streamline threat detection, enable automated workflows, and respond faster to incidents across endpoints, networks, and cloud environments. This integration enhances your security operations by enabling custom workflows that trigger based on XDR alerts, improving response times and efficiency.

- **Conduct attacks** : This hands-on exercise guides you through conducting attacks, providing practical experience with offensive security techniques to understand vulnerabilities and defenses.

- **Create Detections** : In this exercise, you’ll learn how to create threat detections by setting up rules and triggers to identify suspicious activity. You'll configure detection criteria, define alert actions, and test the detection’s effectiveness. This hands-on approach provides practical experience in setting up automated responses to potential threats, helping you strengthen your proactive threat protection skills.

- **Investigate an Incident** : In this hands-on exercise, you'll investigate a cybersecurity incident using tools to analyze and trace suspicious activity. You’ll assess alerts, review logs, and identify threat patterns to determine the incident's scope and impact, enhancing your skills in threat detection and response.

- **Threat Hunting using Notebooks with Microsoft Sentinel** : In this hands-on exercise, you'll use Jupyter notebooks in Microsoft Sentinel for Threat Hunting. This approach allows you to analyze data, visualize patterns, and investigate security threats efficiently by leveraging Python and machine learning to create custom queries and explore anomalies.

- **Mitigate threats using Microsoft 365 Defender** : In this hands-on exercise, you will explore how to mitigate threats using Microsoft 365 Defender. This platform integrates security features across email, endpoints, and cloud applications, providing comprehensive protection against cyber threats. You’ll learn to leverage its AI-driven analytics for threat detection and incident response. By utilizing automated remediation and continuous monitoring, you can effectively identify and respond to potential risks, enhancing your organization’s overall security posture.

## Pre-requisites

- Familiarity with Microsoft 365 Defender and its components.
- Understanding of cybersecurity principles and attack methodologies.
- Access to a Microsoft 365 tenant with appropriate licenses.

## Architecture

The architecture diagram outlines a series of labs focused on configuring and utilizing Microsoft Sentinel and Defender for threat detection and incident response. The labs begin with setting up Sentinel, onboarding devices, and connecting event sources. Users then configure security settings in Microsoft Defender, detect persistence and control attacks, and respond to incidents. Labs progress through creating playbooks, setting up hunting queries, and defining security policies. The sequence culminates with investigating alerts and managing incidents, providing comprehensive security operations training.

## Architecture Diagram

  ![](media/thread1.png)

## Explanation of Components

- **Azure Portal** : It is a web-based interface provided by Microsoft for managing and monitoring Azure resources and services. It serves as a central hub for users to create, configure, and manage their Azure resources, applications, and services.

- **Microsoft Defender Portal** : It is a security management platform that integrates various security solutions within the Microsoft ecosystem, enabling organizations to protect their environments across Microsoft 365, Azure, and other platforms. 

- **Microsoft Sentinel** : Microsoft Sentinel is a cloud-native Security Information and Event Management (SIEM) and Security Orchestration, Automation, and Response (SOAR) solution within the Azure ecosystem. It provides a comprehensive platform for intelligent security analytics, threat detection, and incident response across an organization’s infrastructure.

- **Playbooks**: Playbooks are automated workflows that respond to specific triggers, such as an incident being created. Built with Azure Logic Apps, playbooks automate actions like sending notifications, blocking IP addresses, or opening tickets, thereby streamlining incident response.

- **Incidents**: An incident is a collection of related alerts that indicate a potential threat. Sentinel groups correlated alerts into incidents, helping security teams manage, investigate, and respond to security threats efficiently.

- **Notebooks**: Microsoft Sentinel Notebooks use Jupyter notebooks, which combine code, queries, and visualizations to perform advanced threat analysis, data exploration, and investigation. They are especially useful for deep-dive analysis and threat hunting.

- **Hunting Queries**: Hunting capabilities allow analysts to proactively search for threats in their environment. By running KQL (Kusto Query Language) queries, analysts can identify anomalies, explore patterns, and investigate suspicious activities without relying solely on preconfigured alerts.
## Getting Started with the Lab

Ensure you have access to all required tools, account and carefully read each task and follow the steps in sequence. Refer to screenshots and tips provided for guidance throughout the lab.

## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.

   ![](media/labguide-1.png)

## Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.
 
## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
   ![Explore Lab Resources](media/env-1.png)
 
## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
 ![Use the Split Window Feature](media/spl.png)
 
## Managing Your Virtual Machine
 
Feel free to start, stop, or restart your virtual machine as needed from the **Resources** tab. Your experience is in your hands!
 
![Manage Your Virtual Machine](media/res.png)

## Lab Validation

1. After completing the task, hit the **Validate** button under Validation tab integrated within your lab guide. If you receive a success message, you can proceed to the next task, if not, carefully read the error message and retry the step, following the instructions in the lab guide.

   ![Inline Validation](media/inline-validation.png)

1. You can also validate the task by navigating to the **Lab Validation** tab, from the upper right corner in the lab guide section.

   ![Lab Validation](media/lab-validation.png)

1. If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com.

## Lab Duration Extension

1. To extend the duration of the lab, kindly click the **Hourglass** icon in the top right corner of the lab environment. 

    ![Manage Your Virtual Machine](media/gext.png)

    >**Note:** You will get the **Hourglass** icon when 10 minutes are remaining in the lab.

2. Click **OK** to extend your lab duration.
 
   ![Manage Your Virtual Machine](media/gext2.png)

3. If you have not extended the duration prior to when the lab is about to end, a pop-up will appear, giving you the option to extend. Click **OK** to proceed.

1. Click **"Next"** from the bottom right corner to embark on your Lab journey!

   ![Launch Azure Portal](media/next1.png)


## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on Next from the lower right corner to move on to the next page.

## Happy Learning!!


