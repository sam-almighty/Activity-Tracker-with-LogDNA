---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# カスタム・ビューの作成
{: #views}

{{site.data.keyword.at_full_notm}} の Web UI を使用して、検索基準やフィルター基準を適用することで、カスタム・ビューで表示されるイベントを定義できます。
{:shortdesc}


## 前提条件
{: #views_prereqs}

開始する前に、自分のユーザー ID に Web UI を起動してイベントを表示するための権限があるか確認します。 以下の表は、ユーザーが {{site.data.keyword.at_full_notm}} の Web UI を起動してイベントを表示、検索、フィルタリングするために最低限必要な役割を示しています。

| 役割                      | 付与される許可            |
|---------------------------|-------------------------------|  
| プラットフォーム役割: `ビューアー`     | ユーザーが「プログラム識別情報」ダッシュボードでサービス・インスタンスのリストを表示できるようにします。 |
| サービス役割: `リーダー`      | ユーザーが Web UI を起動して Web UI にイベントを表示できるようにします。  |
{: caption="表 1. IAM 役割" caption-side="top"} 

ユーザーに対してポリシーを構成する方法について詳しくは、[ユーザー許可をユーザーまたはサービス ID に付与する](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)を参照してください。



## ステップ 1. Web UI に移動してビューを選択する
{: #views_step1}

以下のステップを実行します。

1. [Web UI に移動します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。
2. **「ビュー」**アイコン ![構成アイコン](images/views.png) をクリックします。
3. **「すべて (Everything)」**または 1 つのビューを選択します。 


## ステップ 2. 検索照会を適用して、ビューで表示されるイベントのセットを選択する
{: #views_step2}

特定のイベントを検索するには、検索照会を適用できます。 

* 単純検索 (単一語ストリング検索)、複合検索 (複数の検索語と演算子)、フィールド検索 (ログ行を解析できる場合) などを行えます。 詳しくは、[LogDNA 資料の「How to Search Logs」 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://docs.logdna.com/docs/search){:new_window} を参照してください。
* AND 演算子と OR 演算子は大/小文字が区別されるため、大文字にする必要があります。

イベントを検索できるのは、インスタンスのサービス・プランで指定された日数の間に限られます。
{: important}


以下のステップを実行します。
1. 検索照会を入力します。 
2. **Enter** をクリックします。 

照会を適用すると、ビューの名前が**「保存されていないビュー (Unsaved View)」**に変わっていることがわかります。


### サービスによって生成されるイベントの照会
{: #views_step1_1}

特定のサービスに関するイベントをフィルターで除外するには、以下の照会を入力する必要があります。

```
_supertenant:SERVICENAME
```
{: codeblock}

`SERVICENAME` は、{{site.data.keyword.cloud_notm}} 内のサービスの名前です。

以下の表に、コア・サービスをリストします。

| イベントを生成するサービス               | 値                         | サンプル照会            |
|--------------------------------------------|-------------------------------|----------------------------------|
| [IAM アクセス管理サービス](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [IAM Identity サービス](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [IAM アクセス・グループ・サービス](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)   | `iam-groups`  | `_supertenant:iam-groups`     |
| [リソース・コントローラー・サービス](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="表 2. サービス名別の照会" caption-side="top"}

### サービスによって生成されるイベントのセットの照会
{: #views_step1_2}

サービスでさまざまなタイプのイベントが生成される場合、以下の照会を入力できます。

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

説明 

* `SERVICENAME` は {{site.data.keyword.cloud_notm}} 内のサービスの名前
* `TYPEOFACTION` は複合照会で、AND 演算子と OR 演算子を使用でき、`-` を使用してデータを除外することもできます。`AND` 演算子と `OR` 演算子は大/小文字が区別されるため、大文字にする必要があることに注意してください。


以下の表は、サービスによって生成されるイベントのグループを照会する方法の例を示しています。

| イベントを生成するサービス               | イベントのタイプ     | サンプル照会                     |
|--------------------------------------------|--------------------|---------------------------------|
| `IAM Identity サービス`                     | [ログイン・イベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `IAM Identity サービス`                     | [API キー・イベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `IAM Identity サービス`                     | [アカウント・サービス ID イベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `リソース・コントローラー`                      | [サービス・インスタンスのプロビジョニングと管理](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `リソース・コントローラー`                      | [アカウント内のユーザーの管理](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="表 3. 複雑な照会のサンプル" caption-side="top"}


### 特定のアクションがあるイベントの照会
{: #views_step1_3}

各イベントには、そのイベントをトリガーしたアクションについて通知する **action** フィールドがあります。以下の照会を入力して、アクションが同じであるイベントをすべて検索できます。

```
action ACTIONVALUE
```
{: codeblock}

`ACTIONVALUE` は、アクション・フィールドの値または値の一部です。

以下の表に、さまざまなアクションに関する照会の例を示します。

| アクション                 | サンプル照会                     |
|------------------------|----------------------------------|
| サービスのプロビジョン    | `action instance.create`         |
| インスタンスの削除     | `action instance.delete`         |
| ユーザーの追加             | `action user-management.user.create` |
{: caption="表 4. アクション・タイプ別の照会のサンプル" caption-side="top"}



### アクションが失敗したイベントの照会
{: #views_step1_4}

要求されたアクションが失敗すると、**outcome** フィールドが **failure** に設定されます。以下の照会を入力して、これらのタイプのイベントを検索できます。

```
outcome failure
```
{: codeblock}


### イベントの重大度別の照会
{: #views_step1_5}

各イベントには、クラウドでアクションが持つ可能性のある脅威のレベルを定義する **severity** フィールドがあります。 

有効な値は、*normal*、*warning*、*critical* です。 
* **normal** は、クラウドでのルーチン・アクションに対して設定されます。例えば、インスタンスの開始や、トークンのリフレッシュなどです。 
* **warning** は、クラウド・リソースの更新またはクラウド・リソースのメタデータの変更が行われるアクションに対して設定されます。例えば、ワーカー・ノードのバージョンの更新、証明書の名前変更、サービス・インスタンスの名前変更などです。 
* **critical** は、クラウドでのセキュリティーに影響するアクションに対して設定されます。例えば、ユーザーの資格情報の変更、データの削除、クラウド・リソースの処理のための無許可アクセスなどです。

以下の照会を入力して、これらのタイプのイベントを検索できます。

```
severity VALUE
```
{: codeblock}

`VALUE` は *normal*、*warning*、または *critical* に設定できます。

例えば、重大なイベントを照会するには、以下のコマンドを実行できます。

```
severity critical
```
{: codeblock}



## ステップ 3. カスタム・ビューを作成する
{: #views_step3}

検索照会を**「すべて (Everything)」**ビューまたは既存のカスタム・ビューに適用した後に、以下のステップを実行して結果をカスタム・ビューとして保存します。

1. Web UI で、**「保存されていないビュー (Unsaved View)」**をクリックします。
2. **「新規ビュー/アラートとして保存 (Save as new view / alert)」**を選択します。 *「新規ビューの作成 (Create new view)」*ページが開きます。
3. *「名前」* フィールドにビューの名前を入力します。
4. 必要に応じて、カテゴリーを追加します。 名前を入力してから、**「これを新規ビューのカテゴリーとして追加 (Add this as new view category)」**をクリックします。
5. 必要に応じて、アラートをアタッチします。 アラートを構成するための新しいセクションが表示されます。
6. **「ビューを保存 (Save View)」**をクリックします。


## ステップ 4. ビューでイベント行が表示される方法をカスタマイズする
{: #views_step4}

ビューでのデータの表示方法をカスタマイズする方法には、さまざまなオプションがあります。
* ビューのプロパティーを変更できます。ビューの名前を変更したり、ビューの説明の追加または変更を行ったり、特定の行フォーマットを適用したりできます。
* *「ユーザー設定」* セクション内で`ログ・フォーマット`を変更できます。
* *「ツール」*セクションから行テンプレートを適用できます。適用すると、その他の回線構成がオーバーライドされることに注意してください。**「これらの設定を保持する (Persist these settings)」**を選択すると、この UI のすべてのビューで、このセクションで指定された行フォーマットごとにデータが表示されます。
* **「ツール」**セクションで**「用語の強調表示 (Highlight Terms)」**を設定すると、用語またはストリングに色を適用できます。



### 「プロパティーの表示 (view properties)」ページでの行フォーマットの変更
{: #views_step4_1}

単一のビューでイベント行のフォーマットを変更するには、以下のステップを実行します。

1. ビューで、**「ビュー・プロパティーの編集(Edit View Properties)」**を選択します。*「ビュー・プロパティーの編集 (Edit View Properties)」*ページが開きます。

2. **「カスタム行テンプレート (Custom %LINE Template)」**セクションで、カスタムの行フォーマットを入力します。デフォルトは `{{line}}` に設定されています。

    行テンプレートの指針について詳しくは、[指針](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)を参照してください。

3. 「プロパティーの保存 (Save properties)」をクリックします。



### 「ユーザー設定」セクションでの行フォーマットの変更
{: #views_step4_2}

**「ユーザー設定」**セクションで、行単位で表示されるデータ・フィールドの順序を変更できます。

イベント行のフォーマットを変更するには、以下のステップを実行します。

1. Web UI で、**「構成」**アイコン ![構成アイコン](images/admin.png "管理アイコン") をクリックします。
2. **「ユーザー設定」**を選択します。 新しいウィンドウが開きます。
3. **「ログ・フォーマット (Log Format)」**を選択します。
4. *要件に合わせて「行フォーマット (Line Format)」*セクションを変更します。 ボックスをドラッグします。


### 「ツール」セクション内での行テンプレートによる行フォーマットの変更
{: #views_step4_3}

イベント行のフォーマットを変更するには、以下のステップを実行します。

1. ビューで、**「ツール」**アイコン ![「ツール」アイコン](images/tool.png "「ツール」アイコン") をクリックします。
2. **「行テンプレート (Line Template)」**フィールドで、カスタムの行フォーマットを入力します。行テンプレートの指針について詳しくは、[指針](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)を参照してください。
3. オプションで、**「これらの設定を保持する (Persist these settings)」**をクリックして、すべてのビューに行フォーマットを適用します。



### 用語の強調表示
{: #view_events_step4_4}

ビュー内で用語を強調表示するには、以下のステップを実行します。

1. ビューで、**「ツール」**アイコン ![「ツール」アイコン](images/tool.png "「ツール」アイコン") をクリックします。
2. **「行テンプレート (Line Template)」**フィールドで、**「用語の強調表示 (Highlight Terms)」**セクションに単語またはストリングを入力します。
3. オプションで、**「これらの設定を保持する (Persist these settings)」**をクリックして、すべてのビューにこれらの設定を適用します。



## カスタム・ビューの名前と説明の変更
{: #views_step5}

ビューの名前を変更できます。ビューの説明を追加したり変更したりできます。


以下のステップを実行します。

1. ビューで、**「ビュー・プロパティーの編集(Edit View Properties)」**を選択します。*「ビュー・プロパティーの編集(Edit View Properties)」*ページが開きます。

    ビューの名前を変更したり、ビューの説明の追加または変更を行ったり、カスタムの行フォーマットを適用したりできます。

2. **「ビューの名前変更 (Rename View)」**セクションで新しい名前を入力して、ビューの名前を変更します。

3. **「説明」**セクションで、説明を入力するか変更します。

4. **「プロパティーの保存 (Save properties)」**をクリックします。



## 行テンプレートの定義に関する指針
{: #views_line}

行テンプレートを定義する際には、以下の指針を適用する必要があるので考慮してください。
* mustache スタイルの `{{field.name}}` 変数か bash スタイルの `${field.name}` 変数を使用して、テンプレートを構成します。 
* `{{line}}` または `$@` を使用して、元の行を参照します。 
* その他の文字やストリングはすべて、テキスト・リテラルとして解釈されます。 


例えば、行テンプレートを `{{initiator.id}} -- {{action}} -- {{message}}` と定義して、ビュー内のイベントごとにこれらのフィールドを表示できます。


