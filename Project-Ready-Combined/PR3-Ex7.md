# Exercise 7: Integrating Microsoft Sentinel with Microsoft Defender for Threat Detection and Investigation

### Estimated timing: 90 minutes
## Overview

In this exercise, you will connect the Windows security event connector, enable Microsoft Defender for Cloud, and protect an on-premises server. You’ll simulate persistence and command-and-control attacks, detect malicious activity, and investigate the resulting incident to understand how Defender for Cloud responds to advanced threats.

> **⚠ Important Usage Guidance**

> Microsoft Defender for Office 365 may take some time to load certain results or complete specific tasks from the backend. This is expected behavior. If the data does not appear after a couple of refresh attempts, proceed with the next task in the lab and return later to check the results.

## Objectives
 In this exercise, you will perform the following in the M365 Defender portal:
- Task 1: Connect the Windows security event connector
- Task 2: Enable Microsoft Defender for Cloud
- Task 3: Persistence Attack with Registry Key Add 
- Task 4: Command and Control Attack with DNS
- Task 5: Persistence Attack Detection
- Task 6: Investigate an incident

### Task 1: Connect the Windows security event connector

1. On the **Microsoft Defender** portal, in the left navigation pane, select **Microsoft Sentinel (1)**, expand **Content management (2)**, and select **Content hub (3)**.

    ![](./media/t3_g_e1_22.png)

1. On the **Content hub** page, in the search bar, type **Windows Security Events (1)**, then select the checkbox for **Windows Security Events (2)** from the results.

    ![](./media/cor_r_g_3.png)

1. On the **Windows Security Events** solution page, click **Install**.

    ![](./media/cor_r_g_4.png)

1. After receiving the notification of a successful installation, return to the Data Connector page and click on the refresh button to ensure that the changes take effect.

1. You should observe two options: **Security Events Via Legacy Agent** and **Windows Security Event Via AMA**.

1. On the left navigation pane, expand **Configuration (1)**, select **Data connectors (2)**, and in the search bar, type **Security Events via Legacy Agent (3)**. From the results, select **Security Events via Legacy Agent (4)**.

    ![](./media/cor_r_g_5.png)

1. On the **Security Events via Legacy Agent** page, click **Open connector page**.

    ![](./media/cor_r_g_6.png)

1. In the configuration section, opt for **Install Agent on Azure Windows Virtual Machine (1)**, and then choose **Download & Install Agent for Azure Windows Virtual Machines (2)**.

    ![](./media/t3_g_e2_7.png)

9. Select the **svm-<inject key="DeploymentID" enableCopy="false" />** virtual machine.

    ![](./media/t3_g_e2_8.png)

9. On the virtual machine page, click **Connect** to link the VM to Log Analytics.

    ![](./media/t3_g_e2_9.png)
        
10. select the **Virtual Machine** link from the top.

    ![](./media/t3_g_e2_10.png)

11. On the virtual machine page select the **s2vm-<inject key="DeploymentID" enableCopy="false" />** virtual machine.

    ![](./media/t3_g_e2_11.png)

11. On the second virtual machine page, click **Connect** to link the VM to Log Analytics.

    ![](./media/t3_g_e2_12.png)

10. select the **Virtual Machine** link from the top.

    ![](./media/t3_g_e2_13.png)

11. Verify that both virtual machines **s2vm-<inject key="DeploymentID" enableCopy="false" />** and **svm-<inject key="DeploymentID" enableCopy="false" />** display **This workspace (1)** under the **Log Analytics Connection** column, then click **Security Events via Legacy Agent (2)** in the breadcrumb to return to the connector page.

    ![](./media/t3_g_e2_14.png)

11. In the **Instructions** section, under **Select which events to stream**, choose **All Events (1)** and click **Apply changes (2)**.

    ![](./media/t3_g_e2_15.png)

12. Click on Apply Changes now. If you refresh the data connector page, you can see the status Connected for **Security Events Via Legacy Agent**.

### Task 2: Enable Microsoft Defender for Cloud

In this task, you will enable and configure Microsoft Defender for Cloud.

