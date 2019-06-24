---

copyright:
  years: 2019
lastupdated: "2019-04-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, event fields

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



# 事件欄位
{: #event}

{{site.data.keyword.at_full_notm}} 事件是以「雲端審核資料聯盟 (CADF)」標準為基礎。
{:shortdesc}

## 起始者欄位
{: #initiator}

下表列出可供 {{site.data.keyword.at_full_notm}} 事件使用的一般欄位：

| 欄位名稱 | 說明 | 值 |
|------------|-------------|-------|
| `initiator.id` | 動作起始者的 ID。</br></br>起始者的有效類型為 `IBM ID`、`服務 ID` 及 `Cloud Foundry (CF) 使用者 ID`。|IBM ID 的範例為 `IBMid-000000XXX2` </br>服務 ID 的範例為 `iam-ServiceId-12345678-0165-4c89-847d-9660b1632e14` </br> CF 使用者 ID 的範例為 `7666666b-23ae-4a34-8569-cu75tgdr4da3`|
| `initiator.name` | 起始動作之使用者的使用者名稱。| 例如，電子郵件位址。|
| `initiator.typeURI` | 事件來源的類型。| 有效值為 *service/security/account/user*、*service/security/clientid* 及 *service/security/account/serviceid*。|
| `initiator.credential.type` | 起始者 ID 認證的類型。| 有效值為 *user*、*token* 及 *apikey*。|
{: caption="表 1. 一般起始者欄位" caption-side="top"} 

  

## 目標欄位
{: #target}

下表列出可供 {{site.data.keyword.at_full_notm}} 事件使用的一般目標欄位：

| 欄位名稱 | 說明 | 值 |
|------------|-------------|-------|
| `target.id` | 執行動作所在資源的「雲端資源名稱 (CRN)」。</br>如需相關資訊，請參閱 [CRN 格式](/docs/overview?topic=overview-crn#format-crn)。| 例如，`crn:v1:bluemix:public:cloud-object-storage:global:a/12345678e6232019c6567c9123456789:fr56et47-befb-440a-a223c-12345678dae1:bucket:bucket1` |
| `target.name` | 執行動作所在雲端資源的人類可讀名稱。|  |
| `target.typeURI` | 執行動作所在雲端資源的類型。</br>此欄位的格式為 **serviceName/objectType**，其中 `servicename` 是服務的名稱。| 例如，`iam-am/policy` 或 `cloud-object-storage/bucket/acl` |
{: caption="表 2. 一般目標欄位" caption-side="top"} 


 
## 動作欄位
{: #action}

下表列出可供 {{site.data.keyword.at_full_notm}} 事件使用的一般動作欄位：

| 欄位名稱 | 說明 | 值 |
|------------|-------------|-------|
| `action` | 觸發事件的動作。</br>此欄位的格式為 **serviceName.objectType.action**，其中 `servicename` 是服務的名稱。</br>如需服務所產生事件的動作值的相關資訊，請參閱<a href="/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#cloud_services">雲端服務</a>| 例如，`iam-identity.serviceid-apikey.login` |
| `eventTime` | 指出建立事件的時間戳記。</br>該日期以世界標準時間 (UTC) 來代表。</br>格式符合 ISO 8601。| 例如，`2017-10-19T19:07:50.32+0000` |
{: caption="表 3. 一般動作欄位" caption-side="top"} 



## 結果欄位
{: #outcomes}

下表列出可供 {{site.data.keyword.at_full_notm}} 事件使用的一般結果欄位：

| 欄位名稱 | 說明 | 值 |
|------------|-------------|-------|
| `outcome` | 動作的結果。| 有效值為 *success*、*failure* 及 *pending*。|
| `reason.reasonCode` | 包括 HTTP 回應碼的數值欄位。| 例如，*200* 表示結果成功。|
| `severity` | 定義動作可能對「雲端」構成的威脅層次。| 有效值為 *normal*、*warning* 及 *critical*。</br></br>**Normal** 是針對「雲端」中的例行動作而設定的。例如，啟動實例或重新整理記號。</br></br>**Warning** 是針對更新「雲端」資源或修改其 meta 資料的動作而設定的。例如，更新工作者節點的版本、重新命名憑證或重新命名服務實例。</br></br>**Critical** 是針對影響「雲端」中安全的動作而設定的。例如，變更使用者的認證、刪除資料、未獲授與使用「雲端」資源的存取權。|
{: caption="表 4. 一般結果欄位" caption-side="top"} 


