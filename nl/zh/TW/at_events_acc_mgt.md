---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# 帳戶管理事件  
{: #at_events_acc_mgt}

身為安全性管理者、審核員或管理員，您可以使用 {{site.data.keyword.at_full_notm}} 服務來追蹤使用者及應用程式如何與 {{site.data.keyword.cloud_notm}} 帳戶互動。
{:shortdesc}

{{site.data.keyword.at_full_notm}} 服務會記錄由使用者起始並且會變更 {{site.data.keyword.cloud_notm}} 中服務狀態的活動。若要開始使用，請參閱 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。 



## 管理帳戶的事件
{: #at_events_acc_mgt_account}

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------------|-------------|
|`billing.account.create`|將帳戶 ID 指派給帳戶並佈建此帳戶後，會產生事件。|
|`billing.account.update`|當您更新帳戶的相關資訊，即會產生事件。|
|`billing.account.active`|驗證帳戶時會產生事件，亦即，當該帳戶變成作用中時會產生事件。|
|`billing.account.subscription.create`|當您建立<a href="/docs/account?topic=account-accounts#subscription-account">訂閱帳戶</a>時，會產生事件。|
{: caption="表 1. 可產生事件的動作" caption-side="top"} 




## 管理使用者的事件
{: #at_events_acc_mgt_users}

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------------|-------------|
|`user-management.user.create`|當您將邀請傳送至使用者以加入帳戶時，會產生事件。|
|`user-management.user.active`|當您啟動帳戶中的使用者時，會產生事件。當使用者驗證電子郵件位址時，會產生事件。|
|`user-management.user.delete`|當您從帳戶中移除使用者時，會產生事件。|
{: caption="表 2. 產生事件的動作" caption-side="top"} 




## 管理組織的事件
{: #at_events_acc_mgt_org}

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------------|-------------|
|`billing.account.org.create`|當您將組織新增至帳戶時，會產生事件。|
{: caption="表 3. 產生事件的動作" caption-side="top"} 


## 管理標籤的事件
{: #at_events_acc_mgt_resources}

下表列出產生事件的動作：

| 動作                             | 說明 |
|--------------------------------------|-------------|
|`ghost-tags.tag.attach-tag`|將標籤新增至資源時，會產生事件。|
|`ghost-tags.tag.detach-tag`|從資源中移除標籤時，會產生事件。|
{: caption="表 4. 產生事件的動作" caption-side="top"} 


## 到何處尋找事件
{: #at_events_acc_mgt_ui}

在**法蘭克福 (eu-de)** 地區有可用的事件。 

若要檢視這些事件，您必須在**法蘭克福 (eu-de)** 地區中佈建 {{site.data.keyword.at_full_notm}} 服務的[實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然後，您必須[開啟 {{site.data.keyword.at_full_notm}} 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 












