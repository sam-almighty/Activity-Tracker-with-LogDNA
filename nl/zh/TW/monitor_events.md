---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, monitor events

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


# 監視帳戶中的活動
{: #monitor_events}

您可以透過 {{site.data.keyword.at_full_notm}} Web 使用者介面來監視帳戶中的活動。此外，還可以匯出事件集，以在其他環境定義中對事件進行分析。
{:shortdesc}

每個位置有 1 個 {{site.data.keyword.at_full_notm}} 服務實例。因此，若要監視帳戶中的活動，可能需要透過不同的 {{site.data.keyword.at_full_notm}} 實例來檢視和分析事件。 

在 {{site.data.keyword.cloud_notm}} 中，您可以按一下**功能表**圖示 ![功能表圖示](../icons/icon_hamburger.svg) > **觀察** > **Activity Tracker**，以查看儀表板，在儀表板上會列出帳戶中佈建的所有實例。
{: tip}

若要檢視事件，必須在事件可用位置中[啟動 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch)。然後，可以使用視圖來監視這些事件。您會以當地時間來檢視事件。

可以套用時間戳記及（或）搜尋查詢來選取透過視圖顯示的事件。

* 可以套用搜尋查詢，並將其儲存為自訂視圖。 
* 可以套用時間戳記來跳至事件日誌中的特定時間。 

套用搜尋查詢時，可以儲存該視圖以供日後重複使用。但是，不會儲存時間戳記。

請注意，實例可能具有不同的服務方案，因此不同的資料保留期將決定資料可供透過 Web 使用者介面進行搜尋的天數。只能監視保留期內的事件。不同的[服務方案](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan)具有不同的保留期。


## 監視廣域事件和以位置為基礎的事件
{: #mon_def_event_type}

事件可以分類為廣域事件或以位置為基礎的事件。事件的類型將決定必須在哪裡監視事件。

廣域事件的通用佈景主題是單一同步位置，在其中帳戶管理者可以監視整個雲端上特定類型的活動。而以位置為基礎的事件，始終是訂閱雲端服務管理位置的本端事件。
{: note}

### 廣域事件
{: #mon_def_global}

**廣域事件**報告帳戶中與通常會在所有地區中同步的資料和資源相關的活動。
{: note}

會整合使用者與之互動的服務，以構成廣域 {{site.data.keyword.cloud_notm}} 體驗的核心。

廣域網域在**法蘭克福**設定。廣域事件透過在法蘭克福配置的 {{site.data.keyword.at_full_notm}} 實例進行擷取並使其可用。

例如，帳戶管理者邀請使用者加入帳戶時，可以從雲端中的任何位置執行此作業。他們可邀請位於法蘭克福的使用者，並授與他們使用在達拉斯佈建的服務的許可權。對於這種情況，事件應該發送到哪裡？回答是一個與原點或位置無關的廣域網域，其中資訊會在所有地區中同步。
    
另一個範例是，資源控制器事件在 IBM Cloud 中也會被視為廣域事件。這些事件會報告整個雲端中服務實例的佈建和刪除。雖然服務實例是在特定位置建立的，但資源控制器動作會作為廣域事件進行報告，以提供單一視圖來顯示整個帳戶中佈建的所有服務實例。


### 以位置為基礎的事件
{: #mon_def_location}

**以位置為基礎的事件**報告帳戶中在 {{site.data.keyword.IBM_notm}} 資料中心位置（如達拉斯或法蘭克福）管理的 {{site.data.keyword.cloud_notm}} 服務產生的活動。
{: note}


用戶端和應用程式與某個位置內管理的雲端服務互動時，將透過該位置中配置的 {{site.data.keyword.at_full_notm}} 實例來擷取以位置為基礎的事件，並使其可用。您可以藉由在該位置中[啟動 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch)來檢視這些事件。
    
以位置為基礎的事件會維護該雲端位置中執行的服務的資料地區。

例如，如果在法蘭克福位置佈建 {{site.data.keyword.cloudcerts_short}} 服務，則會將來自該實例的事件傳送至在法蘭克福佈建的 {{site.data.keyword.at_full_notm}} 實例。如果在達拉斯位置佈建 {{site.data.keyword.cloudcerts_short}} 服務，則會將來自該實例的事件傳送至在達拉斯佈建的 {{site.data.keyword.at_full_notm}} 實例。在這兩種情況下，事件始終是所訂閱雲端服務的地區和位置的本端事件。




## 透過預設視圖監視事件
{: #mon_def_view}

預設視圖名為**全部**。 

一旦您在某個位置開啟 Web 使用者介面，就會立即看到該視圖。 

實例中的所有事件都將透過此視圖顯示。

若要瞭解如何透過此視圖來檢視事件，請參閱[檢視事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1)。

## 透過自訂視圖監視事件
{: #mon_cus_view}

建議您監視帳戶中的一組事件。若要對事件子集進行分析，可以建立自訂視圖。 

若要建立自訂視圖，必須套用搜尋查詢來定義哪些事件要透過視圖顯示。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2)。

可以向自訂視圖[連接警示](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts)。 

可以從自訂視圖[匯出資料](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export)。 

可以[重新命名視圖以及新增或修改視圖說明](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5)。 

可以向視圖[套用行範本](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4)，以自訂資料的顯示方式。 

可以藉由對視圖依**種類*分組來組織視圖。


## 藉由套用時間範圍來監視事件
{: #mon_time_view}

建議您查看特定時間範圍內的事件。

可以[套用時間範圍](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3)來選取透過視圖顯示的事件。

您可以藉由指定絕對時間、相對時間或時間範圍來套用時間戳記。

* 絕對時間指定事件日誌中的精確復原點，例如 `May 20 7:00pm`。
    
* 相對時間指定不精確的時間範圍，例如 `2 days ago`。

* 時間範圍指定時間間隔，例如 `yesterday 10am to yesterday 11am`。



## 配置警示
{: #mon_alerts}

在某些情境中，建議您在帳戶中產生特定事件時收到通知。例如，建議您在失敗的動作數目超過指定的臨界值時收到通知。 

透過 {{site.data.keyword.at_full_notm}} Web 使用者介面，您可以套用搜尋查詢，以定義透過自訂視圖顯示的事件。然後，您可以將警示連接至該視圖，以便在條件發生時收到通知。視圖中會顯示一個鈴聲圖示，指出此視圖已連接一個警示。

* 每個視圖可以[連接一個警示](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4)。
* 可以配置以符合視圖中搜尋查詢的事件行數及（或）時間頻率為基礎的條件。
* 您可以為一個警示定義多個通知頻道。如需受支援頻道的相關資訊，請參閱[警示通知頻道](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels)。
* 可以[定義**預設**](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3)。預設是警示範本，您可以連接至任意數目的視圖。可以使用預設來定義使用者將警示連接到視圖時可重複使用的範本。 
* 您可以將警示靜音。 
* 可以從視圖[分離警示](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view)。 


### 警示類型
{: #mon_alerts_types}

可以配置下列類型的警示：

* **存在警示**：可以使用此類型警示在視圖中顯示的事件數目超過預期數目時發出通知。 
* **缺少警示**：可以使用此類型警示在視圖中顯示的事件數目低於預期數目或沒有事件時發出通知。 

例如，您可能有一個視圖，其中顯示的事件報告已刪除帳戶中的服務實例。您並不希望刪除服務實例。為此，可以配置*存在警示**，用於在該視圖中顯示一個以上的事件時觸發此警示。

在該視圖中顯示事件後，會啟用缺少警示。
{: note}


### 警示條件
{: #mon_alerts_conditions}

您可以針對警示配置下列任何條件： 

* **時間頻率**：設定此條件以指定觸發警示的頻率。有效值為：30 秒、1 分鐘、5 分鐘、15 分鐘、30 分鐘、1 小時、6 小時、12 小時、24 小時
* **事件行計數器**：設定此條件以指定與視圖的過濾和搜尋準則相符的事件行數。當達到事件行數目時，就會觸發警示。

您可以決定檢查這兩個條件，或只檢查一個條件。如果兩個條件都已設定，則會在達到任何臨界值時觸發警示。 

如果將*事件行計數器* 設定為觸發警示的唯一條件，請注意，配置條件時設定的時間頻率將決定在觸發警示後過多長時間重設警示條件。
{: note}

例如，您可以配置在 30 秒之後觸發的警示，或在收集符合視圖過濾和搜尋準則的 100 個事件行時觸發的警示。



## 匯出事件
{: #mon_export}

您可能需要在 Web 使用者介面外部存取一組事件，以更詳細地調查問題。 

您可以將 JSONL 格式中的資料從 {{site.data.keyword.at_full_notm}} 實例匯出至本端檔案。 

可以透過 Web 使用者介面中的視圖匯出事件，也可以使用 REST API 以程式設計方式匯出事件。

匯出事件時，請考慮下列資訊：
* 您可以匯出一組事件項目。 
* 若要定義您想要匯出的資料集，您可以套用過濾器並搜尋。也可以指定時間範圍。 
* 可以匯出的行數上限為 20,000。

### 使用 REST API
{: #mon_export_api}

可以使用 LogDNA REST API 以程式設計方式匯出事件。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api)。

以程式設計方式匯出事件時，請考慮下列資訊：

* 可以選擇傳送電子郵件或將事件以串流方式傳輸到終端機。
* 必須使用一個服務金鑰來傳遞在發出匯出 REST API 呼叫時必須使用的認證。 

    您必須具有 {{site.data.keyword.at_full_notm}} 實例或服務的**管理員**角色，才能在 Web 使用者介面中檢視和產生服務金鑰。


### 透過 Web 使用者介面中的視圖
{: #mon_export_ui}

可以透過 Web 使用者介面中的視圖來匯出事件。 

在 Web 使用者介面中，可以選取用於顯示要匯出的資料的視圖。對於此視圖，必須選擇**匯出行**作業。您必須指定時間範圍，以及要匯出較新的行還是較舊的行。然後，可以要求匯出。 

提交要求後，您會收到一封傳送到您電子郵件位址的電子郵件，其中附帶包含相應資料之壓縮檔的鏈結。 
* 若要取得資料，您必須按一下該鏈結，然後下載壓縮檔。 
* 包含您要匯出之資料的壓縮檔，可用時間最多 48 小時。 

[進一步瞭解透過 Web 使用者介面匯出事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui)。








