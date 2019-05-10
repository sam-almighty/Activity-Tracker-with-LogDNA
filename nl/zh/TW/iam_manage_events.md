---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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

 
# 將管理許可權授與使用者或服務 ID
{: #iam_manage_events}

{{site.data.keyword.iamlong}} (IAM) 可讓您在 {{site.data.keyword.cloud_notm}} 中，安全地鑑別使用者以及一致地控制對所有雲端資源的存取。請完成下列步驟，授與使用者或服務 ID 使用 {{site.data.keyword.at_full_notm}} 服務的管理許可權：
{:shortdesc}

例如，身為服務的管理者，您可以佈建及移除服務的實例、授與其他使用者使用服務的許可權、將日誌保存至 {{site.data.keyword.cos_full_notm}}(COS) 實例等等。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam)。

## 步驟 1. 建立存取群組
{: #ime_step1}

請完成下列步驟來建立存取群組：

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**存取群組**。
2. 按一下**建立**。
3. 輸入群組的名稱和選用說明，然後按一下**建立**。

您可以選取**移除群組**選項，來刪除群組。從帳戶移除群組時，會從群組移除所有使用者及服務 ID，以及指派給該群組的所有存取權。
{: note}

若要使用 CLI 建立存取群組，您可以使用 [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) 指令。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## 步驟 2. 新增許可權以管理事件
{: #ime_step2}

在設定群組之後，您可以將一般存取原則指派給群組。 

您針對存取群組設定的任何原則都會套用至群組內的所有實體、使用者和服務 ID。
{: note}

您可以利用使用者介面或透過指令行來指派原則。

若要使用 CLI 建立存取群組原則，您可以使用 [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) 指令。

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

請完成下列步驟，透過使用者介面將原則指派給存取群組：

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**存取群組**。
2. 選取您要指派存取權的群組名稱。 
3. 按一下**存取原則**。
4. 按一下**指派存取權**。
5. 選擇依資源群組內的資源指派存取權、依帳戶內可用的個別資源指派存取權，還是依帳戶管理服務指派存取權。例如，您可以選擇下列任何選項，授與使用者管理 {{site.data.keyword.at_full_notm}} 實例的管理者角色：

### 選項 1. 將許可權授與使用者，以變成 {{site.data.keyword.cloud_notm}} 帳戶中服務的管理者
{: #admin_account_opt1}

若要授與使用者管理帳戶中服務的管理者角色，使用者必須具有平台角色**管理者**對 {{site.data.keyword.at_full_notm}} 服務的 IAM 原則。您必須將此使用者存取權指派給帳戶中的個別資源。 

請完成下列步驟，將帳戶中 {{site.data.keyword.at_full_notm}} 服務的管理者角色指派給使用者： 

1. 選取**指派對資源的存取權**。
2. 選取 **IBM Cloud Activity Tracker with LogDNA**。
3. 選取**所有現行地區**。
4. 選取**所有現行服務實例**。
5. 選取平台角色**管理者**。
6. 選取服務角色**管理員**。
7. 按一下**指派**。

### 選項 2. 將許可權授與使用者，以變成資源群組內服務的管理者
{: #admin_account_opt2}

若要將管理者角色授與使用者，以管理帳戶中資源群組內的實例，使用者在資源群組的環境定義內，必須具有平台角色**管理者**對 {{site.data.keyword.at_full_notm}} 服務的 IAM 原則。 

請完成下列步驟，將資源群組環境定義內 {{site.data.keyword.at_full_notm}} 服務的管理者角色指派給使用者： 

1. 選取**指派資源群組內的存取權**。
2. 選取資源群組。
3. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.at_full_notm}} 服務的存取權，可以選取**不存取**。

4. 選取 **IBM Cloud Activity Tracker with LogDNA**。
5. 選取平台角色**管理者**。
6. 選取服務角色**管理員**。
7. 按一下**指派**。

### 選項 3. 將許可權授與使用者，以變成 {{site.data.keyword.cloud_notm}} 中單一服務實例的管理者
{: #admin_account_opt3}

請完成下列步驟，將某個 {{site.data.keyword.at_full_notm}} 服務實例的管理者角色指派給使用者： 

1. 選取**指派對資源的存取權**。
2. 選取 **IBM Cloud Activity Tracker with LogDNA**。
3. 選取實例。
4. 選取平台角色**管理者**。
5. 選取服務角色**管理員**。
6. 按一下**指派**。



## 步驟 3. 將使用者或服務 ID 新增至存取群組
{: #ime_step3}

繼續新增使用者或服務 ID 來設定您的群組。

### 將使用者新增至存取群組
{: #ime_step3_user}

請完成下列步驟來新增使用者：

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**存取群組**。
2. 選取您要指派存取權的群組名稱。 
3. 按一下**使用者**標籤上的**新增使用者**。
4. 從清單中選取您要新增的使用者，然後按一下**新增至群組**。


### 將服務 ID 新增至存取群組
{: #ime_step3_svcid}

請完成下列步驟來新增服務 ID：

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**存取群組**。
2. 選取您要指派存取權的群組名稱。 
3. 按一下**服務 ID** 標籤，然後按一下**新增服務 ID**。
4. 從清單中選取您要新增的 ID，然後按一下**新增至群組**。




