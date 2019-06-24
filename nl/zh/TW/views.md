---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# 建立自訂視圖
{: #views}

透過 {{site.data.keyword.at_full_notm}} Web 使用者介面，您可以套用搜尋和過濾準則，以定義透過自訂視圖顯示的事件。
{:shortdesc}


## 必要條件
{: #views_prereqs}

開始之前，請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。下表列出使用者必須具有的最低角色，才能啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，以及檢視、搜尋及過濾事件：

| 角色                      | 授與的許可權            |
|---------------------------|-------------------------------|  
| 平台角色：`檢視者`     | 容許使用者在「觀察」儀表板中檢視服務實例的清單。|
| 服務角色：`讀者`      | 容許使用者啟動 Web 使用者介面，以及在 Web 使用者介面中檢視事件。|
{: caption="表 1. IAM 角色" caption-side="top"} 

如需如何為使用者配置原則的相關資訊，請參閱[授與使用者對使用者或服務 ID 的許可權](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。



## 步驟 1. 移至 Web 使用者介面並選取視圖
{: #views_step1}

請完成下列步驟：

1. [移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。
2. 按一下**視圖**圖示 ![「配置」圖示](images/views.png)。
3. 選取**所有項目**或視圖。 


## 步驟 2. 套用搜尋查詢來選取要透過視圖顯示的事件集
{: #views_step2}

若要搜尋特定事件，可以套用搜尋查詢。 

* 您可以執行簡式搜尋（單一詞彙字串搜尋）、複合搜尋（多個搜尋詞彙和運算子）、欄位搜尋（如果可以剖析日誌行的話）等。如需相關資訊，請參閱 [LogDNA 文件中的如何搜尋日誌 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://docs.logdna.com/docs/search){:new_window}。
* AND 和 OR 運算子區分大小寫，並且必須為大寫。

只能在透過實例的服務方案所指定天數內搜尋事件。
{: important}


請完成下列步驟：
1. 輸入搜尋查詢。 
2. 按一下 **Enter** 鍵。 

套用查詢時，請注意，視圖名稱會變更為**未保存的視圖**。


### 查詢服務產生的事件
{: #views_step1_1}

若要過濾掉特定服務的事件，需要輸入下列查詢：

```
_supertenant:SERVICENAME
```
{: codeblock}

其中，`SERVICENAME` 是 {{site.data.keyword.cloud_notm}} 中服務的名稱。

下表列出核心服務：

|產生事件者| 值 |查詢範例|
|--------------------------------------------|-------------------------------|----------------------------------|
|[IAM 存取管理服務](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)|`iam-am`|`_supertenant:iam-am`|
| [IAM 身分服務](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)                     |`iam-identity`|`_supertenant:iam-identity`|
|[IAM 存取群組服務](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)|`iam-groups`|`_supertenant:iam-groups`|
|[資源控制器服務](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)|`BSS`|`_supertenant:BSS`|            
{: caption="表 2. 依服務名稱查詢" caption-side="top"}

### 查詢服務產生的事件集
{: #views_step1_2}

服務產生不同類型的事件時，可以輸入下列查詢：

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

其中 

* `SERVICENAME` 是 {{site.data.keyword.cloud_notm}} 中服務的名稱。
* `TYPEOFACTION` 是複合查詢，在其中可以使用 AND 和 OR 運算子，還可以使用 `-` 來排除資料。請注意，`AND` 和 `OR` 運算子區分大小寫，並且必須為大寫。


下表顯示如何查詢服務產生的一組事件的範例：

|產生事件者|事件類型|查詢範例|
|--------------------------------------------|--------------------|---------------------------------|
| `IAM 身分服務`                     |[登入事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)|`_supertenant:iam-identity (action login)`|
| `IAM 身分服務`                     |[API 金鑰事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys)|`_supertenant:iam-identity (action user-apikey) -(action login)`|
| `IAM 身分服務`                     |[帳戶服務 ID 事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids)|`_supertenant:iam-identity (action account-serviceid)`|
| `資源控制器`                      |[佈建和管理服務實例](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)|`_supertenant:BSS (action instance)`| 
| `資源控制器`                      |[管理帳戶中的使用者](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)|`_supertenant:BSS (action user-management.user)`|                   |
{: caption="表 3. 更複雜查詢的範例" caption-side="top"}


### 查詢具有特定動作的事件
{: #views_step1_3}

每個事件都有一個 **action** 欄位，用於通知觸發事件的動作。可以輸入下列查詢來搜尋具有相同動作的所有事件：

```
action ACTIONVALUE
```
{: codeblock}

其中，`ACTIONVALUE` 是 action 欄位的值或值的一部分。

下表顯示針對不同動作的查詢範例：

| 動作                             |查詢範例|
|------------------------|----------------------------------|
|佈建服務|`action instance.create`|
|移除實例|`action instance.delete`|
|新增使用者|`action user-management.user.create`|
{: caption="表 4. 依動作類型進行查詢的範例" caption-side="top"}



### 查詢其動作失敗的事件
{: #views_step1_4}

要求的動作失敗時，**outcome** 欄位會設定為 **failure**。您可以輸入下列查詢，以搜尋這些類型的事件：

```
outcome failure
```
{: codeblock}


### 依事件重要性來查詢
{: #views_step1_5}

每個事件都有一個 **severity** 欄位，用於定義動作可能對雲端產生的威脅層次。 

 有效值為 *normal*、*warning* 及 *critical*。 
* **Normal** 是針對「雲端」中的例行動作而設定的。例如，啟動實例或重新整理記號。 
* **Warning** 是針對更新「雲端」資源或修改其 meta 資料的動作而設定的。例如，更新工作者節點的版本、重新命名憑證或重新命名服務實例。 
* **Critical** 是針對影響「雲端」中安全的動作而設定的。例如，變更使用者的認證、刪除資料、未獲授與使用「雲端」資源的存取權。

您可以輸入下列查詢，以搜尋這些類型的事件：

```
severity VALUE
```
{: codeblock}

其中，`VALUE` 可以設定為 *normal*、*warning* 或 *critical*

例如，若要查詢嚴重事件，可以執行下列查詢：

```
severity critical
```
{: codeblock}



## 步驟 3. 建立自訂視圖
{: #views_step3}

將搜尋查詢套用於**全部**視圖或現有自訂視圖後，請完成下列步驟以將結果另存為自訂視圖：

1. 在 Web 使用者介面中，按一下**未儲存的視圖**。
2. 選取**儲存為新視圖/警示**。*建立新視圖* 頁面即會開啟。
3. 在*名稱* 欄位中輸入視圖的名稱。
4. 選擇性地新增種類。輸入名稱，然後按一下**將此項新增為新的視圖種類**。
5. 選擇性地連接警示。即會顯示一個新區段，供您配置警示。
6. 按一下**儲存視圖**。


## 步驟 4. 自訂如何透過視圖顯示事件行
{: #views_step4}

有不同的選項可自訂在視圖中檢視資料的方式：
* 可以修改視圖的內容，也可以重新命名視圖、新增或修改其說明，以及套用特定行格式。
* 可以在*使用者喜好設定* 區段中變更`日誌格式`。
* 可以在*工具* 區段中套用行範本。請注意，這將置換其他任何行配置。如果選取**持續保存這些設定**，則使用者介面中的所有視圖都將根據此區段中指定的行格式來顯示資料。
* 可以藉由在**工具**區段中設定**強調顯示項目**，將顏色套用於項或字串。



### 透過視圖內容頁面變更行格式
{: #views_step4_1}

請完成下列步驟，以修改單一視圖中事件行的格式：

1. 在您的視圖中，選取**編輯視圖內容**。即會開啟*編輯視圖內容* 頁面。

2. 在**自訂 %LINE 範本**區段中，輸入自訂行格式。預設格式設定為 `{{line}}`。

    如需行範本準則的相關資訊，請參閱[準則](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)。

3. 按一下**儲存內容**。



### 透過使用者喜好設定區段變更行格式
{: #views_step4_2}

在**使用者喜好設定**區段中，您可以修改每行顯示的資料欄位順序。

請完成下列步驟，來修改事件行的格式：

1. 在 Web 使用者介面中，按一下**配置**圖示 ![「配置」圖示](images/admin.png "「管理」圖示")。
2. 選取**使用者喜好設定**。新視窗即會開啟。
3. 選取**日誌格式**。
4. 修改*行格式* 區段，以符合您的需求。拖曳方框。


### 透過工具區段中的行範本變更行格式
{: #views_step4_3}

請完成下列步驟，來修改事件行的格式：

1. 在視圖中，按一下**工具**圖示 ![「工具」圖示](images/tool.png "「工具」圖示")。
2. 在**行範本**欄位中，輸入自訂行格式。如需行範本準則的相關資訊，請參閱[準則](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line)。
3. （選用）按一下**持續保存這些設定**，以將行格式套用至所有視圖。



### 強調顯示項目
{: #view_events_step4_4}

請完成下列步驟，以在視圖中強調顯示項目：

1. 在視圖中，按一下**工具**圖示 ![「工具」圖示](images/tool.png "「工具」圖示")。
2. 在**行範本**欄位的**強調顯示項目**區段中，輸入單字或字串。
3. （選用）按一下**持續保存這些設定**，以將這些設定套用至所有視圖。



## 變更自訂視圖的名稱和說明
{: #views_step5}

可以重新命名視圖。還可以新增或修改視圖的說明。


請完成下列步驟：

1. 在您的視圖中，選取**編輯視圖內容**。即會開啟*編輯視圖內容* 頁面。

    可以重新命名視圖、新增或修改視圖的說明，以及套用自訂行格式。

2. 在**重新命名視圖**區段中，輸入新名稱以重新命名視圖。

3. 在**說明**區段中，輸入或修改說明。

4. 按一下**儲存內容**。



## 定義行範本的準則
{: #views_line}

定義行範本時，請考慮下列必須套用的準則：
* 使用 Mustache 樣式 `{{field.name}}` 或 Bash 樣式 `${field.name}` 變數來建構範本。 
* 使用 `{{line}}` 或 `$@` 來參照原始行。 
* 其他所有字元或字串都會解釋為文字。 


例如，可以將行範本定義為 `{{initiator.id}} -- {{action}} -- {{message}}`，以在視圖中檢視每個事件的這些欄位。


