---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# 管理権限をユーザーまたはサービス ID に付与する
{: #iam_manage_events}

{{site.data.keyword.iamlong}} (IAM) を使用すると、ユーザーを安全に認証し、{{site.data.keyword.cloud_notm}} ですべてのクラウド・リソースへのアクセスを一貫して制御することができます。 {{site.data.keyword.at_full_notm}} サービスを使用して作業するための管理権限をユーザーまたはサービス ID に付与するには、以下のステップを実行します。
{:shortdesc}

例えば、サービスの管理者として、サービスのインスタンスをプロビジョンおよび削除する、サービスで作業するための権限を他のユーザーに付与する、ログを {{site.data.keyword.cos_full_notm}} (COS) インスタンスにアーカイブするなどの作業を行えます。[詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam)。

## ステップ 1. アクセス・グループを作成する
{: #ime_step1}

アクセス・グループを作成するには、以下のステップを実行します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. **「作成」**をクリックします。
3. グループの名前と説明 (オプション) を入力して**「作成」**をクリックします。

**「グループの削除 (Remove group)」**オプションを選択してグループを削除することができます。 グループをアカウントから削除すると、すべてのユーザーとサービス ID がグループから削除され、グループに割り当てられたすべてのアクセス権限が削除されます。
{: note}

CLI を使用してアクセス・グループを作成するには、[ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) コマンドを使用します。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## ステップ 2. イベントを管理する権限を追加する
{: #ime_step2}

グループをセットアップした後で、共通するアクセス・ポリシーをそのグループに割り当てることができます。 

アクセス・グループに設定するポリシーは、そのグループ内のすべてのエンティティー、ユーザー、およびサービス ID に適用されます。
{: note}

UI を使用して、またはコマンド・ラインを使ってポリシーを割り当てることができます。

CLI を使用してアクセス・グループ・ポリシーを作成するには、[ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) コマンドを使用します。

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

UI を使ってアクセス・グループにポリシーを割り当てるには、以下のステップを実行します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. アクセス権限を割り当てる先のグループの名前を選択します。 
3. **「アクセス・ポリシー」**をクリックします。
4. **「アクセス権限の割り当て (Assign access)」**をクリックします。
5. リソース・グループ内のリソース別にアクセス権限を割り当てるのか、アカウント内で使用可能な個々のリソース別にアクセス権限を割り当てるのか、またはアカウント管理サービス別にアクセス権限を割り当てるのかを選択します。 例えば、以下のいずれかのオプションを選択して、{{site.data.keyword.at_full_notm}} インスタンスを管理する管理者役割をユーザーに付与できます。

### オプション 1.  {{site.data.keyword.cloud_notm}} アカウント内のサービスの管理者になるための許可をユーザーに付与する
{: #admin_account_opt1}

アカウント内のサービスを管理する管理者役割をユーザーに付与するには、ユーザーに、**管理者**のプラットフォーム役割とともに、{{site.data.keyword.at_full_notm}} サービスの IAM ポリシーが必要となります。 アカウント内の個別リソースへのアクセス権限をこのユーザーに割り当てる必要があります。 

アカウント内の {{site.data.keyword.at_full_notm}} サービスに対する管理者役割をユーザーに割り当てるには、以下のステップを実行します。 

1. **「リソースへのアクセス権限の割り当て」**を選択します。
2. **「IBM Cloud Activity Tracker with LogDNA」**を選択します。
3. **「すべての現行地域」**を選択します。
4. **「すべての現行サービス・インスタンス」**を選択します。
5. **「管理者」**プラットフォーム役割を選択します。
6. **「管理者」**サービス役割を選択します。
7. **「割り当て」**をクリックします。

### オプション 2. リソース・グループ内のサービスの管理者になるための許可をユーザーに付与する
{: #admin_account_opt2}

アカウントのリソース・グループ内のインスタンスを管理する管理者役割をユーザーに付与するには、ユーザーに、リソース・グループのコンテキスト内での**管理者**のプラットフォーム役割とともに、{{site.data.keyword.at_full_notm}} サービスの IAM ポリシーが必要となります。 

リソース・グループのコンテキスト内で {{site.data.keyword.at_full_notm}} サービスに対する管理者役割をユーザーに割り当てるには、以下のステップを実行します。 

1. **「リソース・グループ内のアクセス権限の割り当て」**を選択します。
2. リソース・グループを選択します。
3. 選択したリソース・グループに対する役割がまだユーザーに付与されていない場合は、**「リソース・グループへのアクセス権限の割り当て」**フィールドで役割を選択します。 

    選択する役割に応じて、ユーザーはダッシュボードでのリソース・グループの表示、リソース・グループ名の編集、またはグループへのユーザー・アクセスの管理を行うことができます。 
    
    リソース・グループ内の {{site.data.keyword.at_full_notm}} サービスへのアクセス権限のみをユーザーに付与する場合は、**「アクセス権限なし」**を選択します。

4. **「IBM Cloud Activity Tracker with LogDNA」**を選択します。
5. **「管理者」**プラットフォーム役割を選択します。
6. **「管理者」**サービス役割を選択します。
7. **「割り当て」**をクリックします。

### オプション 3.  {{site.data.keyword.cloud_notm}} 内のサービスの単一インスタンスの管理者になるための許可をユーザーに付与する
{: #admin_account_opt3}

{{site.data.keyword.at_full_notm}} サービスの 1 つのインスタンスに対する管理者役割をユーザーに割り当てるには、以下のステップを実行します。 

1. **「リソースへのアクセス権限の割り当て」**を選択します。
2. **「IBM Cloud Activity Tracker with LogDNA」**を選択します。
3. インスタンスを選択します。
4. **「管理者」**プラットフォーム役割を選択します。
5. **「管理者」**サービス役割を選択します。
6. **「割り当て」**をクリックします。



## ステップ 3. ユーザーまたはサービス ID をアクセス・グループに追加する
{: #ime_step3}

ユーザーまたはサービス ID を追加することで、グループのセットアップに進みます。

### アクセス・グループへのユーザーの追加
{: #ime_step3_user}

以下のステップを実行してユーザーを追加します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. アクセス権限を割り当てる先のグループの名前を選択します。 
3. **「ユーザー」**タブで**「ユーザーの追加」**をクリックします。
4. 追加するユーザーをリストから選択して、**「グループに追加 (Add to group)」**をクリックします。


### アクセス・グループへの サービス ID の追加
{: #ime_step3_svcid}

以下のステップを実行してサービス ID を追加します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. アクセス権限を割り当てる先のグループの名前を選択します。 
3. **「サービス ID」**タブをクリックして、**「サービス ID の追加」**をクリックします。
4. 追加する ID をリストから選択して、**「グループに追加 (Add to group)」**をクリックします。




