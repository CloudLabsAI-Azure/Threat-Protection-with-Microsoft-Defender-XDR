# **Day-01**

# Lab 1: Configure Threat Policies in Microsoft Defender for Office 365

In this lab, you will strengthen your organization's security posture by enabling Microsoft Defender Cloud Security Posture Management (CSPM) and activating App Governance to monitor OAuth applications. You will then configure both Standard and Strict Preset Security Policies in Microsoft Defender for Office 365, applying advanced protection features—including Safe Attachments, Safe Links, and anti-phishing policies—to selected recipients. This layered approach helps safeguard users against evolving threats and ensures comprehensive email and collaboration security.

> **⚠ Important Usage Guidance:** Microsoft Defender for Office 365 may take some time to load certain results or complete specific labs from the backend. This is expected behavior. If the data does not appear after a couple of refresh attempts, proceed with the next lab and return later to check the results.

1. On a new tab in the browser, go to [https://security.microsoft.com](https://security.microsoft.com).

1. In the left pane, go to **Email & collaboration (1)** → **Policies & rules (2)** → **Threat policies (3)**.

   ![rd_day1_ex1_t1_6](./media/rd_day1_ex1_t1_6.png)

1. On the **Threat policies** page, under **Templated policies**, select **Preset Security Policies**.

   ![rd_day1_ex1_t1_6](./media/combi_g_c_1.png)

   > **Note:** If the **Learn about preset security policies** pop-up appears, click **Cancel** to close it and proceed with the lab.

1. Under **Standard Protection**, click on **Manage protection settings**.

   ![rd_day1_ex1_t1_10](./media/cord1e1_1.png)

1. On the **Apply Exchange Online Protection** screen, select **Specific recipients (1)**, enter and select **<inject key="AzureAdUserEmail"></inject>** in the **Users** field (2), and click **Next (3)**.

   ![rd_day1_ex1_t1_7](./media/rd_day1_ex1_t1_7.png)

1. On the **Apply Defender for Office 365 protection** screen, select **Specific recipients (1)**, enter and select **<inject key="AzureAdUserEmail"></inject>** in the **Users (2)** field, and click **Next (3)**.

   ![rd_day1_ex1_t1_8](./media/rd_day1_ex1_t1_8.png)

1. On the **Impersonation protection** and **Policy mode** screens, keep all settings at their default values and click **Next** until you reach the **Review** section.

1. On the **Review** screen, verify that **Exchange Online Protection (1)** and **Defender for Office 365 (2)** apply to the correct user, then click **Confirm (3)**.

   ![rd_day1_ex1_t1_9](./media/rd_day1_ex1_t1_9.png)

1. On the **Apply standard protection** confirmation screen, verify that the policy update is successful, then click **Done**.

   ![rd_day1_ex1_t1_9](./media/combi_g_c_2.png)

   > **Note:** Standard protection includes Safe Attachments, Safe Links, and anti-phishing policies.

1. Under **Strict Protection**, click **Manage protection settings**.

   ![rd_day1_ex1_t1_10](./media/rd_day1_ex1_t1_10.png)

1. On the **Apply Exchange Online Protection** screen, select **Specific recipients (1)**, enter and select **<inject key="AzureAdUserEmail"></inject>** in the **Users** field (2), and click **Next (3)**.

   ![rd_day1_ex1_t1_11](./media/rd_day1_ex1_t1_11.png)

1. On the **Apply Defender for Office 365 protection** screen, select **Specific recipients (1)**, enter and select **<inject key="AzureAdUserEmail"></inject>** in the **Users (2)** field, and click **Next (3)**.

   ![rd_day1_ex1_t1_12](./media/rd_day1_ex1_t1_12.png)

1. On the **Impersonation protection** and **Policy mode** screens, keep all settings at their default values and click **Next** until you reach the **Review** section.

1. On the **Review** screen, verify that **Exchange Online Protection (1)** and **Defender for Office 365 (2)** apply to the correct user, then click **Confirm (3)**.

   ![rd_day1_ex1_t1_12](./media/combi_g_c_3.png)

1. Once completed, confirm that:
   - **Standard protection is on (1)**
   - **Strict protection is on (2)**

        ![rd_day1_ex1_t1_15](./media/cord1e1_3.png)

      > **Note:** You have now successfully configured multi-layered threat policies for both general and high-risk users.

## Review

In this lab, you:
- Enabled Microsoft Defender CSPM to enhance cloud security posture management.
- Activated App Governance for monitoring and managing OAuth app risks.
- Configured both Standard and Strict Preset Security Policies in Microsoft Defender for Office 365.
- Applied multi-layered email and collaboration protection to specific users, ensuring robust defense against threats.

## You have successfully completed the lab. Click on Next to Continue
