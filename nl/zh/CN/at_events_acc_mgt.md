---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# 帐户管理事件  
{: #at_events_acc_mgt}

作为安全主管、审计员或管理者，您可以使用 {{site.data.keyword.at_full_notm}} 服务来跟踪用户和应用程序与 {{site.data.keyword.cloud_notm}} 帐户的交互方式。
{:shortdesc}

{{site.data.keyword.at_full_notm}} 服务记录由用户启动的会更改 {{site.data.keyword.cloud_notm}} 中服务状态的活动。要开始使用，请参阅 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。 



## 用于管理帐户的事件
{: #at_events_acc_mgt_account}

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------------|-------------|
|`billing.account.create`|在帐户标识分配给帐户并供应此帐户后，将生成事件。|
|`billing.account.update`|更新帐户相关信息时，将生成事件。|
|`billing.account.active`|验证帐户时，将生成事件，即，当帐户变为活动状态时将生成事件。|
|`billing.account.subscription.create`|创建<a href="/docs/account?topic=account-accounts#subscription-account">预订帐户</a>时，将生成事件。|
{: caption="表 1. 生成事件的操作" caption-side="top"} 




## 用于管理用户的事件
{: #at_events_acc_mgt_users}

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------------|-------------|
|`user-management.user.create`|向用户发送加入帐户邀请时，将生成事件。|
|`user-management.user.active`|激活帐户中用户时，将生成事件。用户验证其电子邮件地址时，也将生成该事件。|
|`user-management.user.delete`|从帐户中除去用户时，将生成事件。|
{: caption="表 2. 生成事件的操作" caption-side="top"} 




## 用于管理组织的事件
{: #at_events_acc_mgt_org}

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------------|-------------|
|`billing.account.org.create`|将组织添加到帐户时，将生成事件。|
{: caption="表 3. 生成事件的操作" caption-side="top"} 


## 有关管理标记的事件
{: #at_events_acc_mgt_resources}

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------------|-------------|
|`ghost-tags.tag.attach-tag`|向资源添加标记时，将生成事件。|
|`ghost-tags.tag.detach-tag`|从资源中除去标记时，将生成事件。|
{: caption="表 4. 生成事件的操作" caption-side="top"} 


## 在何处查找事件
{: #at_events_acc_mgt_ui}

事件在**法兰克福 (eu-de)** 区域中可用。 

要查看这些事件，必须在**法兰克福 (eu-de)** 区域中为 {{site.data.keyword.at_full_notm}} 服务[供应实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然后，必须[打开 {{site.data.keyword.at_full_notm}} UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 












