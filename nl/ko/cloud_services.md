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


# 클라우드 서비스
{: #cloud_services}

{{site.data.keyword.at_full}} 서비스를 사용하여 {{site.data.keyword.cloud_notm}} 내 다음 서비스의 상태를 변경하는 사용자 시작 활동을 모니터하십시오.
{:shortdesc}


## 플랫폼 코어 통합 서비스
{: #platform_core_integrated}


코어 플랫폼 서비스에서는 **프랑크푸르트(eu-de)** {{site.data.keyword.at_full_notm}} 웹 UI를 통해 볼 수 있는 이벤트를 생성합니다. 해당 이벤트를 보려면 **프랑크푸르트(eu-de)** 지역에 {{site.data.keyword.at_full_notm}} 서비스의 [인스턴스를 프로비저닝](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)해야 합니다.
{: note}

다음 표에는 {{site.data.keyword.at_full_notm}}에 이벤트를 전송하는 코어 플랫폼 조치가 나열되어 있습니다.

|조치                           |설명 |{{site.data.keyword.at_full_notm}} 이벤트 |
|----------------------------------|-------------|-------------------------------------------|
| [계정 관리](/docs/account?topic=account-accounts#accounts) | 기존 IBM ID를 사용하거나 새 IBM ID를 작성하거나 연합 ID를 사용하여 {{site.data.keyword.IBM_notm}} 계정에 가입할 수 있습니다. |[계정을 관리할 때 생성되는 이벤트](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [사용자 관리](/docs/iam?topic=iam-iamuserinv#iamusermanage) | 사용자가 소유하거나 관리하는 계정 또는 조직 전체에서 사용자를 보고 관리할 수 있습니다. |[사용자를 관리할 때 생성되는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [조직 관리](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | 계정 소유자는 계정에 조직을 추가하고 관리할 수 있습니다. |[조직을 관리할 때 생성되는 이벤트](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [카탈로그 {{site.data.keyword.iamshort}}(IAM) 사용 서비스 프로비저닝 및 관리](/docs/overview?topic=overview-ui#catalogcreate) | 서비스 인스턴스를 프로비저닝하고 서비스 인스턴스의 이름을 바꾸며, 서비스 인스턴스의 플랜을 변경하고, 서비스 인스턴스를 제거할 수 있습니다. | [카탈로그 서비스와 상호작용할 때 생성되는 이벤트 ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [서비스 별명에 대한 작업](/docs/resources?topic=resources-connect_app#what_is_alias) |별명을 통해 리소스 그룹의 IAM 관리 서비스와 조직 또는 공간의 애플리케이션을 연결합니다.| [서비스 인스턴스와 연관된 별명을 관리하는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [서비스 인증 정보에 대한 작업](/docs/resources?topic=resources-service_credentials#service_credentials) |서비스 인증 정보에서는 애플리케이션을 서비스 인스턴스에 연결하는 데 필요한 정보를 제공합니다.| [서비스 인스턴스와 연관된 서비스 인증 정보를 관리하는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [서비스 인스턴스를 앱에 바인딩](/docs/resources?topic=resources-s2s_binding#s2s_binding) | 영역에서 이름이 같은 서비스 인스턴스의 CF(Cloud Foundry) 인스턴스 또는 별칭을 생성할 수 있습니다.  | [서비스 인스턴스를 앱에 바인딩하고 바인딩 해제하는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [태그 관리](/docs/resources?topic=resources-tag) | 태그는 리소스 목록에서 리소스를 쉽게 필터링하기 위해 리소스에 지정하는 레이블입니다.  | [태그 관리 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="코어 플랫폼 조치 목록" caption-side="top"} 






## 플랫폼 내장 보안 서비스
{: #platform_integrated_security}

통합 보안 서비스에서는 **프랑크푸르트(eu-de)** {{site.data.keyword.at_full_notm}} 웹 UI를 통해 볼 수 있는 이벤트를 생성합니다. 해당 이벤트를 보려면 **프랑크푸르트(eu-de)** 지역에 {{site.data.keyword.at_full_notm}} 서비스의 [인스턴스를 프로비저닝](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)해야 합니다.
{: note}

다음 표에는 {{site.data.keyword.at_full_notm}}에 이벤트를 전송하는 코어 보안 플랫폼 조치가 나열되어 있습니다.

|조치                                                     |설명 |{{site.data.keyword.at_full_notm}} 이벤트 |
|-------------------------------------------------------------|-------------|-------------------------------------------|
|[액세스 그룹 관리](/docs/iam?topic=iam-groups#groups) |사용자 및 서비스 ID 세트를 단일 엔티티로 구성하여 권한을 쉽게 지정할 수 있도록 액세스 그룹을 정의할 수 있습니다. |[액세스 그룹을 관리할 때 생성되는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [정책 관리](/docs/iam?topic=iam-userroles#userroles) | IAM을 사용하여 {{site.data.keyword.cloud_notm}} 플랫폼과 인프라 서비스 전체에서 사용자와 역할을 관리할 수 있습니다. | [IAM 정책을 관리할 때 생성되는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [{{site.data.keyword.cloud_notm}}에 로그인](/docs/iam?topic=iam-iamoverview#iamoverview)| 비밀번호, API 키, 권한 코드 또는 패스코드를 사용하여 {{site.data.keyword.cloud_notm}}에 로그인할 수 있습니다. 연합 사용자는 일회성 패스코드 또는 API 키를 사용하여 명령행 인터페이스(CLI)에서 로그인할 수 있습니다. | [사용자나 앱에서 {{site.data.keyword.cloud_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)에 로그인할 때 생성되는 이벤트 |
| [플랫폼 API 키 관리](/docs/iam?topic=iam-manapikey#platform-api-keys) | 사용자 또는 서비스 ID와 연관된 {{site.data.keyword.IBM_notm}} Cloud에서 플랫폼 API 키를 정의할 수 있습니다. | [플랫폼 API 키를 관리할 때 생성되는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [서비스 ID 관리](/docs/iam?topic=iam-serviceids#serviceids) | {{site.data.keyword.IBM_notm}} Cloud의 계쩡 레벨에서 서비스 ID를 정의할 수 있습니다. | [서비스 ID를 관리할 때 생성되는 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="핵심 보안 플랫폼 서비스 목록" caption-side="top"} 



## 플랫폼 통합 서비스
{: #integration}

다음 표에는 {{site.data.keyword.cloudaccesstrailshort}}에 이벤트를 보내는 통합 서비스가 나열되어 있습니다.

|서비스     |설명 |{{site.data.keyword.cloudaccesstrailshort}} 이벤트 |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| {{site.data.keyword.messagehub}}는 Apache Kafka로 빌드된 고처리량 메시지 허브입니다. 서비스와 애플리케이션 사이의 이벤트 스트림 배포 및 {{site.data.keyword.IBM_notm}}에 이벤트 수집용으로 최적화되어 있습니다. | [{{site.data.keyword.messagehub}}에서 생성하는 이벤트 ](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="{{site.data.keyword.cloudaccesstrailshort}}에 이벤트를 보내는 통합 클라우드 서비스 목록" caption-side="top"} 



## 플랫폼 네트워크 서비스
{: #network}

다음 표에는 {{site.data.keyword.at_full_notm}}에 이벤트를 보내는 네트워크 서비스가 나열되어 있습니다.

|서비스     |설명 |{{site.data.keyword.at_full_notm}} 이벤트 |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services(CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| IBM Cloud Internet Services(CIS)에서는 빠르고 신뢰할 수 있는 고성능의 보안 서비스를 제공합니다. | [IBM Cloud Internet Services에서 생성하는 이벤트](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="네트워크 서비스 목록" caption-side="top"} 



## 플랫폼 보안 서비스
{: #security}

다음 표에는 {{site.data.keyword.cloudaccesstrailshort}}에 이벤트를 전송하는 보안 클라우드 서비스가 나열되어 있습니다.


|서비스     |설명 |{{site.data.keyword.at_full_notm}} 이벤트          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | {{site.data.keyword.cloudcerts_short}}를 사용하여 {{site.data.keyword.cloud_notm}} 기반 앱과 서비스의 SSL 인증서를 관리할 수 있습니다. | [{{site.data.keyword.cloudcerts_short}} 서비스에서 생성하는 이벤트](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="{{site.data.keyword.cloudaccesstrailshort}}에 이벤트를 보내는 보안 클라우드 서비스 목록" caption-side="top"} 


