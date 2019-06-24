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


# 雲端服務
{: #cloud_services}

您可以使用 {{site.data.keyword.at_full}} 服務來監視使用者起始的活動，這些活動會在 {{site.data.keyword.cloud_notm}} 中變更下列任何服務的狀態。
{:shortdesc}


## 平台核心整合式服務
{: #platform_core_integrated}


核心平台服務會產生可以透過**法蘭克福 (eu-de)** {{site.data.keyword.at_full_notm}} Web 使用者介面檢視的事件。若要檢視這些事件，您必須在**法蘭克福 (eu-de)** 地區中佈建 {{site.data.keyword.at_full_notm}} 服務的[實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。
{: note}

下表列出將事件傳送到 {{site.data.keyword.at_full_notm}} 的核心平台動作：

| 動作                             | 說明 | {{site.data.keyword.at_full_notm}} 事件 |
|----------------------------------|-------------|-------------------------------------------|
| [管理帳戶](/docs/account?topic=account-accounts#accounts)|您可以使用現有 IBM ID、建立新的 IBM ID 或使用聯合 ID 來註冊 {{site.data.keyword.IBM_notm}} 帳戶。| [管理帳戶時所產生的事件](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account)|
| [管理使用者](/docs/iam?topic=iam-iamuserinv#iamusermanage)|您可以透過您所擁有或管理的帳戶或組織來檢視及管理使用者。| [管理使用者時所產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [管理組織](/docs/account?topic=account-orgsspacesusers#orgsspacesusers)| 身為帳戶擁有者，您可以對該帳戶新增及管理組織。| [管理組織時所產生的事件](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org)|
|[佈建和管理已啟用型錄 {{site.data.keyword.iamshort}} (IAM) 的服務](/docs/overview?topic=overview-ui#catalogcreate)|您可以佈建服務實例、重新命名服務實例、變更服務實例的方案，以及移除服務實例。| [與型錄服務互動時所產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
|[使用服務別名](/docs/resources?topic=resources-connect_app#what_is_alias)|別名是資源群組內 IAM 管理的服務，與組織或空間內的應用程式，兩者之間的連線。|[管理與服務實例相關聯的別名的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias)| 
|[使用服務認證](/docs/resources?topic=resources-service_credentials#service_credentials)|服務認證提供將應用程式連接至服務實例的必要資訊。|[管理與服務實例相關聯的服務認證的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys)| 
|[將服務實例連結至應用程式](/docs/resources?topic=resources-s2s_binding#s2s_binding)|您可以在空間中產生具有相同名稱的服務實例的 Cloud Foundry (CF) 實例或別名。|[將服務實例連結至應用程式以及從應用程式取消連結服務實例的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind)|
|[管理標籤](/docs/resources?topic=resources-tag)|標籤是您指派給資源的標籤，可讓您輕鬆過濾資源清單中的資源。|[管理標籤的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources)|
{: caption="核心平台動作的清單" caption-side="top"} 






## 平台整合安全服務
{: #platform_integrated_security}

整合安全服務會產生可以透過**法蘭克福 (eu-de)** {{site.data.keyword.at_full_notm}} Web 使用者介面檢視的事件。若要檢視這些事件，您必須在**法蘭克福 (eu-de)** 地區中佈建 {{site.data.keyword.at_full_notm}} 服務的[實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)。
{: note}

下表列出將事件傳送到 {{site.data.keyword.at_full_notm}} 的核心安全平台動作：

| 動作                                                                 | 說明 | {{site.data.keyword.at_full_notm}} 事件 |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [管理存取群組](/docs/iam?topic=iam-groups#groups) | 您可以定義存取群組，以將一組使用者和服務 ID 組織成單一實體，讓您能夠輕鬆指派許可權。| [管理存取群組時所產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
|[管理原則](/docs/iam?topic=iam-userroles#userroles)|您可以使用 IAM，跨 {{site.data.keyword.cloud_notm}} 平台及基礎架構服務管理使用者和角色。| [管理 IAM 原則時所產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)|
| [登入 {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)|您可以使用密碼、API 金鑰、授權碼或通行碼來登入 {{site.data.keyword.cloud_notm}}。身為聯合使用者，您可以使用一次性密碼或 API 金鑰，從指令行介面 (CLI) 登入。|[使用者或應用程式登入 {{site.data.keyword.cloud_notm}} 時產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)|
| [管理平台 API 金鑰](/docs/iam?topic=iam-manapikey#platform-api-keys) |您可以在 {{site.data.keyword.IBM_notm}} Cloud 中定義與使用者或服務 ID 相關聯的平台 API 金鑰。| [管理平台 API 金鑰時所產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys)|
| [管理服務 ID](/docs/iam?topic=iam-serviceids#serviceids) |您可以在 {{site.data.keyword.IBM_notm}} Cloud 的帳戶層次上定義服務 ID。| [管理服務 ID 時所產生的事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids)|
{: caption="核心安全平台服務的清單" caption-side="top"} 



## 平台整合服務
{: #integration}

下表列出將事件傳送至 {{site.data.keyword.cloudaccesstrailshort}} 的整合服務：

| 服務     | 說明 | {{site.data.keyword.cloudaccesstrailshort}} 事件 |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)|{{site.data.keyword.messagehub}} 是以 Apache Kafka 建置的高傳輸量訊息匯流排。它經過最佳化，可將事件吸收至 {{site.data.keyword.IBM_notm}} 並在服務與應用程式之間進行事件串流配送。| [{{site.data.keyword.messagehub}} 所產生的事件](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="將事件傳送至 {{site.data.keyword.cloudaccesstrailshort}} 的整合雲端服務清單" caption-side="top"} 



## 平台網路服務
{: #network}

下表列出將事件傳送到 {{site.data.keyword.at_full_notm}} 的網路服務：

| 服務     | 說明 | {{site.data.keyword.at_full_notm}} 事件 |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)|IBM Cloud Internet Services (CIS) 可提供快速、高效能、可靠且安全的網際網路服務。| [IBM Cloud Internet Services 所產生的事件](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="網路服務清單" caption-side="top"} 



## 平台安全服務
{: #security}

下表列出將事件傳送至 {{site.data.keyword.cloudaccesstrailshort}} 的安全雲端服務：


| 服務     | 說明 | {{site.data.keyword.at_full_notm}} 事件 |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) |您可以使用 {{site.data.keyword.cloudcerts_short}} 來管理 {{site.data.keyword.cloud_notm}} 型應用程式和服務的 SSL 憑證。| [{{site.data.keyword.cloudcerts_short}} 服務所產生的事件](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="將事件傳送至 {{site.data.keyword.cloudaccesstrailshort}} 的安全雲端服務清單" caption-side="top"} 


