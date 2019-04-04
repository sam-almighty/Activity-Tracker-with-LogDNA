---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, services

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


# Cloud services
{: #cloud_services}

Use the {{site.data.keyword.at_full}} service to monitor user-initiated activities that change the state of any of the following services in the {{site.data.keyword.cloud_notm}}.
{:shortdesc}


## Platform core integrated services
{: #platform_core_integrated}

Core platform services generate events that you can view through the **us-south** {{site.data.keyword.at_full_notm}} web UI.

The following table lists core platform services that send events to {{site.data.keyword.at_full_notm}}:

| Service     | Description | {{site.data.keyword.at_full_notm}} events |
|-------------|-------------|-------------|
| [Provisioning and managing catalog services for resources that are managed by {{site.data.keyword.iamshort}} (IAM)](/docs/overview?topic=overview-ui#catalogcreate) | You can provision a service instance, rename a service instance, change the plan of a service instance, and remove a service instance. | [Events that are generated when you interact with catalog services ](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_rc#at_events_rc) |  
| [Managing an account](/docs/account?topic=account-accounts#accounts) | You can sign up for an {{site.data.keyword.IBM_notm}} account by using an existing IBMid, creating a new IBMid, or by using a federated ID. | [Events that are generated when you manage an account](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [Managing users](/docs/iam?topic=iam-iamuserinv#iamusermanage) | You can view and manage users across the account or organizations that you own or manage.  | [Events that are generated when you manage users ](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_users) |
{: caption="List of core platform actions" caption-side="top"} 




## Platform integrated security services
{: #platform_integrated_security}

Integrated security services generate events that you can view through the **us-south** {{site.data.keyword.at_full_notm}} web UI.


The following table lists core security platform services that send events to {{site.data.keyword.at_full_notm}}:

| Service     | Description | {{site.data.keyword.at_full_notm}} events |
|-------------|-------------|-------------|
| [{{site.data.keyword.iamlong}} (IAM)](/docs/iam?topic=iam-userroles#userroles) | You can use IAM to manage users and roles across the {{site.data.keyword.cloud_notm}} Platform and Infrastructure services. | [Events that are generated when you manage IAM policies](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_iam#at_events_iam_policies) |
| [Managing access groups](/docs/iam?topic=iam-groups#groups) | You can define access groups to organize a set of users and service IDs into a single entity that makes it easy for you to assign permissions. | [Events that are generated when you manage access groups](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_iam#at_events_iam_access) |
{: caption="List of core security platform services" caption-side="top"} 






