---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, services

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


# クラウド・サービス
{: #cloud_services}

{{site.data.keyword.at_full}} サービスを使用して、{{site.data.keyword.cloud_notm}} 内の以下のいずれかのサービスの状態を変更するユーザー開始アクティビティーをモニターします。
{:shortdesc}


## プラットフォーム・コア統合サービス
{: #platform_core_integrated}


コア・プラットフォーム・サービスは、**フランクフルト (eu-de)** {{site.data.keyword.at_full_notm}} Web UI で表示できるイベントを生成します。これらのイベントを表示するには、**フランクフルト (eu-de)** 地域に {{site.data.keyword.at_full_notm}} サービスの[インスタンスをプロビジョンする](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)必要があります。
{: note}

以下の表に、イベントを {{site.data.keyword.at_full_notm}} に送信するコア・プラットフォーム・アクションをリストします。

| アクション                           | 説明 | {{site.data.keyword.at_full_notm}} イベント |
|----------------------------------|-------------|-------------------------------------------|
| [アカウントの管理](/docs/account?topic=account-accounts#accounts) | {{site.data.keyword.IBM_notm}} アカウントの登録には、既存の IBMid を使用するか、新規 IBMid を作成するか、フェデレーテッド ID を使用することができます。 | [アカウントの管理時に生成されるイベント](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [ユーザーの管理](/docs/iam?topic=iam-iamuserinv#iamusermanage) | 所有または管理するアカウントまたは組織全体のユーザーを表示および管理することができます。  | [ユーザーの管理時に生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [組織の管理](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | アカウント所有者はアカウントへの組織の追加および管理を行うことができます。 | [組織の管理時に生成されるイベント](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [カタログ {{site.data.keyword.iamshort}} (IAM) 対応サービスのプロビジョンおよび管理](/docs/overview?topic=overview-ui#catalogcreate) | サービス・インスタンスのプロビジョン、サービス・インスタンスの名前変更、サービス・インスタンスのプラン変更、およびサービス・インスタンスの削除を行うことができます。 | [カタログ・サービスとの対話時に生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [サービス別名の処理](/docs/resources?topic=resources-connect_app#what_is_alias) |別名は、リソース・グループ内の IAM 管理サービスと、組織またはスペース内のアプリケーションとの間の接続です。| [サービス・インスタンスに関連付けられている別名の管理のイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [サービス資格情報の処理](/docs/resources?topic=resources-service_credentials#service_credentials) |サービス資格情報は、アプリケーションをサービス・インスタンスに接続するために必要な情報を提供します。| [サービス・インスタンスに関連付けられているサービス資格情報の管理のイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [アプリへのサービス・インスタンスのバインド](/docs/resources?topic=resources-s2s_binding#s2s_binding) | スペース内に同じ名前のサービス・インスタンスの Cloud Foundry (CF) インスタンスまたは別名を生成できます。| [アプリへのサービス・インスタンスのバインドおよびアンバインドのイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [タグの管理](/docs/resources?topic=resources-tag) | タグは、リソース・リスト内のリソースを簡単にフィルター操作できるようにするためにリソースに割り当てるラベルです。| [タグ管理のイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="コア・プラットフォーム・アクションのリスト" caption-side="top"} 






## プラットフォーム統合セキュリティー・サービス
{: #platform_integrated_security}

統合セキュリティー・サービスは、**フランクフルト (eu-de)** {{site.data.keyword.at_full_notm}} Web UI で表示できるイベントを生成します。これらのイベントを表示するには、**フランクフルト (eu-de)** 地域に {{site.data.keyword.at_full_notm}} サービスの[インスタンスをプロビジョンする](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)必要があります。
{: note}

以下の表に、イベントを {{site.data.keyword.at_full_notm}} に送信するコア・セキュリティー・プラットフォーム・アクションをリストします。

| アクション                                                     | 説明 | {{site.data.keyword.at_full_notm}} イベント |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [アクセス・グループの管理](/docs/iam?topic=iam-groups#groups) | 許可の割り当てを簡単に行うことができるように、アクセス・グループを定義して、ユーザーとサービス ID のセットを単一のエンティティーに編成することができます。 | [アクセス・グループの管理時に生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [ポリシーの管理](/docs/iam?topic=iam-userroles#userroles) | IAM を使用して、{{site.data.keyword.cloud_notm}} プラットフォームおよびインフラストラクチャーのサービス全体でユーザーおよび役割を管理することができます。 | [IAM ポリシーの管理時に生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [{{site.data.keyword.cloud_notm}} へのログイン](/docs/iam?topic=iam-iamoverview#iamoverview)| パスワード、API キー、許可コード、またはパスコードを使用して、{{site.data.keyword.cloud_notm}} にログインできます。 フェデレーテッド・ユーザーとして、ワンタイム・パスコードまたは API キーを使用してコマンド・ライン・インターフェース (CLI) からログインできます。 | [ユーザーまたはアプリが {{site.data.keyword.cloud_notm}} にログインしたときに生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) |
| [プラットフォーム API キーの管理](/docs/iam?topic=iam-manapikey#platform-api-keys) | {{site.data.keyword.IBM_notm}} Cloud 内で、ユーザーまたはサービス ID に関連付けられたプラットフォーム API キーを定義できます。 | [プラットフォーム API キーの管理時に生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [サービス ID の管理](/docs/iam?topic=iam-serviceids#serviceids) | {{site.data.keyword.IBM_notm}} Cloud 内で、アカウント・レベルでサービス ID を定義できます。 | [サービス ID の管理時に生成されるイベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="コア・セキュリティー・プラットフォーム・サービスのリスト" caption-side="top"} 



## プラットフォーム統合サービス
{: #integration}

以下の表に、イベントを {{site.data.keyword.cloudaccesstrailshort}} に送信する統合サービスをリストします。

| サービス     | 説明 | {{site.data.keyword.cloudaccesstrailshort}} イベント |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| {{site.data.keyword.messagehub}} は、Apache Kafka で構築されている高スループットのメッセージ・バスです。 これは、{{site.data.keyword.IBM_notm}} へのイベントの取り込みのため、および、お客様のサービスおよびアプリケーション間でイベント・ストリームを分散させるために最適化されています。 | [{{site.data.keyword.messagehub}} によって生成されるイベント](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="イベントを {{site.data.keyword.cloudaccesstrailshort}} に送信する統合クラウド・サービスのリスト" caption-side="top"} 



## プラットフォーム・ネットワーク・サービス
{: #network}

以下の表に、イベントを {{site.data.keyword.at_full_notm}} に送信するネットワーク・サービスをリストします。

| サービス     | 説明 | {{site.data.keyword.at_full_notm}} イベント |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| IBM Cloud Internet Services (CIS) は、高速、高パフォーマンスの、信頼できる安全なインターネット・サービスを提供します。 | [IBM Cloud Internet Services によって生成されるイベント](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="ネットワーク・サービスのリスト" caption-side="top"} 



## プラットフォーム・セキュリティー・サービス
{: #security}

以下の表に、イベントを {{site.data.keyword.cloudaccesstrailshort}} に送信するセキュリティー・クラウド・サービスをリストします。


| サービス     | 説明 | {{site.data.keyword.at_full_notm}} イベント          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | {{site.data.keyword.cloudcerts_short}} を使用して、{{site.data.keyword.cloud_notm}} ベースのアプリおよびサービス用に SSL 証明書を管理できます。  | [{{site.data.keyword.cloudcerts_short}} サービスによって生成されるイベント](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="イベントを {{site.data.keyword.cloudaccesstrailshort}} に送信するセキュリティー・クラウド・サービスのリスト" caption-side="top"} 


