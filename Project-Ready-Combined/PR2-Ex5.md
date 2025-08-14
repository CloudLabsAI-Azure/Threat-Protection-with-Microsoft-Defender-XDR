# Exercise 5: Implement App Governance and Risk Detection for OAuth Apps

## Overview

In this exercise, you will enable and configure App Governance within Microsoft Defender for Cloud Apps to monitor OAuth-based third-party applications. These apps often request high-privilege delegated permissions that could lead to security or compliance risks if misused.

App Governance helps organizations:

- Detect unverified or overprivileged apps  
- Monitor risky app behavior  
- Create policies to detect and respond to potential threats

## Objectives

- Task 1: Enable App Governance in Microsoft Defender for Cloud Apps  

## Task 1: Implement App Governance and Risk Detection for OAuth Apps

In this task, you'll enable App Governance, analyze high-risk OAuth apps, and create a custom detection policy to flag suspicious apps based on permissions and publisher verification.

1. On the **Microsoft Defender portal**, go to **System (1)** > **Settings (2)** and click **Cloud Apps (3)**.

   ![](./media/rdr_xdr_1.png)

1. Under **App governance**, select **Service status (1)** and click **Turn on app governance (2)**.

   ![](./media/rdr_xdr_2.png)

   > App Governance is now activated. It will begin evaluating connected OAuth apps and generating insights into their behavior and risk posture.

1. On the OAuth apps page, click **Go to app governance**.

   ![](./media/rdr_xdr_3.png)

   > You may be redirected to the new App Governance interface.

1. In the left menu, go to **Cloud apps (1)** > **Governance log (2)** and select the **AuditLogApp (3)** from the listed apps.

   ![](./media/rdr_xdr_4.png)

1. In the AuditLogApp details pane, select the **Permissions (1)** tab and review the permissions classified as **High privilege (2)**.

   ![](./media/rdr_xdr_5.png)

   > You've now reviewed an OAuth app's access level and identified potentially risky permissions that may require action.

1. Go to the **Policies (1)** tab > select **Microsoft 365 (2)**, then click **Create policy (3)**.

   ![](./media/rdr_xdr_6.png)

1. In the **Choose a policy template** pane, select **Custom (1)** > **Custom policy (2)** and click **Next (3)**.

   ![](./media/rdr_xdr_7.png)

1. Name the policy as **Detect High-Permission OAuth Apps (1)**, set **Severity to High (2)**, and click **Next (3)**.

   ![](./media/rdr_xdr_8.png)

1. Select **No, I’ll customize the policy (1)**, then click **Next (2)**.

   ![](./media/rdr_xdr_9.png)

1. Under policy scope, select **All apps (1)** and click **Next (2)**.

    ![](./media/rdr_xdr_10.png)

1. Configure the policy conditions:  
    - Set **Highly privileged (1)** to **Yes (2)**  
    - Set **Publisher verified (3)** to **No (4)**  
    - Click **Save (5)**

    ![](./media/rdr_xdr_11.png)

1. In the **Set policy action** step, choose **Disable app (1)** and click **Next (2)**.

    ![](./media/rdr_xdr_12.png)

1. Set the policy status to **Active (1)** and click **Next (2)**.

    ![](./media/rdr_xdr_13.png)

1. Review the policy settings and click **Submit** to create the policy.

    ![](./media/rdr_xdr_14.png)

1. On the confirmation screen, click **Done** to finish.

    ![](./media/rdr_xdr_15.png)
   
   > The detection policy is now active and will monitor all onboarded OAuth apps for risky permissions and unverified publishers.

1. Back on the **App governance** overview, click **View all apps** to analyze detected apps.

    ![](./media/rdr_xdr_16.png)

1. In the **Microsoft 365 (1)** tab, notice apps flagged with a **High (2)** privilege level.

    ![](./media/rdr_xdr_17.png)

1. Go to **Incidents & alerts (1)** > **Incidents (2)**, and click the incident **Detect High-Permission OAuth Apps (3)**.

    ![](./media/rdr_xdr_18.png)

1. In the incident details pane, review the violation summary, app, and policy triggered.

    ![](./media/rdr_xdr_19.png)


## Review

In this exercise:

  - You enabled App Governance in Microsoft Defender for Cloud Apps.  
  - You analyzed permissions of onboarded OAuth apps.  
  - You created and activated a custom detection policy.  
  - You reviewed policy results and investigated generated incidents.

## Congratulations you have successfully completed the lab
