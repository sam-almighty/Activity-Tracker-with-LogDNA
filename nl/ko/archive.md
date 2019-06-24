---

copyright:
  years: 2019
lastupdated: "2019-05-01"

keywords: IBM Cloud, LogDNA, Activity Tracker, archive logs, COS, cloud object storage

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

 
# IBM Cloud Object Storage에 이벤트 아카이브
{: #archiving}

{{site.data.keyword.at_full_notm}} 인스턴스의 이벤트를 {{site.data.keyword.cos_full_notm}}(COS) 인스턴스의 버킷으로 아카이브할 수 있습니다. 
{:shortdesc}

{{site.data.keyword.at_full_notm}} 인스턴스를 {{site.data.keyword.cos_full_notm}} 인스턴스의 버킷에 아카이브하려면 다음 단계를 완료하십시오.

## 전제조건
{: #archiving_prereqs}

* [이벤트 아카이브에 관해 자세히 보십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-manage_events#manage_events_archive).

* {{site.data.keyword.at_full_notm}} 서비스에 대한 **유료 서비스 플랜이 있어야 합니다**. [자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 

* 사용자 ID에 웹 UI를 실행하고 이벤트를 관리할 수 있는 권한이 있는지 확인하십시오. 다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI를 실행하며 이벤트를 보고, 검색하고, 필터링하기 위해 보유해야 하는 최소 역할이 나열되어 있습니다.

|역할                      |부여되는 권한            |
|---------------------------|-------------------------------|  
|플랫폼 역할: `뷰어`     |사용자가 관찰 가능성 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
| 서비스 역할: `Manager`      | 사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 관리할 수 있도록 허용합니다. |
{: caption="표 1. IAM 역할" caption-side="top"} 

사용자에 맞게 정책을 구성하는 방법에 대한 자세한 정보는 [사용자 또는 서비스 ID에 사용자 권한 부여](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)를 참조하십시오.



## 1단계. {{site.data.keyword.cos_full_notm}}에 대해 작업할 수 있도록 사용자에게 IAM 정책 부여
{: #archiving_step1}

**참고:** {{site.data.keyword.cloud_notm}}의 {{site.data.keyword.cos_full_notm}} 서비스 관리자 또는 계정 소유자가 이 단계를 완료해야 합니다.

{{site.data.keyword.cos_full_notm}} 서비스의 관리자는 서비스 인스턴스를 프로비저닝하고, 다른 사용자에게 이러한 인스턴스에 대해 작업할 수 있는 권한을 부여하고, 서비스 ID를 작성할 수 있어야 합니다. 

사용자에게 {{site.data.keyword.cos_full_notm}} 서비스의 편집자가 될 수 있는 권한을 부여할 수 있는 여러 가지 방법이 있습니다.

* 계정의 서비스 관리자인 사용자는 플랫폼 역할이 *관리자*인 {{site.data.keyword.cos_full_notm}} 서비스에 대한 IAM 정책을 보유해야 합니다. 계정의 개별 리소스에 이 사용자 액세스 권한을 지정해야 합니다. 

* 리소스 그룹의 컨텍스트 내에 있는 서비스의 관리자인 사용자는 리소스 그룹의 컨텍스트 내에서 플랫폼 역할이 *관리자*인 {{site.data.keyword.cos_full_notm}} 서비스에 대한 IAM 정책을 보유해야 합니다. 


다음 표에는 {{site.data.keyword.cos_full_notm}} 서비스에 대해 나열된 조치를 완료하기 위해 보유할 수 있는 역할이 나열되어 있습니다.

|서비스                    |플랫폼 역할    |조치                                                                                        | 
|----------------------------|-------------------|-----------------------------------------------------------------------------------------------|       
|`Cloud Object Storage`     |관리자     |사용자가 {{site.data.keyword.cos_full_notm}} 서비스에 대해 작업할 수 있도록 계정의 사용자에게 정책을 지정할 수 있게 합니다. |
|`Cloud Object Storage`     | 관리자 </br>편집자                            |사용자가 {{site.data.keyword.cos_full_notm}} 서비스의 인스턴스를 프로비저닝할 수 있게 합니다.    |
|`Cloud Object Storage`     | 관리자 </br>편집자 </br>운영자 |사용자가 서비스 ID를 작성할 수 있게 합니다.    | 
{: caption="표 1.역할 및 조치" caption-side="top"} 


사용자에게 리소스 그룹의 컨텍스트 내의 {{site.data.keyword.cos_full_notm}} 서비스에 대한 관리자 역할을 지정하려면 다음 단계를 완료하십시오. 

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	사용자 ID 및 비밀번호를 사용하여 로그인하면 {{site.data.keyword.cloud_notm}} UI가 열립니다.
    
2. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 후 **사용자**를 선택하십시오.
3. 액세스 권한을 지정할 사용자에 대한 행에서 **조치** 메뉴를 선택한 후 **액세스 권한 지정**을 클릭하십시오.
4. **리소스 그룹 내의 액세스 권한 지정**을 선택하십시오.
5. 리소스 그룹을 선택하십시오.
6. 사용자에게 선택한 리소스 그룹에 대해 이미 부여된 역할이 없는 경우 **리소스 그룹에 대한 액세스 권한 지정** 필드를 위한 역할을 선택하십시오. 

    선택하는 역할에 따라 사용자가 대시보드에서 리소스 그룹을 보거나, 리소스 그룹 이름을 편집하거나, 그룹에 대한 사용자 액세스 권한을 관리할 수 있습니다. 
    
    사용자가 리소스 그룹의 {{site.data.keyword.at_full_notm}} 서비스에만 액세스할 수 있도록 하려는 경우 **액세스 권한 없음**을 선택할 수 있습니다.

7. **Cloud Object Storage**를 선택하십시오.
8. 플랫폼 역할 **관리자**를 선택하십시오.
9. **지정**을 클릭하십시오.



## 2단계. {{site.data.keyword.cos_full_notm}} 인스턴스 프로비저닝
{: #archiving_step2}

**참고:** {{site.data.keyword.cloud_notm}}의 {{site.data.keyword.cos_full_notm}} 서비스 편집자 또는 관리자가 이 단계를 완료해야 합니다. 
{{site.data.keyword.cos_full_notm}} 인스턴스를 프로비저닝하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **카탈로그**를 클릭하십시오. {{site.data.keyword.cloud_notm}}에서 사용 가능한 서비스 목록이 열립니다.

2. 표시되는 서비스 목록을 필터링하려면 **스토리지** 카테고리를 선택하십시오.

3. **Object Storage** 타일을 클릭하십시오.

4. 서비스 인스턴스의 이름을 입력하십시오.

5. 리소스 그룹을 선택하십시오. 

    기본적으로 **default** 리소스 그룹이 설정됩니다.

6. 서비스 플랜을 선택하십시오. 

    기본적으로 **Lite** 플랜이 설정됩니다.

7. **작성**을 클릭하십시오.



## 3단계. 버킷 작성
{: #archiving_step3}

버킷은 {{site.data.keyword.cos_full_notm}} 인스턴스에서 데이터를 구성하는 방법입니다. 

버킷을 관리하려면 사용자에게 {{site.data.keyword.cos_full_notm}} 인스턴스의 버킷에 대해 작업할 수 있는 권한이 부여되어야 합니다. 다음 표에는 사용자가 버킷에 대해 작업하기 위해 보유할 수 있는 여러 조치 및 역할에 대해 설명되어 있습니다.

|서비스                    |역할                   |조치                             | 
|----------------------------|-------------------------|------------------------------------|       
|`Cloud Object Storage`     |플랫폼 역할: 뷰어   | 사용자가 모든 버킷을 보고 해당 버킷에 있는 오브젝트를 나열할 수 있습니다. |
|`Cloud Object Storage`     |서비스 역할: 관리자   |사용자가 오브젝트를 공용으로 설정할 수 있도록 허용합니다.                                                       |
|`Cloud Object Storage`     | 서비스 역할: 관리자 </br>작성자 |사용자가 버킷 및 오브젝트를 작성하고 영구 삭제할 수 있도록 허용합니다.                         | 
|`Cloud Object Storage`     |서비스 역할: 독자    |사용자가 오브젝트를 나열하고 다운로드할 수 있도록 허용합니다.                                                 |
{: caption="표 1. 버킷에 대해 작업하기 위한 역할 및 조치" caption-side="top"} 

**참고:** 버킷을 작성하려면 사용자에게 {{site.data.keyword.cos_full_notm}} 인스턴스에 대한 관리자 또는 작성자 권한이 있어야 합니다.

버킷을 작성하려면 다음 단계를 완료하십시오.

1. 탐색 메뉴에서 **리소스 목록**을 선택하십시오.

2. 버킷을 작성할 {{site.data.keyword.cos_full_notm}} 인스턴스를 선택하십시오.

3. **버킷**을 선택하십시오. 그런 다음 **버킷 작성**을 클릭하십시오.

4. *고유 버킷 이름* 필드에 버킷 이름을 입력하십시오.

    **참고:** 전 세계 모든 지역의 모든 버킷이 단일 네임스페이스를 공유합니다. 

    {{site.data.keyword.at_full_notm}} 인스턴스 이름을 버킷 이름의 일부로 사용할 수 있습니다. 예를 들어, 이름이 *logdna-1*인 인스턴스의 경우 *accountN-logdna-1*을 버킷 이름으로 사용할 수 있습니다.

    {{site.data.keyword.at_full_notm}} 웹 UI를 통해 아카이브를 구성하려면 이 이름이 필요합니다.

5. 복원성 유형과 데이터가 실제로 저장될 위치를 선택하십시오.

    복원성은 데이터가 분배되는 지리적 영역의 범위와 규모를 나타냅니다. 
    
    교차 지역 복원성은 여러 대도시 영역에 데이터를 분산시킵니다.
    
    지역 복원성은 하나의 대도시 영역에 데이터를 분산시킵니다. 
    
    단일 데이터 센터는 단일 사이트 내의 디바이스에만 데이터를 분배합니다.

    자세한 정보는 [지역 및 엔드포인트 선택](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints)을 참조하십시오.

6. *스토리지 클래스*의 유형을 선택하십시오.

    여러 스토리지 클래스로 버킷을 작성할 수 있습니다. 요구사항에 따라 버킷에 대한 스토리지 클래스를 선택하여 데이터를 검색하십시오. 자세한 정보는 [스토리지 클래스 사용](/docs/services/cloud-object-storage?topic=cloud-object-storage-classes)을 참조하십시오.

    **참고:** 일단 버킷이 작성되면 버킷의 스토리지 클래스를 변경할 수 없습니다. 오브젝트가 다시 분류되어야 하는 경우 원하는 스토리지 클래스가 있는 다른 버킷으로 데이터를 이동해야 합니다.

7. 선택적으로 Key Protect 키를 추가하여 저장 데이터를 암호화하십시오.

    기본적으로 모든 오브젝트는 랜덤으로 생성된 키와 AONT(All-or-Nothing Transform)를 사용하여 암호화됩니다. 이 기본 암호화 모델이 저장 데이터 보안을 제공하지만 일부 워크로드는 사용되는 암호화 키를 보유해야 합니다. 자세한 정보는 [암호화 관리](/docs/services/cloud-object-storage?topic=cloud-object-storage-encryption)를 참조하십시오.




## 4단계. {{site.data.keyword.cos_full_notm}} 인스턴스에 대한 서비스 ID 작성
{: #archiving_step4}

서비스 ID는 사용자 ID가 사용자를 식별하는 방법과 유사한 서비스를 식별합니다. 서비스 ID는 특정 사용자와 연결되어 있지 않습니다. 서비스 ID를 작성하는 사용자가 조직을 떠나고 계정에서 삭제되는 경우에도 서비스 ID는 그대로 유지됩니다.

{{site.data.keyword.cos_full_notm}} 인스턴스에 대한 서비스 ID를 작성해야 합니다. 이 서비스 ID는 {{site.data.keyword.at_full_notm}} 인스턴스에서 {{site.data.keyword.cos_full_notm}} 인스턴스를 인증하는 데 사용됩니다. 

특정 서비스를 사용하기 위해 권한을 제한하거나 여러 서비스에 액세스하기 위해 권한을 결합하는 특정 액세스 정책을 서비스 ID에 지정해야 합니다. 예를 들어, 단일 버킷으로 액세스를 제한하려면 콘솔 또는 CLI를 사용하여 서비스 ID에 인스턴스 레벨 정책이 없는지 확인하십시오.


{{site.data.keyword.cos_full_notm}} 인스턴스에 대한 쓰기 권한이 있는 서비스 ID를 작성하려면 다음 단계를 완료하십시오.

1. 대시보드에서 버킷을 작성할 {{site.data.keyword.cos_full_notm}} 인스턴스를 선택하십시오.

2. **서비스 인증 정보**를 선택하십시오. 그런 다음 **새 인증 정보**를 선택하십시오.

3. 인식하기 쉬운 이름을 입력하십시오. 예를 들어, 서비스 ID의 이름을 `activity-tracker-cos-serviceID`로 지정할 수 있습니다. 

4. **작성자** 역할을 선택하십시오.

5. **추가**를 클릭하십시오.

    새 서비스 ID가 작성되어 목록에 추가됩니다. 

    **참고:** {{site.data.keyword.cloud_notm}}에서 작성되고 IAM UI를 통해 나열되는 서비스 ID에는 일반 이름이 있습니다. IAM UI의 서비스 ID 이름은 이 단계에서 COS 서비스 ID UI를 통해 작성한 **iam_apikey_name** 필드의 값에 맵핑됩니다.
    
6. [선택사항] 서비스 ID를 삭제하지 못하도록 잠그려면 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하십시오. 서비스 ID를 검색하십시오. 그런 다음 **잠금** 조치를 선택하십시오.


방금 작성한 서비스 ID에 대해 **인증 정보 보기**를 클릭하십시오. 서비스 ID와 관련된 정보를 볼 수 있습니다. 

* API 키를 복사하십시오. 이는 **apikey** 필드에 설정된 값입니다.
* 리소스 인스턴스 ID를 복사하십시오. 이는 **resource_instance_id** 필드에 설정된 값입니다.
* **iam_apikey_name** 필드의 값을 복사하십시오.


## 5단계. 버킷에 대한 쓰기 권한만 보유하도록 서비스 ID 제한
{: #archiving_step5}

버킷에 대한 쓰기 권한만 보유하도록 서비스 ID를 제한하려면 다음 단계를 완료하십시오.

1. COS UI에서 버킷을 선택하십시오.

2. 버킷 메뉴에서 **정책**을 선택하십시오. *버킷 액세스 정책* 페이지가 열립니다.

3. **서비스 ID**를 선택하십시오.

4. **서비스 ID 선택** 필드에서 이름이 **auto-generated-serviceId-<iam_apikey_name 값의 일부인 ID>인 서비스 ID를 찾으십시오.

5. 서비스 ID를 선택하십시오. 그런 다음 **액세스 정책**에서 **작성자**를 선택하십시오.

6. **액세스 정책 작성**을 클릭하십시오.



## 6단계. 엔드포인트 선택
{: #archiving_step6}

엔드포인트는 버킷을 찾을 위치를 정의합니다. 지역 및 복원성 유형에 따라 여러 엔드포인트가 있습니다. 자세한 정보는 [지역 및 엔드포인트 선택](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints)을 참조하십시오.

버킷에 대한 엔드포인트를 얻으려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.cloud_notm}} 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에 로그인하십시오](https://cloud.ibm.com/login){:new_window}.

	로그인하면 {{site.data.keyword.cloud_notm}} 대시보드가 열립니다.

2. 대시보드에서 버킷을 작성할 {{site.data.keyword.cos_full_notm}} 인스턴스를 선택하십시오.

3. **버킷**을 선택하십시오. 그런 다음 이벤트를 아카이브할 작성한 버킷을 선택하십시오.

4. **구성**을 선택하십시오.

5. 사설 엔드포인트 중 하나를 복사하십시오. 



## 7단계. 이벤트를 아카이브할 수 있도록 사용자에게 IAM 정책 부여
{: #archiving_step7}

다음 표에는 사용자가 {{site.data.keyword.at_full_notm}} 웹 UI에서 이벤트를 {{site.data.keyword.cos_full_notm}} 인스턴스의 버킷으로 아카이브하도록 구성하기 위해 보유해야 하는 정책이 나열되어 있습니다.

|서비스                              |역할                      |부여되는 권한                  | 
|--------------------------------------|---------------------------|-------------------------------------|  
| `{{site.data.keyword.at_full_notm}}` |플랫폼 역할: 뷰어     |사용자가 관찰 가능성 로깅 대시보드에서 서비스 인스턴스 목록을 볼 수 있도록 허용합니다. |
| `{{site.data.keyword.at_full_notm}}` |서비스 역할: 관리자     |사용자가 웹 UI를 실행하고 웹 UI에서 이벤트를 볼 수 있도록 허용합니다.                             |
{: caption="표 2. IAM 정책" caption-side="top"} 

[자세히 보기](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

사용자에게 이벤트를 아카이브할 수 있는 권한을 지정하려면 다음 단계를 완료하십시오. 

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 후 **사용자**를 선택하십시오.
2. 액세스 권한을 지정할 사용자에 대한 행에서 **조치** 메뉴를 선택한 후 **액세스 권한 지정**을 클릭하십시오.
3. **리소스 그룹 내의 액세스 권한 지정**을 선택하십시오.
4. 리소스 그룹을 선택하십시오.
5. 사용자에게 선택한 리소스 그룹에 대해 이미 부여된 역할이 없는 경우 **리소스 그룹에 대한 액세스 권한 지정** 필드를 위한 역할을 선택하십시오. 

    선택하는 역할에 따라 사용자가 대시보드에서 리소스 그룹을 보거나, 리소스 그룹 이름을 편집하거나, 그룹에 대한 사용자 액세스 권한을 관리할 수 있습니다. 
    
    사용자가 리소스 그룹의 {{site.data.keyword.at_full_notm}} 서비스에만 액세스할 수 있도록 하려는 경우 **액세스 권한 없음**을 선택할 수 있습니다.

6. **IBM Log Analysis with LogDNA**를 선택하십시오.
7. 플랫폼 역할 **뷰어**를 선택하십시오.
8. 서비스 역할 **관리자**를 선택하십시오.
9. **지정**을 클릭하십시오.



## 8단계. {{site.data.keyword.at_full_notm}} 인스턴스에 대한 아카이브 구성
{: #archiving_step8}


{{site.data.keyword.at_full_notm}} 인스턴스를 COS 버킷에 아카이브하도록 구성하려면 다음 단계를 완료하십시오.

1. [{{site.data.keyword.at_full_notm}} 웹 UI를 실행하십시오](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch).

2. **구성** 아이콘을 선택하십시오 그런 다음 **아카이브**를 선택하십시오. 

3. **IBM Cloud Object Storage**를 선택하십시오.

4. 이벤트가 아카이브될 버킷, 엔드포인트, API 키 및 인스턴스 ID를 설정하십시오.

    <table>
      <caption>표 3. COS 필드</caption>
      <tr>
         <th>필드</th>
         <th>값</th>
      </tr>
      <tr>
         <td>버킷</td>
         <td>COS 버킷 이름으로 설정하십시오. </td>
      </tr>
      <tr>
         <td>엔드포인트</td>
         <td>COS 버킷 사설 엔드포인트로 설정하십시오.</td>
      </tr>
      <tr>
         <td>API 키</td>
         <td>COS 서비스 ID와 연관된 API 키로 설정하십시오.</td>
      </tr>
      <tr>
         <td>인스턴스 ID</td>
         <td>COS 인스턴스 ID로 설정하십시오. </td>
      </tr>
    </table>

5. **저장**을 클릭하십시오.


구성을 저장하면 이벤트가 하루에 한 번 아카이브됩니다.



