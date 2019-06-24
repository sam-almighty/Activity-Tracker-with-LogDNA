---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# 导航至 Web UI
{: #launch}

在 {{site.data.keyword.cloud_notm}} 中供应 {{site.data.keyword.at_full_notm}} 服务的实例后，可以通过 {{site.data.keyword.at_full_notm}} Web UI 来查看、监视和管理事件。
{:shortdesc}


## 步骤 1. 向用户授予 IAM 策略以查看数据 
{: #step1}

**注：**您必须是 {{site.data.keyword.at_full_notm}} 服务的管理员或 {{site.data.keyword.at_full_notm}} 实例的管理员，或者具有帐户 IAM 许可权，才能向其他用户授予策略。

下表列出了用户要能够启动 Web UI 并通过 {{site.data.keyword.at_full_notm}} Web UI 查看数据而必须具有的最基本策略：

| 角色                      | 授予的许可权       |
|---------------------------|---------------------|
| 平台角色：`查看者`     | 允许用户在“可观察性”仪表板中查看服务实例的列表。|
| 服务角色：`读取者`     | 允许用户通过 Web UI 查看事件。| 
{: caption="表 1. IAM 策略" caption-side="top"} 

有关更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。


## 步骤 2. 通过 {{site.data.keyword.cloud_notm}} UI 启动 Web UI
{: #launch_step2}

在 {{site.data.keyword.at_full_notm}} 实例的上下文中，通过 {{site.data.keyword.cloud_notm}} UI 来启动 Web UI。 

要启动 Web UI，请完成以下步骤：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}}“仪表板”即会打开。

2. 单击**菜单**图标 ![“菜单”图标](../icons/icon_hamburger.svg) > **可观察性**。 

3. 选择 **Activity Tracker**。 

    这将显示 {{site.data.keyword.at_full_notm}} 实例的列表。

    每个区域有 1 个实例。
    {: important}

4. 选择要查看事件的区域中的实例。然后，单击**查看 LogDNA**。

这将打开 {{site.data.keyword.at_full_notm}} Web UI，并显示**所有内容**视图。通过此视图，您可以在您的帐户中查看所选区域的事件。



## 从 {{site.data.keyword.cloud_notm}} 获取 Web UI URL
{: #launch_get}

要获取 Web UI URL，请通过终端完成以下步骤：

1. 设置供应 {{site.data.keyword.at_full_notm}} 实例的资源组。

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. 设置 {{site.data.keyword.at_full_notm}} 实例名称。

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. 设置端点。

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. 设置 IAM 令牌。

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **注：**如果是在 MacOS 终端上工作，那么该命令如下所示：`export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. 设置资源组标识。

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. 在变量中设置 Web UI URL。

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. 获取 Web UI URL。

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

