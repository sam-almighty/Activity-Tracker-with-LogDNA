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


# IAM イベント
{: #at_events_iam}

セキュリティー担当者、監査員、またはマネージャーは、{{site.data.keyword.at_full_notm}} サービスを使用して、ユーザーおよびアプリケーションが {{site.data.keyword.cloud_notm}} 内の {{site.data.keyword.iamlong}} (IAM) サービスとどのように対話しているのかをトラッキングできます。 
{:shortdesc}

{{site.data.keyword.at_full_notm}} サービスは、{{site.data.keyword.cloud_notm}} 内のサービスの状態を変更するユーザー開始アクティビティーを記録します。 ユーザーのアクションのモニターを開始するには、[{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)を参照してください。 

イニシエーターは、ユーザー、サービス、またはアプリケーションのいずれかです。
{: tip}

## アクセス・グループ管理のイベント
{: #at_events_iam_access}

次の表に、イベントを生成するアクションのリストを示します。

| アクション | 説明 |
|----------|---------|
| `iam-groups.group.create`   | イニシエーターがアクセス・グループを作成すると、イベントが生成されます。 | 
| `iam-groups.group.read`     | イニシエーターがアクセス・グループに関連する情報を参照すると、イベントが生成されます。 |
| `iam-groups.group.update`   | イニシエーターがグループの名前または説明を更新すると、イベントが生成されます。 |
| `iam-groups.group.delete`   | イニシエーターがアクセス・グループを削除すると、イベントが生成されます。 |
| `iam-groups.member.add`     | イニシエーターがアクセス・グループにメンバーを追加すると、イベントが生成されます。 |
| `iam-groups.member.delete`  | イニシエーターがアクセス・グループからメンバーを削除すると、イベントが生成されます。 |
| `iam-groups.member.read`    | イニシエーターがメンバーのメンバーシップをチェックすると、イベントが生成されます。 |
| `iam-groups.rule.read`      | イニシエーターがアクセス・グループ内のルールを表示すると、イベントが生成されます。 |
| `iam-groups.rule.create`    | イニシエーターがアクセス・グループにルールを追加すると、イベントが生成されます。 |
| `iam-groups.rule.update`    | イニシエーターがルール名を変更すると、イベントが生成されます。 |
| `iam-groups.rule.delete`    | イニシエーターがアクセス・グループからルールを削除すると、イベントが生成されます。 |
{: caption="表 1. アクセス・グループ管理アクション" caption-side="top"} 




## イベントの表示
{: #at_events_iam_ui}

イベントは、**米国南部**地域内で使用可能です。 

これらのイベントを表示するには、**米国南部**地域に {{site.data.keyword.at_full_notm}} サービスの[インスタンスをプロビジョンする](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)必要があります。 次に、[{{site.data.keyword.at_full_notm}}UI を開く](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)必要があります。 


