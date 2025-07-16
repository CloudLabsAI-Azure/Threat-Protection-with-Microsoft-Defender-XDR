## Task 1: Implement and Monitor Defender for Office 365 Secure Posture

## Task 2: Investigate and Remediate Incidents in Microsoft Defender XDR

In this task, you’ll investigate a phishing email, take appropriate actions, submit it to Microsoft for review, and monitor the automated investigation and alerts triggered in Microsoft Defender XDR.

1. Use Outlook or another email client to send a test phishing message with suspicious links to your lab user.

   ![](./media/g25-1.png)

1. Go to the [Microsoft 365 Defender Portal](https://security.microsoft.com) Navigate to **Email & collaboration** → **Explorer**  

1. Find and click the suspicious message titled **Test Phishing**.

   ![](./media/g25-2.png)

   > **Note:** It may take 2–3 minutes after the phishing email is delivered for it to appear in Threat Explorer.

1. Click the message to view its details, then click **Take action** to initiate response actions.

   ![](./media/g25-3.png)

1. Configure the following settings:

    - Enable **Show all response actions**  
    - Choose **Move to Junk**  
    - Submit to Microsoft for review:
      - Select **I've confirmed it's a threat**
      - Choose **Phish** as the category  
    - Enable **Initiate automated investigation**

1. Click **Next** to continue.

   ![](./media/g25-4.png)

1. Set a name like `report-phish` and confirm impacted users and actions.

   ![](./media/g25-5.png)

1. Navigate to **Incidents & alerts** → **Alerts** and Look for the alert titled **Administrative action submitted by an Administrator**.

   ![](./media/g25-6.png)

1. Click the alert to open details, then click **Manage alert**.

   ![](./media/g25-7.png)

1. In the Manage alert pane:  
 
    - Set **Status** to `In progress`  
    - Assign to your lab user  
    - Set **Classification** to `True positive – Phishing`  
    - Click **Save**

      ![](./media/g25-8.png)

1. Go to **Email & collaboration** → **Investigations**.Click on the newly triggered investigation linked to your phishing test.

    ![](./media/g25-9.png)

1. Review the investigation graph showing the alert path, analyzed entities, and final result.

   ![](./media/g25-10.png)

   >**Note:** It may take **10–15 minutes** for the automated investigation to complete and display results.

   > You've successfully investigated and responded to a phishing incident using Microsoft Defender XDR.
