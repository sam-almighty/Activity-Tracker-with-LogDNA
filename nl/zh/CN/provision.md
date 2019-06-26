---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# 供应实例
{: #provision}

必须先在 {{site.data.keyword.cloud_notm}} 中供应服务的实例，然后才能使用 {{site.data.keyword.at_full_notm}} 监视和管理事件数据。
{:shortdesc}

要在公共云区域中供应 {{site.data.keyword.at_full_notm}} 实例，请考虑以下信息：
* 必须选择与实例关联的服务套餐、在其中收集日志的区域以及用于确定日志保留期的套餐。您可以选择 7 天、14 天或 30 天保留期。或者，{{site.data.keyword.at_full_notm}} 提供了`轻量`套餐，可用于在事件通过系统时查看事件。您可以使用事件跟踪来查看事件。还可以设计过滤器来准备升级为更长保留期的套餐。此套餐的保留期为 0 天。
* 您的用户标识必须具有在资源组中供应服务的许可权。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups)。


每个 {{site.data.keyword.cloud_notm}} 区域只能供应 1 个服务实例。
{: important}

## 通过“可观察性”仪表板供应实例
{: #provision_ui}

要通过 {{site.data.keyword.cloud_notm}} 中的“可观察性”仪表板来供应实例，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}} UI 即会打开。

2. 转至“菜单”图标 ![“菜单”图标](../../icons/icon_hamburger.svg)。然后，选择**可观察性**以访问*可观察性*仪表板。

3. 选择 **Activity Tracker**，然后单击**创建实例**。 

4. 输入服务实例的名称。

5. 选择计划在其中供应实例的[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。 

6. 选择资源组。 

    缺省情况下，已设置 **Default** 资源组。

    **注：**如果无法选择资源组，请检查您是否具有对要在其中供应实例的资源组的编辑许可权。

7. 选择`轻量`服务套餐。 

    缺省情况下，已设置轻量套餐。

8. 单击**创建**。

供应实例后，将打开 *Activity Tracker* 仪表板。 

接下来，转至 Web UI 以查看帐户中的事件。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events)。



## 通过目录供应实例
{: #provision_catalog}

要通过 {{site.data.keyword.cloud_notm}}“目录”来供应 {{site.data.keyword.at_full_notm}} 的实例，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}} UI 即会打开。

2. 单击**目录**。这将打开 {{site.data.keyword.cloud_notm}} 中提供的服务的列表。

3. 要过滤显示的服务列表，请选择**开发者工具**类别。

4. 单击 **{{site.data.keyword.at_full_notm}}** 磁贴。 

5. 输入服务实例的名称。

6. 选择计划在其中供应实例的位置。 

    要获取可用于 {{site.data.keyword.at_full_notm}} 服务的位置的最新列表，请参阅[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

7. 选择资源组。 

    缺省情况下，已设置 **Default** 资源组。

    **注：**如果无法选择资源组，请检查您是否具有对要在其中供应实例的资源组的编辑许可权。

8. 选择`轻量`服务套餐。 

    缺省情况下，已设置轻量套餐。

9. 单击**创建**。

供应实例后，将打开 *Activity Tracker* 仪表板。 

接下来，转至 Web UI 以管理帐户中的事件。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## 通过 CLI 供应实例
{: #provision_cli}

要通过命令行来供应 {{site.data.keyword.at_full_notm}} 的实例，请完成以下步骤：

1. [先决条件] 安装 {{site.data.keyword.cloud_notm}} CLI。[了解更多信息](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

   如果 CLI 已安装，请继续执行下一步。

2. 在 {{site.data.keyword.cloud_notm}} 中登录到要在其中供应实例的位置。运行以下命令：[`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

    要获取可用于 {{site.data.keyword.at_full_notm}} 服务的位置的最新列表，请参阅[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

3. 设置要在其中供应实例的资源组。运行以下命令：[`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    缺省情况下，已设置 `default` 资源组。

4. 创建实例。 运行 [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create) 命令：

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    其中

    * NAME 是实例的名称

    * 值 *logdnaat* 是 {{site.data.keyword.cloud_notm}} 中 {{site.data.keyword.at_full_notm}} 服务的名称

    * SERVICE_PLAN_NAME 是套餐的类型。有效值为 *lite*、*7-days*、*14-days* 和 *30-days*
    
    * LOCATION 是在其中创建 LogDNA 实例的区域。要获取可用于 {{site.data.keyword.at_full_notm}} 服务的位置的最新列表，请参阅[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

    
例如，要为实例供应 7 天保留期的套餐，请运行以下命令：

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



