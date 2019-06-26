---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# 인스턴스 프로비저닝
{: #provision}

{{site.data.keyword.at_full_notm}}를 사용하여 이벤트 데이터를 모니터하고 관리하려면 {{site.data.keyword.cloud_notm}}에서 서비스 인스턴스를 프로비저닝해야 합니다.
{:shortdesc}

퍼블릭 클라우드 지역에 {{site.data.keyword.at_full_notm}} 인스턴스를 프로비저닝하려면 다음 정보를 고려하십시오.
* 인스턴스와 연관된 서비스 플랜, 로그를 수집할 지역 및 로그의 보존 기간을 판별하는 플랜을 선택해야 합니다. 7일, 14일 또는 30일 보존 기간 중에서 선택할 수 있습니다. 또는 {{site.data.keyword.at_full_notm}}는 이벤트가 시스템을 통과할 때 이벤트를 보는 데 사용할 수 있는 `Lite` 플랜을 제공합니다. 이벤트 추적을 사용하여 이벤트를 볼 수 있습니다. 또한 장기 보존 기간 플랜으로의 업그레이드를 준비하기 위해 필터를 디자인할 수 있습니다. 이 플랜에는 0일의 보존 기간이 있습니다.
* 사용자 ID에는 리소스 그룹에 서비스를 프로비저닝하는 권한이 있어야 합니다. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups).


{{site.data.keyword.cloud_notm}} 지역당 서비스 인스턴스를 하나만 프로비저닝할 수 있습니다.
{: important}

## 관찰 가능성 대시보드를 통해 인스턴스 프로비저닝
{: #provision_ui}

{{site.data.keyword.cloud_notm}}의 관찰 가능성 대시보드에서 인스턴스를 프로비저닝하려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.cloud_notm}} UI가 열립니다.

2. 메뉴 아이콘 ![메뉴 아이콘](../../icons/icon_hamburger.svg)으로 이동하십시오. 그런 다음 **관찰 가능성**을 선택하여 *관찰 가능성* 대시보드에 액세스하십시오.

3. **Activity Tracker**를 선택한 후 **인스턴스 작성**을 클릭하십시오. 

4. 서비스 인스턴스의 이름을 입력하십시오.

5. 인스턴스를 프로비저닝하려는 [위치](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)를 선택하십시오. 

6. 리소스 그룹을 선택하십시오. 

    기본적으로 **default** 리소스 그룹이 설정됩니다.

    **참고:** 리소스 그룹을 선택할 수 없는 경우 인스턴스를 프로비저닝할 리소스 그룹에 대한 편집 권한이 있는지 확인하십시오.

7. `Lite` 서비스 플랜을 선택하십시오. 

    기본적으로 Lite 플랜이 설정됩니다.

8. **작성**을 클릭하십시오.

인스턴스를 프로비저닝하면 *Activity Tracker* 대시보드가 열립니다. 

다음으로 웹 UI로 이동하여 계정의 이벤트를 보십시오. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events).



## 카탈로그를 통해 인스턴스 프로비저닝
{: #provision_catalog}

{{site.data.keyword.cloud_notm}} 카탈로그를 통해 {{site.data.keyword.at_full_notm}}의 인스턴스를 프로비저닝하려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.cloud_notm}} UI가 열립니다.

2. **카탈로그**를 클릭하십시오. {{site.data.keyword.cloud_notm}}에서 사용 가능한 서비스 목록이 열립니다.

3. 표시되는 서비스 목록을 필터링하려면 **개발자 도구** 카테고리를 선택하십시오.

4. **{{site.data.keyword.at_full_notm}}** 타일을 클릭하십시오. 

5. 서비스 인스턴스의 이름을 입력하십시오.

6. 위치를 프로비저닝하려는 위치를 선택하십시오. 

    {{site.data.keyword.at_full_notm}} 서비스에 사용 가능한 최신 위치 목록을 확인하려면 [위치](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)를 보십시오.

7. 리소스 그룹을 선택하십시오. 

    기본적으로 **default** 리소스 그룹이 설정됩니다.

    **참고:** 리소스 그룹을 선택할 수 없는 경우 인스턴스를 프로비저닝할 리소스 그룹에 대한 편집 권한이 있는지 확인하십시오.

8. `Lite` 서비스 플랜을 선택하십시오. 

    기본적으로 Lite 플랜이 설정됩니다.

9. **작성**을 클릭하십시오.

인스턴스를 프로비저닝하면 *Activity Tracker* 대시보드가 열립니다. 

다음으로, 웹 UI로 이동하여 계정의 이벤트를 관리하십시오. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## CLI를 통해 인스턴스 프로비저닝
{: #provision_cli}

명령행을 통해 {{site.data.keyword.at_full_notm}}의 인스턴스를 프로비저닝하려면 다음 단계를 완료하십시오.

1. [전제조건] {{site.data.keyword.cloud_notm}} CLI를 설치하십시오. [자세히 보기](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   CLI가 설치되어 있는 경우 다음 단계를 계속하십시오.

2. 인스턴스를 프로비저닝할 {{site.data.keyword.cloud_notm}}의 위치에 로그인하십시오. [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login) 명령을 실행하십시오.

    {{site.data.keyword.at_full_notm}} 서비스에 사용 가능한 최신 위치 목록을 확인하려면 [위치](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)를 보십시오.

3. 인스턴스를 프로비저닝할 리소스 그룹을 설정하십시오. [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target) 명령을 실행하십시오.

    기본적으로 `default` 리소스 그룹이 설정됩니다.

4. 인스턴스를 작성하십시오.  [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create) 명령을 실행하십시오.

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    여기서,

    * NAME은 인스턴스의 이름입니다.

    * *logdnaat* 값은 {{site.data.keyword.cloud_notm}}에 있는 {{site.data.keyword.at_full_notm}} 서비스의 이름입니다.

    * SERVICE_PLAN_NAME은 플랜의 유형입니다. 올바른 값은 *lite*, *7-days*, *14-days*, *30-days*입니다.
    
    * LOCATION은 LogDNA 인스턴스가 작성된 지역입니다. {{site.data.keyword.at_full_notm}} 서비스에 사용 가능한 최신 위치 목록을 확인하려면 [위치](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)를 보십시오.

    
예를 들어, 보존 플랜이 7일인 인스턴스를 프로비저닝하려면 다음 명령을 실행하십시오.

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



