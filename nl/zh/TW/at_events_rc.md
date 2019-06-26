---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# 服務實例事件  
{: #at_events_rc}

身為安全性管理者、審核員或管理員，您可以使用 {{site.data.keyword.at_full_notm}} 服務來追蹤使用者及應用程式如何與 {{site.data.keyword.cloud_notm}} 服務互動。
{:shortdesc}

{{site.data.keyword.at_full_notm}} 服務會記錄由使用者起始並且會變更 {{site.data.keyword.cloud_notm}} 中服務狀態的活動。若要開始監視您使用者的動作，請參閱 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。 


## 佈建及管理服務實例的事件
{: #rc_provision}

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------|---------|
|`service_name.instance.create`|當您佈建服務實例時，會產生事件。|
|`service_name.instance.update`|當您重新命名服務實例或變更服務方案時，會產生事件。|
|`service_name.instance.delete`|在刪除服務實例時，會產生事件。|
{: caption="表 1. 可產生事件的動作" caption-side="top"} 


##  管理與服務實例相關聯的別名的事件
{: #rc_alias}

別名是資源群組內 IAM 管理的服務，與組織或空間內的應用程式，兩者之間的連線。

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------|---------|
|`service_name.alias.create`|建立實例的別名時，會產生事件。|
|`service_name.alias.update`|更新實例的別名時，會產生事件。|
|`service_name.alias.delete`|刪除實例的別名時，會產生事件。|
{: caption="表 2. 產生事件的動作" caption-side="top"} 


##  管理與服務實例相關聯的服務認證的事件
{: #rc_keys}

服務認證提供將應用程式連接至服務實例的必要資訊。 

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------|---------|
|`service_name.key.create`|透過服務實例使用者介面的*服務認證* 區段為服務實例建立 API 金鑰時，會產生事件。|
|`service_name.key.delete`|從服務實例使用者介面的*服務認證* 區段刪除與服務實例相關聯的 API 金鑰時，會產生事件。|
{: caption="表 3. 產生事件的動作" caption-side="top"} 



##  將服務實例連結至應用程式以及從應用程式取消連結服務實例的事件
{: #rc_bind}

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------|---------|
|`service_name.binding.create`|當您將服務實例連結至應用程式時，會產生事件。|
|`service_name.binding.delete`|當您從應用程式取消連結服務實例時，會產生事件。|
{: caption="表 4. 產生事件的動作" caption-side="top"} 



## 到何處尋找事件
{: #rc_ui}

在**法蘭克福 (eu-de)** 地區有可用的事件。 

若要檢視這些事件，您必須在**法蘭克福 (eu-de)** 地區中佈建 {{site.data.keyword.at_full_notm}} 服務的[實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然後，您必須[開啟 {{site.data.keyword.at_full_notm}} 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 



## 分析事件
{: #rc_analyze}

**動作：service_name.instance.delete**

刪除服務實例時，請考慮下列資訊：
* 會自動觸發其他動作，以清除 IAM 許可權。這些動作將移除針對帳戶中的使用者和服務 ID 配置以使用服務實例的原則。 
* 這些動作的起始者是 {{site.data.keyword.IBM_notm}} 服務 ID。


刪除的服務實例未針對使用者和服務 ID 配置 IAM 原則時，為其中任何資源自動產生的事件所報告的結果均為 `failure`，並且結果代碼為 `404`。下列範例顯示在刪除帳戶中未配置原則的服務實例時所產生的事件：

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



