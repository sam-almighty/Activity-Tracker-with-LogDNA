---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, manage events

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


# 管理帐户中的事件
{: #manage_events}

作为 {{site.data.keyword.cloud_notm}} 中 {{site.data.keyword.at_full_notm}} 服务的管理员，您必须在计划监视的每个位置供应服务的实例。您必须定义帐户准则以管理帐户中的事件。
{:shortdesc}


## 按位置供应服务实例
{: #manage_events_provision}

要收集并监视帐户中的活动，必须在帐户中供应 {{site.data.keyword.at_full_notm}} 服务。 

每个位置有 1 个 {{site.data.keyword.at_full_notm}} 服务实例。因此，要监视帐户中的活动，可能需要供应多个 {{site.data.keyword.at_full_notm}} 实例。 

* 在 {{site.data.keyword.cloud_notm}} 中，可以单击**菜单**图标 ![“菜单”图标](../icons/icon_hamburger.svg) > **可观察性** > **Activity Tracker**，以查看列出了帐户中供应的所有实例的仪表板。 
* 如果要监视[全局事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_def_global)，那么必须在法兰克福供应实例。 


[了解有关供应服务的更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision)。

要获取服务在 {{site.data.keyword.cloud_notm}} 中可用的位置的列表，请参阅[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

实例可用后，事件将立即进行收集并可供通过该实例的 Web UI 进行监视。



## 归档事件
{: #manage_events_archive}

您可以将 {{site.data.keyword.at_full_notm}} 实例中的事件归档到 {{site.data.keyword.cos_full_notm}} (COS) 实例中的存储区。
[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-archiving)。

* 事件会以压缩格式 **(.json.gz)** 每天自动归档一次。 每一行都会保留其元数据。
* 保存配置后，事件会在 24-48 小时内进行归档。 

每个 {{site.data.keyword.at_full_notm}} 实例都有其自己的归档配置。
{: important}

下图显示了归档事件时集成的不同组件的高级视图：

![高级视图归档事件](images/archive.png "高级视图归档事件")

{{site.data.keyword.cos_full_notm}} 实例在资源组的上下文中供应。 {{site.data.keyword.at_full_notm}} 实例也在资源组的上下文中供应。可以将这两个实例分组到同一资源组中，也可以分组到不同的资源组中。 

{{site.data.keyword.at_full_notm}} 使用服务标识来与 {{site.data.keyword.cos_full_notm}} 服务进行通信。
* {{site.data.keyword.at_full_notm}} 使用您为 {{site.data.keyword.cos_full_notm}} 实例创建的服务标识来认证和访问 {{site.data.keyword.cos_full_notm}} 实例。 
* 您可以将特定访问策略分配给在 {{site.data.keyword.cos_full_notm}} 实例上限制许可权的服务标识。将服务标识限制为对您计划在其中归档事件的存储区仅具有写许可权。


## 使用类别对事件分类
{: #manage_events_category}

可以通过 Web UI 中的**类别**部分来定义类别。 

可以定义类别以对视图分组。您可以定义一组不同的类别来对仪表板分组。

使用类别对资源分组，以便用户可以轻松找到资源。 








