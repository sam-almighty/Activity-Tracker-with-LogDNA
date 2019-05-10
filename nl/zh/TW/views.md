---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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
{: #views.md}

透過 {{site.data.keyword.at_full_notm}} Web 使用者介面，您可以套用搜尋和過濾準則，以定義透過自訂視圖顯示的事件。
{:shortdesc}


## 必要條件
{: #views_prereqs}

開始之前，請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。然後，[移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。

**附註：**您必須是 {{site.data.keyword.at_full_notm}} 服務的管理者、{{site.data.keyword.at_full_notm}} 實例的管理者，或具有帳戶 IAM 許可權，才能管理原則。

下表列出使用者必須具有的最低原則，才能啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，以及檢視、搜尋及過濾事件：

| 角色                      | 授與的許可權            |
|---------------------------|-------------------------------|  
| 平台角色：`檢視者`     | 容許使用者在「觀察」儀表板中檢視服務實例的清單。|
| 服務角色：`讀者`      | 容許使用者啟動 Web 使用者介面，以及在 Web 使用者介面中檢視事件。|
{: caption="表 1. IAM 原則" caption-side="top"} 

如需如何為使用者配置這些原則的相關資訊，請參閱[授與使用者對使用者或服務 ID 的許可權](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。



## 步驟 1. 過濾事件
{: #views_step1}

您可以依來源、應用程式及記載層次來過濾事件。 

* 來源可以是主機、電腦、虛擬機器或 Heroku 應用程式。
* 應用程式代表日誌檔、程式或容器。
* 記載層次的範例為：INFO、DEBUG、ERROR

請完成下列步驟來過濾日誌：

1. 在 Web 使用者介面中，按一下**視圖**圖示 ![「配置」圖示](images/views.png "「配置」圖示")。
2. 選取**所有項目**或視圖。
3. 展開**所有標籤**，以查看可用的標籤清單。然後，選擇您要的標籤。
4. 展開**所有來源**，以查看可用的來源清單。然後，選擇您要的來源。
5. 展開**所有應用程式**，以查看可用的應用程式清單。然後，選擇您要的應用程式。
6. 展開**所有層次**，以查看可用的層次清單。然後，選擇您要的層次。

套用過濾器時，請注意視圖的名稱會變更為**未儲存的視圖**。

**附註：**在每一個區段中，您可以將多個選項分組成一個群組。將標籤、來源、應用程式及層次分組，以在其他自訂視圖中過濾資料時重複使用這些分組。

若要建立群組，請選取多個值。然後，按一下**儲存為群組**。輸入群組的名稱，然後儲存它。


## 步驟 2. 搜尋事件
{: #views_step2}

當您搜尋事件時，搜尋會套用在該視圖中配置的任何過濾器和時間查詢。

您可以執行簡式搜尋（單一詞彙字串搜尋）、複合搜尋（多個搜尋詞彙和運算子）、欄位搜尋（如果可以剖析日誌行的話）等。如需相關資訊，請參閱 [LogDNA 文件中的如何搜尋日誌 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://docs.logdna.com/docs/search){:new_window}。

**附註：**AND 及 OR 運算子會區分大小寫，而且必須大寫。

套用搜尋準則時，請注意視圖的名稱會變更為**未儲存的視圖**。



## 步驟 3. 建立自訂視圖
{: #views_step3}

在將時間範圍、過濾器及搜尋準則套用至**所有項目**視圖，或套用至現有的自訂視圖之後，請完成下列步驟，將結果儲存為自訂視圖：

1. 在 Web 使用者介面中，按一下**未儲存的視圖**。
2. 選取**儲存為新視圖/警示**。*建立新視圖* 頁面即會開啟。
3. 在*名稱* 欄位中輸入視圖的名稱。
4. 選擇性地新增種類。輸入名稱，然後按一下**將此項新增為新的視圖種類**。
5. 選擇性地連接警示。即會顯示一個新區段，供您配置警示。
6. 按一下**儲存視圖**。




