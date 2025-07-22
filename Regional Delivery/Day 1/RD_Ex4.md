## Objectives

- Task 1: Microsoft Defender for Cloud Apps-Configuring Cloud Discovery
- Task 2: Discover and Analyze Shadow IT Using Cloud Discovery 

## Task 1: Microsoft Defender for Cloud Apps- Configuring Cloud App Discovery

In this task, you will integrate Defender for Cloud Apps with Microsoft Defender for Endpoint, enable discovery of shadow IT, and analyze data using snapshot reports.

1. On the **Microsoft Defender portal**, select **System (1)** and click **Settings (2)**.

   ![](./media/rd_day1_ex4_t1_3.png)

2. On the **Settings** page, click **Endpoints (2)** under the **Settings (1)** category.

   ![](./media/rd_day1_ex4_t1_4.png)

3. If prompted with a loading screen, wait for the workspace setup to complete.

   ![](./media/rd_day1_ex4_t1_5.png)

4. Under the **Endpoints** settings, select **Advanced features (1)**. Toggle **Microsoft Defender for Cloud Apps (2)** to **On**, then click **Save preferences (3)**.

   ![](./media/rd_day1_ex4_t1_6.png)

5. Go back to **Settings (1)** and select **Cloud Apps (2)** from the list.

   ![](./media/rd_day1_ex4_t1_7.png)

6. Under **Cloud Discovery**, click **Microsoft Defender for Endpoint (1)** and check the box to **Enforce app access (2)**.

   ![](./media/rd_day1_ex4_t1_8.png)

> ⚠️ Enabling app access enforcement helps automatically block apps marked as unsanctioned based on Defender for Endpoint insights.

7. Scroll down the left pane under **Cloud Discovery (1)** and select **Snapshot reports (2)**.

   ![](./media/rd_day1_ex4_t1_9.png)

8. Click on **Create snapshot report**.

   ![](./media/rd_day1_ex4_t1_10.png)

9. On the **Overview** step, click **Next** to continue.

   ![](./media/rd_day1_ex4_t1_11.png)

10. Enter a name for your report (e.g., **Test Report**) (1), choose your log source (e.g., **Blue Coat ProxySG – Access log**) (2), then click **Next (3)**.

   ![](./media/rd_day1_ex4_t1_12.png)

11. On the **Upload traffic logs** screen, click **Browse…** to upload a log file.

   ![](./media/rd_day1_ex4_t1_13.png)

12. In the file picker, select **bluecoat_sample.log (1)** and click **Open (2)**.

   ![](./media/rd_day1_ex4_t1_14.png)

13. After uploading the file, click **Upload logs**.

   ![](./media/rd_day1_ex4_t1_15.png)

14. Once the report is ready, verify the status shows **Ready**.

   ![](./media/rd_day1_ex4_t1_16.png)

15. Click the report to open and analyze discovered apps, IPs, users, and traffic risk levels.

   ![](./media/rd_day1_ex4_t1_17.png)

## Task 2: Discover and Analyze Shadow IT Using Cloud Discovery

1. Analyze the report for the following options:

    - **Check the Summary Metrics:** Look at the total number of apps, users, IP addresses, and traffic volume to understand the overall cloud usage.
    
    - **Review App Categories**: Identify which categories (e.g., Cloud Computing, Storage, Collaboration) are using the most bandwidth and check if any unsanctioned apps are involved.
    
    - **Analyze Risk Levels**: Use the risk level chart to see how much traffic is coming from low, medium, or high-risk apps—focus on medium/high risk.
    
    - **Identify Top Users**: Check the “Top entities” section to see which users are generating the most traffic, especially to risky or unsanctioned apps.
    
    - **Inspect Discovered Apps**: Review the list of apps in use, their traffic volume, and verify if they are approved or need to be blocked or reviewed further.

1. In the dashboard, navigate to **Discovered Apps** section.

   ![](./media/rd_day1_ex4_t2_1.png)

1. This section lists all discovered apps, showing their risk score, traffic volume, number of users, and last activity.

   ![](./media/rd_day1_ex4_t2_2.png)

1. Click on the elipsis next to any of the applications to mark the app as **Unsactioned**. This action labels the app as not approved for use, helping you monitor and report on its usage in the dashboard.

   ![](./media/rd_day1_ex4_t2_3.png)

## Review

1. In this exercise, you learnt how to set up Cloud Discovery and generate a snapshot report using sample logs.

1. You also learnt to analyze app usage, risk levels, and detect unsanctioned apps from the dashboard.

## Click Next to continue
