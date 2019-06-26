---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# イベントのエクスポート
{: #export}

データを JSONL 形式で {{site.data.keyword.at_full_notm}} インスタンスからローカル・ファイルにエクスポートできます。 LogDNA REST API または Web UI を使用して、ログをプログラムによってエクスポートできます。
{:shortdesc}


## 前提条件
{: #export_prereqs}

* [イベントのエクスポート方法について確認します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_export)。

* {{site.data.keyword.at_full_notm}} サービスの**有料サービス・プランのご利用**が必要です。 [詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。 

* 自分のユーザー ID に Web UI を起動してイベントを表示するための権限があるか確認します。以下の表は、ユーザーが {{site.data.keyword.at_full_notm}} の Web UI を起動してイベントを表示、検索、フィルタリングするために最低限必要な役割を示しています。

| 役割                      | 付与される許可            |
|---------------------------|-------------------------------|  
| プラットフォーム役割: `ビューアー`     | ユーザーが「プログラム識別情報」ダッシュボードでサービス・インスタンスのリストを表示できるようにします。 |
| サービス役割: `リーダー`      | ユーザーが Web UI を起動して Web UI にイベントを表示できるようにします。  |
{: caption="表 1. IAM 役割" caption-side="top"} 

ユーザーに対してポリシーを構成する方法について詳しくは、[ユーザー許可をユーザーまたはサービス ID に付与する](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)を参照してください。


## ステップ 1. Web UI へ移動する
{: #export_step1}

[Web UI に移動します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## ステップ 2. ビューを作成する
{: #export_step2}

[ビューを作成します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。


## ステップ 3. データをエクスポートする
{: #export_step3}

次のいずれかのオプションを選択して、イベントをエクスポートします。

### オプション 1. Web UI からイベントをエクスポートする
{: #export_ui}

データをエクスポートするには、以下のステップを実行します。

1. **「ビュー」**アイコン ![構成アイコン](images/views.png) をクリックします。
2. **「すべて (Everything)」**または 1 つのビューを選択します。
3. エクスポートしようとしている項目が表示されるまで、時間フレーム、フィルター、検索基準を適用します。
4. **「すべて (Everything)」**ビューから開始している場合は、**「保存されていないビュー (Unsaved View)」**をクリックします。 前のステップでビューを選択した場合は、ビュー名をクリックします。
5. **「行のエクスポート (Export lines)」**を選択します。 新しいウィンドウが開きます。
6. 時刻範囲を確認します。 変更する必要がある場合は、*「エクスポート対象の時刻範囲の変更 (Change the Time Range for export)」*フィールド内で事前定義された時刻範囲をクリックします。
7. エクスポート要求が行の制限を超える場合は、**「新しい行を優先 (Prefer newer lines)」**または**「古い行を優先 (Prefer older lines)」**を選択します。
8. E メールを確認します。 **LogDNA** から、エクスポートされた行をダウンロードするためのリンクがある E メールを受信します。


### オプション 2. API を使用してイベントをプログラマチックにエクスポートする
{: #export_api}

イベントをプログラマチックにエクスポートするには、以下のステップを実行します。

1. サービス・キーを生成します。 

    **注:** このステップを完了するには、{{site.data.keyword.at_full_notm}} インスタンスまたはサービスに対する**管理者**の役割がなければなりません。

    1. [{{site.data.keyword.at_full_notm}} Web UI を起動します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。

    2. **「構成」**アイコン ![構成アイコン](images/admin.png) を選択します。 次に、**「組織」**を選択します。 

    3. **「API キー」**を選択します。

        作成したサービス・キーが表示されます。 

    4. **「サービス・キーの生成 (Generate Service Key)」**をクリックします。リストに新しい鍵が追加されます。 このキーをコピーします。

2. イベントをエクスポートします。 次の cURL コマンドを実行します。

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    説明 

    * ENDPOINT は、サービスのエントリー・ポイントを表します。 地域ごとに URL は異なります。 [詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints)。
    * QUERY_PARAMETERS は、エクスポート要求に適用されるフィルター基準を定義するパラメーターです。
    * SERVICE_KEY は、前のステップで作成したサービス・キーです。

以下の表に、設定できる照会パラメーターをリストします。

| 照会パラメーター | タイプ       | 状況     | 説明 |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | 必須   | 開始時刻。 秒単位かミリ秒単位の UNIX タイム・スタンプとして設定します。 |
| `to`        | `int32`      | 必須   | 終了時刻。 秒単位かミリ秒単位の UNIX タイム・スタンプとして設定します。    |
| `size`      | `string`     | オプション   | エクスポートに組み込むログ行の数。  | 
| `hosts`     | `string`     | オプション   | ホストのコンマ区切りリスト。 |
| `apps`      | `string`     | オプション   | アプリケーションのコンマ区切りリスト。 |
| `levels`    | `string`     | オプション   | ログ・レベルのコンマ区切りリスト。 |
| `query`     | `string`     | オプション   | 検索照会。 詳しくは、[検索ログ](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6)を参照してください。 |
| `prefer`    | `string`     | オプション   | エクスポートするログ行を定義します。 有効な値は `head` (最初のログ行) と `tail` (最後のログ行) です。 指定されていない場合、デフォルトの tail になります。  |
| `email`     | `string`     | オプション   | エクスポート内容をダウンロードできるリンクがある E メールを指定します。 デフォルトでは、ログ行はストリーミングされます。|
| `emailSubject` | `string`     | オプション   | E メールの件名を設定するために使用します。 </br>スペースを表すには、`%20` を使用します。 例えば、サンプル値は `Export%20logs` です。 |
{: caption="照会パラメーター" caption-side="top"} 

例えば、イベントを端末にストリーミングするには、以下のコマンドを実行できます。

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

エクスポートで指定されているイベントをダウンロードするためのリンクがある E メールを送信するには、以下のコマンドを実行できます。

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


件名がカスタマイズされた E メールを送信するには、以下のコマンドを実行できます。

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

