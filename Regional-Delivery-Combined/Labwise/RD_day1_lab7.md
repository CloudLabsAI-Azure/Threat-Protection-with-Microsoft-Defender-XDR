## Lab 6: Microsoft Defender for Cloud Apps- Configuring Cloud App Discovery

In this task, you will integrate Defender for Cloud Apps with Microsoft Defender for Endpoint, enable discovery of shadow IT, and analyze data using snapshot reports.

1. On the **Microsoft Defender portal**, select **System (1)** and click **Settings (2)**.

   ![](./media/rd_day1_ex4_t1_3.png)

1. On the **Settings** page, click **Endpoints (2)** under the **Settings (1)** category.

   ![](./media/rd_day1_ex4_t1_4.png)

1. If prompted with a loading screen, wait for the workspace setup to complete.

   ![](./media/rd_day1_ex4_t1_5.png)

1. Under the **Endpoints** settings, select **Advanced features (1)**. Toggle **Microsoft Defender for Cloud Apps (2)** to **On**, then click **Save preferences (3)**.

   ![](./media/rd_day1_ex4_t1_6.png)

1. Go back to **Settings (1)** and select **Cloud Apps (2)** from the list.

   ![](./media/rd_day1_ex4_t1_7.png)

1. Under **Cloud Discovery**, click **Microsoft Defender for Endpoint (1)** and check the box to **Enforce app access (2)**.

   ![](./media/rd_day1_ex4_t1_8.png)
   > **Note:**  Enabling app access enforcement helps automatically block apps marked as unsanctioned based on Defender for Endpoint insights.

1. Scroll down the left pane under **Cloud Discovery (1)** and select **Snapshot reports (2)**.

   ![](./media/rd_day1_ex4_t1_9.png)

1. Click on **Create snapshot report**.

   ![](./media/rd_day1_ex4_t1_10.png)

1. On the **Overview** step, click **Next** to continue.

   ![](./media/rd_day1_ex4_t1_11.png)

1. Enter a name for your report (e.g., **Test Report**) (1), choose your log source (e.g., **Blue Coat ProxySG – Access log**) (2), then click **Next (3)**.

   ![](./media/rd_day1_ex4_t1_12.png)

1. On the **Upload traffic logs** screen, click **Browse…** to upload a log file.

   ![](./media/rd_day1_ex4_t1_13.png)

1. In the file picker, select **bluecoat_sample.log (1)** and click **Open (2)**.

   ![](./media/rd_day1_ex4_t1_14.png)

1. After uploading the file, click **Upload logs**.

   ![](./media/rd_day1_ex4_t1_15.png)

1. Once the report is ready, verify the status shows **Ready**.

   ![](./media/rd_day1_ex4_t1_16.png)

1. Click the report to open and analyze discovered apps, IPs, users, and traffic risk levels.

   ![](./media/rd_day1_ex4_t1_17.png)

## Review

In this lab, you have completed the following tasks:

- Enabled integration between Defender for Endpoint and Defender for Cloud Apps.

### You have successfully completed the lab. Click on **Next >>** to proceed with the next Lab.

![](./media/rd_gs_1_9.png)
