---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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
{: #view_events.md}

{{site.data.keyword.cloud_notm}} に {{site.data.keyword.at_full_notm}} サービスのインスタンスをプロビジョンすると、{{site.data.keyword.at_full_notm}} Web UI を介してイベントを表示できます。
{:shortdesc}


## 前提条件
{: #view_events_prereqs}

開始する前に、自分のユーザー ID に Web UI を起動し、イベントを表示するための権限があるか確認します。 

**注:** ポリシーを管理するには、{{site.data.keyword.at_full_notm}} サービスの管理者または {{site.data.keyword.at_full_notm}} インスタンスの管理者であるか、アカウントの IAM 権限が必要です。

次の表は、{{site.data.keyword.at_full_notm}} Web UI を起動してイベントを表示するためにユーザーに必要な最小限のポリシーをリストしたものです。

| 役割                      | 付与される許可            |
|---------------------------|-------------------------------|  
| プラットフォーム役割: `ビューアー`     | ユーザーが「プログラム識別情報」ダッシュボードでサービス・インスタンスのリストを表示できるようにします。 |
| サービス役割: `リーダー`      | ユーザーが Web UI を起動して Web UI にイベントを表示できるようにします。  |
{: caption="表 1. IAM ポリシー" caption-side="top"} 

ユーザーに対してこれらのポリシーを構成する方法について詳しくは、[ユーザー許可をユーザーまたはサービス ID に付与する](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)を参照してください。


## Web UI によるイベントの表示
{: #view_events_step1}

{{site.data.keyword.at_full_notm}} Web UI を起動するには、以下のステップを実行します。

1. [{{site.data.keyword.cloud_notm}} アカウントにログイン ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/login){:new_window} します。

	ユーザー ID とパスワードを使用してログインすると、{{site.data.keyword.cloud_notm}} *ダッシュボード* が開きます。

2. メニュー・アイコン ![メニュー・アイコン](../../icons/icon_hamburger.svg) に移動し、**「プログラム識別情報」**を選択します。 

3. **「Activity Tracker」**を選択します。 

    {{site.data.keyword.at_full_notm}} インスタンスのリストが表示されます。

    **注:** 地域ごとに 1 つのインスタンスがあります。

4. イベントを表示する地域のインスタンスを選択します。次に、**「LogDNA の表示 (View LogDNA)」**をクリックします。

{{site.data.keyword.at_full_notm}} Web UI が開き、**「すべて (Everything)」**ビューが表示されます。このビューを介して、選択した地域での自分のアカウントのイベントを表示できます。

**注:** 現在、`ライト`・プランをご利用で、探しているイベントが見つからない場合は、古いイベントに関する検索機能を有効にするために有料プランにアップグレードする必要があることがあります。検索可能なイベントの日数は、選択するプランによって異なります。[詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。


## デフォルト・ビューのカスタマイズ
{: #view_events_step2}

**「ユーザー設定」**セクションで、行単位で表示されるデータ・フィールドの順序を変更できます。

イベント行のフォーマットを変更するには、以下のステップを実行します。

1. Web UI で、**「構成」**アイコン ![構成アイコン](images/admin.png "管理アイコン") をクリックします。
2. **「ユーザー設定」**を選択します。 新しいウィンドウが開きます。
3. **「ログ・フォーマット (Log Format)」**を選択します。
4. *要件に合わせて「行フォーマット (Line Format)」*セクションを変更します。 ボックスをドラッグします。




## コンテキストでイベントを表示する
{: #view_events_step3}

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
{: #view_events_step4}


イベントをクリップボードにコピーするには、以下のステップを実行します。 

1. Web UI で、**「ビュー」**アイコン ![構成アイコン](images/views.png "構成アイコン") をクリックします。
2. **「すべて (Everything)」**または 1 つのカスタム・ビューを選択します。
3. 調べる行を特定します。
4. イベント行を展開します。 

    行 ID、タグ、およびラベルに関する情報が表示されます。

5. **「クリップボードにコピー」**をクリックすると、イベントがクリップボードにコピーされます。

イベントの探索が終了したら、**「閉じる」**をクリックしてイベント行を閉じます。




