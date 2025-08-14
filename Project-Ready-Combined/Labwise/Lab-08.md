# Lab 8: Connect and Onboard a SaaS App to Microsoft Defender for Cloud Apps

## Overview

In this lab, you will connect and onboard a SaaS application—Microsoft 365—to Microsoft Defender for Cloud Apps. You will configure Conditional Access App Control policies in Microsoft Entra ID, enable file monitoring, and connect Microsoft 365 through the App Connectors page. This ensures visibility into user activity, enforces session controls, and enhances data security for your SaaS environment.

> **⚠ Important Usage Guidance:** SaaS app connection and Conditional Access policy propagation may take several minutes to complete. If the connected status or app list does not update immediately, wait and refresh before proceeding.


1. Open the **Microsoft Edge** browser and go to the following URL in the address bar: 

   [https://portal.azure.com](https://portal.azure.com)

1. In the search bar, type **Microsoft Entra ID** and select it.

   ![](./media/g-1-1.png)

1. In the **Overview** pane, select **Users** under the **Manage** section.
  
   ![](./media/g-1-2.png)

1. From the list of users, click on your assigned user (`ODL_User******`).
  
   ![](./media/g-1-3.png)

1. In the user blade, click on **Licenses** and ensure **Microsoft 365 E5 (no Teams)** or an equivalent license is assigned and active.
  
   ![](./media/g-1-4.png)

1. Go back to the **Azure portal** tab. In the search bar at the top, enter **Windows Azure Active Directory**, and then select it from the search results.
  
    ![](./media/g-4-1.png)

1. On the **Windows Azure Active Directory** page, click on **Security**, then select **Conditional Access**, and on the Conditional Access page, click on **+ New policy**.
  
    ![](./media/corg-1-14.png)

1. Name the policy: `MCAS – M365 Session Control`

1. Under the **Assignments** section, click on **Users**, then select the **Select users and groups** radio button.

1. Check the box beside **Users and groups**, then click on **0 users and groups selected**.
  
    ![](./media/corg-1-15.png)

1. In the **Select users and groups** window, search for your lab user (`ODL_User`), check the box beside the user, and click **Select**.
  
    ![](./media/corg-1-16.png)

1. You’ll now see your selected user listed under **Users**.
  
    ![](./media/corg-1-17.png)

1. Under **Assignments > Target resources**, click on the **0 resource included** link and ensure the radio button beside **Select resources** is selected.

1. Click on **Windows Azure Active Directory**, then in the **Select** pane, check the box for **Office 365**, and click **Select**.
  
    ![](./media/corg-1-18.png)

1. Under **Access controls > Session**, click on the **0 controls selected** link.

1. In the Session pane, check the box for **Use Conditional Access App Control**, ensure **Use custom policy** is selected from the dropdown, then click **Select**.
  
    ![](./media/corg-1-19.png)

1. Scroll down, toggle **Enable policy** to **On**, and click **Create**.
  
    ![](./media/corg-1-20.png)

1. Go back to the **Microsoft Defender portal** tab and select **Settings** from the left-sided menu and select **Cloud apps**.

1. Navigate to the **Information Protection** section and select **Files**.

1. Select the checkbox beside **Enable file monitoring**, then click on the **Save** button.
  
    ![](./media/corg-1-21.png)

    ![](./media/corg-1-22.png)

1. Under the **Connected apps** section, click on **App Connectors**. On the **App connectors** page, select the checkbox beside **Microsoft 365**, then click on **+ Connect Microsoft Azure instance**.
  
    ![](./media/corg-1-23.png)

1. Click **Connect Microsoft 365** and complete the authentication.

1. After successful connection, you will see the confirmation message: **“Great, Microsoft 365 is connected.”**, Click **Done**
 
    ![](./media/g-1-11.png)

1. On the **App Connectors** page, verify that Microsoft 365 and Microsoft Azure shows **Connected** status.
  
    ![](./media/g-1-12.png)

1. Under **Connected apps**, select **Conditional Access App Control apps**.

1. Locate and click the ellipsis (**⋮**) next to **Microsoft SharePoint Online – General**, then choose **View settings in Microsoft Entra ID**.

   ![](./media/22-g-2.png)

   > **Note:** If you're unable to view **SharePoint Online**, open an incognito browser window and navigate to [https://www.office.com](https://www.office.com).
   
   > **Note:** Sign in using your lab credentials. From the left pane, go to **Apps** → **SharePoint**.
   
   >**Note:** Then, return to the Conditional Access page and refresh it to load the app properly.

1. In the **Enterprise applications** blade, click **Microsoft Graph Command Line Tools**.

   ![](./media/22-g-3.png)

1. On the overview page, under **3. Conditional Access**, click **Create a policy**.

   ![](./media/22-g-4.png)

1. Click **+ New policy** to define a custom access rule for the application.

   ![](./media/22-g-5.png)

> **Note:** After completing this configuration, go back and repeat steps **17–24** from Task 1 to ensure your Conditional Access App Control policy is correctly applied to **Microsoft Graph Command Line Tools** as well.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.
<validation step="1bbaab69-9291-4c6b-bd0c-7c019d729d2f" />


## Review

In this lab, you:
- Verified that the assigned user has the correct Microsoft 365 E5 license.
- Configured a Conditional Access policy with session controls for Microsoft 365.
- Enabled file monitoring in Microsoft Defender for Cloud Apps.
- Connected Microsoft 365 via App Connectors and confirmed the connection status.
- Applied Conditional Access App Control to specific apps such as SharePoint Online.

## You have successfully completed the lab. Click on Next to Continue
