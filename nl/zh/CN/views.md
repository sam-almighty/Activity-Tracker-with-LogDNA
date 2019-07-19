---

copyright:
  years: 2019
lastupdated: "2019-06-03"

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
{: #views}

通过 {{site.data.keyword.at_full_notm}} Web UI，可以应用搜索和过滤条件来定义通过定制视图显示的事件。
{:shortdesc}


## 先决条件
{: #views_prereqs}

开始之前，请检查用户标识是否有权启动 Web UI 和查看事件。下表列出了用户要能够启动 {{site.data.keyword.at_full_notm}} Web UI 以及查看、搜索和过滤事件而必须具有的最基本角色：

| 角色                      | 授予的许可权            |
|---------------------------|-------------------------------|  
| 平台角色：`查看者`     | 允许用户在“可观察性”仪表板中查看服务实例的列表。|
| 服务角色：`读取者`     | 允许用户启动 Web UI 并在 Web UI 中查看事件。|
{: caption="表 1. IAM 角色" caption-side="top"} 

有关如何为用户配置策略的更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。



## 步骤 1. 转至 Web UI 并选择视图
{: #views_step1}

请完成以下步骤：

1. [转至 Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。
2. 单击**视图**图标 ![“配置”图标](images/views.png)。
3. 选择**所有内容**或某个视图。 


## 步骤 2. 应用搜索查询来选择要通过视图显示的事件集
{: #views_step2}

要搜索特定事件，可以应用搜索查询。 

* 您可以执行简单搜索（单个项字符串搜索）、复合搜索（多个搜索项和运算符）、字段搜索（如果可以解析日志行）和其他搜索。有关更多信息，请参阅 [How to Search Logs in LogDNA docs ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://docs.logdna.com/docs/search){:new_window}。
* AND 和 OR 运算符区分大小写，并且必须为大写。

只能在通过实例的服务套餐所指定天数内搜索事件。
{: important}


请完成以下步骤：
1. 输入搜索查询。 
2. 单击 **Enter** 键。 

应用查询时，请注意，视图名称会更改为**未保存的视图**。


### 查询服务生成的事件
{: #views_step1_1}

要过滤掉特定服务的事件，需要输入以下查询：

```
_supertenant:SERVICENAME
```
{: codeblock}

其中，`SERVICENAME` 是 {{site.data.keyword.cloud_notm}} 中服务的名称。

下表列出了核心服务：

|事件生成方|值|样本查询|
|--------------------------------------------|-------------------------------|----------------------------------|
|[IAM 访问权管理服务](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)|`iam-am`|`_supertenant:iam-am`|
|[IAM 身份服务](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)|`iam-identity`|`_supertenant:iam-identity`|
|[IAM 访问组服务](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)|`iam-groups`|`_supertenant:iam-groups`|
|[资源控制器服务](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)|`BSS`|`_supertenant:BSS`|            
{: caption="表 2. 按服务名称查询" caption-side="top"}

### 查询服务生成的事件集
{: #views_step1_2}

服务生成不同类型的事件时，可以输入以下查询：

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

其中 

* `SERVICENAME` 是 {{site.data.keyword.cloud_notm}} 中服务的名称。
* `TYPEOFACTION` 是复合查询，在其中可以使用 AND 和 OR 运算符，还可以使用 `-` 来排除数据。请注意，`AND` 和 `OR` 运算符区分大小写，并且必须为大写。


下表显示了如何查询服务生成的一组事件的示例：

|事件生成方|事件类型|样本查询|
|--------------------------------------------|--------------------|---------------------------------|
|`IAM 身份服务`|[登录事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)|`_supertenant:iam-identity (action login)`|
|`IAM 身份服务`|[API 密钥事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys)|`_supertenant:iam-identity (action user-apikey) -(action login)`|
|`IAM 身份服务`|[帐户服务标识事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids)|`_supertenant:iam-identity (action account-serviceid)`|
|`资源控制器`|[供应和管理服务实例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)|`_supertenant:BSS (action instance)`| 
|`资源控制器`|[管理帐户中的用户](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)|`_supertenant:BSS (action user-management.user)`|                   |
{: caption="表 3. 更复杂查询的样本" caption-side="top"}


### 查询具有特定操作的事件
{: #views_step1_3}

每个事件都有一个 **action** 字段，用于通知触发事件的操作。可以输入以下查询来搜索具有相同操作的所有事件：

```
action ACTIONVALUE
```
{: codeblock}

其中，`ACTIONVALUE` 是 action 字段的值或值的一部分。

下表显示了针对不同操作的查询示例：

|操作|样本查询|
|------------------------|----------------------------------|
|供应服务|`action instance.create`|
|除去实例|`action instance.delete`|
|添加用户|`action user-management.user.create`|
{: caption="表 4. 按操作类型进行查询的样本" caption-side="top"}



### 查询其操作失败的事件
{: #views_step1_4}

请求的操作失败时，**outcome** 字段会设置为 **failure**。可以输入以下查询来搜索这些类型的事件：

```
outcome failure
```
{: codeblock}


### 按事件重要程度查询
{: #views_step1_5}

每个事件都有一个 **severity** 字段，用于定义操作可能对云产生的威胁级别。 

有效值为 *normal*、*warning* 和 *critical*。 
* **Normal** 设置用于云中的例程操作。例如，启动实例或刷新令牌。 
* **Warning** 设置用于在其中更新云资源或修改其元数据的操作。例如，更新工作程序节点的版本，重命名证书或重命名服务实例。 
* **Critical** 设置用于影响云中安全性的操作。例如，更改用户的凭证，删除数据，或者通过未经授权的访问方式来使用云资源。

可以输入以下查询来搜索这些类型的事件：

```
severity VALUE
```
{: codeblock}

其中，`VALUE` 可以设置为 *normal*、*warning* 或 *critical*

例如，要查询严重事件，可以运行以下查询：

```
severity critical
```
{: codeblock}



## 步骤 3. 创建定制视图
{: #views_step3}

将搜索查询应用于**所有内容**视图或现有定制视图后，请完成以下步骤以将结果另存为定制视图：

1. 在 Web UI 中，单击**未保存的视图**。
2. 选择**另存为新视图/新警报**。这将打开*创建新视图*页面。
3. 在*名称*字段中为该视图输入名称。
4. （可选）添加类别。输入名称，然后单击**将此项添加为新视图类别**。
5. （可选）附加警报。此时将显示用于配置该警报的新部分。
6. 单击**保存视图**


## 步骤 4. 定制如何通过视图显示事件行
{: #views_step4}

有不同的选项可定制在视图中查看数据的方式：
* 可以修改视图的属性，也可以重命名视图，添加或修改其描述，以及应用特定行格式。
* 可以在*用户首选项*部分中更改`日志格式`。
* 可以在*工具*部分中应用行模板。请注意，这将覆盖其他任何行配置。如果选择**持久存储这些设置**，那么 UI 中的所有视图都将按此部分中指定的行格式来显示数据。
* 可以通过在**工具**部分中设置**突出显示项**，将颜色应用于项或字符串。



### 通过视图属性页面更改行格式
{: #views_step4_1}

要修改单个视图中事件行的格式，请完成以下步骤：

1. 在视图中，选择**编辑视图属性**。这将打开*编辑视图属性*页面。

2. 在**定制 %LINE 模板**部分中，输入定制行格式。缺省格式设置为 `{{line}}`。

    有关行模板准则的更多信息，请参阅[准则](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)。

3. 单击**保存属性*。



### 通过用户首选项部分更改行格式
{: #views_step4_2}

在**用户首选项**部分中，可以修改每行显示的数据字段的顺序。

要修改事件行的格式，请完成以下步骤：

1. 在 Web UI 中，单击**配置**图标 ![“配置”图标](images/admin.png "“管理员”图标")。
2. 选择**用户首选项**。这将打开一个新窗口。
3. 选择**日志格式**。
4. 修改*行格式*部分以匹配您的需求。拖动各个框。


### 通过工具部分中的行模板更改行格式
{: #views_step4_3}

要修改事件行的格式，请完成以下步骤：

1. 在视图中，单击**工具**图标 ![“工具”图标](images/tool.png "“工具”图标")。
2. 在**行模板**字段中，输入定制行格式。有关行模板准则的更多信息，请参阅[准则](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)。
3. （可选）单击**持久存储这些设置**以将行格式应用于所有视图。



### 突出显示项
{: #view_events_step4_4}

要在视图中突出显示项，请完成以下步骤：

1. 在视图中，单击**工具**图标 ![“工具”图标](images/tool.png "“工具”图标")。
2. 在**行模板**字段中的**突出显示项**部分中，输入词或字符串。
3. （可选）单击**持久存储这些设置**以将这些设置应用于所有视图。



## 更改定制视图的名称和描述
{: #views_step5}

可以重命名视图。还可以添加或修改视图的描述。


请完成以下步骤：

1. 在视图中，选择**编辑视图属性**。这将打开*编辑视图属性*页面。

    可以重命名视图，添加或修改视图的描述，以及应用定制行格式。

2. 在**重命名视图**部分中，输入新名称以重命名视图。

3. 在**描述**部分中，输入或修改描述。

4. 单击**保存属性**。



## 定义行模板的准则
{: #views_line}

定义行模板时，请考虑必须应用的以下准则：
* 使用 Mustache 样式 `{{field.name}}` 或 Bash 样式 `${field.name}` 变量来构造模板。 
* 使用 `{{line}}` 或 `$@` 来引用原始行。 
* 其他所有字符或字符串都会解释为文本字面值。 


例如，可以将行模板定义为 `{{initiator.id}} -- {{action}} -- {{message}}`，以在视图中查看每个事件的这些字段。


