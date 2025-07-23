# Implement Threat Protection with Microsoft Defender XDR solutions - Day 2

### Overall Estimated Duration: 4 Hours

## Overview

In this lab, you will advance your threat protection capabilities by integrating Microsoft Defender for Cloud Apps, Microsoft Defender for Identity, Microsoft Sentinel, and Power Automate. You’ll start by connecting and onboarding SaaS applications to Defender for Cloud Apps and configuring session policies to detect and block risky user behaviors. Then, you’ll implement App Governance to identify high-risk OAuth applications and create custom detection policies for suspicious activity. You’ll deploy Defender for Identity sensors to domain controllers, simulate and detect identity-based attacks such as Pass-the-Hash and DC Sync, and analyze threat timelines. Finally, you’ll implement automated investigation and response (AIR) for identity threats and build incident response workflows using Microsoft Sentinel and Power Automate.

## Objectives

By the end of Day 2, you will be able to:

- Onboard SaaS applications and configure session policies using Microsoft Defender for Cloud Apps.
- Implement App Governance to detect high-risk OAuth apps and create custom detection policies.
- Deploy Microsoft Defender for Identity sensors and investigate identity-based threats and lateral movement attacks.
- Integrate Defender for Identity with Microsoft Defender XDR and analyze user timelines.
- Implement automated investigation and response (AIR) for identity threats.
- Build incident response workflows using Microsoft Sentinel and Power Automate.

# Getting Started with the Lab
 
Welcome to your Securing Collaboration with Microsoft Defender Solutions workshop! We've prepared a seamless environment for you to familiarize yourself with the Microsoft security operations analyst. You monitor, identify, investigate, and respond to threats in multi-cloud environments and related Microsoft services. Let's begin by making the most of this experience:
 
## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.
 
![Access Your VM and Lab Guide](./media/rd_gs_1_1.png)

### Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.
 
## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment Details** tab.
 
![Explore Lab Resources](./media/rd_gs_1_2.png)
 
## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
![Use the Split Window Feature](./media/rd_gs_1_3.png)
 
## Managing Your Virtual Machine
 
Feel free to start, stop, or restart your virtual machine as needed from the **Resources** tab. Your experience is in your hands!
 
![Manage Your Virtual Machine](./media/rd_gs_1_4.png)

## Let's Get Started with Azure Portal
 
1. On your virtual machine, click on the Azure Portal icon as shown below:
 
    ![Launch Azure Portal](./media/rd_gs_1_5.png)

1. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
     ![Enter Your Username](./media/rd_gs_1_6.png)
 
1. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](./media/rd_gs_1_7.png)

1. If you see the pop-up **Action Required**, click **Ask Later**.

    ![Action Required](./media/rd_gs_1_8.png) 
 
1. If prompted to stay signed in, you can click **No**.

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Cancel** to skip the tour.

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Cancel** to skip the tour.
 
1. Click **Next** from the bottom right corner to embark on your Lab journey!
 
     ![Start Your Azure Journey](./media/rd_gs_1_9.png)

Now you're all set to explore the powerful world of technology. Feel free to reach out if you have any questions along the way. Enjoy your workshop!

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support
