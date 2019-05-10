---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# 创建定制视图
{: #views.md}

通过 {{site.data.keyword.at_full_notm}} Web UI，可以应用搜索和过滤条件来定义通过定制视图显示的事件。
{:shortdesc}


## 先决条件
{: #views_prereqs}

开始之前，请检查用户标识是否有权启动 Web UI 和查看事件。然后，[转至 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。

**注：**您必须是 {{site.data.keyword.at_full_notm}} 服务的管理员或 {{site.data.keyword.at_full_notm}} 实例的管理员，或者具有管理策略的帐户 IAM 许可权。

下表列出了用户要能够启动 {{site.data.keyword.at_full_notm}} Web UI 以及查看、搜索和过滤事件而必须具有的最基本策略：

|角色|授予的许可权
|
|---------------------------|-------------------------------|  
| 平台角色：`查看者`     | 允许用户在“可观察性”仪表板中查看服务实例的列表。|
| 服务角色：`读取者`     | 允许用户启动 Web UI 并在 Web UI 中查看事件。|
{: caption="表 1. IAM 策略" caption-side="top"} 

有关如何为用户配置这些策略的更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。



## 步骤 1. 过滤事件
{: #views_step1}

您可以按源、应用程序和日志级别过滤事件。 

* 源可以是主机、计算机、虚拟机或 Heroku 应用程序。
* 应用程序表示日志文件、程序或容器。
* 日志级别的示例为：INFO、DEBUG、ERROR

完成以下步骤以过滤日志：

1. 在 Web UI 中，单击**视图**图标 ![“配置”图标](images/views.png "“配置”图标")。
2. 选择**所有内容**或某个视图。
3. 展开**所有标记**以查看可用的标记的列表。然后，选择所需的标记。
4. 展开**所有源**以查看可用源的列表。然后，选择所需的源。
5. 展开**所有应用程序**以查看可用的应用程序的列表。然后，选择所需的应用程序。
6. 展开**所有级别**以查看可用的级别的列表。然后，选择所需的级别。

应用过滤器时，请注意视图名称会更改为**未保存的视图**。

**注：**在每个部分中，您可以将多个选项分组到一个组中。对标记、源、应用程序和级别进行分组，这样当您在其他定制视图中过滤数据时，可以复用这些分组。

要创建组，请选择多个值。然后，单击**另存为组**。为该组输入一个名称，然后保存。


## 步骤 2. 搜索事件
{: #views_step2}

搜索事件时，搜索会应用在该视图中配置的任何过滤器和时间查询。

您可以执行简单搜索（单个项字符串搜索）、复合搜索（多个搜索项和运算符）、字段搜索（如果可以解析日志行）和其他搜索。有关更多信息，请参阅 [How to Search Logs in LogDNA docs ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://docs.logdna.com/docs/search){:new_window}。

**注：**AND 和 OR 运算符区分大小写，并且必须为大写。

应用搜索条件时，请注意，视图名称会更改为**未保存的视图**。



## 步骤 3. 创建定制视图
{: #views_step3}

将时间范围、过滤器和搜索条件应用于**所有内容**视图或现有定制视图后，请完成以下步骤以将结果另存为定制视图：

1. 在 Web UI 中，单击**未保存的视图**。
2. 选择**另存为新视图/新警报**。这将打开*创建新视图*页面。
3. 在*名称*字段中为该视图输入名称。
4. （可选）添加类别。输入名称，然后单击**将此项添加为新视图类别**。
5. （可选）附加警报。此时将显示用于配置该警报的新部分。
6. 单击**保存视图**




