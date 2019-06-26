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


# IAM 事件
{: #at_events_iam}

作为安全主管、审计员或管理者，您可以使用 {{site.data.keyword.at_full_notm}} 服务来跟踪用户和应用程序与 {{site.data.keyword.cloud_notm}} 中 {{site.data.keyword.iamlong}} (IAM) 服务的交互方式。
{:shortdesc}

通过 IAM，您能够在 {{site.data.keyword.cloud_notm}} 中安全地针对两个平台服务认证用户，并以一致的方式控制对资源的访问权。[了解更多信息](/docs/iam?topic=iam-iamoverview)。


{{site.data.keyword.at_full_notm}} 服务记录由用户启动的会更改 {{site.data.keyword.cloud_notm}} 中服务状态的活动。要开始监视用户的操作，请参阅 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。发起者可以是用户、服务或应用程序。



## 访问组事件
{: #at_events_iam_access}

下表列出了生成事件的操作：

|操作|描述|
|-----------------------------|---------|
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



## 策略事件
{: #at_events_iam_policies}

下表列出了生成事件的操作：

|操作|描述|
|------------------------|---------|
| `iam-am.policy.create` |发起方将策略添加到用户或访问组时，将生成事件。|
| `iam-am.policy.delete` |发起方修改用户或访问组的策略的许可权时，将生成事件。|
| `iam-am.policy.update` |发起方删除分配给用户或访问组的策略时，将生成事件。|
{: caption="表 5. 管理策略操作" caption-side="top"} 



## 服务标识事件
{: #at_events_iam_serviceids}

下表列出了生成事件的操作：

|操作|描述|
|----------|---------|
| `iam-identity.account-serviceid.create` |发起方创建服务标识时，将生成事件。| 
| `iam-identity.account-serviceid.update` |发起方重命名服务标识或修改其描述时，将生成事件。| 
| `iam-identity.account-serviceid.delete` |发起方删除服务标识时，将生成事件。| 
{: caption="表 2. 使用服务标识操作" caption-side="top"} 


## API 密钥事件
{: #at_events_iam_apikeys}

下表列出了生成事件的操作：

|操作|描述|
|----------|---------|
| `iam-identity.user-apikey.create`      |发起方创建 API 密钥时，将生成事件。| 
| `iam-identity.user-apikey.update`      |发起方重命名 API 密钥或修改其描述时，将生成事件。|  
| `iam-identity.user-apikey.delete`      |发起方删除 API 密钥时，将生成事件。|  
| `iam-identity.serviceid-apikey.create` |发起方创建服务标识的 API 密钥时，将生成事件。|  
| `iam-identity.serviceid-apikey.delete` |发起方删除服务标识的 API 密钥时，将生成事件。|  
{: caption="表 3. 使用 API 密钥操作" caption-side="top"} 


## 登录事件
{: #at_events_iam_login}

下表列出了生成事件的操作：

|操作|描述|
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         |用户使用 API 密钥登录到 {{site.data.keyword.cloud_notm}} 时，将生成事件。|  
| `iam-identity.serviceid-apikey.login`    |发起方使用与服务标识关联的 API 密钥登录 {{site.data.keyword.cloud_notm}} 时，将生成事件。|  
| `iam-identity.user-identitycookie.login` |这是发起方请求身份 cookie 以运行操作时生成的事件。|
| `iam-identity.user-refreshtoken.login`   |这是发起方登录到 IBM Cloud 时生成的事件，或者是已登录到 IBM Cloud 的发起方请求新的刷新令牌以执行操作时生成的事件。|
{: caption="表 4. 用户登录操作" caption-side="top"} 


## 查看事件
{: #at_events_iam_ui}

事件在**法兰克福 (eu-de)** 区域中可用。要查看这些事件，必须在**法兰克福 (eu-de)** 区域中为 {{site.data.keyword.at_full_notm}} 服务[供应实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然后，必须[打开 {{site.data.keyword.at_full_notm}} UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 


## 分析事件
{: #at_events_iam_analyze}


### 删除访问组
{: #an_del_ag}

删除访问组时，所触发事件的 `action` 字段会设置为 `iam-groups.group.delete`。

删除访问组时，请考虑以下信息：
* 其他操作会自动触发，以清除与该组关联的其他资源。触发的某些操作会报告事件，这些事件与删除访问组中的成员、删除策略和删除动态规则相关。 
* 这些操作的发起方是 {{site.data.keyword.IBM_notm}} 服务标识。


删除的访问组没有分配成员、策略和规则时，为其中任何资源生成的事件所报告的结果均为 `failure`，并且结果代码为 `404`。以下样本显示了在删除没有分配成员、策略或动态规则的访问组时所生成的事件：

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

