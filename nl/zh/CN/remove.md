---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# 除去实例
{: #remove}

您可以通过 {{site.data.keyword.cloud_notm}} UI 或通过命令行除去 {{site.data.keyword.at_full_notm}} 服务的实例。
{:shortdesc}



## 通过 {{site.data.keyword.cloud_notm}} UI 除去实例
{: #remove_ui}

要使用 {{site.data.keyword.cloud_notm}} UI 来除去 {{site.data.keyword.at_full_notm}} 实例，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}} UI 即会打开。

2. 转至菜单图标 ![菜单图标](../../icons/icon_hamburger.svg) > **可观察性**以访问*可观察性*仪表板。

3. 选择 **Activity Tracker**。这将显示实例的列表。

4. 选择您要删除的实例。

5. 从*操作*菜单中，选择**除去**。

接下来，除去授予用户以使用您已删除的实例的许可权。

## 通过 CLI 除去实例
{: #remove_cli}

要通过命令行除去 {{site.data.keyword.at_full_notm}} 实例，请完成以下步骤：

1. [先决条件] 安装 {{site.data.keyword.cloud_notm}} CLI。

   有关更多信息，请参阅[安装 {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

   如果 CLI 已安装，请继续执行下一步。

2. 在 {{site.data.keyword.cloud_notm}} 中登录到要在其中供应实例的区域。运行以下命令：[`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. 设置在其中供应该实例的资源组。运行以下命令：[`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    缺省情况下，已设置 *default* 资源组。

4. 除去该实例。运行 [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) 命令：

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    其中 NAME 是实例的名称

    要列出您所登录的资源组中的所有可用实例，请运行以下命令：

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
例如，要除去实例，请运行以下命令：

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

接下来，除去授予用户以使用您已删除的实例的许可权。


