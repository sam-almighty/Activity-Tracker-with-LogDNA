---

copyright:
  years: 2019
lastupdated: "2019-06-06"

keywords: IBM Cloud, LogDNA, Activity Tracker, getting started

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


# 入门教程
{: #getting-started}

使用 {{site.data.keyword.at_full}} 服务可监视 {{site.data.keyword.cloud_notm}} 帐户的活动。您可以使用此服务来调查异常活动和关键操作，并满足监管审计要求。此外，您可以在操作发生时收到警报。收集的事件符合 Cloud Auditing Data Federation (CADF) 标准。
{:shortdesc}

![{{site.data.keyword.at_full_notm}} 服务](images/atov.png "{{site.data.keyword.at_full_notm}} 服务")


{{site.data.keyword.at_full_notm}} 会收集并存储对 {{site.data.keyword.cloud_notm}} 中运行的资源所发起 API 调用的审计记录。您可以在 {{site.data.keyword.cloud_notm}} 上归档这些事件以进行长期存储。
{: note}



## 关于 {{site.data.keyword.at_full}}
{: #gs_ov}

符合内部策略和行业法规是任何组织的策略中的关键要求，与应用程序的运行位置（内部部署、混合云或公共云）无关。{{site.data.keyword.at_full_notm}} 服务提供了框架和功能，可监视对 {{site.data.keyword.cloud_notm}} 上服务的 API 调用并生成证据，证明符合公司政策和特定于行业的市场监管。

在云环境（例如，{{site.data.keyword.cloud_notm}}）中工作时，必须根据内部策略以及基于行业和国家或地区的合规要求，计划用于审计和监视工作负载与数据的云策略。可以使用通过 {{site.data.keyword.at_full_notm}} 服务注册的信息来确定安全事件，检测未经授权的访问，以及符合监管和内部审计要求。

* {{site.data.keyword.at_full_notm}} 支持云中 IT 资源的高级安全监管。
* {{site.data.keyword.at_full_notm}} 为管理员提供了在一个位置中捕获、存储、查看、搜索和监视 API 活动的解决方案。还提供了通知功能，可使用任何支持的通知通道向您发出警报。
* {{site.data.keyword.at_full_notm}} 提供了导出事件的功能，您可以接着使用这些事件来生成审计跟踪报告。您可能需要这些报告，以便您的组织符合内部条例和外部行业与国家或地区法规。

![{{site.data.keyword.at_full_notm}} 服务提供的核心功能](images/features.png "{{site.data.keyword.at_full_notm}} 服务提供的核心功能")

例如，可以使用 {{site.data.keyword.at_full_notm}} 事件来确定以下信息：
* 对云服务发起 API 调用的用户
* 发起 API 调用时的时间戳记
* API 调用的状态
* 操作的关键程度


使用 {{site.data.keyword.at_full_notm}} 服务时，请考虑有关安全性的以下信息：

* 生成 {{site.data.keyword.at_full_notm}} 事件的 IBM 服务遵循 {{site.data.keyword.IBM_notm}} 云安全策略。有关更多信息，请参阅[信任 IBM Cloud 的安全性和隐私 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/security){: new_window}。
* {{site.data.keyword.at_full_notm}} 服务捕获用户发起的用于更改云服务状态的操作。信息不提供对数据库或应用程序的直接访问。
* 只有授权用户才能查看和监视 {{site.data.keyword.at_full_notm}} 事件日志。每个用户通过 {{site.data.keyword.cloud_notm}} 中的用户唯一标识进行确定。
* 每个 {{site.data.keyword.cloud_notm}} 位置（区域）只能供应 1 个服务实例。


## 目标
{: #gs_objectives}

完成本教程以了解如何在 {{site.data.keyword.cloud_notm}} 中供应服务。了解每个事件中可用的常见数据以及如何使用这些数据来帮助您监视云环境。了解如何在 Web UI 中导航。 


## 先决条件
{: #gs_prereq}

* 您需要作为 {{site.data.keyword.cloud_notm}} 帐户的成员或所有者的用户标识。要获取 {{site.data.keyword.cloud_notm}} 用户标识，请转至[注册 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

* 如果您希望使用命令行，那么必须安装 {{site.data.keyword.cloud_notm}} CLI。有关更多信息，请参阅[安装 {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

* 要完成管理服务访问权的步骤，您的用户标识需要**管理员平台许可权**才能管理 {{site.data.keyword.at_full_notm}} 服务。请联系帐户管理员。帐户所有者可以授予其他用户对帐户的访问权，以便管理用户访问权和管理帐户资源。[了解更多信息](/docs/iam?topic=iam-userroles)。



## 步骤 1. 供应 {{site.data.keyword.at_full_notm}} 服务的实例
{: #gs_step1}

要供应实例，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}} UI 即会打开。

2. 转至“菜单”图标 ![“菜单”图标](../../icons/icon_hamburger.svg)。然后，选择**可观察性**以访问*可观察性*仪表板。

3. 选择 **Activity Tracker**，然后单击**创建实例**。 

4. 输入服务实例的名称。

5. 选择**法兰克福**位置。 

    有关服务在其中可用的区域的更多信息，请参阅[区域](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

6. 选择资源组。 

    缺省情况下，已设置 **default** 资源组。

    **注：**如果无法选择资源组，请检查您是否具有对要在其中供应实例的资源组的编辑许可权。

7. 选择`轻量`服务套餐。 

    缺省情况下，已设置轻量套餐。

8. 单击**创建**。

供应实例后，将打开 *Activity Tracker* 仪表板。 


## 步骤 2. 管理对服务的访问权
{: #gs_step2}

**对于访问您帐户中的 {{site.data.keyword.at_full_notm}} 服务的每个用户，必须向其分配定义了 IAM 用户角色的访问策略。**策略确定用户可以在您选择的服务或实例的上下文中执行的操作。允许的操作是定制的，并且定义为允许在服务上执行的操作。然后，这些操作将映射到 IAM 用户角色。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam)。

在本教程中，您将学习如何授予用户管理许可权，以在资源组的上下文中使用 {{site.data.keyword.at_full_notm}} 服务。


### 1. 创建访问组
{: #gs_step2_1}

要创建访问组，请完成以下步骤：
1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 单击**创建**。
3. 输入组的名称和可选描述，然后单击**创建**。

### 2. 添加许可权以管理事件
{: #gs_step2_2}

设置组后，必须为该组分配公共访问策略。为访问组设置的任何策略都将应用于该组中的所有实体、用户和服务标识。


定义策略时，需要选择平台角色和服务角色：
* 平台管理角色涵盖一系列操作，包括创建和删除实例，管理别名、绑定和凭证，以及管理访问权的能力。平台角色有管理员、编辑者、操作员和查看者。平台管理角色还适用于帐户管理服务，这些服务支持用户邀请其他用户，管理服务标识、访问策略和目录条目以及跟踪计费和使用情况，具体取决于用户在帐户管理服务上所分配的角色。
* 服务访问角色定义用户或服务对服务实例执行操作的能力。服务访问角色有管理者、写入者和读取者。

要管理 {{site.data.keyword.at_full_notm}} 服务，用户需要以下角色：
* 平台角色：**管理员**。 
* 服务角色：**管理者**。 


要通过 UI 分配策略，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**。
2. 选择**访问组**。
3. 选择要为其分配访问权的组的名称。 
4. 单击**访问策略**。
5. 单击**分配访问权**。
6. 选择**在资源组中分配访问权**。
7. 选择资源组。
8. 如果尚未向用户授予针对所选资源组的角色，请为**分配对资源组的访问权**字段选择角色。 

    根据选择的角色，用户可以在其仪表板上查看资源组，编辑资源组名称或管理用户对该组的访问权。 
    
    如果希望用户仅有权访问资源组中的 {{site.data.keyword.at_full_notm}} 服务，那么可以选择**无访问权**。

9. 选择 **IBM Cloud Activity Tracker with LogDNA**。
10. 选择**管理员**平台角色。
11. 选择**管理者**服务角色。
12. 单击**分配**。


### 3. 将用户添加到组
{: #gs_step2_3}

要将用户添加到访问组，请完成以下步骤：
1. 单击**用户**选项卡上的**添加用户**。
2. 从列表中选择要添加的用户，然后单击**添加到组**。


## 步骤 3. 生成 {{site.data.keyword.at_full_notm}} 事件
{: #gs_step3}

要在供应 {{site.data.keyword.cloudcerts_short}} 服务实例时生成事件，请完成以下步骤：


1. 从 [{{site.data.keyword.cloud_notm}}“目录”![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/catalog){:new_window} 中，选择**安全性和身份**类别。

2. 选择 {{site.data.keyword.cloudcerts_short}} 服务。

3. 输入服务实例的名称。

4. 选择要在其中供应实例的区域。

5. 选择资源组。 

    缺省情况下，已设置 **Default** 资源组。

    **注：**如果无法选择资源组，请检查您是否具有对要在其中供应实例的资源组的编辑许可权。

6. 选择`免费`服务套餐。 

7. 单击**创建**。

这将创建 {{site.data.keyword.cloudcerts_short}} 服务的实例。

## 步骤 4. 启动 Web UI 
{: #gs_step4}

要启动 Web UI，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}}“仪表板”即会打开。

2. 在导航菜单中，选择**可观察性**。 

3. 选择 **Activity Tracker**。 

    这将显示 {{site.data.keyword.cloud_notm}} 上可用的实例的列表。

4. 选择位于**法兰克福**的实例。然后，单击**查看 LogDNA**。

    全局事件（如供应服务）通过位于法兰克福的全局域实例提供。

这将打开 Web UI。 


## 步骤 5. 查看事件
{: #gs_step5}


{{site.data.keyword.at_full_notm}} 服务捕获与 {{site.data.keyword.cloud_notm}} 中对所选云服务发起的 API 调用和其他操作相关的活动数据。 

* 事件会自动收集。 
* {{site.data.keyword.at_full_notm}} 中收集的事件符合 **Cloud Auditing Data Federation (CADF) 标准**。CADF 标准定义了完整事件模型，包含证明、管理和审计云环境中应用程序安全性所需的信息。
* {{site.data.keyword.at_full_notm}} 按位置存储和分组事件。 
* 报告全局 {{site.data.keyword.cloud_notm}} 帐户操作的事件会收集并存储在**法兰克福 (EU-DE)**。
* 为 {{site.data.keyword.at_full_notm}} 实例选择的服务套餐将设置事件可供通过 Web UI 进行搜索的天数。 

Web UI 打开时，将显示**所有内容**视图。您可以通过此视图来查看事件。

您还可以定义定制视图，以通过应用时间戳记和/或搜索查询来查看一组事件。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。


## 步骤 6. 了解事件的结构
{: #gs_step6}

事件符合 **Cloud Auditing Data Federation (CADF) 标准**。CADF 标准定义了完整事件模型，包含证明、管理和审计云环境中应用程序安全性所需的信息。

CADF 事件模型包含以下组件：

| 组件 | 描述 |
|------------|----------------------------|
| `操作`     | 操作是发起者执行、尝试执行或等待完成的行动或活动。|
| `发起者`   | 发起者是发起 API 调用并生成 CADF 事件的资源。触发的事件取决于 API 调用请求的操作。|
| `观察者`   | 观察者是通过 CADF 事件中可用的信息来创建和存储 CADF 记录的资源。|
| `结果`     | 结果是针对目标所执行的操作的状态。|
| `目标`     | 目标是对其执行操作、尝试执行操作或待完成操作的资源。|
{: caption="表 2. CADF 事件模型中可用的组件" caption-side="top"} 

[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-event#event)。



## 后续步骤
{: #gs_next_steps}

[定义定制视图](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。 

将 {{site.data.keyword.at_full_notm}} 服务套餐升级到付费套餐，以便能够[通过应用查询来搜索事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2)以及[配置警报](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts)。 

有关 {{site.data.keyword.at_full_notm}} 服务套餐的更多信息，请参阅[服务套餐](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。

