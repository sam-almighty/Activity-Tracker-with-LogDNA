---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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

{{site.data.keyword.at_full_notm}} 服務會記錄由使用者起始並且會變更 {{site.data.keyword.cloud_notm}} 中服務狀態的活動。若要開始監視您使用者的動作，請參閱 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。 

起始者可以是使用者、服務或應用程式。
{: tip}

## 管理存取群組事件
{: #at_events_iam_access}

下表列出產生事件的動作：

| 動作 | 說明 |
|----------|---------|
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




## 檢視事件
{: #at_events_iam_ui}

在**美國南部**地區有可用的事件。 

若要檢視這些事件，您必須在**美國南部**地區中佈建 {{site.data.keyword.at_full_notm}} 服務的[實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。然後，您必須[開啟 {{site.data.keyword.at_full_notm}} 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。 


