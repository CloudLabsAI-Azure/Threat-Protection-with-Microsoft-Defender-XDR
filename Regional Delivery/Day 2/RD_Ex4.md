### Task 1: Create a SharePoint Site and List to Log Incident Details

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

## Task 2: Create a Microsoft Sentinel Playbook to Notify SOC

In this task, you will create a Sentinel playbook named **Notify-SOC-OnPowerShellIncident** using Logic Apps. The playbook will trigger from a Sentinel incident and send an email to the SOC team containing dynamic incident details such as title, severity, status, and more.

1. On the **Add an action** pane in Logic App designer, search for **Send an email (V2)** in the search box **(1)**. From the **Office 365 Outlook** connector, click **Send an email (V2) (2)**.<br>
   ![](./media/a_gg_ex4_1.png)

1. In the **Send an email (V2)** configuration pane:
    - In the **To** field, enter the ODL user email (e.g., `odl_user_xxx@otuwa...onmicrosoft.com`) **(1)**.
    - In the **Subject** field, enter:  
      ```
      [Sentinel] Incident: <Incident Title> - Severity: <Severity>
      ```
      **(2)**<br>
   ![](./media/a_gg_ex4_2.png)

1. Select the placeholder text **<Incident Title> (1)** in the **Subject** field and click the **dynamic content icon (2)** to open available variables.

   ![](./media/a_gg_ex4_3.png)

1. In the dynamic content popup, search for **Incident Title (1)** and click **Incident Title (2)** from the Microsoft Sentinel incident list.

   ![](./media/a_gg_ex4_4.png)

1. Similarly, select the placeholder **<Severity> (1)** in the Subject field and click the **dynamic content icon (2)** again.

   ![](./media/a_gg_ex4_5.png)

1. Search for **Incident Severity (1)** and select **Incident Severity (2)**.

   ![](./media/a_gg_ex4_6.png)

1. In the **Body** field, begin entering the incident metadata using the following format:
    ```
    Alert: Incident Title
    Severity: Incident Severity
    Status: Incident Status
    Entities: Entities
    Link: Incident URL
    ```
    Then insert each of the corresponding dynamic content values.<br>

   ![](./media/a_gg_ex4_7.png)
   > **Note:** Use dynamic fields to enrich the SOC email with full visibility into the incident.

1. Add **Incident Status** from dynamic content under **Status**.

   ![](./media/a_gg_ex4_9.png)

1. Add the **Entities** field next to the Entities label.

   ![](./media/a_gg_ex4_10.png)

1. Select and add the **Incident URL** field for the **Link** label to provide direct access to the incident in Microsoft Sentinel.

    ![](./media/a_gg_ex4_11.png)

1. After verifying all fields are correctly added in the **Subject** and **Body** sections, ensure the flow looks like the one shown.

    ![](./media/a_gg_ex4_12.png)

1. On the **Logic App Designer** toolbar, click **Save (1)** to save the playbook.

    ![](./media/a_gg_ex4_13.png)

1. The playbook named **Notify-SOC-OnPowerShellIncident** is now configured to notify SOC teams via email whenever a Sentinel incident is triggered.

    > **Note:** You can now link this playbook to an analytics rule as an automated response to PowerShell-based attacks or similar alerts.


## Task 3: Create Analytics Rule and Trigger Playbook using Microsoft Sentinel

In this task, you'll configure an analytics rule in Microsoft Sentinel to detect suspicious PowerShell activity and trigger an automated playbook when an incident is created.

1. In the **Microsoft Sentinel** portal, under your selected workspace, go to **Configuration (1)** > **Analytics (2)** and click **+ Create (3)** > **Scheduled query rule (4)**.

   ![](./media/crz_e4_g_1.png)

1. On the **Analytics rule wizard**, configure the General settings:
   - Enter **Suspicious PowerShell Execution (1)** as the rule name.
   - Set **Severity (2)** to `High`.
   - Select **Lateral Movement (3)** under MITRE ATT&CK.
   - Ensure **Status (4)** is set to `Enabled`.
   - Click **Next: Set rule logic (5)**.

   ![](./media/crz_e4_g_2.png)

1. On the **Set rule logic** tab:
   - Paste the following KQL under **Rule query (1)**:
     ```
     SecurityAlert
     | where TimeGenerated > ago(5m)
     | where AlertName has "Suspicious Powershell commandline"
     | where ProductName == "Microsoft Defender Advanced Threat Protection"
     | where AlertSeverity != "Informational"
         or (AlertSeverity == "Informational" and DisplayName startswith "[Test Alert]")
     ```
   - Under **Alert enhancement**, set **Entity mapping (2)**:
     - Entity type: `Host`
     - Identifier: `HostName` → `CompromisedEntity`

   ![](./media/crz_e4_g_3.png)

