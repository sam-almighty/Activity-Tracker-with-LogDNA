---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# 서비스 인스턴스 이벤트  
{: #at_events_rc}

보안 담당자, 감사자 또는 관리자는 {{site.data.keyword.at_full_notm}} 서비스를 사용하여 사용자와 애플리케이션이 {{site.data.keyword.cloud_notm}} 서비스와 상호작용하는 방식을 추적할 수 있습니다.
{:shortdesc}

{{site.data.keyword.at_full_notm}} 서비스는 {{site.data.keyword.cloud_notm}} 내 서비스의 상태를 변경하는 사용자 시작 활동을 기록합니다. 사용자 조치의 모니터링을 시작하려면 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)의 내용을 참조하십시오. 


## 서비스 인스턴스 프로비저닝 및 관리 이벤트
{: #rc_provision}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                         |설명 |
|--------------------------------|---------|
| `service_name.instance.create` | 서비스 인스턴스를 프로비저닝할 때 이벤트가 생성됩니다. |
| `service_name.instance.update` | 서비스 인스턴스의 이름을 바꾸거나 서비스 플랜을 변경할 때 이벤트가 생성됩니다. |
| `service_name.instance.delete` | 서비스 인스턴스를 삭제할 때 이벤트가 생성됩니다. |
{: caption="표 1. 이벤트를 생성하는 조치" caption-side="top"} 


##  서비스 인스턴스와 연관된 별명을 관리하는 이벤트
{: #rc_alias}

별명을 통해 리소스 그룹의 IAM 관리 서비스와 조직 또는 공간의 애플리케이션을 연결합니다.

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                         |설명 |
|--------------------------------|---------|
| `service_name.alias.create` | 인스턴스의 별명을 작성할 때 이벤트가 생성됩니다. |
| `service_name.alias.update` | 인스턴스의 별명을 업데이트할 때 이벤트가 생성됩니다. |
| `service_name.alias.delete` | 인스턴스의 별명을 삭제할 때 이벤트가 생성됩니다. |
{: caption="표 2. 이벤트를 생성하는 조치" caption-side="top"} 


##  서비스 인스턴스와 연관된 서비스 인증 정보를 관리하는 이벤트
{: #rc_keys}

서비스 인증 정보에서는 애플리케이션을 서비스 인스턴스에 연결하는 데 필요한 정보를 제공합니다. 

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                         |설명 |
|--------------------------------|---------|
| `service_name.key.create` | 서비스 인스턴스 UI의 *서비스 인증 정보* 섹션을 통해 서비스 인스턴스의 API 키를 작성할 때 이벤트가 생성됩니다. |
| `service_name.key.delete` | 서비스 인스턴스와 연관된 API 키를 서비스 인스턴스 UI의 *서비스 인증 정보* 섹션에서 삭제하면 이벤트가 생성됩니다. |
{: caption="표 3. 이벤트를 생성하는 조치" caption-side="top"} 



##  서비스 인스턴스를 앱에 바인드하고 바인드 해제하는 이벤트
{: #rc_bind}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                         |설명 |
|--------------------------------|---------|
| `service_name.binding.create` | 서비스 인스턴스를 애플리케이션에 바인드할 때 이벤트가 생성됩니다. |
| `service_name.binding.delete` | 서비스 인스턴스를 애플리케이션에서 바인드 해제할 때 이벤트가 생성됩니다. |
{: caption="표 4. 이벤트를 생성하는 조치" caption-side="top"} 



## 이벤트 검색 위치
{: #rc_ui}

이벤트는 **프랑크푸르트(eu-de)** 지역에서 사용할 수 있습니다. 

해당 이벤트를 보려면 **프랑크푸르트(eu-de)** 지역에 {{site.data.keyword.at_full_notm}} 서비스의 [인스턴스를 프로비저닝](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)해야 합니다.
그런 다음 [{{site.data.keyword.at_full_notm}} UI를 열어야 합니다](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 



## 이벤트 분석
{: #rc_analyze}

**조치: service_name.instance.delete**

서비스 인스턴스를 삭제할 때 다음 정보를 고려하십시오.
* IAM 권한을 정리하기 위해 기타 조치가 자동으로 트리거됩니다. 이 조치를 수행하면 서비스 인스턴스에 대해 작업하기 위해 계정의 사용자와 서비스 ID에 맞게 구성된 정책을 제거합니다. 
* 이 조치의 개시자는 {{site.data.keyword.IBM_notm}} 서비스 ID입니다.


삭제한 서비스 인스턴스에 사용자와 서비스 ID의 IAM 정책이 구성되지 않은 경우 해당 리소스용으로 자동으로 생성된 이벤트에서 `404` 결과 코드와 함께 `failure` 결과를 보고합니다. 다음 샘플에서는 계정에 정책이 구성되지 않은 서비스 인스턴스를 삭제할 때 생성되는 이벤트를 보여줍니다.

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



