---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# 服务实例事件  
{: #at_events_rc}

作为安全主管、审计员或管理者，您可以使用 {{site.data.keyword.at_full_notm}} 服务来跟踪用户和应用程序与 {{site.data.keyword.cloud_notm}} 服务的交互方式。
{:shortdesc}

{{site.data.keyword.at_full_notm}} 服务记录由用户启动的会更改 {{site.data.keyword.cloud_notm}} 中服务状态的活动。要开始监视用户的操作，请参阅 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。 


## 用于供应和管理服务实例的事件
{: #rc_provision}

下表列出了生成事件的操作：

|操作| 描述 |
|--------------------------------|---------|
|`service_name.instance.create`|供应服务实例时，将生成事件。|
|`service_name.instance.update`|重命名服务实例或更改服务套餐时，将生成事件。|
|`service_name.instance.delete`|删除服务实例时，将生成事件。|
{: caption="表 1. 生成事件的操作" caption-side="top"} 


##  有关管理与服务实例相关联的别名的事件
{: #rc_alias}

别名是资源组中 IAM 管理的服务与组织或空间中的应用程序之间的连接。

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------|---------|
|`service_name.alias.create`|创建实例的别名时，将生成事件。|
|`service_name.alias.update`|更新实例的别名时，将生成事件。|
|`service_name.alias.delete`|删除实例的别名时，将生成事件。|
{: caption="表 2. 生成事件的操作" caption-side="top"} 


##  有关管理与服务实例相关联的服务凭证的事件
{: #rc_keys}

服务凭证提供了将应用程序连接到服务实例的必要信息。 

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------|---------|
|`service_name.key.create`|通过服务实例 UI 的*服务凭证*部分为服务实例创建 API 密钥时，将生成事件。|
|`service_name.key.delete`|从服务实例 UI 的*服务凭证*部分删除与服务实例相关联的 API 密钥时，将生成事件。|
{: caption="表 3. 生成事件的操作" caption-side="top"} 



##  有关将服务实例绑定到应用程序以及进行取消绑定的事件
{: #rc_bind}

下表列出了生成事件的操作：

|操作|描述|
|--------------------------------|---------|
|`service_name.binding.create`|将服务实例绑定到应用程序时，将生成事件。|
|`service_name.binding.delete`|取消服务实例与应用程序的绑定时，将生成事件。|
{: caption="表 4. 生成事件的操作" caption-side="top"} 



## 在何处查找事件
{: #rc_ui}

事件在**法兰克福 (eu-de)** 区域中可用。 

要查看这些事件，必须在**法兰克福 (eu-de)** 区域中为 {{site.data.keyword.at_full_notm}} 服务[供应实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然后，必须[打开 {{site.data.keyword.at_full_notm}} UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 



## 分析事件
{: #rc_analyze}

**操作：service_name.instance.delete**

删除服务实例时，请考虑以下信息：
* 其他操作会自动触发，以清除 IAM 许可权。这些操作将除去为帐户中的用户和服务标识配置以使用服务实例的策略。 
* 这些操作的发起方是 {{site.data.keyword.IBM_notm}} 服务标识。


删除的服务实例没有为用户和服务标识配置 IAM 策略时，为其中任何资源自动生成的事件所报告的结果均为 `failure`，并且结果代码为 `404`。以下样本显示了在删除帐户中未配置策略的服务实例时所生成的事件：

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



