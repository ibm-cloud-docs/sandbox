---

copyright:
  years: 2026
lastupdated: "2026-05-04"

keywords: sandbox troubleshooting, sandbox provisioning issues, sandbox access problems, sandbox connectivity, sandbox resources

subcollection: sandbox

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Troubleshooting {{site.data.keyword.sandbox_full_notm}}
{: #troubleshoot-sandbox}

General troubleshooting tips and answers to common questions about using {{site.data.keyword.sandbox_full_notm}}.
{: shortdesc}

## Why cannot I create a sandbox?
{: #ts-cannot-create-sandbox}
{: troubleshoot}
{: support}

You receive an error message when attempting to create a sandbox environment.

You might see one of the following error messages:
{: tsSymptoms}

- "Only one sandbox is allowed per account"
- "You are not authorized to create a sandbox"
- "Sandbox service is not available in your account"

This issue can occur for several reasons:
{: tsCauses}

- You already have an active sandbox in your account. Only one sandbox is allowed per allow-listed customer account.
- Your account is not allow-listed for the sandbox service.
- You don't have the required IAM permissions (administrator access) to create a sandbox.

Try the following solutions:
{: tsResolve}

1. Check if you already have an active sandbox by navigating to your [Resource list](https://cloud.ibm.com/resources){: external} and searching for "sandbox".
2. If you have an existing sandbox that you no longer need, delete it using the **End Sandbox** option before creating a new one.
3. Verify that your account is allow-listed by checking for the sandbox invitation email or contacting {{site.data.keyword.Bluemix_notm}} support.
4. Ensure you have administrator access in your {{site.data.keyword.Bluemix_notm}} account. Contact your account administrator to grant the necessary permissions.

## Why is my sandbox provisioning taking longer than expected?
{: #ts-slow-provisioning}
{: troubleshoot}
{: support}

Your sandbox environment is taking more than 10 minutes to provision.

The sandbox provisioning status shows "In Progress" for an extended period, typically longer than 10-15 minutes.
{: tsSymptoms}

Sandbox provisioning typically takes 5-10 minutes but can be delayed due to:
{: tsCauses}

- High demand on {{site.data.keyword.Bluemix_notm}} infrastructure in the selected region
- Backend service availability issues
- Network connectivity problems during provisioning

Try the following solutions:
{: tsResolve}

1. Wait for up to 20 minutes before taking action, as some provisioning operations may take longer during peak times.
2. Refresh your browser and check the [Resource list](https://cloud.ibm.com/resources){: external} to see if the sandbox appears.
3. Check your email for the "Welcome to your IBM Cloud Sandbox" notification, which confirms successful provisioning.
4. If provisioning fails or takes longer than 30 minutes, delete the failed instance and try creating a new sandbox in a different region.
5. Contact {{site.data.keyword.Bluemix_notm}} support if the issue persists.

## Why cannot I access my sandbox trusted profile?
{: #ts-cannot-access-profile}
{: troubleshoot}
{: support}

You cannot switch to or access your sandbox trusted profile.

When attempting to access the sandbox, you cannot find the trusted profile in the account drop-down menu, or you receive an "Access Denied" error.
{: tsSymptoms}

This issue can occur for several reasons:
{: tsCauses}

- The sandbox provisioning is not yet complete
- Your trusted profile has expired (after the 14-day trial period)
- You were not added as a user during sandbox creation
- Browser cache or session issues

Try the following solutions:
{: tsResolve}

1. Verify that you received the "Welcome to your IBM Cloud Sandbox" email, which indicates successful provisioning.
2. Check the account drop-down menu for a trusted profile with the tag `sandbox expires mm/dd`.
3. Clear your browser cache and cookies, then log out and log back in to {{site.data.keyword.Bluemix_notm}}.
4. If the sandbox trial period has expired, the trusted profile is automatically deleted. You'll need to create a new sandbox.
5. Verify that you were added as a user during the initial sandbox creation. If not, contact the sandbox creator to be added.
6. Try accessing the sandbox from a different browser or in incognito/private mode.

## Why cannot I create resources in my sandbox?
{: #ts-cannot-create-resources}
{: troubleshoot}
{: support}

You receive an error when attempting to create resources in your sandbox environment.

When clicking **Create Resources** or attempting to provision servers, you see error messages such as "Insufficient permissions" or "Resource creation failed".
{: tsSymptoms}

This issue can occur for several reasons:
{: tsCauses}

- You don't have write access (administrator, editor, or operator role)
- You've reached the resource quota limits for your sandbox
- The selected region doesn't support the requested resource type
- The sandbox trial period has expired

Try the following solutions:
{: tsResolve}

1. Verify that you have write access by checking your role in the sandbox. Only users with administrator, editor, or operator roles can create resources.
2. Check if you've reached resource quota limits by reviewing your existing resources in the [Resource list](https://cloud.ibm.com/resources){: external}.
3. If provisioning Bare Metal servers, ensure you selected a region that supports Bare Metal during sandbox creation.
4. Verify that your sandbox trial period hasn't expired by checking the expiration date in the trusted profile tag.
5. Try creating a different resource type or reducing the number of instances.
6. Contact the sandbox administrator to adjust your permissions if needed.

## Why is my VPC creation failing?
{: #ts-vpc-creation-fails}
{: troubleshoot}
{: support}

VPC resource creation fails with an error message.

When attempting to create VPC resources in Sandbox Overview page, you receive error messages such as "VPC creation failed" or "Unable to provision network resources".
{: tsSymptoms}

VPC creation can fail due to:
{: tsCauses}

- Insufficient IP address space in the selected region
- Conflicting network configurations
- Resource quota limits reached
- Region-specific service availability issues

Try the following solutions:
{: tsResolve}

1. Verify that you're creating resources in the same region selected during sandbox provisioning.
2. Check for any existing VPC resources that might conflict with the new configuration.
3. Review your resource quotas to ensure you haven't exceeded limits for VPCs, subnets, or security groups.
4. Try creating the VPC with default settings first, then customize after successful creation.
5. Ensure that all the required fields are properly filled out in the Sandbox Overview page.
6. Wait a few minutes and retry the operation, as temporary service issues may resolve automatically.

## Why cannot I SSH into my Virtual Server Instance?
{: #ts-cannot-ssh}
{: troubleshoot}
{: support}

You cannot establish an SSH connection to your Virtual Server Instance.

When attempting to SSH into your VSI, the connection times out or you receive "Connection refused" or "Permission denied" errors.
{: tsSymptoms}

SSH connectivity issues can occur due to:
{: tsCauses}

- Security group rules blocking SSH traffic (port 22)
- Incorrect SSH key configuration
- The VSI is not assigned a public IP address
- Network ACL rules blocking traffic
- The VSI is not fully provisioned or is in a stopped state

Try the following solutions:
{: tsResolve}

1. Verify that your security group allows inbound traffic on port 22 (SSH). Add a rule to allow SSH from your IP address if needed.
2. Ensure you're using the correct SSH private key that corresponds to the public key configured during VSI creation.
3. Check that your VSI has a public IP address assigned if you're connecting from outside the VPC. Navigate to the VSI details page to verify.
4. Review network ACL rules to ensure they're not blocking SSH traffic.
5. Verify that the VSI status is "Running" in the {{site.data.keyword.Bluemix_notm}} Console.
6. If using VPN for VPC, ensure your VPN connection is active and properly configured.
7. Try connecting from a different network or location to rule out local firewall issues.

## Why is my sandbox extension failing?
{: #ts-extension-fails}
{: troubleshoot}
{: support}

You cannot extend your sandbox trial period.

When attempting to extend your sandbox using the **Extend Sandbox** option, you receive an error message or the extension doesn't apply.
{: tsSymptoms}

Sandbox extension can fail due to:
{: tsCauses}

- You've already used your one-time 2-day extension
- The sandbox has already expired
- System issues preventing the extension operation

Try the following solutions:
{: tsResolve}

1. Verify that you haven't already extended your sandbox. Each sandbox is eligible for only one 2-day extension.
2. Check the current expiration date in your trusted profile tag to ensure the sandbox hasn't already expired.
3. Ensure you're requesting the extension before the trial period ends. Extensions cannot be applied after expiration.
4. Refresh your browser and try the extension operation again.
5. If the issue persists, save your sandbox configuration using the **Manage Sandbox** option and create a new sandbox if needed.

## Why cannot I save my sandbox configuration?
{: #ts-cannot-save-config}
{: troubleshoot}
{: support}

The configuration download fails when attempting to save your sandbox setup.

When clicking **Manage Sandbox** and attempting to download the Terraform configuration, the download fails or produces an incomplete file.
{: tsSymptoms}

Configuration save issues can occur due to:
{: tsCauses}

- Browser download restrictions or pop-up blockers
- Insufficient resources created in the sandbox
- Temporary service issues generating the Terraform package
- Network connectivity problems during download

Try the following solutions:
{: tsResolve}

1. Disable pop-up blockers in your browser and allow downloads from cloud.ibm.com.
2. Ensure you have created resources in your sandbox before attempting to save the configuration.
3. Try downloading the configuration using a different browser.
4. Check your browser's download folder for the ZIP file, as it may have downloaded without notification.
5. Verify you have sufficient disk space for the download.
6. Wait a few minutes and retry the download operation.

## Why are my sandbox resources not appearing in the resource list?
{: #ts-resources-not-visible}
{: troubleshoot}
{: support}

Resources you created in the sandbox are not visible in the resource list.

After creating resources in your sandbox, they don't appear in the {{site.data.keyword.Bluemix_notm}} resource list or sandbox overview page.
{: tsSymptoms}

Resources may not be visible due to:
{: tsCauses}

- You're viewing the wrong account (not switched to the sandbox trusted profile)
- Resource provisioning is still in progress
- Browser cache issues
- Resource creation actually failed but didn't show an error

Try the following solutions:
{: tsResolve}

1. Verify that you're switched to the sandbox trusted profile by checking the account drop-down menu.
2. Refresh the resource list page to update the view.
3. Wait 2-3 minutes for newly created resources to appear, as there may be a delay in updating the list.
4. Clear your browser cache and reload the page.
5. Check the Activity Tracker or audit logs to verify if resources were actually created.
6. Navigate directly to the specific service page (e.g., VPC Infrastructure) to see if resources appear there.

## Why did I receive a sandbox suspension notification?
{: #ts-sandbox-suspended}
{: troubleshoot}
{: support}

You received an email notification that your sandbox account has been suspended.

Your sandbox account shows as suspended, and you cannot access or create resources.
{: tsSymptoms}

Sandbox suspension occurs when:
{: tsCauses}

- No resources were created by day 7 of the trial period
- Terms of service violations were detected
- Unusual activity patterns were identified

Try the following solutions:
{: tsResolve}

1. If suspended due to inactivity (no resources created by day 7), create resources immediately to reactivate the sandbox.
2. Review the suspension email for specific reasons and required actions.
3. Contact {{site.data.keyword.Bluemix_notm}} support to understand the suspension reason and request reactivation if appropriate.
4. Ensure you're using the sandbox for legitimate testing and evaluation purposes only.
5. If the suspension cannot be resolved, you may need to create a new sandbox after the current one expires.

## Why cannot I add or modify users in my sandbox?
{: #ts-cannot-modify-users}
{: troubleshoot}
{: support}

You cannot add new users or change user permissions in your sandbox.

When attempting to add users or modify their roles, the options are unavailable or changes don't take effect.
{: tsSymptoms}

User management limitations exist because:
{: tsCauses}

- Users can only be added during initial sandbox creation
- User roles are fixed and cannot be modified after creation
- This is a design limitation of the sandbox environment

This is expected behavior:
{: tsResolve}

1. Users can only be added during the initial sandbox provisioning step, not after creation.
2. Once users are added and the sandbox is created, the user list and their roles remain unchanged throughout the trial period.
3. If you need to add additional users or change permissions, you must delete the current sandbox and create a new one with the desired user configuration.
4. Plan your user access requirements carefully before creating the sandbox to avoid this limitation.

## Why cannot I access resources in a different region?
{: #ts-wrong-region}
{: troubleshoot}
{: support}

You cannot access or create resources in regions other than the one selected during provisioning.

When attempting to create resources or view services in different regions, you receive access denied errors or don't see the expected options.
{: tsSymptoms}

Region access is restricted because:
{: tsCauses}

- The region is locked during sandbox creation and cannot be changed
- IAM policies restrict access to only the selected region
- This is a design limitation to ensure resource isolation

This is expected behavior:
{: tsResolve}

1. Verify which region was selected during sandbox creation by checking the sandbox details.
2. All resources must be created in the region selected during provisioning.
3. You cannot change the region after sandbox creation.
4. If you need to test resources in a different region, you must delete the current sandbox and create a new one with the desired region.
5. Plan your region selection carefully based on your testing requirements before creating the sandbox.

## Why is my Load Balancer not distributing traffic correctly?
{: #ts-load-balancer-issues}
{: troubleshoot}
{: support}

The Load Balancer is not distributing traffic to your server instances as expected.

Traffic is not being balanced across instances, or the Load Balancer shows unhealthy backend servers.
{: tsSymptoms}

Load Balancer issues can occur due to:
{: tsCauses}

- Incorrect health check configuration
- Backend servers are not running or not responding
- Security group rules blocking Load Balancer health checks
- Application not listening on the configured port

Try the following solutions:
{: tsResolve}

1. Verify that all backend server instances are in "Running" state.
2. Check that your application is running and listening on the port configured in the Load Balancer.
3. Review security group rules to ensure they allow traffic from the Load Balancer to backend instances.
4. Verify health check settings (protocol, port, path) match your application configuration.
5. Check Load Balancer logs for specific error messages or health check failures.
6. Ensure backend instances are in the same VPC and subnet as configured in the Load Balancer.
7. Test direct connectivity to backend instances to rule out application issues.

## Why cannot I connect through VPN for VPC?
{: #ts-vpn-connection-fails}
{: troubleshoot}
{: support}

You cannot establish a VPN connection to your sandbox environment.

VPN connection attempts fail, time out, or show as disconnected in the VPN client.
{: tsSymptoms}

VPN connectivity issues can occur due to:
{: tsCauses}

- Incorrect VPN configuration parameters
- Firewall rules blocking VPN traffic (UDP ports 500, 4500)
- Incompatible VPN client or settings
- Network ACL or security group rules blocking VPN traffic

Try the following solutions:
{: tsResolve}

1. Verify that you're using the correct VPN gateway IP address and pre-shared key from the {{site.data.keyword.Bluemix_notm}} Console.
2. Ensure your local firewall allows UDP traffic on ports 500 and 4500 for IPsec VPN.
3. Check that your VPN client supports the IPsec protocols configured in VPN for VPC.
4. Review security group rules to allow VPN traffic to your VPC resources.
5. Verify network ACL rules are not blocking VPN connections.
6. Try connecting from a different network to rule out local network restrictions.
7. Check VPN gateway status in the {{site.data.keyword.Bluemix_notm}} Console to ensure it's active.

## Why is my Transit Gateway not connecting Classic and VPC resources?
{: #ts-transit-gateway-issues}
{: troubleshoot}
{: support}

Resources in Classic Infrastructure and VPC cannot communicate through the Transit Gateway.

Network traffic between Classic and VPC resources fails, or resources cannot reach each other.
{: tsSymptoms}

Transit Gateway connectivity issues can occur due to:
{: tsCauses}

- Incorrect routing configuration
- Overlapping IP address ranges between Classic and VPC
- Security group or firewall rules blocking traffic
- Transit Gateway not properly attached to both networks

Try the following solutions:
{: tsResolve}

1. Verify that the Transit Gateway is properly connected to both Classic Infrastructure and VPC networks.
2. Check for IP address conflicts between Classic and VPC subnets.
3. Review routing tables to ensure proper routes exist for cross-network communication.
4. Verify security group rules allow traffic between Classic and VPC resources.
5. Check that both source and destination resources have appropriate network configurations.
6. Test connectivity using ping or traceroute to identify where traffic is being blocked.
7. Review Transit Gateway status and connection state in the {{site.data.keyword.Bluemix_notm}} Console.

## Getting help and support
{: #ts-getting-help}

If you continue to experience issues with {{site.data.keyword.sandbox_full_notm}} after trying these troubleshooting steps, you can get help through the following resources:

- Review the [{{site.data.keyword.sandbox_full_notm}} documentation](/docs/sandbox)
- Check the [FAQ](/docs/sandbox?topic=sandbox-my-service-faq) for common questions
- Contact [{{site.data.keyword.Bluemix_notm}} Support](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}
- Search for similar issues in the [{{site.data.keyword.Bluemix_notm}} Community](https://community.ibm.com/community/user/cloud/home){: external}

When contacting support, provide the following information:
- Your sandbox name and creation date
- The specific error messages you're receiving
- Steps you've already taken to troubleshoot
- Screenshots of the issue (if applicable)
- Your {{site.data.keyword.Bluemix_notm}} account ID
