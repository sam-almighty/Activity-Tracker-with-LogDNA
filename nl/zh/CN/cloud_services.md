---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{:important: .important}
{:note: .note}


# 云服务
{: #cloud_services}

使用 {{site.data.keyword.at_full}} 服务可监视用户发起的用于更改 {{site.data.keyword.cloud_notm}} 中以下任一服务状态的活动。
{:shortdesc}


## 平台核心集成服务
{: #platform_core_integrated}


核心平台服务会生成可以通过**法兰克福 (eu-de)** {{site.data.keyword.at_full_notm}} Web UI 查看的事件。要查看这些事件，必须在**法兰克福 (eu-de)** 区域中为 {{site.data.keyword.at_full_notm}} 服务[供应实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。
{: note}

下表列出了将事件发送到 {{site.data.keyword.at_full_notm}} 的核心平台操作：

|操作|描述|{{site.data.keyword.at_full_notm}} 事件|
|----------------------------------|-------------|-------------------------------------------|
|[管理帐户](/docs/account?topic=account-accounts#accounts)|您可以通过使用现有 IBM 标识、创建新 IBM 标识或使用联合标识来注册 {{site.data.keyword.IBM_notm}} 帐户。| [管理帐户时生成的事件](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
|[管理用户](/docs/iam?topic=iam-iamuserinv#iamusermanage)|您可以查看和管理自己所拥有或管理的帐户或组织中的用户。| [管理用户时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
|[管理组织](/docs/account?topic=account-orgsspacesusers#orgsspacesusers)|如果您是帐户所有者，那么可以向帐户中添加组织，还可以管理组织。| [管理组织时生成的事件](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
|[供应和管理启用 {{site.data.keyword.iamshort}} (IAM) 的目录服务](/docs/overview?topic=overview-ui#catalogcreate)|您可以供应服务实例，重命名服务实例，更改服务实例的套餐以及除去服务实例。| [与目录服务交互时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
|[使用服务别名](/docs/resources?topic=resources-connect_app#what_is_alias)|别名是资源组中 IAM 管理的服务与组织或空间中的应用程序之间的连接。|[有关管理与服务实例相关联的别名的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias)| 
|[使用服务凭证](/docs/resources?topic=resources-service_credentials#service_credentials)|服务凭证提供了将应用程序连接到服务实例的必要信息。|[有关管理与服务实例相关联的服务凭证的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys)| 
|[将服务实例绑定到应用程序](/docs/resources?topic=resources-s2s_binding#s2s_binding)|您可以在空间中生成具有相同名称的服务实例的 Cloud Foundry (CF) 实例或别名。|[有关将服务实例绑定到应用程序以及进行取消绑定的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind)|
|[管理标记](/docs/resources?topic=resources-tag)|标记是您为资源分配的标签，用于对资源列表中的资源进行轻松过滤。|[有关管理标记的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources)|
{: caption="核心平台操作的列表" caption-side="top"} 






## 平台集成安全服务
{: #platform_integrated_security}

集成安全服务会生成可以通过**法兰克福 (eu-de)** {{site.data.keyword.at_full_notm}} Web UI 查看的事件。要查看这些事件，必须在**法兰克福 (eu-de)** 区域中为 {{site.data.keyword.at_full_notm}} 服务[供应实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。
{: note}

下表列出了将事件发送到 {{site.data.keyword.at_full_notm}} 的核心安全平台操作：

| 操作                                                                    |描述|{{site.data.keyword.at_full_notm}} 事件|
|-------------------------------------------------------------|-------------|-------------------------------------------|
|[管理访问组](/docs/iam?topic=iam-groups#groups)|您可以定义访问组，以便将一组用户和服务标识组织到单个实体中，从而轻松地分配许可权。|[管理访问组时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)|
|[管理策略](/docs/iam?topic=iam-userroles#userroles)|您可以使用 IAM 来管理 {{site.data.keyword.cloud_notm}} 平台和基础架构服务中的用户和角色。| [管理 IAM 策略时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
|[登录到 {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)|您可以使用密码、API 密钥、授权代码或通行码来登录到 {{site.data.keyword.cloud_notm}}。如果您是联合用户，那么可以使用一次性密码或 API 密钥从命令行界面 (CLI) 进行登录。|[用户或应用程序登录到 {{site.data.keyword.cloud_notm}} 时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)|
|[管理平台 API 密钥](/docs/iam?topic=iam-manapikey#platform-api-keys)|您可以在 {{site.data.keyword.IBM_notm}} Cloud 中定义与用户或服务标识相关联的平台 API 密钥。| [管理平台 API 密钥时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
|[管理服务标识](/docs/iam?topic=iam-serviceids#serviceids)|在 {{site.data.keyword.IBM_notm}} Cloud 中，您可以在帐户级别定义服务标识。| [管理服务标识时生成的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="核心安全平台服务的列表" caption-side="top"} 



## 平台集成服务
{: #integration}

下表列出了将事件发送到 {{site.data.keyword.cloudaccesstrailshort}} 的集成服务：

|服务|描述|{{site.data.keyword.cloudaccesstrailshort}} 事件|
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)|{{site.data.keyword.messagehub}} 是使用 Apache Kafka 构建的高吞吐量消息传递总线。它已针对将事件获取到 {{site.data.keyword.IBM_notm}} 中以及在服务和应用程序之间进行事件流分发进行了优化。| [{{site.data.keyword.messagehub}} 生成的事件](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="将事件发送到 {{site.data.keyword.cloudaccesstrailshort}} 的集成云服务的列表" caption-side="top"} 



## 平台网络服务
{: #network}

下表列出了将事件发送到 {{site.data.keyword.at_full_notm}} 的网络服务：

|服务|描述|{{site.data.keyword.at_full_notm}} 事件|
|-------------|-------------|-------------|
|[IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)|IBM Cloud Internet Services (CIS) 提供了一个快速、高性能、可靠且安全的因特网服务。|[IBM Cloud Internet Services 生成的事件](/docs/infrastructure/cis?topic=cis-at_events#at_events)|  
{: caption="网络服务列表" caption-side="top"} 



## 平台安全服务
{: #security}

下表列出了将事件发送到 {{site.data.keyword.cloudaccesstrailshort}} 的安全云服务：


|服务|描述|{{site.data.keyword.at_full_notm}} 事件|
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) |您可以使用 {{site.data.keyword.cloudcerts_short}} 来管理基于 {{site.data.keyword.cloud_notm}} 的应用程序和服务的 SSL 证书。| [{{site.data.keyword.cloudcerts_short}} 服务生成的事件](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="将事件发送到 {{site.data.keyword.cloudaccesstrailshort}} 的安全云服务的列表" caption-side="top"} 


