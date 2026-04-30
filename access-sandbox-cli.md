---

copyright:
  years: 2026
lastupdated: "2026-04-30"

keywords: save configuration, terraform, export configuration, download terraform, infrastructure as code, terraform files

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Accessing Sandbox - CLI
{: #save-config}

To access Sandbox using CLI, you need the following commands:

1. In the IBM Cloud console, go to https://cloud.ibm.com URL.

2. Login to your account.

3. On your profile icon, click **Log in to CLI and API** from the drop-down.

4. A pop-up window appears with **One-time passcode**. Copy the IBM Cloud CLI login command:

    `ibmcloud login -a https://cloud.ibm.com --sso -r us-south -g Default`

5. Install VPC Plugin using the command:

    `ibmcloud plugin install vpc-infrastructure`

6. Verify the installed plugins using the command:

    `ibmcloud plugin list`

7. Login to IBM Cloud using the command:

    `ibmcloud loginFor SSO / One-time passcode login:ibmcloud login -a https://cloud.ibm.com --sso -r us-south -g Default`

8. Set the resource group using the command:

    `ibmcloud target -g sandbox-rg`

9. List the VPCs using the command:

    `ibmcloud is vpcs`

10. List the subnets using the command:

    `ibmcloud is subnets`

11. List the virtual server instances using the command:
    `ibmcloud is instances`

12. Check the regions and zones using the commands:

    `ibmcloud is regions`
    `ibmcloud is zones`

13. Following are the basic CLI verification commands:

* `ibmcloud --version`
* `ibmcloud help`
* `ibmcloud target`
