## Task 1: Implement App Governance and Risk Detection for OAuth Apps

In this task, you'll create a custom policy using App Governance in Microsoft Defender for Cloud Apps to detect high-permission OAuth apps, and then verify if incidents are triggered when such apps are detected.

1. In the Microsoft Defender portal, navigate to **Cloud apps** from the left-hand menu.

2. Select **App governance** from the submenu.

3. On the **App governance** page, select the **Policies** tab.

   ![](./media/rd_day2_ex2_t1_1.png)

4. Click **+ Create policy** at the top.

   ![](./media/rd_day2_ex2_t1_2.png)

5. On the **Create a new policy** page, choose **Custom policy** under the Custom category.

6. Click **Next** to proceed.

   ![](./media/rd_day2_ex2_t1_3.png)

7. Provide the following policy details:

   - **Name**: `Detect High-Permission OAuth Apps`  
   - **Description**: Flags apps with high-risk delegated permissions and unverified publishers  
   - **Severity**: High

8. Click **Next**.

   ![](./media/rd_day2_ex2_t1_4.png)

9. When asked to use a template, select **No, I'll customize the policy**, then click **Next**.

   ![](./media/rd_day2_ex2_t1_5.png)

10. Under the **Scope** section, select **All apps** and click **Next**.

   ![](./media/rd_day2_ex2_t1_6.png)

11. In the **Conditions** page, apply the following filters:

   - **Highly privileged** = Yes  
   - **Publisher verified** = No

12. Click **Save**.

   ![](./media/rd_day2_ex2_t1_7.png)

13. On the **Set policy action** page, leave the **Disable app** checkbox **unchecked (1)**, then click **Next (2)**.

   ![](./media/rd_day2_ex2_t1_8.png)

14. On the **Set policy status** screen, select **Active (1)** and click **Next (2)**.

   ![](./media/rd_day2_ex2_t1_9.png)

15. Review the configuration and click **Submit** to create the policy.

   ![](./media/rd_day2_ex2_t1_10.png)

16. When the confirmation screen appears, click **Done**.

   ![](./media/rd_day2_ex2_t1_11.png)

17. Back on the **App governance** homepage, click **View all apps**.

   ![](./media/rd_day2_ex2_t1_12.png)

18. Select the **Microsoft 365 (1)** tab and look for apps with **High** privilege level (2).

   ![](./media/rd_day2_ex2_t1_13.png)

19. From the left-hand menu, go to **Incidents & alerts (1)** → **Incidents (2)**.

20. Locate the incident named **Detect High-Permission OAuth Apps (3)** and click on it.

   ![](./media/rd_day2_ex2_t1_14.png)

21. In the incident pane, note the alert description and involved entity, e.g., `AuditLogApp`.

   ![](./media/rd_day2_ex2_t1_15.png)

22. Expand the **Alert description** and **Incident details** sections to verify:

   - Entity Name  
   - Remediation status  
   - Verdict  
   - Incident severity  
   - Linked policy name

   ![](./media/rd_day2_ex2_t1_16.png)

23. ⚠️ **(MISSING STEP)**: Ideally, include a screenshot that shows the **Permissions**, **Activity**, and **Risk indicators** tabs for the flagged app, to complete the validation.

   > If available, please capture a screenshot of the app detail view showing risk indicators, and permissions usage.

24. ⚠️ **(MISSING STEP)**: Optionally validate the **Policy list** to ensure the created policy is listed as **Active** under **App Governance > Policies**.

   > Screenshot needed for completeness of policy validation.

25. ✅ You have now implemented a custom App Governance policy, triggered an alert, and reviewed the incident tied to risky OAuth behavior.

---

Let me know when you're ready for Task 2 of this exercise, or if you want to fill in the missing pieces, I’ll hold the space.

