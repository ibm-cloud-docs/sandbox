---
copyright:
  years: 2026
lastupdated: "2026-04-23"

keywords: activity tracking, events, sandbox

subcollection: sandbox
---

{{site.data.keyword.attribute-definition-list}}

# Activity tracking events for Sandbox
{: #at_events}

Activity tracking events report on activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use the events to investigate abnormal activity and critical actions and to comply with regulatory audit requirements.
{: shortdesc}

You can use {{site.data.keyword.atracker_full_notm}}, a platform service, to route auditing events in your account to destinations of your choice by configuring targets and routes that define where activity tracking events are sent. For more information, see [About {{site.data.keyword.atracker_full_notm}}](/docs/atracker?topic=atracker-about).

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in your account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

## Locations where activity tracking events are generated
{: #at-locations}

IBM Cloud Sandbox sends activity tracking events by {{site.data.keyword.atracker_full_notm}} in the regions that are indicated in the following table.

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

## Enabling activity tracking events for IBM Cloud Sandbox
{: #at-enable}

No special steps are required. Activity tracking events for IBM Cloud Sandbox are automatically enabled and forwarded to {{site.data.keyword.logs_full_notm}} via {{site.data.keyword.atracker_full_notm}}.

## Viewing activity tracking events for IBM Cloud Sandbox
{: #at-viewing}

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in your account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

### Launching {{site.data.keyword.logs_full_notm}} from the IBM Cloud Sandbox dashboard
{: #log-launch-integrated}

IBM Cloud Sandbox does not currently support integrated dashboard launching for {{site.data.keyword.logs_full_notm}}. Please use the Observability page.

### Launching {{site.data.keyword.logs_full_notm}} from the Observability page
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

## Analyzing IBM Cloud Sandbox activity tracking events
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
