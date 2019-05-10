---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# 配置警报
{: #alerts.md}

通过 {{site.data.keyword.at_full_notm}} Web UI，可以应用搜索和过滤条件来定义通过定制视图显示的事件。然后，可以将警报附加到要通知的视图。您可以将一个或多个警报连接到视图，为一个警报定义多个通知通道，针对警报禁用通知，还可以从视图拆离警报。
{:shortdesc}


可以为警报配置以下任何条件：

* *时间频率*：指定触发警报的频率。有效值为：30 秒、1 分钟、5 分钟、15 分钟、30 分钟、1 小时、6 小时、12 小时和 24 小时
* *事件行计数器*：指定与视图的过滤和搜索条件相匹配的事件行数。达到该事件行数时，将触发警报。

您可以决定是同时检查这两个条件，还是只检查其中一个条件。如果同时设置了这两个条件，那么将在达到任一阈值时触发警报。 

例如，可以将警报配置为在 30 秒后触发，或者在收集了与视图的过滤和搜索条件相匹配的 100 个事件行时触发。

可以配置多个通知通道。有效通道为：`电子邮件`、`Slack`、`PagerDuty`、`Webhook`、`OpsGenie`、`Datadog`、`AppOptics` 和 `VictorOps`

您还可以定义**预设**。预设是可以连接到任意数量的视图的警报模板。 

这将在视图中显示一个钟状图标，以指示此视图已连接警报。


## 先决条件
{: #views_prereqs}

开始之前，请检查用户标识是否有权启动 Web UI 和查看事件。 

**注：**您必须是 {{site.data.keyword.at_full_notm}} 服务的管理员或 {{site.data.keyword.at_full_notm}} 实例的管理员，或者具有管理策略的帐户 IAM 许可权。

下表列出了用户要能够启动 {{site.data.keyword.at_full_notm}} Web UI 以及查看、搜索和过滤事件而必须具有的最基本策略：

| 角色                      | 授予的许可权            |
|---------------------------|-------------------------------|  
| 平台角色：`查看者`     | 允许用户在“可观察性”仪表板中查看服务实例的列表。|
| 服务角色：`读取者`     | 允许用户启动 Web UI 并在 Web UI 中查看事件。|
{: caption="表 1. IAM 策略" caption-side="top"} 

有关如何为用户配置这些策略的更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。

**您必须具有 {{site.data.keyword.at_full_notm}} 服务的付费服务套餐**。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。 


## 步骤 1. 转至 Web UI
{: #alerts_step1}

[转至 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## 步骤 2. 创建视图
{: #alerts_step2}

[创建视图](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md)。



## 步骤 3. [可选] 配置预设（警报模板）
{: #alerts_step3}

要将警报配置复用于不同的视图，请配置**警报预设**。
{: note}

要配置预设，请完成以下步骤：

1. 在 Web UI 中，选择**配置**图标 ![“配置”图标](images/admin.png "“管理员”图标")。
2. 选择**警报**。
3. 选择**添加预设警报**。
4. 选择通知通道。 
5. 定义阈值条件。

    1. 选择时间频率。例如，12 小时。

    2. 输入您希望在触发警报之前达到的事件行数。

    3. 选择是要同时检查这两个条件，还是仅检查其中一个条件。

6. 添加所选通知通道的详细信息。

    例如，对于电子邮件通知通道，添加一个或多个收件人，还可选择添加时区。

7. 单击**保存警报**。



## 步骤 4. 配置警报
{: #alerts_step4}

选择以下任一选项以将警报连接到视图：

### 选项 1. 使用预设配置警报
{: #alerts_step4_preset}

要将预设连接到视图，请完成以下步骤：

1. 在 Web UI 中，单击**视图**图标 ![“配置”图标](images/views.png)。
2. 单击要将警报连接到的视图名称。然后，选择**连接警报**。
3. 选择预设以复用警报定义。 
4. 单击**保存警报**。 




### 选项 2. 配置特定于视图的警报
{: #alerts_step4_view}

要将警报连接到视图，请完成以下步骤：

1. 在 Web UI 中，单击**视图**图标 ![“配置”图标](images/views.png)。
2. 单击视图名称。然后，选择**连接警报**。
3. 选择**特定于视图的警报**。
4. 选择通知通道。 
5. 定义阈值条件。

    1. 选择时间频率。例如，12 小时。

    2. 输入您希望在触发警报之前达到的事件行数。

    3. 选择是要同时检查这两个条件，还是仅检查其中一个条件。

6. 添加所选通知通道的详细信息。

    例如，对于电子邮件通知通道，添加一个或多个收件人，还可选择添加时区。

7. 单击**保存警报**。



## 删除预设（警报模板）
{: #alerts_delete_preset}

要删除预设，请完成以下步骤：

1. 在 Web UI 中，选择**配置**图标 ![“配置”图标](images/admin.png "“管理员”图标")。
2. 选择**警报**。
3. 将鼠标悬停在要删除的预设的*编辑*按钮上。这将显示*删除*选项。
4. 选择**删除**。
5. 确认要删除该预设。单击**删除**。

## 从视图拆离特定于视图的警报
{: #alerts_delete_view}

要拆离预设，请完成以下步骤：

1. 在 Web UI 中，选择**配置**图标 ![“配置”图标](images/admin.png "“管理员”图标")。
2. 选择**警报**。
3. 将鼠标悬停在要删除的警报的*编辑*按钮上。这将显示*删除*选项。
4. 选择**拆离**。
5. 确认要删除该警报。单击**拆离**。












