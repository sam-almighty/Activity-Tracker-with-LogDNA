---

copyright:
  years: 2019
lastupdated: "2019-05-22"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# 向用户或服务标识授予管理许可权
{: #iam_manage_events}

通过 {{site.data.keyword.iamlong}} (IAM)，您能够在 {{site.data.keyword.cloud_notm}} 中安全地认证用户，并以一致的方式控制对所有云资源的访问权。完成以下步骤，以向用户或服务标识授予使用 {{site.data.keyword.at_full_notm}} 服务的管理许可权：
{:shortdesc}

例如，作为服务的管理员，您可以供应和除去服务的实例，授予其他用户使用服务的许可权以及将日志归档到 {{site.data.keyword.cos_full_notm}} (COS) 实例等。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam)。

## 先决条件
{: #iam_manage_events_prereq}

您的用户标识需要**管理员平台许可权**才能管理 {{site.data.keyword.at_full_notm}} 服务。请联系帐户管理员。帐户所有者可以授予其他用户对帐户的访问权，以便管理用户访问权和管理帐户资源。[了解更多信息](/docs/iam?topic=iam-userroles)。


## 步骤 1. 创建访问组
{: #ime_step1}

要创建访问组，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 单击**创建**。
3. 输入组的名称和可选描述，然后单击**创建**。

可以通过选择**除去组**选项来删除组。从帐户中除去组时，将除去该组中的所有用户和服务标识以及分配给该组的所有访问权。
{: note}

要使用 CLI 创建访问组，可以使用 [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) 命令。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## 步骤 2. 添加许可权以管理事件
{: #ime_step2}

设置组后，可以为该组分配公共访问策略。 

为访问组设置的任何策略都将应用于该组中的所有实体、用户和服务标识。
{: note}

您可以使用 UI 或通过命令行来分配策略。

要使用 CLI 创建访问组策略，可以使用 [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) 命令。

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

定义策略时，需要选择平台角色和服务角色：
* 平台管理角色涵盖一系列操作，包括创建和删除实例，管理别名、绑定和凭证，以及管理访问权的能力。平台角色有管理员、编辑者、操作员和查看者。平台管理角色还适用于帐户管理服务，这些服务支持用户邀请其他用户，管理服务标识、访问策略和目录条目以及跟踪计费和使用情况，具体取决于用户在帐户管理服务上所分配的角色。
* 服务访问角色定义用户或服务对服务实例执行操作的能力。服务访问角色有管理者、写入者和读取者。

要管理 {{site.data.keyword.at_full_notm}} 服务，用户需要以下角色：
* 平台角色：**管理员**。 
* 服务角色：**管理者**。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam)。

要通过 UI 为访问组分配策略，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 选择要为其分配访问权的组的名称。 
3. 单击**访问策略**。
4. 单击**分配访问权**。
5. 选择是按资源组中的资源，还是按帐户中可用的单个资源分配访问权。例如，可以选择以下任一选项向用户授予管理 {{site.data.keyword.at_full_notm}} 的管理员角色：

### 选项 1. 授予对服务的许可权
{: #admin_account_opt1}

要为用户分配对帐户中 {{site.data.keyword.at_full_notm}} 服务的管理员角色，请完成以下步骤： 

1. 选择**分配对资源的访问权**。
2. 选择 **IBM Cloud Activity Tracker with LogDNA**。
3. 选择**所有当前区域**。
4. 选择**所有当前服务实例**。
5. 选择**管理员**平台角色。
6. 选择**管理者**服务角色。
7. 单击**分配**。

### 选项 2. 授予资源组的上下文中的许可权
{: #admin_account_opt2}

要为用户分配对资源组上下文中 {{site.data.keyword.at_full_notm}} 服务的管理员角色，请完成以下步骤： 

1. 选择**在资源组中分配访问权**。
2. 选择资源组。
3. 如果尚未向用户授予针对所选资源组的角色，请为**分配对资源组的访问权**字段选择角色。 

    根据选择的角色，用户可以在其仪表板上查看资源组，编辑资源组名称或管理用户对该组的访问权。 
    
    如果希望用户仅有权访问资源组中的 {{site.data.keyword.at_full_notm}} 服务，那么可以选择**无访问权**。

4. 选择 **IBM Cloud Activity Tracker with LogDNA**。
5. 选择**管理员**平台角色。
6. 选择**管理者**服务角色。
7. 单击**分配**。

### 选项 3. 授予对某个位置的许可权
{: #admin_account_opt3}

每个位置只能供应 1 个 {{site.data.keyword.at_full_notm}} 服务实例。因此，使用此选项授予许可权时，是按位置控制访问权。
{: note}

要为用户分配对 {{site.data.keyword.at_full_notm}} 服务的一个实例的管理员角色，请完成以下步骤： 

1. 选择**分配对资源的访问权**。
2. 选择 **IBM Cloud Activity Tracker with LogDNA**。
3. 选择实例。
4. 选择**管理员**平台角色。
5. 选择**管理者**服务角色。
6. 单击**分配**。



## 步骤 3. 将用户或服务标识添加到访问组
{: #ime_step3}

继续通过添加用户或服务标识来设置组。

### 将用户添加到访问组
{: #ime_step3_user}

要添加用户，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 选择要为其分配访问权的组的名称。 
3. 单击**用户**选项卡上的**添加用户**。
4. 从列表中选择要添加的用户，然后单击**添加到组**。


### 将服务标识添加到访问组
{: #ime_step3_svcid}

要添加服务标识，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 选择要为其分配访问权的组的名称。 
3. 单击**服务标识**选项卡，然后单击**添加服务标识**。
4. 从列表中选择要添加的标识，然后单击**添加到组**。




