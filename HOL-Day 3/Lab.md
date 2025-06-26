# Hands on Labs- Day 3 
## Estimated Duration: 90 Minutes
### Exercise: 1

### Task 1: Deploy Microsoft Defender for Identity Sensor on Domain Controllers

In this task you will install and configure the Defender for Identity sensor on a domain controller to monitor identity-based threats.

1. **Sign in to the Microsoft Defender Portal**:
   - Open a browser and navigate to `security.microsoft.com`.
   - Sign in with a Security Administrator or Global Administrator account (e.g., `admin@yourdomain.com`).

2. **Navigate to Defender for Identity Settings**:
   - In the left-hand navigation pane, click **Settings** (gear icon at the bottom).
   - Under **General**, select **Identities** to open Defender for Identity settings.

3. **Create a Sensor**:
   - In the **Identities** section, click **Sensors** at the top.
   - Click **Add sensor** in the top-right corner.
   - A pop-up will display a **Download installer** button and an **Access key**. Click **Download installer** to download `Azure ATP Sensor Setup.zip`.
   - Copy the **Access key** to your clipboard (you’ll need it during installation).

4. **Prepare the Domain Controller**:
   - Log in to the domain controller (e.g., `DC01.yourdomain.com`) with an account that has local admin privileges.
   - Verify connectivity to `https://<your-workspace-name>sensorapi.atp.azure.com` by opening a browser on the domain controller and navigating to the URL (replace `<your-workspace-name>` with your Defender for Identity workspace name, found in the **Sensors** section).
   - Ensure .NET Framework 4.7 or later is installed. Run in PowerShell:
     ```powershell
     Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" | Select-Object Version
     ```

5. **Install the Sensor**:
   - Copy the `Azure ATP Sensor Setup.zip` file to the domain controller.
   - Extract the ZIP file to a folder (e.g., `C:\ATP`).
   - Run `Azure ATP Sensor Setup.exe` as an administrator.
   - Follow the wizard:
     - Accept the license terms and click **Next**.
     - Enter the **Access key** copied earlier and click **Next**.
     - Choose the default installation path (e.g., `C:\Program Files\Azure Advanced Threat Protection Sensor`) and click **Install**.
   - Wait for the installation to complete (typically 2-5 minutes).

6. **Verify Sensor Status**:
   - Return to the Microsoft Defender portal.
   - Navigate to **Settings** > **Identities** > **Sensors**.
   - Locate the sensor for `DC01.yourdomain.com` in the list.
   - Check the **Status** column; it should display **Connected** within 5-10 minutes.

### Task 2: Simulate and Detect Lateral Movement Attacks (Pass-the-Hash, DC Sync)

In this task you will simulate Pass-the-Hash and DC Sync attacks and detect them using Defender for Identity.

1. **Prepare a Test Machine**:
   - Log in to a test machine (e.g., `TestPC1.yourdomain.com`) joined to the domain, using a local admin account.
   - Download Mimikatz (use a legitimate source or pre-installed lab image) to `C:\Tools`.
   - Ensure the machine has network access to the domain controller (`DC01.yourdomain.com`).
2. **Simulate Pass-the-Hash Attack**:
   - Open a command prompt as administrator on `TestPC1`.
   - Navigate to the Mimikatz folder (e.g., `cd C:\Tools\Mimikatz`).
   - Run Mimikatz to extract NTLM hashes:
     ```powershell
     mimikatz.exe "sekurlsa::logonpasswords" exit
     ```
     - Note the NTLM hash for a test user (e.g., `testuser1`).
   - Use the hash to access a domain resource (e Psexec to access `DC01`:
     ```powershell
     psexec.exe \\DC01.yourdomain.com -u yourdomain\testuser1 -p <NTLM-hash> cmd
     ```
     - Replace `<NTLM-hash>` with the hash obtained from Mimikatz.
       
3. **Simulate DC Sync Attack**:
   - In the same Mimikatz session, run:
     ```powershell
     mimikatz.exe "lsadump::dcsync /domain:yourdomain.com /user:krbtgt" exit
     ```
     - This simulates a DC Sync attack to extract the `krbtgt` account’s credentials.

4. **Check Alerts in the Defender Portal**:
   - In the Microsoft Defender portal, navigate to **Incidents & alerts** in the left-hand navigation pane.
   - Click **Alerts** to view the alerts queue.
   - Look for alerts such as:
     - "Suspected Pass-the-Hash attack (NTLM)" for the Pass-the-Hash simulation.
     - "Suspected DCSync attack" for the DC Sync simulation.
   - Click an alert to view details, including the affected user (`testuser1`) and entity (`DC01.yourdomain.com`).
