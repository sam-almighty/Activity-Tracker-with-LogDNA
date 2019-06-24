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

# サービス・インスタンスのイベント  
{: #at_events_rc}

セキュリティー担当者、監査員、またはマネージャーは、{{site.data.keyword.at_full_notm}} サービスを使用して、ユーザーおよびアプリケーションが {{site.data.keyword.cloud_notm}} サービスとどのように対話しているのかをトラッキングできます。 
{:shortdesc}

{{site.data.keyword.at_full_notm}} サービスは、{{site.data.keyword.cloud_notm}} 内のサービスの状態を変更するユーザー開始アクティビティーを記録します。 ユーザーのアクションのモニターを開始するには、[{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)を参照してください。 


## サービス・インスタンスのプロビジョンおよび管理のイベント
{: #rc_provision}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                         | 説明 |
|--------------------------------|---------|
| `service_name.instance.create` | サービス・インスタンスをプロビジョンすると、イベントが生成されます。|
| `service_name.instance.update` | サービス・インスタンスを名前変更するか、サービス・プランを変更すると、イベントが生成されます。|
| `service_name.instance.delete` | サービス・インスタンスが削除されると、イベントが生成されます。|
{: caption="表 1. イベントを生成するアクション" caption-side="top"} 


##  サービス・インスタンスに関連付けられている別名の管理のイベント
{: #rc_alias}

別名は、リソース・グループ内の IAM 管理サービスと、組織またはスペース内のアプリケーションとの間の接続です。

次の表に、イベントを生成するアクションのリストを示します。

| アクション                         | 説明 |
|--------------------------------|---------|
| `service_name.alias.create` | インスタンスの別名が作成されると、イベントが生成されます。|
| `service_name.alias.update` | インスタンスの別名が更新されると、イベントが生成されます。|
| `service_name.alias.delete` | インスタンスの別名が削除されると、イベントが生成されます。|
{: caption="表 2. イベントを生成するアクション" caption-side="top"} 


##  サービス・インスタンスに関連付けられているサービス資格情報の管理のイベント
{: #rc_keys}

サービス資格情報は、アプリケーションをサービス・インスタンスに接続するために必要な情報を提供します。 

次の表に、イベントを生成するアクションのリストを示します。

| アクション                         | 説明 |
|--------------------------------|---------|
| `service_name.key.create` | サービス・インスタンス UI の*「サービス資格情報」*セクションを介してサービス・インスタンス用の API キーが作成されると、イベントが生成されます。|
| `service_name.key.delete` | サービス・インスタンス UI の*「サービス資格情報」*セクションから、サービス・インスタンスと関連付けられた API キーが削除されると、イベントが生成されます。|
{: caption="表 3. イベントを生成するアクション" caption-side="top"} 



##  アプリへのサービス・インスタンスのバインドおよびアンバインドのイベント
{: #rc_bind}

次の表に、イベントを生成するアクションのリストを示します。

| アクション                         | 説明 |
|--------------------------------|---------|
| `service_name.binding.create` | サービス・インスタンスをアプリケーションにバインドすると、イベントが生成されます。|
| `service_name.binding.delete` | サービス・インスタンスをアプリケーションからアンバインドすると、イベントが生成されます。|
{: caption="表 4. イベントを生成するアクション" caption-side="top"} 



## イベントを検索する場所
{: #rc_ui}

イベントは、**フランクフルト (eu-de)** 地域内で使用可能です。 

これらのイベントを表示するには、**フランクフルト (eu-de)** 地域に {{site.data.keyword.at_full_notm}} サービスの[インスタンスをプロビジョンする](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)必要があります。次に、[{{site.data.keyword.at_full_notm}}UI を開く](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)必要があります。 



## イベントの分析
{: #rc_analyze}

**アクション: service_name.instance.delete**

サービス・インスタンスが削除されたときには、以下の情報を考慮してください。
* その他のアクションが自動的にトリガーされて、IAM 許可をクリーンアップします。これらのアクションは、アカウント内のユーザーおよびサービス ID に対して構成された、そのサービス・インスタンスを処理するためのポリシーを削除します。 
* これらのアクションのイニシエーターは、{{site.data.keyword.IBM_notm}} サービス ID です。


削除されるサービス・インスタンスに、ユーザーおよびサービス ID に対して構成された IAM ポリシーがない場合、これらのリソースのいずれかに対して自動的に生成されるイベントは、`failure` の結果を `404` 結果コードと共に報告します。以下のサンプルは、アカウントにポリシーが構成されていないサービス・インスタンスが削除されたときに生成されるイベントを示しています。

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



