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

# アカウント管理イベント  
{: #at_events_acc_mgt}

セキュリティー担当者、監査員、またはマネージャーは、{{site.data.keyword.at_full_notm}} サービスを使用して、ユーザーおよびアプリケーションが {{site.data.keyword.cloud_notm}} アカウントとどのように対話しているのかをトラッキングできます。 
{:shortdesc}

{{site.data.keyword.at_full_notm}} サービスは、{{site.data.keyword.cloud_notm}} 内のサービスの状態を変更するユーザー開始アクティビティーを記録します。 開始する方法については、[{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)を参照してください。 



## アカウント管理のイベント
{: #at_events_acc_mgt_account}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                               | 説明 |
|--------------------------------------|-------------|
| `billing.account.create`             | アカウントをプロビジョンすると、そのアカウントにアカウント ID が割り当てられた後に、イベントが生成されます。|
| `billing.account.update`             | アカウントに関する情報を更新すると、イベントが生成されます。|
| `billing.account.active`             | アカウントを検証すると、イベントが生成されます。つまり、アカウントがアクティブになると、イベントが生成されます。|
| `billing.account.subscription.create` | <a href="/docs/account?topic=account-accounts#subscription-account">サブスクリプション・アカウント</a>を作成すると、イベントが生成されます。|
{: caption="表 1. イベントを生成するアクション" caption-side="top"} 




## ユーザー管理のイベント
{: #at_events_acc_mgt_users}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                               | 説明 |
|--------------------------------------|-------------|
| `user-management.user.create`        | アカウントに参加するようにユーザーに招待を送信すると、イベントが生成されます。|
| `user-management.user.active`        | アカウントでユーザーをアクティブにすると、イベントが生成されます。このイベントは、ユーザーが E メール・アドレスを検証したときに生成されます。|
| `user-management.user.delete`        | アカウントからユーザーを削除すると、イベントが生成されます。|
{: caption="表 2. イベントを生成するアクション" caption-side="top"} 




## 組織管理のイベント
{: #at_events_acc_mgt_org}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                               | 説明 |
|--------------------------------------|-------------|
| `billing.account.org.create`         | アカウントに組織を追加すると、イベントが生成されます。|
{: caption="表 3. イベントを生成するアクション" caption-side="top"} 


## タグ管理のイベント
{: #at_events_acc_mgt_resources}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                               | 説明 |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | リソースにタグを追加すると、イベントが生成されます。|
| `ghost-tags.tag.detach-tag`          | リソースからタグを削除すると、イベントが生成されます。|
{: caption="表 4. イベントを生成するアクション" caption-side="top"} 


## イベントを検索する場所
{: #at_events_acc_mgt_ui}

イベントは、**フランクフルト (eu-de)** 地域内で使用可能です。 

これらのイベントを表示するには、**フランクフルト (eu-de)** 地域に {{site.data.keyword.at_full_notm}} サービスの[インスタンスをプロビジョンする](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)必要があります。次に、[{{site.data.keyword.at_full_notm}}UI を開く](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)必要があります。 












