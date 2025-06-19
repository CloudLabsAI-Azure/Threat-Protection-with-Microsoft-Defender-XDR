# Lab 02 - Integrate Logic App with Threat Protection and XDR

## Lab scenario

The integration of a Logic App with Threat Protection involves configuring triggers and actions to receive alerts, while interaction with XDR solutions requires adding actions to exchange data, perform analyses, and trigger responses. Implementing conditional checks and logic within the Logic App allows for tailored handling of received threat information, ensuring effective responses and workflow execution before thorough testing and deployment to production environments. 

## Lab objectives
 In this lab, you will perform the following:
 - Task 1: Connect the Windows security event connector
 - Task 2: Enable Microsoft Defender for Cloud
 - Task 3: Create a Security Operations Center Team in Microsoft Teams
 - Task 4: Create a Playbook in Microsoft Sentinel
 - Task 5: Update a Playbook in Microsoft Sentinel
 
## Estimated timing: 60 minutes

## Architecture Diagram
 ![Lab overview.](./media/XDR-Lab-02.png)

### Task 1: Connect the Windows security event connector

1. In the Search bar of the Azure portal, type *Microsft Sentinel (1)*, then select **Microsoft Sentinel (2)**.

    ![](./media/09.png) 

1. Select the pre-created Sentinel **loganalyticworkspace** from the available list.

    ![](./media/Lab01-task2-loganalyticworkspace.png) 

1. Navigate to the left menu and go to the *Content Management* section, below that select **Content Hub (1)**. On the Content Hub page, locate **Windows Security Events (2)**, and then **select (3)** it. Finally, click on **Install (4)**.

    ![Picture 1](./media/Lab02-task1-contenthub.png)  

1. After receiving the notification of a successful installation, return to the **Data connectors** page under *Configuration* and click on the refresh button to ensure that the changes take effect.

1. You should observe two options: **Security Events Via Legacy Agent** and **Windows Security Event Via AMA**.

1. Choose **Security Events Via Legacy Agent (1)**, and then click on **Open Connector Page (2)**.

    ![Picture 1](./media/xdr8.png) 
   
8. In the configuration section, opt for **Install Agent on Azure Windows Virtual Machine (1)**, and then choose **Download & Install Agent for Azure Windows Virtual Machines (2)**.

    ![Picture 1](./media/xdr9.png) 

9. Select the **svm-<inject key="DeploymentID" enableCopy="false" />** virtual machine. 

    ![Picture 1](./media/xdr10.png) 
        
10. Click on **Connect (1)**. Once **connected**, select the **Virtual Machine (2)** link from the top.

    ![Picture 1](./media/xdr11.png) 

11. On the virtual machine page select the **s2vm-<inject key="DeploymentID" enableCopy="false" />** virtual machine and click on connect. wait until get connected.

    ![Picture 1](./media/xdr12.png)

11. Then, come back to the Configuration and scroll down a bit. You can find **Select which events to stream**. Select **All Events (1)** and then click on **Apply changes (2).**

    ![Picture 1](./media/xdr13.png) 

12. If you refresh the data connector page, you can see the status Connected for **Security Events Via Legacy Agent**.

    ![Picture 1](./media/xdr14.png) 

### Task 2: Enable Microsoft Defender for Cloud

In this task, you will enable and configure Microsoft Defender for Cloud.

1. In the search bar of the Azure portal, type *Defender (1)*, then select **Microsoft Defender for Cloud (2)**.

    ![Picture 1](./media/xdr15.png) 

1. On the **Overview** page, select the **Azure subscriptions**.

    ![Picture 1](./media/subscription-01.png)

1. On the **Environment Settings (1)** page, select **Subscription > Log Analytics Workspace (3)**, then toggle **Foundational CSPM** to **On(4)** and Click on **Save button**. Please wait 2-5 minutes for the process to complete.

    ![Picture 1](./media/envsettings-01.png)

    ![Picture 1](./media/foundationalcspm.png)

1. Navigate back to the **Environment settings (1)** then click on the subscription (or its equivalent name in your language). **(2)**

    ![Picture 1](./media/moc-hol-3001.png) 

1. Review the Azure resources that are now protected with the Defender for Cloud plans.

1. Select the **Settings & Monitoring** tab from the Settings area (next to Save).

    ![Picture 1](./media/Lab-02-task2-reviewplans.png)

1. Review the monitoring extensions and confirm that **Log Analytics agent** is by-default **On**.

    ![Picture 1](./media/loganalytics-agent.png) 


### Task 3: Create a Security Operations Center Team in Microsoft Teams.

In this task, you will create a team in Microsoft Teams for use in the lab.  

1. Access File Explorer and navigate to the directory **C:\LabFiles (1)**. Then, double-click on the named **MSTeams-86 (2)**. Allow a moment for the installation process to commence. Once installed, proceed to log in using the following credentials:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
   - **Password:** <inject key="AzureAdUserPassword"></inject>

        ![Lab overview.](./media/lab2.10.png)

        >**Note:** If you come up with the popup stay signed in to all your apps click on **No, sign in to this app only**.

1. Close any other popup opened and do not switch from classic teams, teams might automatically switch to new version after reopening the teams. please perform the below steps in the classic version as there might be steps vary in new version. 

1. Select **Teams (2)** on the left menu, then select **Join or create a team (2)**.

    ![Lab overview.](./media/xdr40.png) 

1. Select the **Create Team** button from the drop-down.

1. Select the **From scratch** button.

    ![Lab overview.](./media/lab03-task01-privatebutton.png)  
       
1. Select the **Private** button.

    ![Lab overview.](./media/lab03-task01-private2.png) 

