---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, monitor events

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


# 监视帐户中的活动
{: #monitor_events}

您可以通过 {{site.data.keyword.at_full_notm}} Web UI 来监视帐户中的活动。此外，还可以导出事件集，以在其他上下文中对事件进行分析。
{:shortdesc}

每个位置有 1 个 {{site.data.keyword.at_full_notm}} 服务实例。因此，要监视帐户中的活动，可能需要通过不同的 {{site.data.keyword.at_full_notm}} 实例来查看和分析事件。 

在 {{site.data.keyword.cloud_notm}} 中，可以单击**菜单**图标 ![“菜单”图标](../icons/icon_hamburger.svg) > **可观察性** > **Activity Tracker**，以查看列出了帐户中供应的所有实例的仪表板。
{: tip}

要查看事件，必须在事件可用的位置中[启动 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch)。然后，可以使用视图来监视这些事件。您可以使用本地时间查看事件。

可以应用时间戳记和/或搜索查询来选择通过视图显示的事件。

* 可以应用搜索查询，并将其保存为定制视图。 
* 可以应用时间戳记来跳转至事件日志中的特定时间。 

应用搜索查询时，可以保存该视图以供日后复用。但是，不会保存时间戳记。

请注意，实例可能具有不同的服务套餐，因此不同的数据保留期将确定数据可供通过 Web UI 进行搜索的天数。只能监视保留期内的事件。不同的[服务套餐](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan)具有不同的保留期。


## 监视全局事件和基于位置的事件
{: #mon_def_event_type}

事件可以分类为全局事件或基于位置的事件。事件的类型将确定必须在哪里监视事件。

全局事件的通用主题是一个同步位置，在其中帐户管理员可以监视整个云上特定类型的活动。而基于位置的事件始终是预订云服务的托管位置的本地事件。
{: note}

### 全局事件
{: #mon_def_global}

**全局事件**报告帐户中与通常会在所有区域中同步的数据和资源相关的活动。
{: note}

用户与之交互的服务集成在一起，构成了全局 {{site.data.keyword.cloud_notm}} 体验的核心。

全局域在**法兰克福**设置。全局事件通过在法兰克福配置的 {{site.data.keyword.at_full_notm}} 实例进行捕获并使其可用。

例如，帐户管理员邀请用户加入帐户时，可以从云中的任何位置执行此操作。他们可邀请位于法兰克福的用户，并授予他们使用在达拉斯供应的服务的许可权。对于这种情况，事件应该发送到哪里？答案是一个与源或位置无关的全局域，其中信息会在所有区域中同步。
    
再例如，资源控制器事件在 IBM Cloud 中也会被视为全局事件。这些事件报告整个云中服务实例的供应和删除。虽然服务实例是在特定位置创建的，但资源控制器操作会作为全局事件进行报告，以提供单个视图来显示整个帐户中供应的所有服务实例。


### 基于位置的事件
{: #mon_def_location}

**基于位置的事件**报告帐户中在 {{site.data.keyword.IBM_notm}} 数据中心位置（如达拉斯或法兰克福）托管的 {{site.data.keyword.cloud_notm}} 服务生成的活动。
{: note}


客户机和应用程序与某个位置托管的云服务进行交互时，将通过该位置中配置的 {{site.data.keyword.at_full_notm}} 实例来捕获基于位置的事件，并使其可用。您可以通过在该位置中[启动 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) 来查看这些事件。
    
基于位置的事件会使数据保持本地性，即相对于在该云位置中运行的服务为本地事件。

例如，如果在法兰克福位置供应了 {{site.data.keyword.cloudcerts_short}} 服务，那么来自该实例的事件将发送到在法兰克福供应的 {{site.data.keyword.at_full_notm}} 实例。如果在达拉斯位置供应了 {{site.data.keyword.cloudcerts_short}} 服务，那么来自该实例的事件将发送到在达拉斯供应的 {{site.data.keyword.at_full_notm}} 实例。在这两种情况下，事件始终是所预订云服务的区域和位置的本地事件。




## 通过缺省视图监视事件
{: #mon_def_view}

缺省视图名为**所有内容**。 

一旦您在某个位置打开 Web UI，就会立即看到该视图。 

实例中的所有事件都将通过此视图显示。

要了解如何通过此视图来查看事件，请参阅[查看事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1)。

## 通过定制视图监视事件
{: #mon_cus_view}

您可能希望监视帐户中的一组事件。要对事件子集进行分析，可以创建定制视图。 

要创建定制视图，必须应用搜索查询来定义哪些事件要通过视图显示。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2)。

可以向定制视图[附加警报](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts)。 

可以从定制视图[导出数据](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export)。 

可以[重命名视图以及添加或修改视图描述](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5)。 

可以向视图[应用行模板](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4)，以定制数据的显示方式。 

可以通过对视图按**类别*分组来组织视图。


## 通过应用时间范围来监视事件
{: #mon_time_view}

您可能希望查看特定时间范围内的事件。

可以[应用时间范围](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3)来选择通过视图显示的事件。

可以通过指定绝对时间、相对时间或时间范围来应用时间戳记。

* 绝对时间指定事件日志中的精确时间点，例如 `May 20 7:00pm`。
    
* 相对时间指定不精确的时间范围，例如 `2 days ago`。

* 时间范围指定时间间隔，例如 `yesterday 10am to yesterday 11am`。



## 配置警报
{: #mon_alerts}

在某些场景中，您可能希望在帐户中生成特定事件时收到通知。例如，您可能希望失败的操作数超过指定的阈值时收到通知。 

通过 {{site.data.keyword.at_full_notm}} Web UI，可以应用搜索查询来定义通过定制视图显示的事件。然后，可以将警报附加到该视图以在发生条件时接收通知。这将在视图中显示一个钟状图标，以指示此视图已连接警报。

* 每个视图可以[附加一个警报](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4)。
* 可以配置基于满足视图中搜索查询的事件行数和/或基于时间频率的条件。
* 为一个警报定义多个通知通道，有关受支持通道的信息，请参阅[警报通知通道](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)。
* 可以[定义**预设**](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3)。预设是可以连接到任意数量的视图的警报模板。可以使用预设来定义用户将警报附加到视图时可复用的模板。 
* 针对警报禁用通知， 
* 可以从视图[拆离警报](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view)。 


### 警报类型
{: #mon_alerts_types}

可以配置以下类型的警报：

* **存在警报**：可以使用此类型警报在视图中显示的事件数超过预期数量时发出通知。 
* **缺少警报**：可以使用此类型警报在视图中显示的事件数低于预期数量或没有事件时发出通知。 

例如，您可能有一个视图，其中显示的事件报告删除了帐户中的服务实例。您并不希望删除服务实例。为此，可以配置*存在警报**，用于在该视图中显示一个或多个事件时触发此警报。

在该视图中显示事件后，会启用缺少警报。
{: note}


### 警报条件
{: #mon_alerts_conditions}

可以为警报配置以下任何条件：

* **时间频率**：设置此条件以指定触发警报的频率。有效值为：30 秒、1 分钟、5 分钟、15 分钟、30 分钟、1 小时、6 小时、12 小时和 24 小时
* **事件行计数器**：设置此条件以指定与视图的过滤和搜索条件相匹配的事件行数。达到该事件行数时，将触发警报。

您可以决定是同时检查这两个条件，还是只检查其中一个条件。如果同时设置了这两个条件，那么将在达到任一阈值时触发警报。 

如果将*事件行计数器*设置为触发警报的唯一条件，请注意，配置条件时设置的时间频率将确定在触发警报后过多长时间重置警报条件。
{: note}

例如，可以将警报配置为在 30 秒后触发，或者在收集了与视图的过滤和搜索条件相匹配的 100 个事件行时触发。



## 导出事件
{: #mon_export}

您可能需要在 Web UI 外部访问一组事件，以更详细地调查问题。 

您可以将数据以 JSONL 格式从 {{site.data.keyword.at_full_notm}} 实例导出到本地文件。 

可以通过 Web UI 中的视图导出事件，也可以使用 REST API 以编程方式导出事件。

导出事件时，请考虑以下信息：
* 导出一组事件条目。 
* 要定义希望导出的数据集，可以应用过滤器和搜索。还可以指定时间范围。 
* 可以导出的最大行数为 20,000。

### 使用 REST API
{: #mon_export_api}

可以使用 LogDNA REST API 以编程方式导出事件。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api)。

以编程方式导出事件时，请考虑以下信息：

* 可以选择发送电子邮件或将事件流式传输到终端。
* 必须使用一个服务密钥来传递在发出导出 REST API 调用时必须使用的凭证。 

    您必须对 {{site.data.keyword.at_full_notm}} 实例或服务具有**管理者**角色，才能在 Web UI 中查看和生成服务密钥。


### 通过 Web UI 中的视图
{: #mon_export_ui}

可以通过 Web UI 中的视图来导出事件。 

在 Web UI 中，可以选择用于显示要导出的数据的视图。对于此视图，必须选择**导出行**任务。您必须指定时间范围，以及是导出较新的行还是较旧的行。然后，可以请求导出。 

提交请求后，您会收到一封发送到您电子邮件地址的电子邮件，其中附带包含相应数据的压缩文件的链接。 
* 要获取数据，必须单击链接并下载压缩文件。 
* 包含要导出的数据的压缩文件最多在 48 小时内可用。 

[了解有关通过 Web UI 导出事件的更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui)。








