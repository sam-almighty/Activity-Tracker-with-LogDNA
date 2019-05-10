---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# 인스턴스 제거
{: #remove}

{{site.data.keyword.cloud_notm}} UI에서 또는 명령행을 통해 {{site.data.keyword.at_full_notm}} 서비스의 인스턴스를 제거할 수 있습니다.
{:shortdesc}



## {{site.data.keyword.cloud_notm}} UI를 통해 인스턴스 제거
{: #remove_ui}

{{site.data.keyword.cloud_notm}} UI를 사용하여 {{site.data.keyword.at_full_notm}}의 인스턴스를 제거하려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.cloud_notm}} UI가 열립니다.

2. 메뉴 아이콘 ![메뉴 아이콘](../../icons/icon_hamburger.svg) &gt; **관찰 가능성**으로 이동하여 *관찰 가능성* 대시보드에 액세스하십시오.

3. **Activity Tracker**를 선택하십시오. 인스턴스 목록이 표시됩니다.

4. 삭제할 인스턴스를 선택하십시오.

5. *조치* 메뉴에서 **제거**를 선택하십시오.

다음으로, 삭제한 인스턴스에 대해 작업할 수 있도록 사용자에게 부여된 권한을 제거하십시오.

## CLI를 통해 인스턴스 제거
{: #remove_cli}

명령행을 통해 {{site.data.keyword.at_full_notm}}의 인스턴스를 제거하려면 다음 단계를 완료하십시오.

1. [전제조건] {{site.data.keyword.cloud_notm}} CLI를 설치하십시오.

   자세한 정보는 [{{site.data.keyword.cloud_notm}} CLI 설치](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)를 참조하십시오.

   CLI가 설치되어 있는 경우 다음 단계를 계속하십시오.

2. 인스턴스를 프로비저닝할 {{site.data.keyword.cloud_notm}}의 지역에 로그인하십시오. [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login) 명령을 실행하십시오.

3. 인스턴스가 프로비저닝된 리소스 그룹을 설정하십시오. [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target) 명령을 실행하십시오.

    기본적으로 *default* 리소스 그룹이 설정됩니다.

4. 인스턴스를 제거하십시오. [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) 명령을 실행하십시오.

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    여기서 NAME은 인스턴스의 이름입니다.

    로그인한 리소스 그룹에서 사용 가능한 모든 인스턴스를 나열하려면 다음 명령을 실행하십시오.

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
예를 들어, 인스턴스를 제거하려면 다음 명령을 실행하십시오.

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

다음으로, 삭제한 인스턴스에 대해 작업할 수 있도록 사용자에게 부여된 권한을 제거하십시오.


