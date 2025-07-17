## Objectives

- Task 1: Microsoft Defender for Cloud Apps-Configuring Cloud Discovery
- Task 2: Discover and Analyze Shadow IT Using Cloud Discovery 

## Task 1: Configure Cloud Discovery in Microsoft Defender for Cloud Apps

In this task, you'll enable Microsoft Defender for Cloud Apps integration, configure app access blocking, upload snapshot traffic logs, and analyze discovered apps through the Cloud Discovery dashboard.

1. On the **Microsoft Defender portal**, select **Settings (1)** from the left navigation menu and click **Cloud Apps (2)**.

   ![](./media/rd_day1_ex4_t1_3.png)

2. On the **Cloud apps** settings page, select **Microsoft Defender for Endpoint (1)** from the left panel, then check the box to **Enforce app access (2)**.

   ![](./media/rd_day1_ex4_t1_4.png)

3. In the same portal, go to **Settings > Endpoints**, then select **Advanced features (1)**. Toggle **Microsoft Defender for Cloud Apps** to **On (2)** and click **Save preferences (3)**.

   ![](./media/rd_day1_ex4_t1_3.png)

4. In the Microsoft Defender portal, under the **Cloud apps** section, click **Cloud discovery (1)** → **Snapshot reports (2)**.

   ![](./media/rd_day1_ex4_t1_4.png)

5. On the **Snapshot reports** page, click **+ Create snapshot report**.

   ![](./media/rd_day1_ex4_t1_5.png)

6. On the **Create new Cloud Discovery snapshot report** wizard, review the **Overview** tab and click **Next**.

   ![](./media/rd_day1_ex4_t1_6.png)

7. On the **Report Details** page:
   - Enter a report name (e.g., `Test Report`) **(1)**
   - From the **Source** dropdown, select **Blue Coat ProxySG - Access log (W3C)** **(2)**
   - Click **Next (3)** to proceed

   ![](./media/rd_day1_ex4_t1_7.png)

8. On the **Upload Traffic Logs** screen, click **Browse...** to select the log file.

   ![](./media/rd_day1_ex4_t1_8.png)

9. In the file picker, navigate to `C:\Lab Files`, select **bluecoat_sample.log (1)** and click **Open (2)**.

   ![](./media/rd_day1_ex4_t1_9.png)

10. Click **Upload logs** to begin uploading your traffic log.

   ![](./media/rd_day1_ex4_t1_10.png)

11. After upload, the **Snapshot reports** page displays your report with a **Ready** status once processing completes.

   ![](./media/rd_day1_ex4_t1_11.png)

12. Click on the completed report to open the **Cloud Discovery Dashboard**. Review:
   - App categories  
   - IP addresses  
   - Users and Traffic details

   ![](./media/rd_day1_ex4_t1_12.png)

13. Scroll through the dashboard to review risk levels by color-coded categories: High (red), Medium (orange), Low (yellow).

   ![](./media/rd_day1_ex4_t1_13.png)

14. Scroll further to analyze **Top users** and **Discovered apps** based on traffic volume.

   ![](./media/rd_day1_ex4_t1_14.png)

15. Under **Discovered apps**, check usage stats for apps like **Microsoft Exchange Online** and **Microsoft 365 Copilot**.

   ![](./media/rd_day1_ex4_t1_15.png)

16. Review **Discovered IP addresses** and **Discovered resources** to assess shadow IT risk.

   ![](./media/rd_day1_ex4_t1_16.png)

17. Review the **Score metric configuration** and export report if needed.

   ![](./media/rd_day1_ex4_t1_17.png)

1. Click the **IP addresses (1)** tab to view network details tied to app usage.

   ![](./media/rd_day1_ex4_t1_17.png)

> You have successfully enabled Cloud App Discovery and uploaded snapshot data for traffic analysis in Microsoft Defender for Cloud Apps.
