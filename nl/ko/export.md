---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# 이벤트 내보내기
{: #export}

{{site.data.keyword.at_full_notm}} 인스턴스에서 로컬 파일로 JSONL 형식의 데이터를 내보낼 수 있습니다. LogDNA REST API를 사용하거나 웹 UI를 통해 프로그래밍 방식으로 로그를 내보낼 수 있습니다.
{:shortdesc}


## 전제조건
{: #export_prereqs}

* [이벤트 내보내기에 관해 자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_export).

* {{site.data.keyword.at_full_notm}} 서비스에 대한 **유료 서비스 플랜이 있어야 합니다**. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 

* 사용자 ID에 웹 UI를 실행하고 이벤트를 볼 수 있는 권한이 있는지 확인하십시오. 다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI를 실행하며 이벤트를 보고, 검색하고, 필터링하기 위해 보유해야 하는 최소 역할이 나열되어 있습니다.

|역할                      |부여되는 권한            |
|---------------------------|-------------------------------|  
|플랫폼 역할: `뷰어`     |사용자가 관찰 가능성 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
|서비스 역할: `독자`      |사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 볼 수 있도록 허용합니다.  |
{: caption="표 1. IAM 역할" caption-side="top"} 

사용자에 맞게 정책을 구성하는 방법에 대한 자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.


## 1단계. 웹 UI로 이동
{: #export_step1}

[웹 UI로 이동하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## 2단계. 보기 작성
{: #export_step2}

[보기를 작성하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).


## 3단계. 데이터 내보내기
{: #export_step3}

이벤트를 내보내려면 다음 옵션 중 하나를 선택하십시오.

### 옵션 1. 웹 UI에서 이벤트 내보내기
{: #export_ui}

데이터를 내보내려면 다음 단계를 완료하십시오.

1. **보기** 아이콘 ![구성 아이콘](images/views.png)을 클릭하십시오.
2. **모든 항목** 또는 보기를 선택하십시오.
3. 내보낼 항목이 표시될 때까지 시간 범위, 필터 및 검색 기준을 적용하십시오.
4. **모든 항목** 보기에서 시작하는 경우 **저장되지 않은 보기**를 클릭하십시오. 이전 단계에서 보기를 선택한 경우 보기 이름을 클릭하십시오.
5. **행 내보내기**를 선택하십시오. 새 창이 열립니다.
6. 시간 범위를 확인하십시오. 변경해야 하는 경우 *내보내기를 위한 시간 범위 변경* 필드에서 사전 정의된 시간 범위를 클릭하십시오.
7. 내보내기 요청이 행 한계를 초과하는 경우 **새 행 선호** 또는 **이전 행 선호**를 선택하십시오.
8. 이메일을 확인하십시오. **LogDNA**에서 링크가 포함된 이메일을 수신하여 내보낸 행을 다운로드하십시오.


### 옵션 2. API를 사용하여 프로그래밍 방식으로 이벤트 내보내기
{: #export_api}

이벤트를 프로그래밍 방식으로 내보내려면 다음 단계를 완료하십시오.

1. 서비스 키를 생성하십시오. 

    **참고:** 이 단계를 완료하려면 {{site.data.keyword.at_full_notm}} 인스턴스 또는 서비스의 **관리자** 역할이 있어야 합니다.

    1. [{{site.data.keyword.at_full_notm}} 웹 UI를 실행하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2).

    2. **구성** 아이콘 ![구성 아이콘](images/admin.png)을 선택하십시오. 그런 다음 **조직**을 선택하십시오. 

    3. **API 키**를 선택하십시오.

        작성된 서비스 키를 볼 수 있습니다. 

    4. **서비스 키 생성**을 클릭하십시오. 새 키가 목록에 추가됩니다. 이 키를 복사하십시오.

2. 이벤트를 내보내십시오. 다음 cURL 명령을 실행하십시오.

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    여기서, 

    * ENDPOINT는 서비스의 시작점을 나타냅니다. 각 지역의 URL은 서로 다릅니다. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints).
    * QUERY_PARAMETERS는 내보내기 요청에 적용되는 필터링 기준을 정의하는 매개변수입니다.
    * SERVICE_KEY는 이전 단계에서 작성한 서비스 키입니다.

다음 표에는 설정할 수 있는 조회 매개변수가 나열되어 있습니다.

|조회 매개변수 |유형       |상태     |설명 |
|-----------|------------|------------|-------------|
|`from`      |`int32`      |필수   |시작 시간입니다. 초 또는 밀리초 단위의 UNIX 시간소인으로 설정합니다. |
|`to`        |`int32`      |필수   |종료 시간입니다. 초 또는 밀리초 단위의 UNIX 시간소인으로 설정합니다.    |
|`size`      |`string`     |선택사항   |내보내기에 포함할 로그 행 수입니다.  | 
|`hosts`     |`string`     |선택사항   |쉼표로 구분된 호스트 목록입니다. |
|`apps`      |`string`     |선택사항   |쉼표로 구분된 애플리케이션 목록입니다. |
|`levels`    |`string`     |선택사항   |쉼표로 구분된 로그 레벨 목록입니다. |
|`query`     |`string`     |선택사항   |검색 조회입니다. 자세한 정보는 [로그 검색](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6)을 참조하십시오. |
|`prefer`    |`string`     |선택사항   |내보낼 로그 행을 정의합니다. 올바른 값은 `head`(첫 번째 로그 행) 및 `tail`(마지막 로그 행)입니다. 지정되지 않은 경우 기본값은 tail입니다.  |
|`email`     |`string`     |선택사항   |내보내기의 다운로드 가능 링크가 포함된 이메일을 지정합니다. 기본적으로 로그 행은 스트리밍됩니다.|
|`emailSubject` |`string`     |선택사항   |이메일의 제목을 설정하는 데 사용합니다. </br>영역을 표시하려면 `%20`을 사용하십시오. 예를 들어, 샘플 값은 `Export%20logs`입니다. |
{: caption="조회 매개변수" caption-side="top"} 

예를 들어, 이벤트를 터미널로 스트리밍하려면 다음 명령을 실행할 수 있습니다.

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

내보내기에 지정된 이벤트를 다운로드하기 위해 링크가 포함된 이메일을 발송하려면 다음 명령을 실행할 수 있습니다.

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


사용자 정의 제목이 포함된 이메일을 발송하려면 다음 명령을 실행할 수 있습니다.

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