1. Go to the [Azure Portal](https://portal.azure.com), and search for **Microsoft Defender for Cloud**.

   ![](./media/gg-1-1.png)

1. When prompted, click **Enable** to activate Defender CSPM.
     
   ![](./media/gg-1-2.png)

   > **Note:** If you don’t see the pop-up prompt, simply continue and follow the lab guide steps as shown below.

   >**Note:** This enables advanced posture capabilities like attack path analysis and permissions management.

1. In the **Microsoft Defender for Cloud** page, under **Management**, select **Environment settings (1)**, expand **Azure** and **Tenant Root Group**, then select **Subscription (2)**.

   ![](./media/gg-1-3.png)

1. On the **Settings & monitoring** page, turn **On (1)** the toggle for **Foundational CSPM** and **On (2)** for **Servers** under Cloud Workload Protection, then click **Save (3)**.

   ![](./media/t3_g_e2_16.png)

1. Click **Environment settings** in the top to return to the environment settings page.

   ![](./media/t3_g_e2_17.png)

1. On the **Environment settings** page, expand **Azure (1)**, then expand **Subscription** and select **loganalycticworkspace (2)**.

   ![](./media/t3_g_e2_18.png)

1. On the **Select Defender plan** page, turn **On (1)** the toggles for **Foundational CSPM** and **Servers**, then click **Save (2)**.

   ![](./media/t3_g_e2_19.png)

1. Close the Defender plans page by selecting the 'X' in the upper right corner of the page to return to the **Environment settings**.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.
<validation step="ea9784ef-a103-41e0-859f-f673a96cf886" />
    
### Task 3: Persistence Attack with Registry Key Add 

1. In the search of the taskbar, enter *Command*. A Command Prompt will be displayed in the search results. Right-click on the Command Prompt and select **Run as Administrator**. Select **Yes** in the User Account Control window that allows the app to run.

1. In the Command Prompt, create a Temp folder in the root directory. Remember to press Enter after the last row:

    ```CommandPrompt
    cd \
    mkdir temp
    cd temp
    ```

    >**Note**: If there is any error on temp directory already exists, please perform the next steps.  
   
1. Copy and run this command to simulate program persistence:

    ```CommandPrompt
    REG ADD "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run" /V "SOC Test" /t REG_SZ /F /D "C:\temp\startup.bat"
    ```

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   - If you receive a success message, you can proceed to the next task.
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.
 
   <validation step="4308381b-c9df-4237-b612-a6aa4f974757" />
   
### Task 4: Command and Control Attack with DNS

1. Copy and run this command to create a script that will simulate a DNS query to a C2 server:

      ```CommandPrompt
      notepad c2.ps1
      ```

1. Select **Yes** to create a new file and copy the following PowerShell script into *c2.ps1*.

      >**Note:** Pasting into the virtual machine file might not show the full script length. Make sure the script matches the instructions within the *c2.ps1* file.

      ```PowerShell
      param(
        [string]$Domain = "microsoft.com",
        [string]$Subdomain = "subdomain",
        [string]$Sub2domain = "sub2domain",
        [string]$Sub3domain = "sub3domain",
        [string]$QueryType = "TXT",
        [int]$C2Interval = 8,
        [int]$C2Jitter = 20,
        [int]$RunTime = 240
    )
    $RunStart = Get-Date
    $RunEnd = $RunStart.addminutes($RunTime)
    $x2 = 1
    $x3 = 1 
    Do {
        $TimeNow = Get-Date
        Resolve-DnsName -type $QueryType $Subdomain".$(Get-Random -Minimum 1 -Maximum 999999)."$Domain -QuickTimeout
        if ($x2 -eq 3 )
        {
            Resolve-DnsName -type $QueryType $Sub2domain".$(Get-Random -Minimum 1 -Maximum 999999)."$Domain -QuickTimeout
            $x2 = 1
        }
        else
        {
            $x2 = $x2 + 1
        }    
        if ($x3 -eq 7 )
        {
            Resolve-DnsName -type $QueryType $Sub3domain".$(Get-Random -Minimum 1 -Maximum 999999)."$Domain -QuickTimeout
            $x3 = 1
        }
        else
        {
            $x3 = $x3 + 1
        }
        $Jitter = ((Get-Random -Minimum -$C2Jitter -Maximum $C2Jitter) / 100 + 1) +$C2Interval
        Start-Sleep -Seconds $Jitter
    }
    Until ($TimeNow -ge $RunEnd)
    ```

1. In the Notepad menu, select **File** and then **Save**. 

1. Go back to the Command Prompt window, enter the following command and press Enter.

      ```CommandPrompt
      Start PowerShell.exe -file c2.ps1
      ```
    
      ![Lab overview.](./media/cmd.png)
   
      >**Note:** You will see DNS resolve errors. This is expected.

      >**Important**: Do not close these windows. Let this PowerShell script run in the background. The command needs to generate log entries for some hours. You can proceed to the next task and next exercises while this script runs. The data created by this task will be used in the Threat Hunting lab later. This process will not create substantial amounts of data or processing.

### Task 5: Persistence Attack Detection

In this task, you will create a detection for the first attack of the previous exercise.
1. In the Search bar of the Azure portal, type *Microsft Sentinel (1)*, then select **Microsoft Sentinel (2)**.

   ![](./media/09.png)
   
1. Select the Microsoft Sentinel Workspace you created earlier.

1. Select **Logs** from the *General* section.

   ![](./media/cor_r_g_7.png)

    >**Note:** You might see some popup after clicking on **Logs**. close all Popups by clicking on **X** Icon.

1. In the query editor, enter the following KQL statement **(1)** and click **Run (2)** to retrieve the records that start with the specified EventId. Review the results in the table below **(3)**.

    ```KQL
    SecurityEvent 
    | where Activity startswith "4624" 
    ```
   ![](./media/cor_r_g_8.png)

    >**Note:** It may take **5 to 10 minutes** for the SecurityEvent data to become available after onboarding or activity generation. 

    >**Note:** The number of output rows and values may differ depending on your environment and data availability.

1. In the query editor, enter the following KQL statement **(1)** to project entities for investigation and click **Run (2)**. Review the results in the table below **(3)**.

    ```KQL
    SecurityEvent 
    | where Activity startswith "4624" 
    | extend timestamp = TimeGenerated, HostCustomEntity = Computer, AccountCustomEntity = SubjectUserName
    ```

   ![](./media/cor_r_g_9.png)

1. In the **Logs** window, click the ellipsis **(1)** in the command bar, select **New alert rule (2)**, and then select **Create Microsoft Sentinel alert (3)**.
   
   ![](./media/cor_r_g_11.png)

1. In the **Analytics rule wizard** on the **General** tab: 
 
    - Enter **Startup RegKey (1)** in the *Name* field.  
    - Type **Startup RegKey in c:\temp (2)** in the *Description* field.  
    - Select **High (3)** for *Severity*.  
    - Choose **Persistence (4)** for *MITRE ATT&CK*.  
    - Ensure *Status* is set to **Enabled (5)**.  
    - Click **Next: Set rule logic > (6)**.  

        ![](./media/cor_r_g_12.png)

1. On the *Set rule logic* tab, the *Rule query* should be populated already with your KQL query, under **Alert enhancement** expand *Entity mapping* and select **+ Add New Entity**.

    |Entity|Identifier|Data Field|
    |:----|:----|:----|
    |Account|FullName|AccountCustomEntity|
    |Host|Hostname|HostCustomEntity|

   ![](./media/cor_r_g_13.png)

   ![](./media/cor_r_g_14.png)

1. If **Hostname** isn't selected for *Host* Entity, select it from the drop-down list.

1. For *Query scheduling* set the following:

    |Setting|Value|
    |---|---|
    |Run Query every|5 minutes|
    |Lookup data from the last|1 Days|

   ![](./media/cor_r_g_15.png)

    >**Note:** We are purposely generating many incidents for the same data. This enables the Lab to use these alerts.

1. Leave the rest of the options with the defaults. Select **Next: Incident settings>** button.

1. For the *Incident settings* tab, leave the default values and select **Next: Automated response >** button.

1. On the *Automated response* tab, leave everything as default and select  **Next: Review + Create** button.
  
1. On the **Review and create** tab, select the **Save** button to create the new Scheduled Analytics rule.

   ![](./media/cor_r_g_16.png)

### Task 6: Investigate an incident

In this task, you will investigate an incident.

1. On the **Microsoft Defender portal**, under **Investigation & response**, select **Incidents & alerts (1)**, then select **Incidents (2)**, and from the list click the incident named **Startup RegKey (3)** to open its details.

   ![](./media/cor_r_g_17.png)

1. Under the **Incident details** section, select the linked incident name **Multi-stage incident involving Execution & Persistence on multiple endpoints reported by multiple sources (1)** to view full incident details.

   ![](./media/cor_r_g_20.png)

    >**Note:** The Analytics rules are generating alerts and incidents on the same specific log entry. Remember that this was done in the *Query scheduling* configuration to generate more alerts and incidents to be utilized in the lab.
  
1. On the incident details page, under the **Attack story** tab, select **Play attack story (1)** to visualize the sequence of events in the incident graph.

   ![](./media/cor_r_g_21.png)

1. On the incident details page, select the **Assets (1)** tab to view all associated assets, including devices, users, and other resources involved in the incident.

   ![](./media/cor_r_g_22.png)

1. On the incident details page, select the **Evidence and Response (1)** tab to view all related evidence, including processes, IP addresses, and registry values identified during the investigation.

   ![](./media/cor_r_g_23.png)

1. On the incident details page, click **Manage incident (1)** to modify the incident’s properties or take remediation actions.

   ![](./media/cor_r_g_24.png)

1. In the **Manage incident** pane, update the incident details as follows:  
    - Set **Severity (1)** to **High**.  
    - In **Incident tags (2)**, enter `RegKey`.  
    - In **Assign to (3)**, select your account.  
    - Set **Status (4)** to **Resolved**.  
    - Set **Classification (5)** to **True positive - Multi staged attack**.  
    - Click **Save (6)**.

        ![](./media/cor_r_g_25.png)

## Review
In this lab, you have completed the following tasks:
- Connected the Windows security event connector
- Enabled Microsoft Defender for Cloud
- Conducted Persistence Attack with Registry Key Add 
- Conducted Command and Control Attack with DNS
- Conducted Persistence Attack Detection
- Investigated an incident
