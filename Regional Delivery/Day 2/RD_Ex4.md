### Task 2: Create a SharePoint Site and List to Log Incident Details

In this task, you'll create a SharePoint communication site named `Incident_Logs` and set up a list called `Powershell_Logs_list`. This list will be used to log incident details such as flagged emails via Power Automate.

1. On the **SharePoint home page**, click **Create site** from the top menu **(1)**.

   ![](./media/sp_gg_e4_1.png)

1. On the **Select the site type** screen, choose **Communication site** **(2)**.

   ![](./media/sp_gg_e4_2.png)

1. Under **Select a template**, click **Standard communication** **(3)**.

   ![](./media/sp_gg_e4_3.png)

1. On the template preview screen, click **Use template** **(4)**.

   ![](./media/sp_gg_e4_4.png)

1. Enter **Incident_Logs** as the **Site name** **(1)**, then click **Next** **(2)**.

   ![](./media/sp_gg_e4_5.png)

1. On the **Set language and other options** screen, keep the default language as **English** **(1)** and click **Create site** **(2)**.

   ![](./media/sp_gg_e4_6.png)

1. After the site is created, click **New (1)** and select **List (2)** from the dropdown to begin creating a custom list.

   ![](./media/sp_gg_e4_7.png)

1. In the **How would you like to start?** dialog, select **List** under **Create from blank**.

   ![](./media/sp_gg_e4_8.png)

1. Name the list as **Powershell_Logs_list** **(1)** and click **Create** **(2)**.

   ![](./media/sp_gg_e4_9.png)

1. On the newly created list page, click **+ Add column** to begin adding custom fields to the list.

   ![](./media/sp_gg_e4_10.png)

1. In the **Create a column** pane, choose **Text** as the column type **(1)** and click **Next** **(2)**.

   ![](./media/sp_gg_e4_11.png)

1. Enter **Flagged by** as the column name **(1)** and click **Save** **(2)**.

   ![](./media/sp_gg_e4_12.png)

1. Repeat the previous steps to add the following columns:

    - **Email Body** (Text)
    - **Message ID** (Text)
    - **Flagged Date** (Date and time)
    - **Email URL** (Hyperlink)

   ![](./media/sp_gg_e4_13.png)

