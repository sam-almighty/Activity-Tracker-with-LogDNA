---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #view_events}

在 {{site.data.keyword.cloud_notm}} 中供应 {{site.data.keyword.at_full_notm}} 服务的实例后，可以通过 {{site.data.keyword.at_full_notm}} Web UI 来查看事件。
您可以使用本地时间查看事件。
{:shortdesc}


## 查看事件
{: #view_events_step1}

要查看事件，请完成以下步骤：

1. 检查用户标识是否有权启动 Web UI 和查看事件。 

    下表列出了用户要能够启动 {{site.data.keyword.at_full_notm}} Web UI 以及查看、搜索和过滤事件而必须具有的最基本角色：

    <table>
      <caption>表 1. IAM 角色</caption>
      <tr>
        <th>角色</th>
        <th> 授予的许可权       </th>
      </tr>
      <tr>
        <td>平台角色：`查看者`</td>     <td>允许用户在*可观察性*仪表板中查看服务实例的列表。</td>
      </tr>
      <tr>
        <td>服务角色：`读取者`</td>     <td>允许用户启动 Web UI 并在 Web UI 中查看、搜索和过滤事件。</td>
      </tr>
    </table>

    有关如何为用户配置策略的更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。

2. [转至 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。

3. 单击**视图**图标 ![“配置”图标](images/views.png)。

4. 选择**所有内容**以查看所有事件，或选择一个视图。 

可以通过所选视图来查看事件。



## 通过应用搜索查询来查看事件子集
{: #view_events_step2}

可以应用搜索查询来选择通过视图显示的事件。可以保存该视图以供日后复用。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2)。

 


## 通过应用时间范围来查看事件子集
{: #view_events_step3}

可以应用时间范围来选择通过视图显示的事件。

可以通过指定绝对时间、相对时间或时间范围来应用时间戳记。

要跳转至特定时间，请完成以下步骤：
1. [转至 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。
2. 单击**视图**图标 ![“配置”图标](images/views.png)。
3. 选择**所有内容**或某个视图。
4. 输入时间查询。选择以下任一选项：

    * 输入绝对时间以跳转至事件中的某个时间点，例如 `May 20 7:00pm`。
    
    * 输入相对时间，例如 `2 days ago`、`today at 12am` 或 `an hour ago`。

    * 输入时间范围，例如 `yesterday 10am to yesterday 11am`、`last fri 4:30pm to 11/12 1 AM`、`last wed 4:30pm to 23/05 1 AM` 或 `May 20 10am to May 22 10am`。确保包含 `to` 以分隔初始时间戳记与结束时间戳记。

5. 单击 **ENTER** 键。

    您可能会收到以下错误消息：`请求用时比预期要长，请稍后尝试刷新浏览器，我们将尽快处理请求。请重试。`指定的时间范围内没有任何事件可供显示时，您可能会收到此错误。请更改时间查询，然后重试。



## 在上下文中查看事件
{: #view_events_step4}

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
{: #view_events_step5}


要将事件复制到剪贴板，请完成以下步骤： 

1. 在 Web UI 中，单击**视图**图标 ![“配置”图标](images/views.png "“配置”图标")。
2. 选择**所有内容**或某个定制视图。
3. 确定要探索的行。
4. 展开事件行。 

    这将显示有关行标识、标记和标签的信息。

5. 单击**复制到剪贴板**以将事件复制到剪贴板。

完成探索事件后，单击**关闭**以关闭该行。




