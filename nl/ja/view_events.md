---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# イベントの表示
{: #view_events}

{{site.data.keyword.cloud_notm}} に {{site.data.keyword.at_full_notm}} サービスのインスタンスをプロビジョンすると、{{site.data.keyword.at_full_notm}} Web UI を介してイベントを表示できます。イベントはユーザーの現地時間で表示されます。{:shortdesc}


## イベントの表示
{: #view_events_step1}

イベントを表示するには、以下のステップを実行します。

1. 自分のユーザー ID に、Web UI を起動してイベントを表示するための権限があるか確認します。 

    以下の表は、ユーザーが {{site.data.keyword.at_full_notm}} の Web UI を起動してイベントを表示、検索、フィルタリングするために最低限必要な役割を示しています。

    <table>
      <caption>表 1. IAM 役割</caption>
      <tr>
        <th>役割</th>
        <th>付与される許可</th>
      </tr>
      <tr>
        <td>プラットフォーム役割: `ビューアー`</td>
        <td>ユーザーが*「プログラム識別情報」*ダッシュボードでサービス・インスタンスのリストを表示できるようにします。</td>
      </tr>
      <tr>
        <td>サービス役割: `リーダー`</td>
        <td>ユーザーが Web UI を起動して Web UI でイベントを表示、検索、フィルタリングできるようにします。</td>
      </tr>
    </table>

    ユーザーに対してポリシーを構成する方法について詳しくは、[ユーザー許可をユーザーまたはサービス ID に付与する](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)を参照してください。

2. [Web UI に移動します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。

3. **「ビュー」**アイコン ![構成アイコン](images/views.png) をクリックします。

4. すべてのイベントまたは 1 つのビューを表示するには、**「すべて (Everything)」** を選択します。 

選択したビューを介してイベントを表示できます。



## 検索照会を適用してイベントのサブセットを表示する
{: #view_events_step2}

検索照会を適用して、ビューで表示されるイベントを選択できます。このビューを後で再使用するために保存できます。[詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2)。

 


## 時間フレームを適用してイベントのサブセットを表示する
{: #view_events_step3}

時間フレームを適用して、ビューで表示されるイベントを選択できます。

絶対時刻、相対時間、または時刻範囲を指定してタイム・スタンプを適用できます。

特定の時刻にジャンプするには、以下のステップを実行します。
1. [Web UI に移動します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。
2. **「ビュー」**アイコン ![構成アイコン](images/views.png) をクリックします。
3. **「すべて (Everything)」**または 1 つのビューを選択します。
4. 時刻照会を入力します。以下のいずれかのオプションを選択します。

    * `May 20 7:00pm` などの、イベント内の特定の時点にジャンプするための絶対時間を入力します。
    
    * `2 days ago`、`today at 12am`、`an hour ago` などの相対時刻を入力します。

    * `yesterday 10am to yesterday 11am`、`last fri 4:30pm to 11/12 1 AM`、`last wed 4:30pm to 23/05 1 AM`、`May 20 10am to May 22 10am` などの時刻範囲を入力します。開始タイム・スタンプと終了タイム・スタンプを区切る `to` を必ず入力してください。

5. **Enter** をクリックします。

    `「要求は予想より長い時間がかかっています。後れを取り戻そうとしているので、すぐにブラウザーの最新表示を試行してください。再試行してください。(Your request is taking longer than expected, try refreshing your browser in a bit as we try to catch up. Retry.)」`というエラー・メッセージが表示されます。このエラーは、指定した時間フレームに表示可能なイベントがない場合に発生することがあります。時間照会を変更し、再試行してください。



## コンテキストでイベントを表示する
{: #view_events_step4}

コンテキスト内の各イベント行を随時表示できます。

以下のステップを実行します。 

1. Web UI で、**「ビュー」**アイコン ![構成アイコン](images/views.png "構成アイコン") をクリックします。
2. **「すべて (Everything)」**または 1 つのカスタム・ビューを選択します。
3. 調べる行を特定します。
4. イベント行を展開します。 

    行 ID、タグ、およびラベルに関する情報が表示されます。

5. **「コンテキスト内のビュー (View in Context)」**をクリックすると、そのホストまたはアプリ、あるいはその両方からの他の項目のコンテキスト内のイベント行が表示されます。

イベントの探索が終了したら、**「閉じる」**をクリックしてイベント行を閉じます。



## イベントをクリップボードにコピーする
{: #view_events_step5}


イベントをクリップボードにコピーするには、以下のステップを実行します。 

1. Web UI で、**「ビュー」**アイコン ![構成アイコン](images/views.png "構成アイコン") をクリックします。
2. **「すべて (Everything)」**または 1 つのカスタム・ビューを選択します。
3. 調べる行を特定します。
4. イベント行を展開します。 

    行 ID、タグ、およびラベルに関する情報が表示されます。

5. **「クリップボードにコピー」**をクリックすると、イベントがクリップボードにコピーされます。

イベントの探索が終了したら、**「閉じる」**をクリックしてイベント行を閉じます。




