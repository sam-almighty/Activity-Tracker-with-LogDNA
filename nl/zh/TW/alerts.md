---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #alerts}

透過 {{site.data.keyword.at_full_notm}} Web 使用者介面，您可以套用搜尋查詢，以定義透過自訂視圖顯示的事件。然後，您可以將警示連接至該視圖，以便在條件發生時收到通知。您可以將一個以上的警示連接至一個視圖。您可以為一個警示定義多個通知頻道。您可以將警示靜音。也可以從視圖分離警示。
{:shortdesc}


## 必要條件
{: #alerts_prereqs}

* [進一步瞭解警示](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts)。

* 您必須具有 {{site.data.keyword.at_full_notm}} 服務**的付費服務方案**。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。

* 請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。下表列出使用者必須具有的最低角色，才能啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，以及檢視、搜尋及過濾事件：

| 角色                      | 授與的許可權            |
|---------------------------|-------------------------------|  
| 平台角色：`檢視者`     | 容許使用者在「觀察」儀表板中檢視服務實例的清單。|
| 服務角色：`讀者`      | 容許使用者啟動 Web 使用者介面，以及在 Web 使用者介面中檢視事件。|
{: caption="表 1. IAM 角色" caption-side="top"} 

如需如何為使用者配置原則的相關資訊，請參閱[授與使用者對使用者或服務 ID 的許可權](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。

 


## 步驟 1. 移至 Web 使用者介面
{: #alerts_step1}

[移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## 步驟 2. 建立視圖
{: #alerts_step2}

[建立視圖](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。



## 步驟 3. [選用] 配置預設（警示範本）
{: #alerts_step3}

若要在不同的視圖重複使用警示配置，請配置**警示預設**。
{: note}

請完成下列步驟來配置預設：

1. 在 Web 使用者介面中，選取**配置**圖示 ![「配置」圖示](images/admin.png "「管理」圖示")。
2. 選取**警示**。
3. 選取**新增預設警示**。
4. 選擇通知頻道。如需支援頻道的清單，請參閱[警示通知頻道](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)。
5. 選取警示類型。選擇**存在警示**類型，以在視圖中顯示事件數目多於您預期數目時，進行通知。選擇**缺少警示**類型，以在視圖中顯示事件數目少於您預期數目，或是未顯示任何事件時，進行通知。 
5. 選擇通知頻道。如需支援頻道的清單，請參閱[警示通知頻道](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)。
6. 定義臨界條件。

    1. 選取時間頻率。例如，12 小時。

    2. 輸入事件行數目，您想要在這個數目之後觸發警示。

    3. 選取您想要檢查這兩個條件，還是只檢查一個條件。

7. 新增所選擇之通知頻道的詳細資料。

    例如，針對電子郵件通知頻道，新增一個以上的收件者，以及選擇性地新增一個時區。

8. 按一下**儲存警示**。



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
5. 選取警示類型。選擇**存在警示**類型，以在視圖中顯示事件數目多於您預期數目時，進行通知。選擇**缺少警示**類型，以在視圖中顯示事件數目少於您預期數目，或是未顯示任何事件時，進行通知。 
6. 定義臨界條件。

    1. 選取時間頻率。例如，12 小時。

    2. 輸入事件行數目，您想要在這個數目之後觸發警示。

    3. 選取您想要檢查這兩個條件，還是只檢查一個條件。

7. 新增所選擇之通知頻道的詳細資料。

    例如，針對電子郵件通知頻道，新增一個以上的收件者，以及選擇性地新增一個時區。

8. 按一下**儲存警示**。



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












