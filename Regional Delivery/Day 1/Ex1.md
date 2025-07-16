## Exercise 1: Configure Threat Policies in Microsoft Defender for Office 365

### Task 1: Enable Defender CSPM and Configure Threat Policies

In this task, you will enable Microsoft Defender CSPM for your environment and configure standard and strict threat protection policies using Microsoft Defender XDR.

1. On the **Azure Portal** home page, search for **Microsoft Defender for Cloud (1)** and select it from the **results (2)**.

   ![rd_day1_ex1_t1_1](./media/rd_day1_ex1_t1_1.png)

3. In the **Enhance your security posture by enabling Defender CSPM** dialog, click **Enable** to activate the Defender CSPM plan.

   ![rd_day1_ex1_t1_2](./media/rd_day1_ex1_t1_2.png)

5. On the **Microsoft Defender for Cloud | Inventory** blade, select **Inventory (2)** under **General (1)** and confirm the Defender status is **Off (3)** for listed resources.
 
   ![rd_day1_ex1_t1_3](./media/rd_day1_ex1_t1_3.png)

7. In the **Management (1)** section, select **Environment settings (2)**. Expand **Azure (3)** > **Tenant Root Group (4)** and select the **subscription (5)**.

   ![rd_day1_ex1_t1_4](./media/rd_day1_ex1_t1_4.png)

9. Under **Settings**, select **Defender plans (1)**. Turn on **Foundational CSPM (2)**, **Defender CSPM (3)**, and **Servers under Cloud Workload Protection (4)**. Click **Save (5)**.
 
   ![rd_day1_ex1_t1_5](./media/rd_day1_ex1_t1_5.png)

11. In the Microsoft Defender portal, expand **Email & collaboration (1)**, then go to **Policies & rules (2)**, and click **Threat policies (3)**.
  
   ![rd_day1_ex1_t1_6](./media/rd_day1_ex1_t1_6.png)

13. In the **Apply standard protection** wizard, select **Specific recipients (1)** and enter the user email (2). Click **Next (3)**.
  
   ![rd_day1_ex1_t1_7](./media/rd_day1_ex1_t1_7.png)

15. On the **Defender for Office 365 protection** tab, again select **Specific recipients (1)**, provide the user (2), and click **Next (3)**.
  
   ![rd_day1_ex1_t1_8](./media/rd_day1_ex1_t1_8.png)

17. On the **Review** screen, verify Exchange Online and Defender for Office 365 policies are applied to the correct user. Click **Confirm (3)**.
  
   ![rd_day1_ex1_t1_9](./media/rd_day1_ex1_t1_9.png)

19. On the protection profiles page, click **Manage protection settings** under **Standard protection**.
  
    ![rd_day1_ex1_t1_10](./media/rd_day1_ex1_t1_10.png)

21. In the **Apply strict protection** wizard, select **Specific recipients (1)**, enter the user (2), and click **Next (3)**.
  
    ![rd_day1_ex1_t1_11](./media/rd_day1_ex1_t1_11.png)

23. Under **Defender for Office 365 protection**, confirm **Specific recipients (1)** is selected, user is added (2), and click **Next (3)**.
  
    ![rd_day1_ex1_t1_12](./media/rd_day1_ex1_t1_12.png)

25. On the **Impersonation protection** screen, add an external email address (1)(2), click **Add (3)**, and then click **Next (4)**.
  
    ![rd_day1_ex1_t1_13](./media/rd_day1_ex1_t1_13.png)

27. Add a domain to be flagged for impersonation detection (1), click **Add (2)**, and proceed by clicking **Next (3)**.

    ![rd_day1_ex1_t1_14](./media/rd_day1_ex1_t1_14.png)

29. Confirm that **Standard protection is on** and **Strict protection is on** as shown.
 
    ![rd_day1_ex1_t1_15](./media/rd_day1_ex1_t1_15.png)
