---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# アラートの構成
{: #alerts}

{{site.data.keyword.at_full_notm}} の Web UI で、検索照会を適用することで、カスタム・ビューで表示されるイベントを定義できます。その後、条件が発生したときに通知するアラートをそのビューにアタッチできます。1 つのビューに 1 つ以上のアラートをアタッチできます。 1 つのアラートについて複数の通知チャネルを定義できます。 アラートをミュートすることができます。 アラートをビューからデタッチできます。
{:shortdesc}


## 前提条件
{: #alerts_prereqs}

* [アラートについての詳細を確認します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts)。

* {{site.data.keyword.at_full_notm}} サービスの**有料サービス・プランのご利用**が必要です。 [詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。

* 自分のユーザー ID に Web UI を起動してイベントを表示するための権限があるか確認します。以下の表は、ユーザーが {{site.data.keyword.at_full_notm}} の Web UI を起動してイベントを表示、検索、フィルタリングするために最低限必要な役割を示しています。

| 役割                      | 付与される許可            |
|---------------------------|-------------------------------|  
| プラットフォーム役割: `ビューアー`     | ユーザーが「プログラム識別情報」ダッシュボードでサービス・インスタンスのリストを表示できるようにします。 |
| サービス役割: `リーダー`      | ユーザーが Web UI を起動して Web UI にイベントを表示できるようにします。  |
{: caption="表 1. IAM 役割" caption-side="top"} 

ユーザーに対してポリシーを構成する方法について詳しくは、[ユーザー許可をユーザーまたはサービス ID に付与する](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)を参照してください。

 


## ステップ 1. Web UI へ移動する
{: #alerts_step1}

[Web UI に移動します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## ステップ 2. ビューを作成する
{: #alerts_step2}

[ビューを作成します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。



## ステップ 3. [オプション] 事前設定 (アラート・テンプレート) の構成
{: #alerts_step3}

さまざまなビューと共にアラート構成を再利用するには、**アラートの事前設定**を構成します。
{: note}

事前設定を構成するには、以下のステップを実行します。

1. Web UI で、**「構成」**アイコン ![構成アイコン](images/admin.png "管理アイコン") を選択します。
2. **「アラート (Alerts)」**を選択します。
3. **「事前設定アラートの追加 (Add a preset alert)」**を選択します。
4. 通知チャネルを選択します。サポートされているチャネルのリストについては、[アラート通知チャネル](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)を参照してください。
5. アラートのタイプを選択します。ビューに表示されるイベントの数が予想より多い場合に通知するには、**「存在アラート (Presence alert)」**タイプを選択します。ビューに表示されるイベントの数が予想より少ない場合や存在しない場合に通知するには、**「不在アラート (Absence alert)」**タイプを選択します。 
5. 通知チャネルを選択します。サポートされているチャネルのリストについては、[アラート通知チャネル](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)を参照してください。
6. しきい値条件を定義します。

    1. 時間頻度を選択します。 例えば、12 時間を選択します。

    2. アラートのトリガーまでに要するイベント行の数を入力します。

    3. 両方の条件とも検査するか、一方だけにするかを選択します。

7. 選択した通知チャネルに関する詳細情報を追加します。

    例えば、E メール通知チャネルの場合、1 つ以上の宛先と、オプションでタイム・ゾーンを追加します。

8. **「アラートの保存 (Save alert)」**をクリックします。



## ステップ 4. アラートの構成
{: #alerts_step4}

以下のいずれかのオプションを使用して、ビューにアラートをアタッチします。

### オプション 1. 事前設定を使用したアラートの構成
{: #alerts_step4_preset}

ビューに事前設定をアタッチするには、以下のステップを実行します。

1. Web UI で、**「ビュー」**アイコン ![構成アイコン](images/views.png) をクリックします。
2. アラートをアタッチするビュー名をクリックします。 次に、**「アラートのアタッチ (Attach an alert)」**を選択します。
3. 事前設定を選択してアラート定義を再利用します。 
4. **「アラートの保存 (Save alert)」**をクリックします。 




### オプション 2. ビュー固有アラートの構成
{: #alerts_step4_view}

ビューにアラートをアタッチするには、以下のステップを実行します。

1. Web UI で、**「ビュー」**アイコン ![構成アイコン](images/views.png) をクリックします。
2. ビュー名をクリックします。 次に、**「アラートのアタッチ (Attach an alert)」**を選択します。
3. **「ビューに固有のアラート (view-specific alert)」**をクリックします。
4. 通知チャネルを選択します。 
5. アラートのタイプを選択します。ビューに表示されるイベントの数が予想より多い場合に通知するには、**「存在アラート (Presence alert)」**タイプを選択します。ビューに表示されるイベントの数が予想より少ない場合や存在しない場合に通知するには、**「不在アラート (Absence alert)」**タイプを選択します。 
6. しきい値条件を定義します。

    1. 時間頻度を選択します。 例えば、12 時間を選択します。

    2. アラートのトリガーまでに要するイベント行の数を入力します。

    3. 両方の条件とも検査するか、一方だけにするかを選択します。

7. 選択した通知チャネルに関する詳細情報を追加します。

    例えば、E メール通知チャネルの場合、1 つ以上の宛先と、オプションでタイム・ゾーンを追加します。

8. **「アラートの保存 (Save alert)」**をクリックします。



## 事前設定 (アラート・テンプレート) の削除
{: #alerts_delete_preset}

事前設定を削除するには、以下のステップを実行します。

1. Web UI で、**「構成」**アイコン ![構成アイコン](images/admin.png "管理アイコン") を選択します。
2. **「アラート (Alerts)」**を選択します。
3. 削除しようとしている事前設定の*「編集」*ボタンの上にマウスを移動します。 *「削除」*オプションが表示されます。
4. **「削除」**を選択します。
5. 事前設定を削除することを確認します。 **「削除」**をクリックします。

## ビューからのビュー固有アラートのデタッチ
{: #alerts_delete_view}

事前設定をデタッチするには、以下のステップを実行します。

1. Web UI で、**「構成」**アイコン ![構成アイコン](images/admin.png "管理アイコン") を選択します。
2. **「アラート (Alerts)」**を選択します。
3. 削除しようとしているアラートの*「編集」*ボタンの上にマウスを移動します。 *「削除」*オプションが表示されます。
4. **「デタッチ」**を選択します。
5. アラートを削除することを確認します。 **「デタッチ」**をクリックします。












