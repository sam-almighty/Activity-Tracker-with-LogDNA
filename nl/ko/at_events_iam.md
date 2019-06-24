---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# IAM 이벤트
{: #at_events_iam}

보안 담당자, 감사자 또는 관리자는 {{site.data.keyword.at_full_notm}} 서비스를 사용하여 사용자 및 애플리케이션이 {{site.data.keyword.cloud_notm}}의 {{site.data.keyword.iamlong}}(IAM) 서비스와 상호작용하는 방식을 추적할 수 있습니다. 
{:shortdesc}

IAM을 사용하면 두 플랫폼 서비스 모두에 대해 사용자를 안전하게 인증하고 {{site.data.keyword.cloud_notm}} 전체에서 리소스에 대한 액세스를 일관되게 제어할 수 있습니다. [자세히 보기](/docs/iam?topic=iam-iamoverview).


{{site.data.keyword.at_full_notm}} 서비스는 {{site.data.keyword.cloud_notm}} 내 서비스의 상태를 변경하는 사용자 시작 활동을 기록합니다. 사용자 조치의 모니터링을 시작하려면 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)의 내용을 참조하십시오. 개시자는 사용자, 서비스 또는 애플리케이션일 수 있습니다.


## 액세스 그룹 이벤트
{: #at_events_iam_access}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                      |설명 |
|-----------------------------|---------|
|`iam-groups.group.create`   |개시자가 액세스 그룹을 작성할 때 이벤트가 생성됩니다. | 
|`iam-groups.group.read`     |개시자가 액세스 그룹과 관련된 정보를 볼 때 이벤트가 생성됩니다. |
|`iam-groups.group.update`   |개시자가 그룹 이름 또는 설명을 업데이트할 때 이벤트가 생성됩니다. |
|`iam-groups.group.delete`   |개시자가 액세스 그룹을 삭제할 때 이벤트가 생성됩니다. |
|`iam-groups.member.add`     |개시자가 액세스 그룹에 구성원을 추가할 때 이벤트가 생성됩니다. |
|`iam-groups.member.delete`  |개시자가 액세스 그룹에서 구성원을 제거할 때 이벤트가 생성됩니다. |
|`iam-groups.member.read`    |개시자가 구성원의 멤버십을 확인할 때 이벤트가 생성됩니다. |
|`iam-groups.rule.read`      |개시자가 액세스 그룹의 규칙을 볼 때 이벤트가 생성됩니다. |
|`iam-groups.rule.create`    |개시자가 액세스 그룹에 규칙을 추가할 때 이벤트가 생성됩니다. |
|`iam-groups.rule.update`    |개시자가 규칙 이름을 수정할 때 이벤트가 생성됩니다. |
|`iam-groups.rule.delete`    |개시자가 액세스 그룹에서 규칙을 제거할 때 이벤트가 생성됩니다. |
{: caption="표 1. 액세스 그룹 조치 관리" caption-side="top"} 



## 정책 이벤트
{: #at_events_iam_policies}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                 |설명 |
|------------------------|---------|
| `iam-am.policy.create` | 개시자가 사용자나 액세스 그룹에 정책을 추가할 때 이벤트가 생성됩니다. |
| `iam-am.policy.delete` | 개시자가 사용자나 액세스 그룹의 정책에 대한 권한을 수정할 때 이벤트가 생성됩니다. |
| `iam-am.policy.update` | 개시자가 사용자나 액세스 그룹에 지정된 정책을 삭제할 때 이벤트가 생성됩니다. |
{: caption="표 5. 정책 조치 관리" caption-side="top"} 



## 서비스 ID 이벤트
{: #at_events_iam_serviceids}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치 |설명 |
|----------|---------|
| `iam-identity.account-serviceid.create` | 개시자가 서비스 ID를 작성할 때 이벤트가 생성됩니다. | 
| `iam-identity.account-serviceid.update` | 개시자가 서비스 ID의 이름을 바꾸거나 해당 설명을 수정할 때 이벤트가 생성됩니다. | 
| `iam-identity.account-serviceid.delete` | 개시자가 서비스 ID를 삭제할 때 이벤트가 생성됩니다. | 
{: caption="표 2. 서비스 ID 조치에 대한 작업" caption-side="top"} 


## API 키 이벤트
{: #at_events_iam_apikeys}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치 |설명 |
|----------|---------|
| `iam-identity.user-apikey.create`      | 개시자가 API 키를 작성할 때 이벤트가 생성됩니다. | 
| `iam-identity.user-apikey.update`      | 개시자가 API 키의 이름을 바꾸거나 해당 설명을 수정할 때 이벤트가 생성됩니다. |  
| `iam-identity.user-apikey.delete`      | 개시자가 API 키를 삭제할 때 이벤트가 생성됩니다. |  
| `iam-identity.serviceid-apikey.create` | 개시자가 서비스 ID의 API 키를 작성할 때 이벤트가 생성됩니다. |  
| `iam-identity.serviceid-apikey.delete` | 개시자가 서비스 ID의 API 키를 삭제할 때 이벤트가 생성됩니다. |  
{: caption="표 3. API 키 조치 작업" caption-side="top"} 


## 로그인 이벤트
{: #at_events_iam_login}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                                   |설명 |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | 사용자가 API 키를 사용하여 {{site.data.keyword.cloud_notm}}에 로그인할 때 이벤트가 생성됩니다. |  
| `iam-identity.serviceid-apikey.login`    | 개시자가 서비스 ID와 연관된 API 키를 사용하여 {{site.data.keyword.cloud_notm}}에 로그인할 때 이벤트가 생성됩니다. |  
| `iam-identity.user-identitycookie.login` | 개시자가 조치를 실행하기 위해 ID 쿠키를 요청할 때 생성되는 이벤트입니다. |
| `iam-identity.user-refreshtoken.login`   | 개시자가 IBM Cloud에 로그인하거나 이미 IBM Cloud에 로그인한 개시자가 조치를 실행하기 위해 새로 고치기 토큰을 새로 요청할 때 생성되는 이벤트입니다. |
{: caption="표 4. 사용자 로그인 조치" caption-side="top"} 


## 이벤트 보기
{: #at_events_iam_ui}

이벤트는 **프랑크푸르트(eu-de)** 지역에서 사용할 수 있습니다.해당 이벤트를 보려면 **프랑크푸르트(eu-de)** 지역에 {{site.data.keyword.at_full_notm}} 서비스의 [인스턴스를 프로비저닝](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)해야 합니다.
그런 다음 [{{site.data.keyword.at_full_notm}} UI를 열어야 합니다](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


## 이벤트 분석
{: #at_events_iam_analyze}


### 액세스 그룹 삭제
{: #an_del_ag}

액세스 그룹을 삭제할 때, 트리거된 이벤트의 `action` 필드는 `iam-groups.group.delete`로 설정되어 있습니다.

액세스 그룹을 삭제할 때 다음 정보를 고려하십시오.
* 그룹과 연관된 다른 리소스를 정리하도록 기타 조치가 자동으로 트리거됩니다. 트리거된 일부 조치에서 액세스 그룹의 멤버 삭제, 정책 삭제 및 동적 규칙 삭제와 관련된 이벤트를 보고합니다. 
* 이 조치의 개시자는 {{site.data.keyword.IBM_notm}} 서비스 ID입니다.


삭제한 액세스 그룹에 멤버, 정책 및 규칙이 지정되지 않은 경우 해당 리소스용으로 생성된 이벤트에서 `404` 결과 코드와 함께 `failure` 결과를 보고합니다. 다음 샘플에서는 멤버, 정책 또는 동적 규칙이 지정되지 않은 액세스 그룹을 삭제할 때 생성되는 이벤트를 보여줍니다.

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