1. Give the team the name: **SOC (1)** and select the **Create (2)** button.

    ![Lab overview.](./media/xdr41.png)  

1. In the Add members to SOC screen, select the **Skip** button. 

1. Scroll down the Teams blade to locate the newly created SOC team, select the ellipsis **(...) (1)** on the right side of the name and select **Add channel (2)**.
   
    ![Lab overview.](./media/xdr42.png) 

1. Enter a channel name as **New Alerts (1)** then select the **Add (2)** button.

    ![Lab overview.](./media/xdr30.png) 

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   - If you receive a success message, you can proceed to the next task.
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.
 
   <validation step="5e120148-dee3-45fe-8e37-6cbed679379f" />

### Task 4: Create a Playbook in Microsoft Sentinel.

In this task, you will create a Logic App that is used as a Playbook in Microsoft Sentinel.

1. In the Microsoft Edge browser, open a new tab and paste https://github.com/Azure/Azure-Sentinel to navigate to Microsoft Sentinel on GitHub.

1. Scroll down and select the **Solutions** folder.

1. Next select the **SentinelSOARessentials** folder, then the **Playbooks** folder.

1. Select the **Post-Message-Teams** folder.

1. In the readme.md box, scroll down to the **Quick Deployment (1)** section, **Deploy with incident trigger (recommended) (2)** and select the **Deploy to Azure (3)** button.

    ![Lab overview.](./media/xdr46.png) 

1. On the **Custom deployment** page provide the following details.

    - Make sure your Azure Subscription is selected. **(1)**

    - For Resource Group, select **threat-xdr** **(2)** 

    - Leave **(US) East US** as the default value for *Region*. **(3)**

    - Rename the *Playbook Name* to **PostMessageTeams-OnIncident (4)**. 

    - Provide the **Teams Group Id(5)** and **Teams Channel ID(6)** in order to get these values navigate back to the MS teams.

        i.  For **Teams Group Id** click on **SOC Ellipse(1)** then click on **Get  link to team(2)**.

        ![Lab overview.](./media/L2T4S6-i.png)

        ii. For **Teams Channel Id** click on **New Alerts Ellipse(1)** then click on **Get  link to Channel(2)**.

        ![Lab overview.](./media/L2T4S6-ii.png)

        iii. Copy the values to the **Notepad**.

        ![Lab overview.](./media/L2T4S6-iii.png)

1. Select **Review + create (7)** and then click **Create**.

      ![Lab overview.](./media/L2T4S7.png) 

    >**Note:** Wait for the deployment to finish before proceeding to the next task. It may take a couple of minutes to deploy.

### Task 5: Update a Playbook in Microsoft Sentinel.

In this task, you will update the new playbook you created with the proper connection information.

1. In the Search bar of the Azure portal, type *Microsft Sentinel (1)*, then select **Microsoft Sentinel (2)**.

    ![](./media/09.png) 

1. Select the pre-created Sentinel **loganalyticworkspace** from the available list.

    ![](./media/Lab01-task2-loganalyticworkspace.png)

1. Select the **Automation (1)** from the Configuration area and then select the **Active Playbooks (2)** tab, If **PostMessageTeams-OnIncident (3)** is not visiable refresh the page and check.

1. Select the **PostMessageTeams-OnIncident** playbook and click on it to go to the logic App page.

    ![Lab overview.](./media/Lab03-task03-activeplaybook.png) 

1. On the Logic App page for *PostMessageTeams-OnIncident*, in the center menu, select **Edit**.
   
    ![Lab overview.](./media/Lab03-task1-001.png) 

1. Select the *first* block **Microsoft Sentinel Incident**.

    ![Lab overview.](./media/xdr32.png) 

1. Select the **Change connection** link.
   
   ![Lab overview.](./media/xdr33.png) 

1. Select **Add new.**

   ![Lab overview.](./media/xdr34.png) 

1. Select **Sign in**. In the new window, select your Azure subscription admin credentials when prompted. The last line of the block should now read “Connected to your-admin-username”.  

    ![Lab overview.](./media/incident-01.png) 

1. Now select the *second block*, **Connections**.

   ![Lab overview.](./media/xdr35.png) 

1. Click on **Change connection.**  

   ![Lab overview.](./media/xdr36.png) 

1. Select **Add new** then **Sign in** and select your Azure admin credentials when prompted. The last line of the block should now read “Connected to your-admin-username”.

    ![Lab overview.](./media/incidnet-02.png)
   
1. The block has now been renamed to **Post a message (V3)**, at the end of the Team field, select the X to clear the contents. The field is changed to a drop-down with a listing of the available Teams from Microsoft Teams. Select **SOC (1)**.

1. Do the same for the Channel field, select the **X** at the end of the field to clear the contents. The field is changed to a drop-down with a listing of the Channels of the SOC Teams. Select **New Alerts (2)**. 

    ![Lab overview.](./media/xdr37.png)    

1. Under the **Message** section, type **Entities: (1)** and click on the **dynamic content (2)** icon.

   ![Lab overview.](./media/xdr43.png)    

1. Search and select **Entities (2)** dynamic content from the right panel.

   ![Lab overview.](./media/xdr38.png)

   >**Note:** Click in the **Thunder Icon** to check fir the entities field content.

1. Select **Save** on the command bar. The Logic App will be used in a future lab.
   
   ![Lab overview.](./media/xdr39.png)
   
## Review
 In this lab you have completed the following tasks:
 - Connect the Windows security event connector
 - Enable Microsoft Defender for Cloud
 - Create a Security Operations Center Team in Microsoft Teams
 - Create a Playbook in Microsoft Sentinel
 - Update a Playbook in Microsoft Sentinel
