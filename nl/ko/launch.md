---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# 웹 UI 탐색
{: #launch}

{{site.data.keyword.cloud_notm}}에서 {{site.data.keyword.at_full_notm}} 서비스의 인스턴스를 프로비저닝한 후 {{site.data.keyword.at_full_notm}} 웹 UI를 통해 이벤트를 보고 모니터하고 관리할 수 있습니다.
{:shortdesc}


## 1단계. 데이터를 볼 수 있도록 사용자에게 IAM 정책 부여 
{: #step1}

**참고:** {{site.data.keyword.at_full_notm}} 서비스의 관리자 또는 {{site.data.keyword.at_full_notm}} 인스턴스의 관리자이거나 다른 사용자에게 정책을 부여할 수 있는 계정 IAM 권한이 있어야 합니다.

다음 표에는 사용자가 웹 UI를 실행하고 {{site.data.keyword.at_full_notm}} 웹 UI를 통해 데이터를 보기 위해 보유해야 하는 최소 정책이 나열되어 있습니다.

|역할                      |부여되는 권한            |
|---------------------------|---------------------|
|플랫폼 역할: `뷰어`     |사용자가 관찰 가능성 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
|서비스 역할: `독자`     |사용자가 웹 UI를 통해 이벤트를 볼 수 있도록 허용합니다. | 
{: caption="표 1. IAM 정책" caption-side="top"} 

자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.


## 2단계. {{site.data.keyword.cloud_notm}} UI를 통해 웹 UI 실행
{: #launch_step2}

{{site.data.keyword.cloud_notm}} UI를 통해 {{site.data.keyword.at_full_notm}} 인스턴스의 컨텍스트 내에서 웹 UI를 실행합니다. 

웹 UI를 실행하려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.cloud_notm}} 대시보드가 열립니다.

2. 탐색 메뉴에서 **관찰 가능성**을 선택하십시오. 

3. **Activity Tracker**를 선택하십시오.  

    {{site.data.keyword.cloud_notm}}에서 사용 가능한 인스턴스의 목록이 표시됩니다.

4. 하나의 인스턴스를 선택하십시오. 그런 다음 **LogDNA 보기**를 클릭하십시오.

웹 UI가 열립니다.


## {{site.data.keyword.cloud_notm}}에서 웹 UI URL 가져오기
{: #launch_get}

웹 UI URL을 가져오려면 터미널에서 다음 단계를 완료하십시오.

1. {{site.data.keyword.at_full_notm}} 인스턴스가 프로비저닝된 리소스 그룹을 설정하십시오.

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. {{site.data.keyword.at_full_notm}} 인스턴스 이름을 설정하십시오.

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. 엔드포인트를 설정하십시오.

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. IAM 토큰을 설정하십시오.

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **참고:** MacOS 터미널에서 작업하는 경우 명령은 다음과 같습니다. `export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. 리소스 그룹 ID를 설정하십시오.

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. 변수에 웹 UI URL을 설정하십시오.

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. 웹 UI URL을 가져오십시오.

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

