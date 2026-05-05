---

copyright:
  years: 2022, 2023
lastupdated: "2026-05-05"

keywords:

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Adding users to your account for Sandbox access
{: #create-user}

Users can only be added during Sandbox provisioning from the catalog tile. To add users to your account, follow these steps:

1. In the {{site.data.keyword.Bluemix_notm}} console, **select Manage** > **Access (IAM)**.

2. In the *IAM navigation* menu, select **Users**.

3. Click **Invite** users.

4. Enter the email addresses.

5. Select **Access policy**. Ensure that you add access policies and grant administrator-level access to the following services:

    * All Identity and Access–enabled services
    * All Account Management services
    * Cloud Sandbox

6. Click **Next**.

7. Select **Roles and Action** and assign **Administrator** as the platform access to the user. Click **Review**.

8. To add this level of access for these users, click **Add**. It will be added to the summary panel. You can add additional access policies if desired, or click **Invite** to send email invitations.

9. On the right-hand side, click **Invite**.

The user gets an email invitation with the link to complete the process. This will add the user in the User list and to the Sandbox provisioning page.

![Creating a user](images/create-user.png "Creating a user"){: caption="Creating a user" caption-side="bottom"}
