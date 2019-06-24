---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #view_events}

在 {{site.data.keyword.cloud_notm}} 中佈建 {{site.data.keyword.at_full_notm}} 服務的實例之後，您可以透過 {{site.data.keyword.at_full_notm}} Web 使用者介面檢視事件。
您會以當地時間來檢視事件。
{:shortdesc}


## 檢視事件
{: #view_events_step1}

請完成下列步驟，以檢視事件：

1. 請檢查您的使用者 ID 是否具有啟動 Web 使用者介面及檢視事件的許可權。 

    下表列出使用者必須具有的最低角色，才能啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面，以及檢視、搜尋及過濾事件：

    <table>
      <caption>表 1. IAM 角色</caption>
      <tr>
        <th> 角色    </th>
        <th> 授與的許可權            </th>
      </tr>
      <tr>
        <td>平台角色：`檢視者`</td>     <td>容許使用者在*觀察* 儀表板中檢視服務實例的清單。</td>
      </tr>
      <tr>
        <td>服務角色：`讀者`</td>      <td>容許使用者啟動 Web 使用者介面，並在 Web 使用者介面中檢視、搜尋和過濾事件。</td>
      </tr>
    </table>

    如需如何為使用者配置原則的相關資訊，請參閱[授與使用者對使用者或服務 ID 的許可權](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。

2. [移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。

3. 按一下**視圖**圖示 ![「配置」圖示](images/views.png)。

4. 選取**全部**以檢視所有事件，或選取一個視圖。 

可以透過所選視圖來檢視事件。



## 套用搜尋查詢來檢視事件子集
{: #view_events_step2}

可以套用搜尋查詢來選取透過視圖顯示的事件。可以儲存該視圖以供日後重複使用。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2)。

 


## 套用時間範圍來檢視事件子集
{: #view_events_step3}

可以套用時間範圍來選取透過視圖顯示的事件。

您可以藉由指定絕對時間、相對時間或時間範圍來套用時間戳記。

請完成下列步驟，以跳至特定時間：
1. [移至 Web 使用者介面](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。
2. 按一下**視圖**圖示 ![「配置」圖示](images/views.png)。
3. 選取**所有項目**或視圖。
4. 輸入時間查詢。選擇下列任一選項：

    * 輸入絕對時間以跳至事件中的某個復原點，例如 `May 20 7:00pm`。
    
    * 輸入相對時間，例如 `2 days ago`、`today at 12am` 或 `an hour ago`。

    * 輸入時間範圍，例如 `yesterday 10am to yesterday 11am`、`last fri 4:30pm to 11/12 1 AM`、`last wed 4:30pm to 23/05 1 AM` 或 `May 20 10am to May 22 10am`。務必包括 `to` 以分隔初始時間戳記與結束時間戳記。

5. 按一下 **ENTER** 鍵。

    您可能會收到以下錯誤訊息：`Your request is taking longer than expected, try refreshing your browser in a bit as we try to catch up. Retry.` 指定的時間範圍內沒有任何事件可供顯示時，您可能會收到此錯誤。請變更時間查詢，然後重試。



## 檢視環境定義中的事件
{: #view_events_step4}

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
{: #view_events_step5}


請完成下列步驟，將事件複製到剪貼簿： 

1. 在 Web 使用者介面中，按一下**視圖**圖示 ![「配置」圖示](images/views.png "「配置」圖示")。
2. 選取**所有項目**或自訂視圖。
3. 識別您要探索的行。
4. 展開事件行。 

    即會顯示行 ID、標記及標籤的相關資訊。

5. 按一下**複製到剪貼簿**，將事件複製到剪貼簿。

完成探索事件時，請按一下**關閉**來關閉該行。




