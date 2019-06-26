---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# 경보 구성
{: #alerts}

{{site.data.keyword.at_full_notm}} 웹 UI를 통해 검색 조회를 적용하여 사용자 정의 보기를 통해 표시되는 이벤트를 정의할 수 있습니다. 그런 다음, 조건이 발생하면 알림을 받도록 보기에 경보를 연결할 수 있습니다. 하나 이상의 경보를 보기에 첨부할 수 있습니다. 경보에 대한 다중 알림 채널을 정의할 수 있습니다. 경보를 차단할 수 있습니다. 보기에서 경보를 분리할 수 있습니다.
{:shortdesc}


## 전제조건
{: #alerts_prereqs}

* [경보에 관해 자세히 알아보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts).

* {{site.data.keyword.at_full_notm}} 서비스에 대한 **유료 서비스 플랜이 있어야 합니다**. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).

* 사용자 ID에 웹 UI를 실행하고 이벤트를 볼 수 있는 권한이 있는지 확인하십시오. 다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI를 실행하며 이벤트를 보고, 검색하고, 필터링하기 위해 보유해야 하는 최소 역할이 나열되어 있습니다.

|역할                      |부여되는 권한            |
|---------------------------|-------------------------------|  
|플랫폼 역할: `뷰어`     |사용자가 관찰 가능성 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
|서비스 역할: `독자`      |사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 볼 수 있도록 허용합니다.  |
{: caption="표 1. IAM 역할" caption-side="top"} 

사용자에 맞게 정책을 구성하는 방법에 대한 자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.

 


## 1단계. 웹 UI로 이동
{: #alerts_step1}

[웹 UI로 이동하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## 2단계. 보기 작성
{: #alerts_step2}

[보기를 작성하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).



## 3단계. [선택사항] 사전 설정(경보 템플리트) 구성
{: #alerts_step3}

다른 보기에 경보 구성을 재사용하려면 **경보 사전 설정**을 구성하십시오.
{: note}

사전 설정을 구성하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **구성** 아이콘 ![구성 아이콘 ](images/admin.png "관리 아이콘")을 선택하십시오.
2. **경보**를 선택하십시오.
3. **사전 설정 경보 추가**를 선택하십시오.
4. 알림 채널을 선택하십시오. 지원되는 채널 목록은 [경보 알림 채널](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)을 참조하십시오.
5. 경고 유형을 선택합니다. 보기에 표시되는 이벤트 수가 예상보다 많으면 알리도록 **존재 경보** 유형을 선택하십시오. 보기에 표시되는 이벤트 수가 예상보다 적으면 알리도록 **부재 경보** 유형을 선택하십시오. 
5. 알림 채널을 선택하십시오. 지원되는 채널 목록은 [경보 알림 채널](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)을 참조하십시오.
6. 임계값 조건을 정의하십시오.

    1. 시간 빈도를 선택하십시오 (예: 12시간).

    2. 경보가 트리거될 이벤트 행 수를 입력하십시오.

    3. 두 조건을 모두 선택할지 아니면 하나만 선택할지를 선택하십시오.

7. 선택한 알림 채널에 대한 세부사항을 추가하십시오.

    예를 들어, 이메일 알림 채널의 경우 하나 이상의 수신인 및 선택적으로 시간대를 추가하십시오.

8. **경보 저장**을 클릭하십시오.



## 4단계. 경보 구성
{: #alerts_step4}

보기에 경보를 첨부하려면 다음 옵션 중 하나를 선택하십시오.

### 옵션 1. 사전 설정을 사용하여 경보 구성
{: #alerts_step4_preset}

보기에 사전 설정을 첨부하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **보기** 아이콘 ![구성 아이콘](images/views.png)을 클릭하십시오.
2. 경보를 첨부할 보기 이름을 클릭하십시오. 그런 다음 **경보 첨부**를 선택하십시오.
3. 경보 정의를 재사용할 사전 설정을 선택하십시오. 
4. **경보 저장**을 클릭하십시오. 




### 옵션 2. 보기 특정 경보 구성
{: #alerts_step4_view}

보기에 경보를 첨부하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **보기** 아이콘 ![구성 아이콘](images/views.png)을 클릭하십시오.
2. 보기 이름을 클릭하십시오. 그런 다음 **경보 첨부**를 선택하십시오.
3. **보기 특정 경보**를 선택하십시오.
4. 알림 채널을 선택하십시오. 
5. 경고 유형을 선택합니다. 보기에 표시되는 이벤트 수가 예상보다 많으면 알리도록 **존재 경보** 유형을 선택하십시오. 보기에 표시되는 이벤트 수가 예상보다 적으면 알리도록 **부재 경보** 유형을 선택하십시오. 
6. 임계값 조건을 정의하십시오.

    1. 시간 빈도를 선택하십시오 (예: 12시간).

    2. 경보가 트리거될 이벤트 행 수를 입력하십시오.

    3. 두 조건을 모두 선택할지 아니면 하나만 선택할지를 선택하십시오.

7. 선택한 알림 채널에 대한 세부사항을 추가하십시오.

    예를 들어, 이메일 알림 채널의 경우 하나 이상의 수신인 및 선택적으로 시간대를 추가하십시오.

8. **경보 저장**을 클릭하십시오.



## 사전 설정(경보 템플리트) 삭제
{: #alerts_delete_preset}

사전 설정을 삭제하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **구성** 아이콘 ![구성 아이콘 ](images/admin.png "관리 아이콘")을 선택하십시오.
2. **경보**를 선택하십시오.
3. 삭제할 사전 설정의 *편집* 단추 위로 마우스를 이동하십시오. *삭제* 옵션이 표시됩니다.
4. **삭제**를 선택하십시오.
5. 사전 설정을 삭제할지 확인하십시오. **삭제**를 클릭하십시오.

## 보기에서 보기 특정 경보 분리
{: #alerts_delete_view}

사전 설정을 분리하려면 다음 단계를 완료하십시오.

1. 웹 UI에서 **구성** 아이콘 ![구성 아이콘 ](images/admin.png "관리 아이콘")을 선택하십시오.
2. **경보**를 선택하십시오.
3. 삭제할 경보의 *편집* 단추 위로 마우스를 이동하십시오. *삭제* 옵션이 표시됩니다.
4. **분리**를 선택하십시오.
5. 경보를 삭제할지 확인하십시오. **분리**를 클릭하십시오.












