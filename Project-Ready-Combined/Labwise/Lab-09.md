# Lab 9: Configure Session Policies to Monitor and Block Risky Behavior

In this lab, you will configure a Session Policy in Microsoft Defender for Cloud Apps to monitor and block risky behavior. The policy will target non-compliant devices and prevent downloads of high-risk file types from Microsoft SharePoint Online. You will validate the configuration by attempting to download a blocked executable file, ensuring that the session policy enforcement works as intended.

> **⚠ Important Usage Guidance:** Microsoft Defender for Office 365 may take some time to load certain results or complete specific labs from the backend. This is expected behavior. If the data does not appear after a couple of refresh attempts, proceed with the next lab and return later to check the results.

1. In Microsoft Defender portal go to **Cloud Apps** → **Policy (1)** → **Policy management (2)** from the left pane.

1. On the **Policy management** page, in the **All policies (3)** section click on **+ Create policy (4)**, then select **Session policy (5)**.
  
   ![Create Session Policy](./media/corg-1-24.png)

1. Configure the policy settings:
   - **Policy template**: `No template` **(1)**
   - **Policy name**: `Block-All-Download` **(2)**
   - **Policy severity**: Choose high (red) **(3)**
   - **Category**: `Threat detection` **(4)**
   - **Session control type**: `Control file download (with inspection)` **(5)**
   - **Activities matching all of the following** **(6)**:  
     - `Device`, `tag`, `does not equal` → `Intune compliant, Microsoft Entra Hybrid joined`  
     - `App`, `Manual onboarding`, `equals` → `Microsoft SharePoint Online`

       ![Policy Filters](./media/gftix-1-1.png)
   > **Note**: On the **Apply template?** dialog box, click on the **Cancel** button.

1. Scroll to **Files matching all of the following** and configure the following:
   - `Extension`, `equals`, `exe` 
   - Click on **+** next to **exe** and add OR `apk` in the text box
   - Under **Actions**, select **Block**

      ![File Extension Block](./media/gftix-1-2.png)

1. Click **Create** to save and activate the policy.

   ![Save Policy](./media/grpg-1-1.png)

   > **Note**: Ensure your Conditional Access policy is routing sessions through Microsoft Defender for Cloud.

1. Right-click the **Microsoft Edge (1)** shortcut on the **Desktop**, select **Send to (2)** → **Documents (3)** to send a copy of the shortcut to the Documents folder.

   ![Send Shortcut to Documents](./media/tgs-1-3.png)

1. Open the Edge browser, open **New InPrivate window** and go to https://www.office.com.

1. Click on **Sign in** from the top right corner from home page of Office.com

   ![Create Site](./media/signinoffice.png)

1. Enter the Username and Password in the SignIn prompt:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
   - **Password:** <inject key="AzureAdUserPassword"></inject>

1. From the left pane, go to **Apps (1)** → **SharePoint (2)**.

   ![Create Site](./media/sharepoint1.png)
   > **Note:** If you see a redirect to *Access to Microsoft SharePoint Online is monitored*, click on **Continue to Microsoft SharePoint Online**

1. On *Sign in with your work account*, click on **Continue with current profile**

   ![Create Site](./media/sharepoint2.png)

1. Click on **+ Create site**.

   ![Create Site](./media/corg-1-25.png)

1. Then select **Communication site**.

   ![Select Communication Site](./media/corg-1-26.png)

1. Click **Standard communication (template)** and then select **Use template**.

   ![Create Site](./media/sharepoint3.png)

1. Enter the **Site name** as `Demo (1)` or any name of your choice, then click on the **Next (2)** button.

   ![Site Name](./media/corg-1-27.png)

1. Under the **Select a language** field, ensure that **English (1)** is selected, then click on the **Create site (2)** button.

   ![Select Language](./media/corg-1-28.png)

1. On the **Demo** site, click on the **three horizontal bars** (☰) on the top-left corner.

   ![Site Menu](./media/corg-1-29.png)

1. Navigate the left-hand menu and click on **Documents**.

   ![Documents Menu](./media/corg-1-30.png)

1. Click on **Upload**, then select **Files**.

   ![Upload Files](./media/corg-1-31.png)

1. Navigate and click on **Documents (1)**, then select **Microsoft Edge (2)** application. Now, click on the **Open (3)** button.

   ![Select Microsoft Edge Application](./media/corg-1-32.png)
   
   > **Note**: If `msedge.exe` is not available in the **Documents** folder, navigate to `C:\Program Files (x86)\Microsoft\Edge\Application`, locate `msedge` (the executable file), and upload it from there.

1. `msedge.exe` is successfully uploaded. Now, click on it.

   ![Uploaded Executable](./media/corg-1-33.png)

1. Click on the **Download** button.
  
   ![Download Executable](./media/corg-1-34.png)

1. The download should be blocked with a message:  
    **"Download blocked – Downloading msedge.exe is blocked by your organization’s security policy."**
  
    ![Download Blocked Message](./media/g-3-9.png)

1. Click on **Close** and close the InPrivate window.

## Review

In this lab, you:
- Created a high-severity Session Policy in Microsoft Defender for Cloud Apps.
- Configured filters to target non-compliant devices accessing Microsoft SharePoint Online.
- Set file inspection rules to block downloads of specific file types such as `.exe` and `.apk`.
- Validated the policy by attempting to download a blocked executable and confirming that it was successfully blocked.

## You have successfully completed the lab. Click on Next to Continue
