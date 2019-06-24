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


# IAM イベント
{: #at_events_iam}

セキュリティー担当者、監査員、またはマネージャーは、{{site.data.keyword.at_full_notm}} サービスを使用して、ユーザーおよびアプリケーションが {{site.data.keyword.cloud_notm}} 内の {{site.data.keyword.iamlong}} (IAM) サービスとどのように対話しているのかをトラッキングできます。 
{:shortdesc}

IAM を使用すると、両方のプラットフォーム・サービスに関してユーザーをセキュアに認証でき、また {{site.data.keyword.cloud_notm}} 全体で一貫してリソースへのアクセスを制御できます。[詳細はこちら](/docs/iam?topic=iam-iamoverview)。


{{site.data.keyword.at_full_notm}} サービスは、{{site.data.keyword.cloud_notm}} 内のサービスの状態を変更するユーザー開始アクティビティーを記録します。 ユーザーのアクションのモニターを開始するには、[{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)を参照してください。 イニシエーターは、ユーザー、サービス、またはアプリケーションのいずれかです。


## アクセス・グループ・イベント
{: #at_events_iam_access}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                      | 説明 |
|-----------------------------|---------|
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



## ポリシー・イベント
{: #at_events_iam_policies}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                 | 説明 |
|------------------------|---------|
| `iam-am.policy.create` | イニシエーターがユーザーまたはアクセス・グループにポリシーを追加すると、イベントが生成されます。 |
| `iam-am.policy.delete` | イニシエーターがユーザーまたはアクセス・グループのポリシーへの許可を変更すると、イベントが生成されます。|
| `iam-am.policy.update` | イニシエーターがユーザーまたはアクセス・グループに割り当てられたポリシーを削除すると、イベントが生成されます。 |
{: caption="表 5. ポリシー管理アクション" caption-side="top"} 



## サービス ID イベント
{: #at_events_iam_serviceids}

次の表に、イベントを生成するアクションのリストを示します。

| アクション | 説明 |
|----------|---------|
| `iam-identity.account-serviceid.create` | イニシエーターがサービス ID を作成すると、イベントが生成されます。  | 
| `iam-identity.account-serviceid.update` | イニシエーターがサービス ID の名前または説明を変更すると、イベントが生成されます。 | 
| `iam-identity.account-serviceid.delete` | イニシエーターがサービス ID を削除すると、イベントが生成されます。 | 
{: caption="表 2. サービス ID 処理アクション" caption-side="top"} 


## API キー・イベント
{: #at_events_iam_apikeys}

次の表に、イベントを生成するアクションのリストを示します。

| アクション | 説明 |
|----------|---------|
| `iam-identity.user-apikey.create`      | イニシエーターが API キーを作成すると、イベントが生成されます。 | 
| `iam-identity.user-apikey.update`      | イニシエーターが API キーの名前または説明を変更すると、イベントが生成されます。 |  
| `iam-identity.user-apikey.delete`      | イニシエーターが API キーを削除すると、イベントが生成されます。 |  
| `iam-identity.serviceid-apikey.create` | イニシエーターがサービス ID 用の API キーを作成すると、イベントが生成されます。 |  
| `iam-identity.serviceid-apikey.delete` | イニシエーターがサービス ID 用の API キーを削除すると、イベントが生成されます。 |  
{: caption="表 3. API キー処理アクション" caption-side="top"} 


## ログイン・イベント
{: #at_events_iam_login}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                                   | 説明 |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | ユーザーが API キーを使用して {{site.data.keyword.cloud_notm}} にログインすると、イベントが生成されます。 |  
| `iam-identity.serviceid-apikey.login`    | イニシエーターがサービス ID と関連付けられた API キーを使用して {{site.data.keyword.cloud_notm}} にログインすると、イベントが生成されます。 |  
| `iam-identity.user-identitycookie.login` | これは、イニシエーターがアクションを実行するために ID Cookie を要求すると生成されるイベントです。|
| `iam-identity.user-refreshtoken.login`   | これは、イニシエーターが IBM Cloud にログインするか、または、IBM Cloud に既にログインしたイニシエーターがアクションを実行するために新しいリフレッシュ・トークンを要求すると生成されるイベントです。 |
{: caption="表 4. ユーザーのログインのアクション" caption-side="top"} 


## イベントの表示
{: #at_events_iam_ui}

イベントは、**フランクフルト (eu-de)** 地域内で使用可能です。これらのイベントを表示するには、**フランクフルト (eu-de)** 地域に {{site.data.keyword.at_full_notm}} サービスの[インスタンスをプロビジョンする](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)必要があります。次に、[{{site.data.keyword.at_full_notm}}UI を開く](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)必要があります。 


## イベントの分析
{: #at_events_iam_analyze}


### アクセス・グループを削除します
{: #an_del_ag}

アクセス・グループを削除すると、トリガーされるイベントの `action` フィールドが `iam-groups.group.delete` に設定されます。

アクセス・グループが削除されたときには、以下の情報を考慮してください。
* その他のアクションが自動的にトリガーされて、グループに関連付けられている他のリソースをクリーンアップします。トリガーされる一部のアクションは、アクセス・グループ内のメンバーの削除、ポリシーの削除、および動的ルールの削除に関連するイベントを報告します。 
* これらのアクションのイニシエーターは、{{site.data.keyword.IBM_notm}} サービス ID です。


削除されるアクセス・グループにメンバー、ポリシー、およびルールが割り当てられていない場合、これらのリソースのいずれかに対して生成されるイベントは、`failure` の結果を `404` 結果コードと共に報告します。以下のサンプルは、メンバー、ポリシー、または動的ルールが割り当てられていないアクセス・グループが削除されたときに生成されるイベントを示しています。

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

