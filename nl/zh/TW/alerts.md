---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# 配置警示
{: #alerts.md}

透過 {{site.data.keyword.at_full_notm}} Web 使用者介面，您可以套用搜尋和過濾準則，以定義透過自訂視圖顯示的事件。然後，您可以將警示連接至要通知的視圖。您可以將一個以上的警示連接至一個視圖。您可以為一個警示定義多個通知頻道。您可以將警示靜音。也可以從視圖分離警示。
{:shortdesc}


您可以針對警示配置下列任何條件： 

* *時間頻率*：指定觸發警示的頻率。有效值為：30 秒、1 分鐘、5 分鐘、15 分鐘、30 分鐘、1 小時、6 小時、12 小時、24 小時
* *事件行計數器*：指定符合視圖過濾及搜尋準則的事件行數目。當達到事件行數目時，就會觸發警示。

您可以決定檢查這兩個條件，或只檢查一個條件。如果兩個條件都已設定，則會在達到任何臨界值時觸發警示。 

例如，您可以配置在 30 秒之後觸發的警示，或在收集了符合視圖過濾和搜尋準則的 100 個事件行時觸發的警示。

您可以配置多個通知頻道。有效頻道為：`email`、`Slack`、`PagerDuty`、`Webhook`、`OpsGenie`、`Datadog`、`AppOptics`、`VictorOps`

您也可以定義**預設**。預設是警示範本，您可以連接至任意數目的視圖。 

視圖中會顯示一個鈴聲圖示，指出此視圖已連接一個警示。


## 必要條件
{: #views_prereqs}

開始之前，請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。 

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
{: #alerts_step1}

[移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## 步驟 2. 建立視圖
{: #alerts_step2}

[建立視圖](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md)。



## 步驟 3. [選用] 配置預設（警示範本）
{: #alerts_step3}

若要在不同的視圖重複使用警示配置，請配置**警示預設**。
{: note}

請完成下列步驟來配置預設：

1. 在 Web 使用者介面中，選取**配置**圖示 ![「配置」圖示](images/admin.png "「管理」圖示")。
2. 選取**警示**。
3. 選取**新增預設警示**。
4. 選擇通知頻道。 
5. 定義臨界條件。

    1. 選取時間頻率。例如，12 小時。

    2. 輸入事件行數目，您想要在這個數目之後觸發警示。

    3. 選取您想要檢查這兩個條件，還是只檢查一個條件。

6. 新增所選擇之通知頻道的詳細資料。

    例如，針對電子郵件通知頻道，新增一個以上的收件者，以及選擇性地新增一個時區。

7. 按一下**儲存警示**。



## 步驟 4. 配置警示
{: #alerts_step4}

選擇下列任何選項，以將警示連接至視圖：

### 選項 1. 使用預設來配置警示
{: #alerts_step4_preset}

請完成下列步驟，以將預設連接至視圖：

1. 在 Web 使用者介面中，按一下**視圖**圖示 ![「配置」圖示](images/views.png)。
2. 按一下要連接警示的視圖名稱。然後，選取**連接警示**。
3. 選擇預設以重複使用警示定義。 
4. 按一下**儲存警示**。 




### 選項 2. 配置視圖特定警示
{: #alerts_step4_view}

請完成下列步驟，以將警示連接至視圖：

1. 在 Web 使用者介面中，按一下**視圖**圖示 ![「配置」圖示](images/views.png)。
2. 按一下視圖名稱。然後，選取**連接警示**。
3. 選擇**視圖特定警示**。
4. 選擇通知頻道。 
5. 定義臨界條件。

    1. 選取時間頻率。例如，12 小時。

    2. 輸入事件行數目，您想要在這個數目之後觸發警示。

    3. 選取您想要檢查這兩個條件，還是只檢查一個條件。

6. 新增所選擇之通知頻道的詳細資料。

    例如，針對電子郵件通知頻道，新增一個以上的收件者，以及選擇性地新增一個時區。

7. 按一下**儲存警示**。



## 刪除預設（警示範本）
{: #alerts_delete_preset}

請完成下列步驟來刪除預設：

1. 在 Web 使用者介面中，選取**配置**圖示 ![「配置」圖示](images/admin.png "「管理」圖示")。
2. 選取**警示**。
3. 將滑鼠移至您要刪除之預設的*編輯* 按鈕之上。即會顯示*刪除* 選項。
4. 請選取**刪除**。
5. 確認您要刪除預設。按一下**刪除**。

## 從視圖中分離視圖特定警示
{: #alerts_delete_view}

請完成下列步驟來分離預設：

1. 在 Web 使用者介面中，選取**配置**圖示 ![「配置」圖示](images/admin.png "「管理」圖示")。
2. 選取**警示**。
3. 將滑鼠移至您要刪除之警示的*編輯* 按鈕之上。即會顯示*刪除* 選項。
4. 選取**分離**。
5. 確認您要刪除警示。按一下**分離**。












