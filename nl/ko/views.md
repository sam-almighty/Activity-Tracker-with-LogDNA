---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# 사용자 정의 보기 작성
{: #views}

{{site.data.keyword.at_full_notm}} 웹 UI를 통해 검색 및 필터링 기준을 적용하여 사용자 정의 보기를 통해 표시되는 이벤트를 정의할 수 있습니다.
{:shortdesc}


## 전제조건
{: #views_prereqs}

시작하기 전에 사용자 ID에 웹 UI를 실행하고 이벤트를 볼 수 있는 권한이 있는지 확인하십시오. 다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI를 실행하며 이벤트를 보고, 검색하고, 필터링하기 위해 보유해야 하는 최소 역할이 나열되어 있습니다.

|역할                      |부여되는 권한            |
|---------------------------|-------------------------------|  
|플랫폼 역할: `뷰어`     |사용자가 관찰 가능성 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
|서비스 역할: `독자`      |사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 볼 수 있도록 허용합니다.  |
{: caption="표 1. IAM 역할" caption-side="top"} 

사용자에 맞게 정책을 구성하는 방법에 대한 자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.



## 1단계. 웹 UI로 이동하여 보기 선택
{: #views_step1}

다음 단계를 완료하십시오.

1. [웹 UI로 이동하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. **보기** 아이콘 ![구성 아이콘](images/views.png)을 클릭하십시오.
3. **모든 항목** 또는 보기를 선택하십시오. 


## 2단계. 검색 조회를 적용하여 보기에 표시할 이벤트 세트 선택
{: #views_step2}

특정 이벤트를 검색하려면 검색 조회를 적용할 수 있습니다. 

* 단순 검색(단일 용어 문자열 검색), 복합 검색(다중 검색어 및 연산자), 필드 검색(로그 행을 구문 분석할 수 있는 경우) 및 기타 검색을 수행할 수 있습니다. 자세한 정보는 [LogDNA에서 로그를 검색하는 방법에 대한 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://docs.logdna.com/docs/search){:new_window}를 참조하십시오.
* AND 및 OR 연산자는 대소문자를 구분하며 대문자로 입력해야 합니다.

인스턴스의 서비스 플랜을 통해 지정된 기간(일 수) 동안 이벤트만 검색할 수 있습니다.
{: important}


다음 단계를 완료하십시오.
1. 검색 조회를 입력하십시오. 
2. **Enter**를 클릭하십시오. 

조회를 적용하면 보기의 이름이 **저장되지 않은 보기**로 변경됩니다.


### 서비스에서 생성한 이벤트 조회
{: #views_step1_1}

특정 서비스의 이벤트를 필터링하려면 다음 조회를 입력해야 합니다.

```
_supertenant:SERVICENAME
```
{: codeblock}

여기서 `SERVICENAME`은 {{site.data.keyword.cloud_notm}}의 서비스 이름입니다.

다음 표에는 코어 서비스가 나열되어 있습니다.

| 생성된 이벤트               |값                         | 샘플 조회                     |
|--------------------------------------------|-------------------------------|----------------------------------|
| [IAM 액세스 관리 서비스](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [IAM ID 서비스](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [IAM 액세스 그룹 서비스](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)   | `iam-groups`  | `_supertenant:iam-groups`     |
| [리소스 제어기 서비스](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="표 2. 서비스 이름별 조회" caption-side="top"}

### 서비스에서 생성한 이벤트 세트 조회
{: #views_step1_2}

서비스에서 여러 다른 유형의 이벤트를 생성할 때 다음 조회를 입력할 수 있습니다.

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

여기서, 

* `SERVICENAME`은 {{site.data.keyword.cloud_notm}}의 서비스 이름입니다.
* `TYPEOFACTION`은 AND 및 OR 연산자를 사용할 수 있는 복합 조회이며 `-`도 사용하여 데이터를 제외합니다. `AND` 및 `OR` 연산자는 대소문자를 구분하며 대문자로 입력해야 합니다.


다음 표에서는 서비스를 통해 생성한 이벤트 그룹을 조회하는 방법의 예제를 보여줍니다.

| 생성된 이벤트               | 이벤트 유형       | 샘플 조회                     |
|--------------------------------------------|--------------------|---------------------------------|
| `IAM ID 서비스`   | [로그인 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `IAM ID 서비스`   | [API 키 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `IAM ID 서비스`   | [계정 서비스 ID 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `리소스 제어기`                      | [서비스 인스턴스 프로비저닝 및 관리](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `리소스 제어기`                      | [계정에서 사용자 관리](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="표 3. 더 복합한 조회 샘플" caption-side="top"}


### 특정 조치가 있는 이벤트 조회
{: #views_step1_3}

각 이벤트에는 이벤트를 트리거한 조치에 관해 알리는 **조치** 필드가 있습니다. 다음 조회를 입력하여 동일한 조치가 있는 모든 이벤트를 검색할 수 있습니다.

```
action ACTIONVALUE
```
{: codeblock}

여기서 `ACTIONVALUE`는 조치 필드의 값 또는 값의 일부입니다.

다음 표에는 여러 다른 조치의 조회 예제가 표시되어 있습니다.

|조치                 | 샘플 조회                     |
|------------------------|----------------------------------|
| 서비스 프로비저닝   | `action instance.create`         |
| 인스턴스 제거       | `action instance.delete`         |
| 사용자 추가         | `action user-management.user.create` |
{: caption="표 4. 조치 유형별 조회 샘플" caption-side="top"}



### 실패한 조치가 있는 이벤트 조회
{: #views_step1_4}

요청한 조치가 실패하면 **결과** 필드가 **실패**로 설정됩니다. 다음 조회를 입력하여 해당 유형의 이벤트를 검색할 수 있습니다.

```
outcome failure
```
{: codeblock}


### 이벤트 심각도별 조회
{: #views_step1_5}

각 이벤트에는 클라우드에서 조치를 수행할 때 수반될 수 있는 위협 레벨을 정의하는 **심각도** 필드가 있습니다. 

올바른 값은 *normal*, *warning* 및 *critical*입니다. 
* **normal**은 클라우드의 일상적인 조치에 대해 설정됩니다. 예를 들어, 인스턴스 시작 또는 토큰 새로 고치기가 있습니다. 
* **warning**은 클라우드 리소스가 업데이트되거나 해당 메타데이터가 수정되는 조치에 대해 설정됩니다. 예를 들어, 작업자 노드의 버전 업데이트, 인증서 이름 바꾸기 또는 서비스 인스턴스 이름 바꾸기가 있습니다. 
* **critical**은 클라우드의 보안에 영향을 미치는 조치에 대해 설정됩니다. 예를 들어, 사용자의 인증 정보 변경, 데이터 삭제, 클라우드 리소스에 대해 작업하기 위한 무단 액세스가 있습니다.

다음 조회를 입력하여 해당 유형의 이벤트를 검색할 수 있습니다.

```
severity VALUE
```
{: codeblock}

여기서 `VALUE`는 *정상*, *경고* 또는 *심각*으로 설정할 수 있습니다.

예를 들어 심각한 이벤트를 조회하려면 다음 조회를 실행할 수 있습니다.

```
severity critical
```
{: codeblock}



## 3단계. 사용자 정의 보기 작성
{: #views_step3}

검색 조회를 **모든 항목** 보기나 기존 사용자 정의 보기에 적용한 후 다음 단계를 완료하여 결과를 사용자 정의 보기로 저장하십시오.

1. 웹 UI에서 **저장되지 않은 보기**를 클릭하십시오.
2. **새 보기/경보로 저장**을 선택하십시오. *새 보기 작성* 페이지가 열립니다.
3. *이름* 필드에 보기의 이름을 입력하십시오.
4. 선택적으로 카테고리를 추가하십시오. 이름을 입력한 후 **이를 새 보기 카테고리로 추가**를 클릭하십시오.
5. 선택적으로 경보를 첨부하십시오. 경보를 구성하도록 새 섹션이 표시됩니다.
6. **보기 저장**을 클릭하십시오.


## 4단계. 보기를 통해 이벤트 행을 표시하는 방법 사용자 정의
{: #views_step4}

보기에서 데이터를 보는 방법을 사용자 정의할 수 있는 여러 가지 옵션이 있습니다.
* 보기의 특성을 수정할 수 있습니다. 보기의 이름을 바꾸고 해당 설명을 추가하거나 수정하고 특정 행 형식을 적용할 수 있습니다.
* *사용자 환경 설정* 섹션에서 `로그 형식`을 변경할 수 있습니다.
* *도구* 섹션에서 행 템플리트를 적용할 수 있습니다. 그러면 다른 행 구성을 모두 대체합니다. **이 설정 지속**을 선택하면 UI에 있는 모든 보기에서 이 섹션에 지정된 행 형식별로 데이터를 표시합니다.
* **도구** 섹션에서 **용어 강조표시**를 설정하여 용어나 문자열에 색상을 적용할 수 있습니다. 



### 보기 특성 페이지를 통해 행 형식 변경
{: #views_step4_1}

단일 보기에서 이벤트 행의 형식을 수정하려면 다음 단계를 완료하십시오.

1. 보기에서 **보기 특성 편집**을 선택하십시오. *보기 특성 편집* 페이지가 열립니다.

2. **사용자 정의 %LINE 템플리트** 섹션에서 사용자 정의 행 형식을 입력하십시오. 기본값은 `{{line}}`(으)로 설정됩니다.

    행 템플리트 가이드라인에 관한 자세한 정보는 [가이드라인](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)을 참조하십시오.

3. **특성 저장*을 클릭하십시오.



### 사용자 환경 설정 섹션을 통해 행 형식을 변경하십시오.
{: #views_step4_2}

**사용자 환경 설정** 섹션에서 행마다 표시되는 데이터 필드의 순서를 수정할 수 있습니다.

이벤트 행의 형식을 수정하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **구성** 아이콘 ![구성 아이콘](images/admin.png "관리 아이콘")을 클릭하십시오.
2. **사용자 환경 설정**을 선택하십시오. 새 창이 열립니다.
3. **로그 형식**을 선택하십시오.
4. 요구사항에 맞게 *행 형식* 섹션을 수정하십시오. 상자를 끌어오십시오.


### 도구 섹션의 행 템플리트를 통해 행 형식을 변경하십시오.
{: #views_step4_3}

이벤트 행의 형식을 수정하려면 다음 단계를 완료하십시오.

1. 보기에서 **도구** 아이콘 ![도구 아이콘](images/tool.png "도구 아이콘")을 클릭하십시오.
2. **행 템플리트** 필드에 사용자 정의 행 형식을 입력하십시오. 행 템플리트 가이드라인에 관한 자세한 정보는 [가이드라인](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)을 참조하십시오.
3. 선택적으로 **이 설정 지속**을 클릭하여 행 형식을 모든 보기에 적용하십시오.



### 용어 강조표시
{: #view_events_step4_4}

보기에서 용어를 강조표시하려면 다음 단계를 완료하십시오.

1. 보기에서 **도구** 아이콘 ![도구 아이콘](images/tool.png "도구 아이콘")을 클릭하십시오.
2. **행 템플리트** 필드에 **용어 강조표시** 섹션의 단어 또는 문자열을 입력하십시오.
3. 선택적으로 **이 설정 지속**을 클릭하여 해당 설정을 모든 보기에 적용하십시오.



## 사용자 정의 보기의 이름 및 설명 변경
{: #views_step5}

보기의 이름을 바꿀 수 있습니다. 보기에 대한 설명을 추가하거나 수정할 수 있습니다.


다음 단계를 완료하십시오.

1. 보기에서 **보기 특성 편집**을 선택하십시오. *보기 특성 편집* 페이지가 열립니다.

    보기 이름을 바꾸고 보기의 설명을 추가하거나 수정하며 사용자 정의 행 형식을 적용할 수 있습니다.

2. 보기의 이름을 바꾸려면 **보기 이름 바꾸기** 섹션에 새 이름을 입력하십시오.

3. **설명** 섹션에서 설명을 입력하거나 수정하십시오.

4. **특성 저장**을 클릭하십시오.



## 행 템플리트를 정의하는 가이드라인
{: #views_line}

행 템플리트를 정의할 때 적용해야 하는 다음 가이드라인을 고려하십시오.
* 콧수염(mustache) 스타일 `{{field.name}}` 또는 배시 스타일 `${field.name}` 변수를 사용하여 템플리트를 생성하십시오. 
* `{{line}}` 또는 `$@`를 사용하여 원래 행을 참조하십시오. 
* 기타 모든 문자 또는 문자열은 텍스트 리터럴로 해석됩니다. 


예를 들어 행 템플리트를 `{{initiator.id}} -- {{action}} -- {{message}}`로 정의하여 보기에서 각 이벤트의 해당 필드를 볼 수 있습니다.


