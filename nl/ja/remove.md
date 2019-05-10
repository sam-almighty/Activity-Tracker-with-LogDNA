---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# インスタンスの削除
{: #remove}

{{site.data.keyword.at_full_notm}} サービスのインスタンスは、{{site.data.keyword.cloud_notm}} UI またはコマンド・ラインを使用して削除できます。
{:shortdesc}



## {{site.data.keyword.cloud_notm}} UI によるインスタンスの削除
{: #remove_ui}

{{site.data.keyword.cloud_notm}} UI を使用して {{site.data.keyword.at_full_notm}} のインスタンスを削除するには、以下の手順を実行します。

1. [{{site.data.keyword.cloud_notm}} アカウントにログイン ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/login){:new_window} します。

	ユーザー ID とパスワードを使用してログインすると、{{site.data.keyword.cloud_notm}} UI が開きます。

2. メニュー・アイコン ![メニュー・アイコン](../../icons/icon_hamburger.svg) &gt; **「プログラム識別情報」**に移動して、「*プログラム識別情報*」ダッシュボードにアクセスします。

3. **「Activity Tracker」**を選択します。 インスタンスのリストが表示されます。

4. 削除するインスタンスを選択します。

5. *「アクション」*メニューから、**「削除」**を選択します。

次に、削除したインスタンスを処理するためにユーザーに付与されている許可を削除します。

## CLI を使用したインスタンスの削除
{: #remove_cli}

コマンド・ラインを使用して {{site.data.keyword.at_full_notm}} のインスタンスを削除するには、以下のステップを実行します。

1. [前提条件] {{site.data.keyword.cloud_notm}} CLI をインストールします。

   詳しくは、[『{{site.data.keyword.cloud_notm}}CLI のインストール』](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)を参照してください。

   CLI がインストールされている場合は、次のステップに進みます。

2. インスタンスをプロビジョンしたい、{{site.data.keyword.cloud_notm}} の地域にログインします。 次のコマンドを実行します。 [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. インスタンスがプロビジョンされるリソース・グループを設定します。 次のコマンドを実行します。 [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    デフォルトでは、*default* リソース・グループが設定されます。

4. インスタンスを削除します。 次の [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) コマンドを実行します。

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    ここで、NAME は、インスタンスの名前です

    ログインしているリソース・グループで使用可能なすべてのインスタンスをリストするには、次のコマンドを実行します。

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
例えば、インスタンスを削除するために、以下のコマンドを実行します。

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

次に、削除したインスタンスを処理するためにユーザーに付与されている許可を削除します。


