---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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


# IAM 事件
{: #at_events_iam}

作为安全主管、审计员或管理者，您可以使用 {{site.data.keyword.at_full_notm}} 服务来跟踪用户和应用程序与 {{site.data.keyword.cloud_notm}} 中 {{site.data.keyword.iamlong}} (IAM) 服务的交互方式。
{:shortdesc}

{{site.data.keyword.at_full_notm}} 服务记录由用户启动的会更改 {{site.data.keyword.cloud_notm}} 中服务状态的活动。要开始监视用户的操作，请参阅 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。 

发起者可以是用户、服务或应用程序。
{: tip}

## 管理访问组事件
{: #at_events_iam_access}

下表列出了生成事件的操作：

|操作|描述|
|----------|---------|
| `iam-groups.group.create`   |发起方创建访问组时，将生成事件。| 
| `iam-groups.group.read`     |发起方查看与访问组相关的信息时，将生成事件。|
| `iam-groups.group.update`   |发起方更新组名或描述时，将生成事件。|
| `iam-groups.group.delete`   |发起方删除访问组时，将生成事件。|
| `iam-groups.member.add`     |发起方将成员添加至访问组时，将生成事件。|
| `iam-groups.member.delete`  |发起方从访问组除去成员时，将生成事件。|
| `iam-groups.member.read`    |发起方检查成员的成员资格时，将生成事件。|
| `iam-groups.rule.read`      |发起方查看访问组中的规则时，将生成事件。|
| `iam-groups.rule.create`    |发起方将规则添加至访问组时，将生成事件。|
| `iam-groups.rule.update`    |发起方修改规则名称时，将生成事件。|
| `iam-groups.rule.delete`    |发起方从访问组删除规则时，将生成事件。|
{: caption="表 1. 管理访问组操作" caption-side="top"} 




## 查看事件
{: #at_events_iam_ui}

事件在**美国南部**区域中可用。 

要查看这些事件，必须在**美国南部**区域中为 {{site.data.keyword.at_full_notm}} 服务[供应实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然后，必须[打开 {{site.data.keyword.at_full_notm}} UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 


