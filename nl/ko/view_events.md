---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #view_events}

{{site.data.keyword.cloud_notm}}에서 {{site.data.keyword.at_full_notm}} 서비스의 인스턴스를 프로비저닝한 후 {{site.data.keyword.at_full_notm}} 웹 UI를 통해 이벤트를 볼 수 있습니다. 이벤트는 로컬 시간으로 표시됩니다.{:shortdesc}


## 이벤트 보기
{: #view_events_step1}

다음 단계를 완료하여 이벤트를 보십시오.

1. 사용자 ID에 웹 UI를 실행하고 이벤트를 볼 수 있는 권한이 있는지 확인하십시오.  

    다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI를 실행하며 이벤트를 보고, 검색하고, 필터링하기 위해 보유해야 하는 최소 역할이 나열되어 있습니다.

    <table>
      <caption>표 1. IAM 역할</caption>
      <tr>
        <th>역할</th>
        <th>부여되는 권한</th>
      </tr>
      <tr>
        <td>플랫폼 역할: `뷰어`</td>
        <td>사용자가 *관찰 가능성* 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다.</td>
      </tr>
      <tr>
        <td>서비스 역할: `독자`</td>
        <td>사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 보고 검색하며 필터링할 수 있도록 허용합니다.</td>
      </tr>
    </table>

    사용자에 맞게 정책을 구성하는 방법에 대한 자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.

2. [웹 UI로 이동하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

3. **보기** 아이콘 ![구성 아이콘](images/views.png)을 클릭하십시오.

4. **모든 항목**을 선택하여 모든 이벤트 또는 보기를 확인하십시오. 

선택한 보기를 통해 이벤트를 볼 수 있습니다.



## 검색 조회를 적용하여 이벤트의 서브세트 보기
{: #view_events_step2}

검색 조회를 적용하여 보기를 통해 표시되는 이벤트를 선택할 수 있습니다. 나중에 다시 사용하도록 해당 보기를 저장할 수 있습니다. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2).

 


## 시간 범위를 적용하여 이벤트의 서브세트 보기
{: #view_events_step3}

시간 범위를 적용하여 보기를 통해 표시되는 이벤트를 선택할 수 있습니다. 

절대 시간, 상대 시간 또는 시간 범위를 지정하여 시간소인을 적용할 수 있습니다.

특정 시간으로 건너뛰려면 다음 단계를 완료하십시오.
1. [웹 UI로 이동하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. **보기** 아이콘 ![구성 아이콘](images/views.png)을 클릭하십시오.
3. **모든 항목** 또는 보기를 선택하십시오.
4. 시간 조회를 입력하십시오. 다음 옵션을 선택하십시오.

    * `May 20 7:00pm`과 같은 이벤트의 특정 시점으로 건너뛰려면 절대 시간을 입력하십시오.
    
    * `2 days ago`, `today at 12am` 또는 `an hour ago`와 같은 상대 시간을 입력하십시오.

    * `yesterday 10am to yesterday 11am`, `last fri 4:30pm to 11/12 1 AM`, `last wed 4:30pm to 23/05 1 AM` 또는 `May 20 10am to May 22 10am`과 같은 시간 범위를 입력하십시오. 종료 시간소인에서 초기 시간 소인을 구분하기 위해 `to`를 포함시키십시오.

5. **ENTER**를 클릭하십시오.

    다음과 같은 오류가 발생할 수 있습니다. `Your request is taking longer than expected, try refreshing your browser in a bit as we try to catch up. Retry.` 지정한 시간 범위에 표시할 수 있는 이벤트가 없으면 이 오류가 발생할 수 있습니다. 시간 조회를 변경하고 다시 시도하십시오.



## 컨텍스트에서 이벤트 보기
{: #view_events_step4}

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
{: #view_events_step5}


이벤트를 클립보드에 복사하려면 다음 단계를 완료하십시오. 

1. 웹 UI에서 **보기** 아이콘 ![구성 아이콘](images/views.png "구성 아이콘")을 클릭하십시오.
2. **모든 항목** 또는 사용자 정의 보기를 선택하십시오.
3. 탐색할 행을 식별하십시오.
4. 이벤트 행을 펼치십시오. 

    행 ID, 태그 및 레이블에 대한 정보가 표시됩니다.

5. **클립보드에 복사**를 클릭하여 이벤트를 클립보드에 복사하십시오.

이벤트 탐색이 완료되면 **닫기**를 클릭하여 행을 닫으십시오.




