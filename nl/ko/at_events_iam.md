---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# IAM 이벤트
{: #at_events_iam}

보안 담당자, 감사자 또는 관리자는 {{site.data.keyword.at_full_notm}} 서비스를 사용하여 사용자 및 애플리케이션이 {{site.data.keyword.cloud_notm}}의 {{site.data.keyword.iamlong}}(IAM) 서비스와 상호작용하는 방식을 추적할 수 있습니다.
{:shortdesc}

{{site.data.keyword.at_full_notm}} 서비스는 {{site.data.keyword.cloud_notm}} 내 서비스의 상태를 변경하는 사용자 시작 활동을 기록합니다. 사용자 조치의 모니터링을 시작하려면 [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)의 내용을 참조하십시오. 

개시자는 사용자, 서비스 또는 애플리케이션일 수 있습니다.
{: tip}

## 액세스 그룹 이벤트 관리
{: #at_events_iam_access}

다음 표에는 이벤트를 생성하는 조치가 나열되어 있습니다.

|조치 |설명 |
|----------|---------|
|`iam-groups.group.create`   |개시자가 액세스 그룹을 작성할 때 이벤트가 생성됩니다. | 
|`iam-groups.group.read`     |개시자가 액세스 그룹과 관련된 정보를 볼 때 이벤트가 생성됩니다. |
|`iam-groups.group.update`   |개시자가 그룹 이름 또는 설명을 업데이트할 때 이벤트가 생성됩니다. |
|`iam-groups.group.delete`   |개시자가 액세스 그룹을 삭제할 때 이벤트가 생성됩니다. |
|`iam-groups.member.add`     |개시자가 액세스 그룹에 구성원을 추가할 때 이벤트가 생성됩니다. |
|`iam-groups.member.delete`  |개시자가 액세스 그룹에서 구성원을 제거할 때 이벤트가 생성됩니다. |
|`iam-groups.member.read`    |개시자가 구성원의 멤버십을 확인할 때 이벤트가 생성됩니다. |
|`iam-groups.rule.read`      |개시자가 액세스 그룹의 규칙을 볼 때 이벤트가 생성됩니다. |
|`iam-groups.rule.create`    |개시자가 액세스 그룹에 규칙을 추가할 때 이벤트가 생성됩니다. |
|`iam-groups.rule.update`    |개시자가 규칙 이름을 수정할 때 이벤트가 생성됩니다. |
|`iam-groups.rule.delete`    |개시자가 액세스 그룹에서 규칙을 제거할 때 이벤트가 생성됩니다. |
{: caption="표 1. 액세스 그룹 조치 관리" caption-side="top"} 




## 이벤트 보기
{: #at_events_iam_ui}

이벤트는 **미국 남부** 지역에서 사용할 수 있습니다. 

이러한 이벤트를 보려면 **미국 남부** 지역에 {{site.data.keyword.at_full_notm}} 서비스의 [인스턴스를 프로비저닝](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision)해야 합니다. 그런 다음 [{{site.data.keyword.at_full_notm}} UI를 열어야 합니다](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


