---

copyright:
  years: 2019
lastupdated: "2019-05-22"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# 사용자 또는 서비스 ID에 관리 권한 부여
{: #iam_manage_events}

{{site.data.keyword.iamlong}}(IAM)를 사용하여 사용자를 안전하게 인증하고 {{site.data.keyword.cloud_notm}}에서 모든 클라우드 리소스에 대한 액세스를 일관되게 제어할 수 있습니다. 사용자 또는 서비스 ID에 {{site.data.keyword.at_full_notm}} 서비스에 대해 작업할 수 있는 관리 권한을 부여하려면 다음 단계를 완료하십시오.
{:shortdesc}

예를 들어, 서비스의 관리자는 서비스의 인스턴스를 프로비저닝 및 제거하고, 다른 사용자에게 서비스에 대해 작업할 수 있는 권한을 부여하고, 로그를 {{site.data.keyword.cos_full_notm}}(COS) 인스턴스에 아카이브할 수 있습니다. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

## 전제조건
{: #iam_manage_events_prereq}

{{site.data.keyword.at_full_notm}} 서비스를 관리하려면 사용자 ID에 **관리자 플랫폼 권한**이 필요합니다. 계정 관리자에게 문의하십시오. 계정 소유자는 사용자 액세스를 관리하고 계정 리소스를 관리하기 위해 계정에 다른 사용자 액세스 권한을 부여할 수 있습니다. [자세히 보기](/docs/iam?topic=iam-userroles).


## 1단계. 액세스 그룹 작성
{: #ime_step1}

액세스 그룹을 작성하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 후 **액세스 그룹**을 선택하십시오.
2. **작성**을 클릭하십시오.
3. 그룹의 이름과 선택적 설명을 입력한 후 **작성**을 클릭하십시오.

**그룹 제거** 옵션을 선택하여 그룹을 삭제할 수 있습니다. 계정에서 그룹을 제거하면 그룹 및 그룹에 지정된 모든 액세스에서 모든 사용자 및 서비스 ID가 제거됩니다.
{: note}

CLI를 사용하여 액세스 그룹을 작성하기 위해 [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) 명령을 사용할 수 있습니다.
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## 2단계. 이벤트를 관리할 수 있는 권한 추가
{: #ime_step2}

그룹을 설정한 후 그룹에 공통 액세스 정책을 지정할 수 있습니다. 

액세스 그룹에 대해 설정하는 정책은 그룹 내의 모든 엔티티, 사용자 및 서비스 ID에 적용됩니다. 
{: note}

UI를 사용하거나 명령행을 통해 정책을 지정할 수 있습니다.

CLI를 사용하여 액세스 그룹 정책을 작성하기 위해 [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) 명령을 사용할 수 있습니다.

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

정책을 정의할 때 플랫폼 역할 및 서비스 역할을 선택해야 합니다.
* 플랫폼 관리 역할은 인스턴스를 작성하고 삭제하며, 별명, 바인딩 및 인증 정보를 관리하고, 액세스를 관리하는 기능을 포함하여 다양한 조치를 수행합니다. 플랫폼 역할은 관리자, 편집자, 운영자, 뷰어입니다. 플랫폼 관리 역할은 계정 관리 서비스에 지정된 역할에 따라 사용자가 사용자를 초대하고 서비스 ID를 관리하며 정책에 액세스하고 항목을 카탈로그화하며 비용 청구와 사용을 추적할 수 있도록 허용하는 계정 관리 서비스에도 적용됩니다.
* 서비스 액세스 역할을 통해서는 사용자나 서비스가 서비스 인스턴스에서 조치를 수행하는 기능을 정의합니다. 서비스 액세스 역할은 관리자, 작성자 및 독자입니다.

{{site.data.keyword.at_full_notm}} 서비스를 관리하려면 사용자에게 다음 역할이 있어야 합니다.
* 플랫폼 역할: **관리자**. 
* 서비스 역할: **관리자**.[자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

UI를 통해 액세스 그룹에 정책을 지정하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 후 **액세스 그룹**을 선택하십시오.
2. 액세스 권한을 지정할 그룹의 이름을 선택하십시오. 
3. **액세스 정책**을 클릭하십시오.
4. **액세스 권한 지정**을 클릭하십시오.
5. 리소스 그룹의 리소스별 또는 계정에서 사용할 수 있는 개별 리소스별로 액세스를 지정하도록 선택하십시오. 예를 들어, 다음 옵션 중 하나를 선택하여 사용자에게 {{site.data.keyword.at_full_notm}}를 관리할 수 있는 관리자 역할을 부여할 수 있습니다.

### 옵션 1. 서비스에 대한 권한 부여
{: #admin_account_opt1}

사용자에게 계정의 {{site.data.keyword.at_full_notm}} 서비스에 대한 관리자 역할을 지정하려면 다음 단계를 완료하십시오. 

1. **리소스에 대한 액세스 권한 지정**을 선택하십시오.
2. **IBM Cloud Activity Tracker with LogDNA**를 선택하십시오.
3. **모든 현재 지역**을 선택하십시오.
4. **모든 현재 서비스 인스턴스**를 선택하십시오.
5. 플랫폼 역할 **관리자**를 선택하십시오.
6. 서비스 역할 **관리자**를 선택하십시오.
7. **지정**을 클릭하십시오.

### 옵션 2. 리소스 그룹의 컨텍스트에 권한 부여
{: #admin_account_opt2}

사용자에게 리소스 그룹의 컨텍스트 내의 {{site.data.keyword.at_full_notm}} 서비스에 대한 관리자 역할을 지정하려면 다음 단계를 완료하십시오. 

1. **리소스 그룹 내의 액세스 권한 지정**을 선택하십시오.
2. 리소스 그룹을 선택하십시오.
3. 사용자에게 선택한 리소스 그룹에 대해 이미 부여된 역할이 없는 경우 **리소스 그룹에 대한 액세스 권한 지정** 필드를 위한 역할을 선택하십시오. 

    선택하는 역할에 따라 사용자가 대시보드에서 리소스 그룹을 보거나, 리소스 그룹 이름을 편집하거나, 그룹에 대한 사용자 액세스 권한을 관리할 수 있습니다. 
    
    사용자가 리소스 그룹의 {{site.data.keyword.at_full_notm}} 서비스에만 액세스할 수 있도록 하려는 경우 **액세스 권한 없음**을 선택할 수 있습니다.

4. **IBM Cloud Activity Tracker with LogDNA**를 선택하십시오.
5. 플랫폼 역할 **관리자**를 선택하십시오.
6. 서비스 역할 **관리자**를 선택하십시오.
7. **지정**을 클릭하십시오.

### 옵션 3. 위치에서 권한 부여
{: #admin_account_opt3}

위치당 {{site.data.keyword.at_full_notm}} 서비스 인스턴스를 하나만 프로비저닝할 수 있습니다. 따라서 이 옵션을 사용하여 권한을 부여할 때 위치당 액세스 권한을 제어합니다.
{: note}

사용자에게 하나의 {{site.data.keyword.at_full_notm}} 서비스 인스턴스에 대한 관리자 역할을 지정하려면 다음 단계를 완료하십시오. 

1. **리소스에 대한 액세스 권한 지정**을 선택하십시오.
2. **IBM Cloud Activity Tracker with LogDNA**를 선택하십시오.
3. 인스턴스를 선택하십시오.
4. 플랫폼 역할 **관리자**를 선택하십시오.
5. 서비스 역할 **관리자**를 선택하십시오.
6. **지정**을 클릭하십시오.



## 3단계. 액세스 그룹에 사용자 또는 서비스 ID 추가
{: #ime_step3}

사용자 또는 서비스 ID를 추가하여 그룹 설정을 계속하십시오.

### 액세스 그룹에 사용자 추가
{: #ime_step3_user}

사용자를 추가하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 후 **액세스 그룹**을 선택하십시오.
2. 액세스 권한을 지정할 그룹의 이름을 선택하십시오. 
3. **사용자** 탭에서 **사용자 추가**를 클릭하십시오.
4. 목록에서 추가할 사용자를 선택하고 **그룹에 추가**를 클릭하십시오.


### 액세스 그룹에 서비스 ID 추가
{: #ime_step3_svcid}

서비스 ID를 추가하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 후 **액세스 그룹**을 선택하십시오.
2. 액세스 권한을 지정할 그룹의 이름을 선택하십시오. 
3. **서비스 ID** 탭을 클릭한 후 **서비스 ID 추가**를 클릭하십시오.
4. 목록에서 추가할 ID를 선택하고 **그룹에 추가**를 클릭하십시오.




