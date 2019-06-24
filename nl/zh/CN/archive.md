---

copyright:
  years: 2019
lastupdated: "2019-05-01"

keywords: IBM Cloud, LogDNA, Activity Tracker, archive logs, COS, cloud object storage

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

 
# 将事件归档到 IBM Cloud Object Storage
{: #archiving}

您可以将 {{site.data.keyword.at_full_notm}} 实例中的事件归档到 {{site.data.keyword.cos_full_notm}} (COS) 实例中的存储区。
{:shortdesc}

完成以下步骤以将 {{site.data.keyword.at_full_notm}} 实例归档到 {{site.data.keyword.cos_full_notm}} 实例的存储区中：

## 先决条件
{: #archiving_prereqs}

* [了解有关归档事件的更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-manage_events#manage_events_archive)。

* **您必须具有 {{site.data.keyword.at_full_notm}} 服务的付费服务套餐**。[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。 

* 检查用户标识是否有权启动 Web UI 和管理事件。下表列出了用户要能够启动 {{site.data.keyword.at_full_notm}} Web UI 以及查看、搜索和过滤事件而必须具有的最基本角色：

|角色|授予的许可权
|
|---------------------------|-------------------------------|  
| 平台角色：`查看者`     | 允许用户在“可观察性”仪表板中查看服务实例的列表。|
| 服务角色：`管理者`     | 允许用户启动 Web UI 并在 Web UI 中管理事件。|
{: caption="表 1. IAM 角色" caption-side="top"} 

有关如何为用户配置策略的更多信息，请参阅[授予用户对用户或服务标识的许可权](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。



## 步骤 1. 将 IAM 策略授予用户以使用 {{site.data.keyword.cos_full_notm}}
{: #archiving_step1}

**注：**此步骤必须由帐户所有者或 {{site.data.keyword.cloud_notm}} 上的 {{site.data.keyword.cos_full_notm}} 服务的管理员完成。

作为 {{site.data.keyword.cos_full_notm}} 服务的管理员，您必须能够供应服务的实例，向其他用户授予使用这些实例的许可权，并创建服务标识。 

可以通过不同的方式来向用户授予成为 {{site.data.keyword.cos_full_notm}} 服务的编辑者的许可权：

* 作为帐户中服务的管理员，用户必须针对 {{site.data.keyword.cos_full_notm}} 服务分配有带有*管理员*平台角色的 IAM 策略。您必须为此用户分配对帐户中单个资源的访问权。 

* 作为资源组上下文中的服务的管理员，用户必须在该资源组的上下文中针对 {{site.data.keyword.cos_full_notm}} 服务分配有带有*管理员*平台角色的 IAM 策略。 


下表列出了用户为完成针对 {{site.data.keyword.cos_full_notm}} 服务所列出的操作而可以具有的角色：

| 服务                    | 平台角色    | 操作                                                                                        | 
|----------------------------|-------------------|-----------------------------------------------------------------------------------------------|       
| `Cloud Object Storage`     | 管理员 | 允许用户将策略分配给该帐户中的用户以使用 {{site.data.keyword.cos_full_notm}} 服务。|
| `Cloud Object Storage`     | 管理员 </br>编辑者 | 允许用户供应 {{site.data.keyword.cos_full_notm}} 服务的实例。    |
| `Cloud Object Storage`     | 管理员 </br>编辑者 </br>操作员 | 允许用户创建服务标识。    | 
{: caption="表 1. 角色和操作" caption-side="top"} 


完成以下步骤，以在资源组上下文中向用户分配对 {{site.data.keyword.cos_full_notm}} 服务的管理员角色： 

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	使用用户标识和密码登录后，{{site.data.keyword.cloud_notm}} UI 即会打开。
    
2. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
3. 在要为其分配访问权的用户所在的行中，选择**操作**菜单，然后单击**分配访问权**。
4. 选择**在资源组中分配访问权**。
5. 选择资源组。
6. 如果用户尚未针对所选资源组授予角色，请为**分配对资源组的访问权**字段选择角色。 

    根据选择的角色，用户可以在其仪表板上查看资源组，编辑资源组名称或管理用户对该组的访问权。 
    
    如果希望用户仅有权访问资源组中的 {{site.data.keyword.at_full_notm}} 服务，那么可以选择**无访问权**。

7. 选择 **Cloud Object Storage**。
8. 选择**管理员**平台角色。
9. 单击**分配**。



## 步骤 2. 供应 {{site.data.keyword.cos_full_notm}} 的实例
{: #archiving_step2}

**注：**此步骤必须由 {{site.data.keyword.cloud_notm}} 上的 {{site.data.keyword.cos_full_notm}} 服务的编辑者或管理员完成。完成以下步骤以供应 {{site.data.keyword.cos_full_notm}} 实例：

1. 在菜单栏中，单击**目录**。这将打开 {{site.data.keyword.cloud_notm}} 中提供的服务的列表。

2. 要过滤所显示的服务列表，请选择**存储器**类别。

3. 单击**对象存储器**磁贴。

4. 输入服务实例的名称。

5. 选择资源组。 

    缺省情况下，已设置 **Default** 资源组。

6. 选择服务套餐。 

    缺省情况下，已设置**轻量**套餐。

7. 单击**创建**。



## 步骤 3. 创建存储区
{: #archiving_step3}

存储区是在 {{site.data.keyword.cos_full_notm}} 实例中组织数据的一种方法。 

要管理存储区，必须授予用户在 {{site.data.keyword.cos_full_notm}} 实例上使用存储区的许可权。下表概述了使用存储区时用户可以执行的操作以及具有的角色：

| 服务                    |角色|操作| 
|----------------------------|-------------------------|------------------------------------|       
| `Cloud Object Storage`     | 平台角色：查看者  | 允许用户查看所有存储区，并列出这些存储区中的对象。|
| `Cloud Object Storage`     | 服务角色：管理者  | 允许用户使对象成为公共对象。                                                       |
| `Cloud Object Storage`     | 服务角色：管理者 </br>写入者 | 允许用户创建和销毁存储区和对象。                         | 
| `Cloud Object Storage`     | 服务角色：读取者  | 允许用户列出和下载对象。                                                 |
{: caption="表 1. 使用存储区所需的角色以及可执行的操作" caption-side="top"} 

**注：**要创建存储区，您的用户必须具有 {{site.data.keyword.cos_full_notm}} 实例的管理者或写入者许可权。

完成以下步骤以创建存储区：

1. 从“导航”菜单中，选择**资源列表**。

2. 选择您计划在其中创建存储区的 {{site.data.keyword.cos_full_notm}} 实例。

3. 选择**存储区**。然后，单击**创建存储区**。

4. 在*唯一存储区名称*字段中输入存储区名称。

    **注：**全球所有区域中的所有存储区都共享一个名称空间。 

    您可以将 {{site.data.keyword.at_full_notm}} 实例名称用作存储区名称的一部分。例如，对于名称为 *logdn-1* 的实例，可以将 *accountN-logdn-1* 用作存储区名称。

    您将需要此名称以通过 {{site.data.keyword.at_full_notm}} Web UI 来配置归档。

5. 选择弹性类型以及希望物理存储数据的位置。

    弹性是指数据分布所在的地理区域的范围和规模。 
    
    跨区域弹性将跨多个大都市区域分布数据。
    
    区域弹性将跨单个大都市区域分布数据。 
    
    单个数据中心将仅在单个站点内的设备之间分布数据。

    有关更多信息，请参阅[选择区域和端点](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints)。

6. 选择*存储类*的类型。

    您可以使用不用的存储类来创建存储区。根据您的需求来选择存储区的存储类以检索数据。有关更多信息，请参阅[使用存储类](/docs/services/cloud-object-storage?topic=cloud-object-storage-classes)。

    **注：**一旦创建存储区，就将无法更改存储区的存储类。如果对象需要重新分类，那么需要将相应数据移至另一个使用所需存储类的存储区中。

7. （可选）添加 Key Protect 密钥以对数据进行静态加密。

    缺省情况下，所有对象都会使用随机生成的密钥以及全有或全无变换进行加密。虽然此缺省加密模型提供了静态安全性，但某些工作负载需要拥有所使用的加密密钥。 有关更多信息，请参阅[管理加密](/docs/services/cloud-object-storage?topic=cloud-object-storage-encryption)。




## 步骤 4. 为 {{site.data.keyword.cos_full_notm}} 实例创建服务标识
{: #archiving_step4}

服务标识用于识别服务，类似于用户标识识别用户的方式。服务标识不与特定用户相绑定。如果创建服务标识的用户离开组织并从帐户中删除，那么服务标识会保留。

您必须为 {{site.data.keyword.cos_full_notm}} 实例创建服务标识。此服务标识由 {{site.data.keyword.at_full_notm}} 实例用于向 {{site.data.keyword.cos_full_notm}} 实例进行认证。 

您必须为限制使用特定服务的许可权的服务标识分配特定访问策略，甚至可以组合许可权以访问不同的服务。例如，要限制对单个存储区的访问，请确保服务标识不具有任何使用控制台或者 CLI 的实例级别策略。


完成以下步骤以创建针对 {{site.data.keyword.cos_full_notm}} 实例具有写许可权的服务标识：

1. 在仪表板中，选择您计划在其中创建存储区的 {{site.data.keyword.cos_full_notm}} 实例。

2. 选择**服务凭证**。然后，选择**新建凭证**。

3. 输入易于识别的名称。例如，可以将服务标识命名为 `activity-tracker-cos-serviceID`。 

4. 选择**写入者**角色。

5. 单击**添加**。

    新的服务标识已创建并添加到列表中。 

    **注：**在 {{site.data.keyword.cloud_notm}} 中创建并通过 IAM UI 列出来的服务标识有一个通用名称。IAM UI 中服务标识的名称会映射到您在此步骤中通过 COS 服务标识 UI 创建的字段 **iam_apikey_name** 的值。
    
6. [可选] 要锁定服务标识以阻止删除，请在菜单栏中单击**管理** &gt; **访问权 (IAM)**。搜索服务标识。然后，选择操作**锁定**。


针对刚刚创建的服务标识，单击**查看凭证**。您可以查看与该服务标识相关的信息。 

* 复制 API 密钥。这是为字段 **apikey** 设置的值。
* 复制资源实例标识。这是为字段 **resource_instance_id** 设置的值。
* 复制 **iam_apikey_name** 字段的值。


## 步骤 5. 将服务标识限制为对存储区仅具有写许可权
{: #archiving_step5}

如果要将服务标识限制为对存储区仅具有写许可权，请完成以下步骤：

1. 在 COS UI 中，选择存储区。

2. 从存储区菜单中，选择**策略**。这将打开*存储区访问策略*页面。

3. 选择**服务标识**。

4. 在**选择服务标识**字段中，查找名称为 **auto-generated-serviceId-<属于 iam_apikey_name 值的一部分的标识> 的服务标识。

5. 选择服务标识。然后，在**访问策略**中，选择 **写入者**。

6. 单击**创建访问策略**。



## 步骤 6. 选择端点
{: #archiving_step6}

端点定义了要在何处查找存储区。根据区域和弹性类型的不用，端点也不同。有关更多信息，请参阅[选择区域和端点](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints)。

完成以下步骤以获取存储区的端点：

1. [登录到 {{site.data.keyword.cloud_notm}} 帐户 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/login){:new_window}。

	登录后，{{site.data.keyword.cloud_notm}}“仪表板”即会打开。

2. 在仪表板中，选择您计划在其中创建存储区的 {{site.data.keyword.cos_full_notm}} 实例。

3. 选择**存储区**。然后，选择您创建的要在其中归档事件的存储区。

4. 选择**配置**。

5. 复制其中一个专用端点。 



## 步骤 7. 将 IAM 策略授予用户以归档事件
{: #archiving_step7}

下表列出了用户为将事件配置为从 {{site.data.keyword.at_full_notm}} Web UI 归档到 {{site.data.keyword.cos_full_notm}} 实例中的存储区中而必须具有的策略：

|服务|角色|授予的许可权
| 
|--------------------------------------|---------------------------|-------------------------------------|  
| `{{site.data.keyword.at_full_notm}}` | 平台角色：查看者  | 允许用户在“可观察性 - 日志记录”仪表板中查看服务实例的列表。|
| `{{site.data.keyword.at_full_notm}}` | 服务角色：管理者  | 允许用户启动 Web UI 并在 Web UI 中查看事件。|
{: caption="表 2. IAM 策略" caption-side="top"} 

[了解更多信息](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam)。

完成以下步骤以向用户分配归档事件的许可权： 

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 在要为其分配访问权的用户所在的行中，选择**操作**菜单，然后单击**分配访问权**。
3. 选择**在资源组中分配访问权**。
4. 选择资源组。
5. 如果用户尚未针对所选资源组授予角色，请为**分配对资源组的访问权**字段选择角色。 

    根据选择的角色，用户可以在其仪表板上查看资源组，编辑资源组名称或管理用户对该组的访问权。 
    
    如果希望用户仅有权访问资源组中的 {{site.data.keyword.at_full_notm}} 服务，那么可以选择**无访问权**。

6. 选择 **IBM Log Analysis with LogDNA**。
7. 选择**查看者**平台角色。
8. 选择**管理者**服务角色。
9. 单击**分配**。



## 步骤 8. 针对 {{site.data.keyword.at_full_notm}} 实例配置归档
{: #archiving_step8}


完成以下步骤以配置将 {{site.data.keyword.at_full_notm}} 实例归档到 COS 存储区中：

1. [启动 {{site.data.keyword.at_full_notm}} Web UI](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch)。

2. 选择**配置**图标。然后选择**归档**。 

3. 选择 **IBM Cloud Object Storage**。

4. 设置要在其中归档事件的存储区、端点、API 密钥和实例标识。

    <table>
      <caption>表 3. COS 字段</caption>
      <tr>
         <th>字段</th>
         <th>值</th>
      </tr>
      <tr>
         <td>存储区</td>
         <td>设置为 COS 存储区名称。</td>
      </tr>
      <tr>
         <td>端点</td>
         <td>设置为 COS 存储区专用端点。</td>
      </tr>
      <tr>
         <td>API 密钥</td>
         <td>设置为与 COS 服务标识相关联的 API 密钥。</td>
      </tr>
      <tr>
         <td>实例标识</td>
         <td>设置为 COS 实例标识。</td>
      </tr>
    </table>

5. 单击**保存**。


保存配置后，事件将每天归档一次。



