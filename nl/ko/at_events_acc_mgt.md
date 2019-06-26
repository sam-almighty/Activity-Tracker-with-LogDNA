---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# 계정 관리 이벤트  
{: #at_events_acc_mgt}

보안 담당자, 감사자 또는 관리자는 {{site.data.keyword.at_full_notm}} 계정을 사용하여 사용자와 애플리케이션이 {{site.data.keyword.cloud_notm}} 서비스와 상호작용하는 방식을 추적할 수 있습니다.
{:shortdesc}

{{site.data.keyword.at_full_notm}} 서비스는 {{site.data.keyword.cloud_notm}} 내 서비스의 상태를 변경하는 사용자 시작 활동을 기록합니다. 시작하려면 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started) 페이지를 참조하십시오. 



## 계정 관리 이벤트
{: #at_events_acc_mgt_account}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                               |설명 |
|--------------------------------------|-------------|
| `billing.account.create`             | 계정 ID를 계정에 지정한 후 계정을 프로비저닝할 때 이벤트가 생성됩니다. |
| `billing.account.update`             | 계정에 관한 정보를 업데이트할 때 이벤트가 생성됩니다. |
| `billing.account.active`             | 계정을 확인할 때 이벤트가 생성됩니다. 즉, 계정이 활성이 되면 이벤트가 생성됩니다. |
| `billing.account.subscription.create` | <a href="/docs/account?topic=account-accounts#subscription-account">구독 계정</a>을 작성할 때 이벤트가 생성됩니다. |
{: caption="표 1. 이벤트를 생성하는 조치" caption-side="top"} 




## 사용자 관리 이벤트
{: #at_events_acc_mgt_users}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                               |설명 |
|--------------------------------------|-------------|
| `user-management.user.create`        | 계정에 가입하도록 사용자에게 초대를 보낼 때 이벤트가 생성됩니다. |
| `user-management.user.active`        | 계정에서 사용자를 활성화하면 이벤트가 생성됩니다. 사용자가 이메일 주소를 확인하면 이벤트가 생성됩니다. |
| `user-management.user.delete`        | 계정에서 사용자를 제거하면 이벤트가 생성됩니다. |
{: caption="표 2. 이벤트를 생성하는 조치" caption-side="top"} 




## 조직 관리 이벤트
{: #at_events_acc_mgt_org}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                               |설명 |
|--------------------------------------|-------------|
| `billing.account.org.create`         | 계정에 조직을 추가할 때 이벤트가 생성됩니다. |
{: caption="표 3. 이벤트를 생성하는 조치" caption-side="top"} 


## 태그 관리 이벤트
{: #at_events_acc_mgt_resources}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치                               |설명 |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | 리소스에 태그를 추가할 때 이벤트가 생성됩니다. |
| `ghost-tags.tag.detach-tag`          | 리소스에서 태그를 제거할 때 이벤트가 생성됩니다. |
{: caption="표 4. 이벤트를 생성하는 조치" caption-side="top"} 


## 이벤트 검색 위치
{: #at_events_acc_mgt_ui}

이벤트는 **프랑크푸르트(eu-de)** 지역에서 사용할 수 있습니다. 

해당 이벤트를 보려면 **프랑크푸르트(eu-de)** 지역에 {{site.data.keyword.at_full_notm}} 서비스의 [인스턴스를 프로비저닝](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)해야 합니다.
그런 다음 [{{site.data.keyword.at_full_notm}} UI를 열어야 합니다](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 












