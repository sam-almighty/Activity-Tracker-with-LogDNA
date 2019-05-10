---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# 이벤트 보기
{: #view_events.md}

{{site.data.keyword.cloud_notm}}에서 {{site.data.keyword.at_full_notm}} 서비스의 인스턴스를 프로비저닝한 후 {{site.data.keyword.at_full_notm}} 웹 UI를 통해 이벤트를 볼 수 있습니다.
{:shortdesc}


## 전제조건
{: #view_events_prereqs}

시작하기 전에 사용자 ID에 웹 UI를 실행하고 이벤트를 볼 수 있는 권한이 있는지 확인하십시오. 

**참고:** {{site.data.keyword.at_full_notm}} 서비스의 관리자 또는 {{site.data.keyword.at_full_notm}} 인스턴스의 관리자이거나 정책을 관리할 수 있는 계정 IAM 권한이 있어야 합니다.

다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI를 실행하고 이벤트를 보기 위해 보유해야 하는 최소 정책이 나열되어 있습니다.

|역할                      |부여되는 권한            |
|---------------------------|-------------------------------|  
|플랫폼 역할: `뷰어`     |사용자가 관찰 가능성 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
|서비스 역할: `독자`     |사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 볼 수 있도록 허용합니다. |
{: caption="표 1. IAM 정책" caption-side="top"} 

사용자를 위해 이러한 정책을 구성하는 방법에 대한 자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.


## 웹 UI를 통해 이벤트 보기
{: #view_events_step1}

{{site.data.keyword.at_full_notm}} 웹 UI를 실행하려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.cloud_notm}} *대시보드*가 열립니다.

2. 메뉴 아이콘 ![메뉴 아이콘](../../icons/icon_hamburger.svg)으로 이동하여 **관찰 가능성**을 선택하십시오. 

3. **Activity Tracker**를 선택하십시오.  

    {{site.data.keyword.at_full_notm}} 인스턴스의 목록이 표시됩니다.

    **참고:** 지역마다 하나의 인스턴스가 있습니다.

4. 이벤트를 보려는 지역의 인스턴스를 선택하십시오. 그런 다음 **LogDNA 보기**를 클릭하십시오.

{{site.data.keyword.at_full_notm}} 웹 UI가 열리고 **모든 항목** 보기가 표시됩니다. 이 보기를 통해 선택한 지역에 대한 계정의 이벤트를 볼 수 있습니다.

**참고:** `Lite` 플랜이 있고 검색 중인 이벤트를 볼 수 없는 경우 이전 이벤트에서 검색 기능을 사용할 수 있도록 유료 플랜으로 업그레이드해야 할 수 있습니다. 이벤트를 검색에 사용할 수 있는 일 수는 선택한 플랜에 따라 다릅니다. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).


## 기본 보기 사용자 정의
{: #view_events_step2}

**사용자 환경 설정** 섹션에서 행마다 표시되는 데이터 필드의 순서를 수정할 수 있습니다.

이벤트 행의 형식을 수정하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **구성** 아이콘 ![구성 아이콘](images/admin.png "관리 아이콘")을 클릭하십시오.
2. **사용자 환경 설정**을 선택하십시오. 새 창이 열립니다.
3. **로그 형식**을 선택하십시오.
4. 요구사항에 맞게 *행 형식* 섹션을 수정하십시오. 상자를 끌어오십시오.




## 컨텍스트에서 이벤트 보기
{: #view_events_step3}

언제든지 컨텍스트에서 각 이벤트 행을 볼 수 있습니다.

다음 단계를 완료하십시오. 

1. 웹 UI에서 **보기** 아이콘 ![구성 아이콘](images/views.png "구성 아이콘")을 클릭하십시오.
2. **모든 항목** 또는 사용자 정의 보기를 선택하십시오.
3. 탐색할 행을 식별하십시오.
4. 이벤트 행을 펼치십시오. 

    행 ID, 태그 및 레이블에 대한 정보가 표시됩니다.

5. **컨텍스트에서 보기**를 클릭하여 해당 호스트, 앱 또는 둘 다에서 다른 항목의 컨텍스트에 있는 이벤트 행을 보십시오.

이벤트 탐색이 완료되면 **닫기**를 클릭하여 행을 닫으십시오.




## 이벤트를 클립보드에 복사
{: #view_events_step4}


이벤트를 클립보드에 복사하려면 다음 단계를 완료하십시오. 

1. 웹 UI에서 **보기** 아이콘 ![구성 아이콘](images/views.png "구성 아이콘")을 클릭하십시오.
2. **모든 항목** 또는 사용자 정의 보기를 선택하십시오.
3. 탐색할 행을 식별하십시오.
4. 이벤트 행을 펼치십시오. 

    행 ID, 태그 및 레이블에 대한 정보가 표시됩니다.

5. **클립보드에 복사**를 클릭하여 이벤트를 클립보드에 복사하십시오.

이벤트 탐색이 완료되면 **닫기**를 클릭하여 행을 닫으십시오.




