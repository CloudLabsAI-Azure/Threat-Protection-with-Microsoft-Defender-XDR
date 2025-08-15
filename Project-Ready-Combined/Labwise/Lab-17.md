# Lab 17: Review and explore Sentinel workspace  

In this lab, you will integrate the **Windows Security Events** data connector with Microsoft Sentinel. By completing this setup, Microsoft Sentinel will automatically collect and analyze Windows security event logs from your Azure virtual machines, enabling advanced threat detection and investigation.

> **⚠ Important Usage Guidance:** Microsoft Defender for Office 365 may take some time to load certain results or complete specific labs from the backend. This is expected behavior. If the data does not appear after a couple of refresh attempts, proceed with the next lab and return later to check the results.

1. On the **Microsoft Defender** portal, in the left navigation pane:
   - Select **Microsoft Sentinel (1)**.
   - Expand **Content management (2)** and select **Content hub (3)**.

   ![](./media/t3_g_e1_22.png)

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

1. Select the **svm-<inject key="DeploymentID" enableCopy="false" />** virtual machine.

   ![](./media/t3_g_e2_8.png)

1. On the virtual machine page, click **Connect** to link the VM to Log Analytics.

   ![](./media/t3_g_e2_9.png)

1. Select the **Virtual Machine** link from the top.

   ![](./media/t3_g_e2_10.png)

1. On the virtual machine page select the **s2vm-<inject key="DeploymentID" enableCopy="false" />** virtual machine.

   ![](./media/t3_g_e2_11.png)

1. On the second virtual machine page, click **Connect** to link the VM to Log Analytics.

   ![](./media/t3_g_e2_12.png)

1. Select the **Virtual Machine** link from the top.

   ![](./media/t3_g_e2_13.png)

1. Verify that both virtual machines **s2vm-<inject key="DeploymentID" enableCopy="false" />** and **svm-<inject key="DeploymentID" enableCopy="false" />** display **This workspace (1)** under the **Log Analytics Connection** column, then click **Security Events via Legacy Agent (2)** in the breadcrumb to return to the connector page.

   ![](./media/t3_g_e2_14.png)

1. In the **Instructions** section, under **Select which events to stream**, choose **All Events (1)** and click **Apply changes (2)**.

   ![](./media/t3_g_e2_15.png)

1. Click on Apply Changes now. If you refresh the data connector page, you can see the status Connected for **Security Events Via Legacy Agent**.

## Review

In this lab, you:
- Installed the **Windows Security Events** solution from the Content Hub.
- Connected Azure Windows virtual machines to Log Analytics.
- Configured the **Security Events via Legacy Agent** connector to stream all security events.
- Verified the successful connection of both virtual machines in the data connector status.

## You have successfully completed the lab. Click on Next to Continue
