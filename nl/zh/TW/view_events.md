---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# 檢視事件
{: #view_events.md}

在 {{site.data.keyword.cloud_notm}} 中佈建 {{site.data.keyword.at_full_notm}} 服務的實例之後，您可以透過 {{site.data.keyword.at_full_notm}} Web 使用者介面檢視事件。
{:shortdesc}


## 必要條件
{: #view_events_prereqs}

開始之前，請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。 

**附註：**您必須是 {{site.data.keyword.at_full_notm}} 服務的管理者、{{site.data.keyword.at_full_notm}} 實例的管理者，或具有帳戶 IAM 許可權，才能管理原則。

下表列出使用者必須具有的最低原則，才能啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，以及檢視事件：

| 角色                      | 授與的許可權            |
|---------------------------|-------------------------------|  
| 平台角色：`檢視者`     | 容許使用者在「觀察」儀表板中檢視服務實例的清單。|
| 服務角色：`讀者`      | 容許使用者啟動 Web 使用者介面，以及在 Web 使用者介面中檢視事件。|
{: caption="表 1. IAM 原則" caption-side="top"} 

如需如何為使用者配置這些原則的相關資訊，請參閱[授與使用者對使用者或服務 ID 的許可權](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。


## 透過 Web 使用者介面檢視事件
{: #view_events_step1}

若要啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，請完成下列步驟：

1. [登入 {{site.data.keyword.cloud_notm}} 帳戶 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}。

	在使用您的使用者 ID 和密碼登入之後，「{{site.data.keyword.cloud_notm}} *儀表板*」即會開啟。

2. 移至功能表圖示 ![功能表圖示](../../icons/icon_hamburger.svg)，然後選取**觀察**。 

3. 選取 **Activity Tracker**。 

    即會顯示 {{site.data.keyword.at_full_notm}} 實例的清單。

    **附註：**每個地區都有 1 個實例。

4. 在您要檢視事件的地區中選取實例。然後，按一下**檢視 LogDNA**。

{{site.data.keyword.at_full_notm}} Web 使用者介面即會開啟，並顯示**所有項目**視圖。透過此視圖，您可以針對已選取的地區查看帳戶中的事件。

**附註：**如果您具有`精簡`方案，且看不到您正在尋找的事件，則可能需要升級至付費方案，才能在較舊事件上啟用搜尋功能。事件可供搜尋的天數視您選擇的方案而定。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)。


## 自訂預設視圖
{: #view_events_step2}

在**使用者喜好設定**區段中，您可以修改每行顯示的資料欄位順序。

請完成下列步驟，來修改事件行的格式：

1. 在 Web 使用者介面中，按一下**配置**圖示 ![「配置」圖示](images/admin.png "「管理」圖示")。
2. 選取**使用者喜好設定**。新視窗即會開啟。
3. 選取**日誌格式**。
4. 修改*行格式* 區段，以符合您的需求。拖曳方框。




## 檢視環境定義中的事件
{: #view_events_step3}

您可以隨時檢視環境定義中的每一個事件行。

請完成下列步驟： 

1. 在 Web 使用者介面中，按一下**視圖**圖示 ![「配置」圖示](images/views.png "「配置」圖示")。
2. 選取**所有項目**或自訂視圖。
3. 識別您要探索的行。
4. 展開事件行。 

    即會顯示行 ID、標記及標籤的相關資訊。

5. 按一下**在環境定義中檢視**，以從該主機、應用程式或兩者查看其他項目之環境定義中的事件行。

完成探索事件時，請按一下**關閉**來關閉該行。




## 將事件複製到剪貼簿
{: #view_events_step4}


請完成下列步驟，將事件複製到剪貼簿： 

1. 在 Web 使用者介面中，按一下**視圖**圖示 ![「配置」圖示](images/views.png "「配置」圖示")。
2. 選取**所有項目**或自訂視圖。
3. 識別您要探索的行。
4. 展開事件行。 

    即會顯示行 ID、標記及標籤的相關資訊。

5. 按一下**複製到剪貼簿**，將事件複製到剪貼簿。

完成探索事件時，請按一下**關閉**來關閉該行。




