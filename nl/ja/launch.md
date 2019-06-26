---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# Web UI へのナビゲート
{: #launch}

{{site.data.keyword.cloud_notm}} に {{site.data.keyword.at_full_notm}} サービスのインスタンスをプロビジョンすると、{{site.data.keyword.at_full_notm}} Web UI を介してイベントを表示、モニター、および管理できます。
{:shortdesc}


## ステップ 1. データを表示するための IAM ポリシーをユーザーに付与する 
{: #step1}

**注:** 他のユーザーにポリシーを付与するには、{{site.data.keyword.at_full_notm}} サービスの管理者または {{site.data.keyword.at_full_notm}} インスタンスの管理者であるか、アカウント IAM 許可を所持している必要があります。

以下の表は、{{site.data.keyword.at_full_notm}} Web UI を介して Web UI を起動し、データを表示できるようにするために最低限必要なポリシーをリストしたものです。

| 役割                      | 付与される許可       |
|---------------------------|---------------------|
| プラットフォーム役割: `ビューアー`   | ユーザーが「プログラム識別情報」ダッシュボードでサービス・インスタンスのリストを表示できるようにします。 |
| サービス役割: `リーダー`    | ユーザーが Web UI を介してイベントを表示できるようにします。 | 
{: caption="表 1. IAM ポリシー" caption-side="top"} 

詳しくは、[ユーザー許可をユーザーまたはサービス ID に付与する](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)を参照してください。


## ステップ 2. {{site.data.keyword.cloud_notm}} UI を介して Web UI を起動する
{: #launch_step2}

{{site.data.keyword.cloud_notm}} UI から {{site.data.keyword.at_full_notm}} インスタンスのコンテキスト内で Web UI を起動します。 

Web UI を起動するには、以下の手順を実行します。

1. [{{site.data.keyword.cloud_notm}} アカウントにログイン ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/login){:new_window} します。

	ユーザー ID とパスワードを使用してログインすると、{{site.data.keyword.cloud_notm}} ダッシュボードが開きます。

2. **「メニュー」**アイコン ![メニュー・アイコン](../icons/icon_hamburger.svg) >**「プログラム識別情報」**をクリックします。 

3. **「Activity Tracker」**を選択します。 

    {{site.data.keyword.at_full_notm}} インスタンスのリストが表示されます。

    地域ごとに 1 つのインスタンスがあります。
    {: important}

4. イベントを表示する地域のインスタンスを選択します。 次に、**「LogDNA の表示 (View LogDNA)」**をクリックします。

{{site.data.keyword.at_full_notm}} Web UI が開き、**「すべて (Everything)」**ビューが表示されます。 このビューを介して、選択した地域での自分のアカウントのイベントを表示できます。



## {{site.data.keyword.cloud_notm}} からの Web UI URL の取得
{: #launch_get}

Web UI URL を取得するには、端末から以下の手順を実行します。

1. {{site.data.keyword.at_full_notm}} インスタンスがプロビジョンされるリソース・グループを設定します。

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. {{site.data.keyword.at_full_notm}} インスタンス名を設定します。

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. エンドポイントを設定します。

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. IAM トークンを設定します。

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **注:** MacOS 端末で作業している場合、コマンドは次のようになります。 `export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. リソース・グループ ID を設定します。

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. 変数に Web UI URL を設定します。

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. Web UI URL を取得します。

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