1. Scroll down to **Query scheduling**:
   - Set **Run query every (3)**: `5` Minutes
   - Set **Lookup data from the last (4)**: `6` Minutes
   - Choose **Automatically (5)** for start running
   - Click **Next: Incident settings (6)**

   ![](./media/crz_e4_g_4.png)

1. On the **Automated response** tab, click **+ Add new** to create a new automation rule.

   ![](./media/crz_e4_g_5.png)

1. In the **Create new automation rule** window:
   - Set **Automation rule name (1)**: `Run Notify-SOC-OnPowerShellIncident Playbook`
   - Under **Trigger (2)**: Select `When incident is created`
   - Click **+ Add (3)** and select **Condition (And) (4)**

   ![](./media/crz_e4_g_6.png)

1. Configure the condition and action:
   - Set condition:
     - Property: `Title (1)`
     - Operation: `Contains (2)`
     - Value: `PowerShell (3)`
   - Under **Actions**, select **Run playbook (4)** and choose:
     - `Notify-SOC-OnPowerShellIncident (5)` from your `threadprotection-rg` resource group.
   - Click **Apply (6)**

   ![](./media/crz_e4_g_7.png)

1. The configured automation rule will now run the playbook when an incident title contains `PowerShell`. Once triggered, an email notification is sent with incident details including severity, entities, and incident link.

   ![](./media/crz_e4_g_8.png)


### Task 2: Create a Power Automate Flow to Log Flagged Emails into SharePoint

In this task, you'll create a flow in Power Automate that triggers when an email is flagged in Outlook and logs its details (subject, sender, body, etc.) into the SharePoint list you created earlier.

1. On the **Power Automate portal**, click **Create (1)** in the left menu and select **Automated cloud flow (2)**.

   ![](./media/z_gg_e4_1.png)

1. In the **Build an automated cloud flow** window:
   - Enter **Automate Flagged Mail** as the **Flow name (1)**.
   - Search and select **When an email is flagged (V3)** as the trigger **(2, 3)**.
   - Click **Create (4)** to proceed.

   ![](./media/z_gg_e4_2.png)

1. On the flow canvas, click the **+ (1)** icon below the trigger to add a new action.

   ![](./media/z_gg_e4_3.png)

1. In the **Add an action** pane:
   - Search for **Get email (V2)** **(1)**.
   - Select **Get email (V2)** from **Office 365 Outlook** **(2)**.

   ![](./media/z_gg_e4_4.png)

1. In the **Get email (V2)** action, under **Message Id**, click the field **(1)** and select **Insert dynamic content (2)**.

   ![](./media/z_gg_e4_5.png)

1. In the dynamic content pane, search for **Message Id (1)** and select the field from **When an email is flagged (V3)** **(2)**.

   ![](./media/z_gg_e4_6.png)

1. Verify that **Message Id** is now populated dynamically. Leave the other default values as-is.

   ![](./media/z_gg_e4_7.png)

1. Click the **+ (1)** icon below the **Get email (V2)** step to add another action.

   ![](./media/z_gg_e4_8.png)

1. Search for **Create item (1)** and select it under **SharePoint (2)**.

   ![](./media/z_gg_e4_9.png)

1. In the **Create item** action:
    - Set **Site Address** to your SharePoint site (e.g., `Incident_Logs`) **(1)**.
    - Set **List Name** to `Powershell_Logs_list` **(2)**.
    - Expand **Advanced parameters** to view list columns **(3)**.

   ![](./media/z_gg_e4_10.png)

1. Select the following fields to display: **Title**, **Flagged by**, **Email Body**, **Message ID**, and **Flagged Date**.

   ![](./media/z_gg_e4_11.png)

1. In the **Title** field, click inside and select **Insert dynamic content (2)**.

   ![](./media/z_gg_e4_12.png)

1. From the dynamic content pane, search for **Subject** and select it from either trigger or action.

   ![](./media/z_gg_e4_13.png)

1. Fill in the remaining fields as follows:
    - **Title**: `Subject`
    - **Flagged by**: `From`
    - **Email Body**: `Body`
    - **Message ID**: `Internet Message Id`
    - **Flagged Date**: `Received Time`

   ![](./media/z_gg_e4_14.png)

   > **Note:** Use the dynamic content from **Get email (V2)** wherever possible for more complete data.  
   > **Important:** The **Body** field might store raw HTML — use additional processing if formatting is needed.

1. Once the flow is complete, click **Save** in the top-right corner.

   ![](./media/z_gg_e4_15.png)

1. Now go to your Outlook mailbox and flag an email you want to test the flow with.

   ![](./media/z_gg_e4_16.png)

1. After a few moments, go to the **Powershell_Logs_list** on your SharePoint site and verify that the email entry appears with all details logged.

   ![](./media/z_gg_e4_17.png)

> **Tip:** You can further extend this flow by notifying the SOC via Teams or email, or even triggering an Azure Logic App or Defender investigation.


