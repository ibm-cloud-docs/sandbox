---
copyright:
  years: 2026
lastupdated: "2026-05-04"

keywords: activity tracking, events, sandbox

subcollection: sandbox
---

{{site.data.keyword.attribute-definition-list}}

# Activity tracking events for Sandbox
{: #at_events}

Activity tracking events report on activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use the events to investigate abnormal activity and critical actions and to comply with regulatory audit requirements.
{: shortdesc}

Account administrators can use {{site.data.keyword.atracker_full_notm}}, a platform service, to route auditing events in the account to destinations of their choice by configuring targets and routes that define where activity tracking events are sent. For more information, see [About {{site.data.keyword.atracker_full_notm}}](/docs/atracker?topic=atracker-about).

Account administrators can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in the account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

Users with trusted profiles may not have access to view Activity Tracker or Logs data. Contact your account administrator for access to auditing information.
{: note}

## Locations where activity tracking events are generated
{: #at-locations}

{{site.data.keyword.sandbox_full_notm}} sends activity tracking events by {{site.data.keyword.atracker_full_notm}} in the regions that are indicated in the following table.

| Dallas ( `us-south` ) | Washington ( `us-east` ) | Toronto ( `ca-tor` ) | Montreal ( `ca-mon` ) | Sao Paulo ( `br-sao` ) |
|---|---|---|---|---|
| [No]{: tag-red} | [Yes]{: tag-green} | [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Americas locations" caption-side="top"}
{: #atracker-table-1}
{: tab-title="Americas"}
{: tab-group="atracker"}
{: class="simple-tab-table"}

| Tokyo ( `jp-tok` ) | Sydney ( `au-syd` ) | Osaka ( `jp-osa` ) | Chennai ( `in-che` ) |
|---|---|---|---|
| [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Asia Pacific locations" caption-side="top"}
{: #atracker-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="atracker"}
{: class="simple-tab-table"}

| Frankfurt (`eu-de`) | London (`eu-gb`) | Madrid (`eu-es`) |
|---|---|---|
| [Yes]{: tag-green} | [No]{: tag-red} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Europe locations" caption-side="top"}
{: #atracker-table-3}
{: tab-title="Europe"}
{: tab-group="atracker"}
{: class="simple-tab-table"}

## Enabling activity tracking events for {{site.data.keyword.sandbox_full_notm}}
{: #at-enable}

No special steps are required. Activity tracking events for {{site.data.keyword.sandbox_full_notm}} are automatically enabled and forwarded to {{site.data.keyword.logs_full_notm}} via {{site.data.keyword.atracker_full_notm}}.

## Viewing activity tracking events for {{site.data.keyword.sandbox_full_notm}}
{: #at-viewing}

Account administrators can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in the account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

Users with trusted profiles typically do not have permissions to access {{site.data.keyword.logs_full_notm}} or {{site.data.keyword.atracker_full_notm}} data. If you need to view activity tracking events, contact your account administrator.
{: important}

### Launching {{site.data.keyword.logs_full_notm}}
{: #log-launch-standalone}

For information on launching the {{site.data.keyword.logs_full_notm}} UI, see [Launching the UI in the {{site.data.keyword.logs_full_notm}} documentation](/docs/cloud-logs?topic=cloud-logs-instance-launch).

## List of management events
{: #at_actions}

The following table lists the management actions that generate activity tracking events in Sandbox.

| Action | Description |
|---|---|
| `sandbox.invite.create` | Generated when a user submits a request to create a sandbox invitation. |
| `sandbox.resource.create` | Generated when sandbox resources are provisioned for an approved invite. This is an asynchronous operation. |
| `sandbox.invite.update` | Generated when a user extends the sandbox trial period for an existing invite. |
| `sandbox.invite.delete` | Generated when a sandbox invitation is deleted. |
| `sandbox.configuration.export` | Generated when a user exports the Terraform configuration for a sandbox. |
| `sandbox.user.create` | Generated when bulk user data is added or updated. |
{: caption="Actions that generate management events" caption-side="bottom"}

## Analyzing {{site.data.keyword.sandbox_full_notm}} activity tracking events
{: #at_events_iam_analyze}

Use the following fields in the CADF event to filter and correlate sandbox events:

| Field | Description |
|---|---|
| `action` | The AT action string (for example, `sandbox.invite.create`). Use this field to filter events by operation type. |
| `target.id` | The CRN of the sandbox resource on which the action was performed. |
| `outcome` | The result of the operation: `success`, `failure`, or `pending`. Search for `failure` to identify problems. |
| `severity` | The criticality of the action: `normal`, `warning`, or `critical`. Search for `critical` to surface security-relevant events such as authorization failures and deletions. |
| `initiator.id` | The IBMid or Service ID of the entity that initiated the action. |
| `correlationId` | Links related events together — especially the initial `pending` and final completion events for asynchronous provisioning operations (`sandbox.resource.create`). |
| `reason.reasonCode` | The HTTP status code of the operation. |
| `reason.reasonType` | A human-readable reason for the outcome, populated for all `failure` events. Includes detailed IBM IAM authorization deny reasons. |
