---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# 查看事件
{: #view_events.md}

在 {{site.data.keyword.cloud_notm}} 中供应 {{site.data.keyword.at_full_notm}} 服务的实例后，可以通过 {{site.data.keyword.at_full_notm}} Web UI 来查看事件。
{:shortdesc}


## 先决条件
{: #view_events_prereqs}

开始之前，请检查用户标识是否有权启动 Web UI 和查看事件。 

**注：**您必须是 {{site.data.keyword.at_full_notm}} 服务的管理员或 {{site.data.keyword.at_full_notm}} 实例的管理员，或者具有管理策略的帐户 IAM 许可权。

下表列出了用户要能够启动 {{site.data.keyword.at_full_notm}} Web UI 并查看事件而必须具有的最基本策略：

| 角色                      | 授予的许可权       |
|---------------------------|-------------------------------|  
| 平台角色：`查看者`     | 允许用户在“可观察性”仪表板中查看服务实例的列表。|
| 服务角色：`读取者`     | 允许用户启动 Web UI 并在 Web UI 中查看事件。|
{: caption="表 1. IAM 策略" caption-side="top"} 

有关如何为用户配置这些策略的更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。


## 通过 Web UI 查看事件
{: #view_events_step1}

要启动 {{site.data.keyword.at_full_notm}} Web UI，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}} *仪表板*即会打开。

2. 转至“菜单”图标 ![“菜单”图标](../../icons/icon_hamburger.svg)，然后选择**可观察性**。 

3. 选择 **Activity Tracker**。 

    这将显示 {{site.data.keyword.at_full_notm}} 实例的列表。

    **注：**每个区域有 1 个实例。

4. 选择要查看事件的区域中的实例。然后，单击**查看 LogDNA**。

这将打开 {{site.data.keyword.at_full_notm}} Web UI，并显示**所有内容**视图。通过此视图，您可以在您的帐户中查看所选区域的事件。

**注：**如果您拥有`轻量`套餐，并且看不到您要查找的事件，那么可能需要升级到付费套餐以启用对较旧事件的搜索功能。事件可供搜索的天数取决于您选择的套餐。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。


## 定制缺省视图
{: #view_events_step2}

在**用户首选项**部分中，可以修改每行显示的数据字段的顺序。

要修改事件行的格式，请完成以下步骤：

1. 在 Web UI 中，单击**配置**图标 ![“配置”图标](images/admin.png "“管理员”图标")。
2. 选择**用户首选项**。这将打开一个新窗口。
3. 选择**日志格式**。
4. 修改*行格式*部分以匹配您的需求。拖动各个框。




## 在上下文中查看事件
{: #view_events_step3}

您可以随时在上下文中查看每个事件行。

请完成以下步骤： 

1. 在 Web UI 中，单击**视图**图标 ![“配置”图标](images/views.png "“配置”图标")。
2. 选择**所有内容**或某个定制视图。
3. 确定要探索的行。
4. 展开事件行。 

    这将显示有关行标识、标记和标签的信息。

5. 单击**在上下文中查看**，以在该主机和/或应用程序的其他条目的上下文中查看事件行。

完成探索事件后，单击**关闭**以关闭该行。




## 将事件复制到剪贴板
{: #view_events_step4}


要将事件复制到剪贴板，请完成以下步骤： 

1. 在 Web UI 中，单击**视图**图标 ![“配置”图标](images/views.png "“配置”图标")。
2. 选择**所有内容**或某个定制视图。
3. 确定要探索的行。
4. 展开事件行。 

    这将显示有关行标识、标记和标签的信息。

5. 单击**复制到剪贴板**以将事件复制到剪贴板。

完成探索事件后，单击**关闭**以关闭该行。




