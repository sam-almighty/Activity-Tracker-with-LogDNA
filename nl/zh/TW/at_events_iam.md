---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# IAM 事件
{: #at_events_iam}

身為安全性管理者、審核員或管理員，您可以使用 {{site.data.keyword.at_full_notm}} 服務，來追蹤使用者及應用程式如何與 {{site.data.keyword.cloud_notm}} 中的 {{site.data.keyword.iamlong}} (IAM) 服務互動。
{:shortdesc}

IAM 可讓您在 {{site.data.keyword.cloud_notm}} 中安全地針對兩個平台服務鑑別使用者，並以一致的方式控制對資源的存取權。[進一步瞭解](/docs/iam?topic=iam-iamoverview)。


{{site.data.keyword.at_full_notm}} 服務會記錄由使用者起始並且會變更 {{site.data.keyword.cloud_notm}} 中服務狀態的活動。若要開始監視您使用者的動作，請參閱 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。起始者可以是使用者、服務或應用程式。



## 存取群組事件
{: #at_events_iam_access}

下表列出產生事件的動作：

| 動作 | 說明 |
|-----------------------------|---------|
| `iam-groups.group.create`   | 起始者建立存取群組時會產生事件。| 
| `iam-groups.group.read`     | 起始者查看與存取群組相關的資訊時會產生事件。|
| `iam-groups.group.update`   | 起始者更新群組名稱或說明時會產生事件。|
| `iam-groups.group.delete`   | 起始者刪除存取群組時會產生事件。|
| `iam-groups.member.add`     | 起始者將成員新增至存取群組時會產生事件。|
| `iam-groups.member.delete`  | 起始者從存取群組中移除成員時會產生事件。|
| `iam-groups.member.read`    | 起始者檢查成員的成員資格時會產生事件。|
| `iam-groups.rule.read`      | 起始者檢視存取群組中的規則時會產生事件。|
| `iam-groups.rule.create`    | 起始者將規則新增至存取群組時會產生事件。|
| `iam-groups.rule.update`    | 起始者修改規則名稱時會產生事件。|
| `iam-groups.rule.delete`    | 起始者從存取群組中刪除規則時會產生事件。|
{: caption="表 1. 管理存取群組動作" caption-side="top"} 



## 原則事件
{: #at_events_iam_policies}

下表列出產生事件的動作：

| 動作 | 說明 |
|------------------------|---------|
| `iam-am.policy.create` | 起始者將原則新增至使用者或存取群組時會產生事件。|
| `iam-am.policy.delete` | 起始者修改使用者或存取群組的原則許可權時會產生事件。|
| `iam-am.policy.update` | 起始者刪除指派給使用者或存取群組的原則時會產生事件。|
{: caption="表 5. 管理原則動作" caption-side="top"} 



## 服務 ID 事件
{: #at_events_iam_serviceids}

下表列出產生事件的動作：

| 動作 | 說明 |
|----------|---------|
| `iam-identity.account-serviceid.create` | 起始者建立服務 ID 時會產生事件。| 
| `iam-identity.account-serviceid.update` | 起始者重新命名服務 ID 或修改其說明時會產生事件。| 
| `iam-identity.account-serviceid.delete` | 起始者刪除服務 ID 時會產生事件。| 
{: caption="表 2. 使用服務 ID 動作" caption-side="top"} 


## API 金鑰事件
{: #at_events_iam_apikeys}

下表列出產生事件的動作：

| 動作 | 說明 |
|----------|---------|
| `iam-identity.user-apikey.create`      | 起始者建立 API 金鑰時會產生事件。| 
| `iam-identity.user-apikey.update`      | 起始者重新命名 API 金鑰或修改其說明時會產生事件。|  
| `iam-identity.user-apikey.delete`      | 起始者刪除 API 金鑰時會產生事件。|  
| `iam-identity.serviceid-apikey.create` | 起始者建立服務 ID 的 API 金鑰時會產生事件。|  
| `iam-identity.serviceid-apikey.delete` | 起始者刪除服務 ID 的 API 金鑰時會產生事件。|  
{: caption="表 3. 使用 API 金鑰動作" caption-side="top"} 


## 登入事件
{: #at_events_iam_login}

下表列出產生事件的動作：

| 動作 | 說明 |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         |使用者使用 API 金鑰登入 {{site.data.keyword.cloud_notm}} 時會產生事件。|  
| `iam-identity.serviceid-apikey.login`    |起始者使用與服務 ID 相關聯的 API 金鑰登入 {{site.data.keyword.cloud_notm}} 時會產生事件。|  
| `iam-identity.user-identitycookie.login` |這是起始者要求身分 Cookie 執行動作時所產生的事件。|
| `iam-identity.user-refreshtoken.login`   | 這是當起始者登入 IBM Cloud 時，或是已登入 IBM Cloud 的起始者要求新的重新整理記號來執行動作時，所產生的事件。|
{: caption="表 4. 使用者登入動作" caption-side="top"} 


## 檢視事件
{: #at_events_iam_ui}

在**法蘭克福 (eu-de)** 地區有可用的事件。若要檢視這些事件，您必須在**法蘭克福 (eu-de)** 地區中佈建 {{site.data.keyword.at_full_notm}} 服務的[實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然後，您必須[開啟 {{site.data.keyword.at_full_notm}} 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 


## 分析事件
{: #at_events_iam_analyze}


### 刪除存取群組
{: #an_del_ag}

刪除存取群組時，所觸發事件的 `action` 欄位會設定為 `iam-groups.group.delete`。

刪除存取群組時，請考慮下列資訊：
* 會自動觸發其他動作，以清除與該群組關聯的其他資源。觸發的某些動作會報告事件，這些事件與刪除存取群組中的成員、刪除原則和刪除動態規則相關。 
* 這些動作的起始者是 {{site.data.keyword.IBM_notm}} 服務 ID。


刪除的存取群組未指派成員、原則和規則時，為其中任何資源產生的事件所報告的結果均為 `failure`，並且結果代碼為 `404`。下列範例顯示在刪除未指派成員、原則或動態規則的存取群組時所產生的事件：

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

