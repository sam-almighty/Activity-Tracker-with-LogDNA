---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

subcollection: logdnaat

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}


# IAM events
{: #at_events_iam}

As a security officer, auditor, or manager, you can use the {{site.data.keyword.at_full_notm}} service to track how users and applications interact with the {{site.data.keyword.iamlong}} (IAM) service in {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

IAM enables you to securely authenticate users for both platform services and control access to resources consistently across {{site.data.keyword.cloud_notm}}. [Learn more](/docs/iam?topic=iam-iamoverview).


The {{site.data.keyword.at_full_notm}} service records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. To get started monitoring your user's actions, see [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). An initiator can be a user, a service, or an application.


## Access groups events
{: #at_events_iam_access}

The following table lists the actions that generate an event:

| Action                      | Description |
|-----------------------------|---------|
| `iam-groups.group.create`   | An event is generated when an initiator creates an access group. | 
| `iam-groups.group.read`     | An event is generated when an initiator looks at information that is related with access groups. |
| `iam-groups.group.update`   | An event is generated when an initiator updates a group name or a description. |
| `iam-groups.group.delete`   | An event is generated when an initiator deletes an access group. |
| `iam-groups.member.add`     | An event is generated when an initiator adds a member to an access group. |
| `iam-groups.member.delete`  | An event is generated when an initiator removes a member from an access group. |
| `iam-groups.member.read`    | An event is generated when an initiator checks a member's membership. |
| `iam-groups.rule.read`      | An event is generated when an initiator views a rule in an access group. |
| `iam-groups.rule.create`    | An event is generated when an initiator adds a rule to an access group. |
| `iam-groups.rule.update`    | An event is generated when an initiator modifies the rule name. |
| `iam-groups.rule.delete`    | An event is generated when an initiator deletes a rule from an access group. |
{: caption="Table 1. Manage access groups actions" caption-side="top"} 



## Policy events
{: #at_events_iam_policies}

The following table lists the actions that generate an event:

| Action                 | Description |
|------------------------|---------|
| `iam-am.policy.create` | An event is generated when an initiator adds a policy to a user or access group. |
| `iam-am.policy.delete` | An event is generated when an initiator modifies permissions to a policy of a user or access group.|
| `iam-am.policy.update` | An event is generated when an initiator deletes a policy that is assigned to a user or access group. |
{: caption="Table 5. Managing policy actions" caption-side="top"} 



## Service ID events
{: #at_events_iam_serviceids}

The following table lists the actions that generate an event:

| Action | Description |
|----------|---------|
| `iam-identity.account-serviceid.create` | An event is generated when an initiator creates a service ID.  | 
| `iam-identity.account-serviceid.update` | An event is generated when an initiator renames a service ID or modifies its description. | 
| `iam-identity.account-serviceid.delete` | An event is generated when an initiator deletes a service ID. | 
{: caption="Table 2. Working with service IDs actions" caption-side="top"} 


## API key events
{: #at_events_iam_apikeys}

The following table lists the actions that generate an event:

| Action | Description |
|----------|---------|
| `iam-identity.user-apikey.create`      | An event is generated when an initiator creates an API key. | 
| `iam-identity.user-apikey.update`      | An event is generated when an initiator renames an API key or modifies its description. |  
| `iam-identity.user-apikey.delete`      | An event is generated when an initiator deletes an API key. |  
| `iam-identity.serviceid-apikey.create` | An event is generated when an initiator creates an API key for a service ID. |  
| `iam-identity.serviceid-apikey.delete` | An event is generated when an initiator deletes an API key for a service ID. |  
{: caption="Table 3. Working with API keys actions" caption-side="top"} 


## Login events
{: #at_events_iam_login}

The following table lists the actions that generate an event:

| Action                                   | Description |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | An event is generated when a user logs in to the {{site.data.keyword.cloud_notm}} by using an API key. |  
| `iam-identity.serviceid-apikey.login`    | An event is generated when an initiator logs in to the {{site.data.keyword.cloud_notm}} by using an API key that is associated with a service ID. |  
| `iam-identity.user-identitycookie.login` | This is an event that is generated when an initiator requests an identity cookie to run an action. |
| `iam-identity.user-refreshtoken.login`   | This is an event that is generated when the initiator logs in to the IBM Cloud , or when an initiator that has already logged in to the IBM Cloud requests a new refresh token to run an action. |
{: caption="Table 4. User login actions" caption-side="top"} 


## Viewing events
{: #at_events_iam_ui}

Events are available in the **Frankfurt (eu-de)** region. To view these events, you must [provision an instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) of the {{site.data.keyword.at_full_notm}} service in the **Frankfurt (eu-de)** region. Then, you must [open the {{site.data.keyword.at_full_notm}} UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


## Analyzing events
{: #at_events_iam_analyze}


### Delete an access group
{: #an_del_ag}

When you delete an access group, the event that is triggered has an `action` field set to `iam-groups.group.delete`.

When an access group is deleted, consider the following information:
* Other actions are automatically triggered to clean up other resources that are associated with the group. Some actions that are triggered report events that are related to deletion of members in an access group, deletion of policies, and deletion of dynamic rules. 
* The initiator of these actions is an {{site.data.keyword.IBM_notm}} service ID.


When the access group that is deleted does not have members, policies, and rules assigned, the events that are generated for any of these resources report an outcome of`failure` with a `404` outcome code. The following sample shows the events that are generated when an access group that does not have members, policies or dynamic rules assigned is deleted:

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

