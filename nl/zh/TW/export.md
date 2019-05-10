---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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

 
# 匯出事件
{: #export}

您可以將 JSONL 格式中的資料從 {{site.data.keyword.at_full_notm}} 實例匯出至本端檔案。也可以透過程式設計方式，或從 IBM Log Analysis Web 使用者介面匯出日誌。
{:shortdesc}

匯出日誌資料時，請考量下列資訊：
* 您可以匯出一組事件項目。若要定義您想要匯出的資料集，您可以套用過濾器並搜尋。也可以指定時間範圍。 
* 從 Web 使用者介面中，當您匯出事件時，您會取得傳送至電子郵件位址的電子郵件，隨附一個包含資料之壓縮檔的鏈結。若要取得資料，您必須按一下該鏈結，然後下載壓縮檔。
* 以程式設計方式匯出事件時，您可以選擇傳送電子郵件，或將其中的事件串流至您的終端機。
* 包含您要匯出之資料的壓縮檔，可用時間最多 48 小時。 
* 您可以匯出的行數上限是 10,000 行。



## 必要條件
{: #export_prereqs}

開始之前，請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。然後，[移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。

**附註：**您必須是 {{site.data.keyword.at_full_notm}} 服務的管理者、{{site.data.keyword.at_full_notm}} 實例的管理者，或具有帳戶 IAM 許可權，才能管理原則。

下表列出使用者必須具有的最低原則，才能啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，以及檢視、搜尋及過濾事件：

| 角色                      | 授與的許可權            |
|---------------------------|-------------------------------|  
| 平台角色：`檢視者`     | 容許使用者在「觀察」儀表板中檢視服務實例的清單。|
| 服務角色：`讀者`      | 容許使用者啟動 Web 使用者介面，以及在 Web 使用者介面中檢視事件。|
{: caption="表 1. IAM 原則" caption-side="top"} 

如需如何為使用者配置這些原則的相關資訊，請參閱[授與使用者對使用者或服務 ID 的許可權](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。

您必須對 {{site.data.keyword.at_full_notm}} 服務**具有付費服務方案**。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。 



## 步驟 1. 移至 Web 使用者介面
{: #export_step1}

[移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## 步驟 2. 建立視圖
{: #export_step2}

[建立視圖](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md)。


## 步驟 3. 匯出資料
{: #export_step3}

請選擇下列其中一個選項來匯出事件：

### 選項 1. 從 Web 使用者介面匯出事件
{: #export_ui}

請完成下列步驟來匯出資料：

1. 按一下**視圖**圖示 ![「配置」圖示](images/views.png)。
2. 選取**所有項目**或視圖。
3. 套用時間範圍、過濾器及搜尋準則，直到您看到要匯出的項目為止。
4. 如果是從**所有項目**視圖開始，請按一下**未儲存的視圖**。如果已在前一個步驟中選取視圖，請按一下您的視圖名稱。
5. 選取**匯出行**。新視窗即會開啟。
6. 檢查時間範圍。如果您需要變更它，請按一下*變更匯出時間範圍* 欄位中預先定義的時間範圍。
7. 如果匯出要求超出了行的限制，請選取**偏好較新的行**或**偏好較舊的行**。
8. 檢查您的電子郵件。您會從 **LogDNA** 收到一封電子郵件，隨附的鏈結可用來下載您已匯出的行。


### 選項 2. 使用 API 以程式設計方式匯出事件
{: #export_api}

請完成下列步驟，以程式設計方式匯出資料：

1. 產生「服務金鑰」。 

    **附註：**您必須具有**管理員**角色，{{site.data.keyword.at_full_notm}} 實例或服務才能完成此步驟。

    1. 啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面。如需相關資訊，請參閱[移至 {{site.data.keyword.at_full_notm}} Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2)。

    2. 選取**配置**圖示 ![「配置」圖示](images/admin.png)。然後，選取**組織**。 

    3. 選取 **API 金鑰**。

        您可以看到所建立的服務金鑰。 

    4. 按一下**產生服務金鑰**。

        這時會在清單中新增一個新的金鑰。請複製此金鑰。

2. 匯出事件。請執行下列 cURL 指令：

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    其中 

    * ENDPOINT 代表服務的進入點。每一個地區都有不同的 URL。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints)。
    * QUERY_PARAMETERS 是定義套用至匯出要求之過濾準則的參數。
    * SERVICE_KEY 是您在前一個步驟中建立的服務金鑰。

下表列出您可以設定的查詢參數：

| 查詢參數 | 類型       | 狀態     | 說明 |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | 必要   | 開始時間。設為 UNIX 時間戳記（以秒或毫秒為單位）。|
| `to`        | `int32`      | 必要   | 結束時間。設為 UNIX 時間戳記（以秒或毫秒為單位）。|
| `size`      | `string`     | 選用   | 要併入匯出中的日誌行數。  | 
| `hosts`     | `string`     | 選用   | 以逗點區隔的主機清單。|
| `apps`      | `string`     | 選用   | 以逗點區隔的應用程式清單。|
| `levels`    | `string`     | 選用   | 以逗點區隔的記載層次清單。|
| `query`     | `string`     | 選用   | 搜尋查詢。如需相關資訊，請參閱[搜尋日誌](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6)。|
| `prefer`    | `string`     | 選用   | 定義您要匯出的日誌行。有效值為 `head`（第一個日誌行）及 `tail` (最後一個日誌行）。如果未指定，則預設為 tail。|
| `email`     | `string`     | 選用   | 指定電子郵件，其中具有可下載您匯出項目的鏈結。依預設，會串流日誌行。|
| `emailSubject` | `string`     | 選用   | 用來設定電子郵件的主旨。</br>使用 `%20` 來代表空格。例如，範例值為 `Export%20logs`。|
{: caption="查詢參數" caption-side="top"} 

例如，若要將事件串流至終端機，您可以執行下列指令：

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

若要傳送電子郵件，其隨附的鏈結可用來下載在匯出時指定的事件，您可以執行下列指令：

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


若要傳送電子郵件與自訂主旨，您可以執行下列指令：

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

