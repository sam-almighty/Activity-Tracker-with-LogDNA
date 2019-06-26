---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# 佈建實例
{: #provision}

必須先在 {{site.data.keyword.cloud_notm}} 中佈建服務的實例，才能使用 {{site.data.keyword.at_full_notm}} 監視和管理事件資料。
{:shortdesc}

若要在公用雲端地區中佈建 {{site.data.keyword.at_full_notm}} 實例，請考慮下列資訊：
* 您必須選取與該實例相關聯的服務方案、從中收集日誌的地區，以及決定日誌保留期間的方案。您可以選擇 7、14 或 30 天保留期間。另外，{{site.data.keyword.at_full_notm}} 還提供`精簡`方案，可用來檢視透過系統的日誌。您可以使用事件追蹤來檢視事件。您也可以設計過濾器，以準備升級至較長的保留期間方案。此方案的保留期間為 0 天。
* 您的使用者 ID 必須具有在資源群組中佈建服務的許可權。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups)。


每個 {{site.data.keyword.cloud_notm}} 地區只能佈建 1 個服務實例。
{: important}

## 透過觀察儀表板佈建實例
{: #provision_ui}

若要從 {{site.data.keyword.cloud_notm}} 中的「觀察」儀表板佈建實例，請完成下列步驟：

1. [登入 {{site.data.keyword.cloud_notm}} 帳戶 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}。

	在使用您的使用者 ID 和密碼登入之後，{{site.data.keyword.cloud_notm}} 使用者介面即會開啟。

2. 移至功能表圖示 ![功能表圖示](../../icons/icon_hamburger.svg)。然後，選取**觀察**以存取*觀察* 儀表板。

3. 選取 **Activity Tracker**，然後按一下**建立實例**。 

4. 輸入服務實例的名稱。

5. 選取計劃在其中佈建實例的[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。 

6. 選取資源群組。 

    依預設，會設定 **Default** 資源群組。

    **附註：**如果您無法選取資源群組，請檢查您對要佈建實例的資源群組是否具有編輯許可權。

7. 選取`精簡`服務方案。 

    依預設，會設定精簡方案。

8. 按一下**建立**。

在佈建實例之後，*Activity Tracker* 儀表板即會開啟。 

接下來，移至 Web 使用者介面以檢視帳戶中的事件。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events)。



## 透過型錄佈建實例
{: #provision_catalog}

若要透過 {{site.data.keyword.cloud_notm}} 型錄佈建 {{site.data.keyword.at_full_notm}} 的實例，請完成下列步驟：

1. [登入 {{site.data.keyword.cloud_notm}} 帳戶 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}。

	在使用您的使用者 ID 和密碼登入之後，{{site.data.keyword.cloud_notm}} 使用者介面即會開啟。

2. 按一下**型錄**。即會開啟 {{site.data.keyword.cloud_notm}} 中可用的服務清單。

3. 若要過濾顯示的服務清單，請選取**開發人員工具**種類。

4. 按一下 **{{site.data.keyword.at_full_notm}}** 磚。 

5. 輸入服務實例的名稱。

6. 選取計劃在其中佈建實例的位置。 

    若要取得可用於 {{site.data.keyword.at_full_notm}} 服務的最新位置清單，請參閱[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

7. 選取資源群組。 

    依預設，會設定 **Default** 資源群組。

    **附註：**如果您無法選取資源群組，請檢查您對要佈建實例的資源群組是否具有編輯許可權。

8. 選取`精簡`服務方案。 

    依預設，會設定精簡方案。

9. 按一下**建立**。

在佈建實例之後，*Activity Tracker* 儀表板即會開啟。 

接著，移至 Web 使用者介面，以管理您帳戶中的事件。[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)。


## 透過 CLI 佈建實例
{: #provision_cli}

若要透過指令行佈建 {{site.data.keyword.at_full_notm}} 的實例，請完成下列步驟：

1. [必要條件] 安裝 {{site.data.keyword.cloud_notm}} CLI。[進一步瞭解](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

   如果已安裝 CLI，請繼續進行下一步。

2. 在 {{site.data.keyword.cloud_notm}} 中登入要在其中佈建實例的位置。請執行下列指令：[`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

    若要取得可用於 {{site.data.keyword.at_full_notm}} 服務的最新位置清單，請參閱[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

3. 設定您要在其中佈建實例的資源群組。請執行下列指令：[`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    依預設，會設定 `Default` 資源群組。

4. 建立實例。執行 [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create) 指令：

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    其中

    * NAME 是實例的名稱

    * 值 *logdnaat* 是 {{site.data.keyword.cloud_notm}} 中 {{site.data.keyword.at_full_notm}} 服務的名稱

    * SERVICE_PLAN_NAME 是方案的類型。有效值為 *lite*、*7-days*、*14-days*、*30-days*
    
    * LOCATION 是建立 LogDNA 實例的地區。若要取得可用於 {{site.data.keyword.at_full_notm}} 服務的最新位置清單，請參閱[位置](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)。

    
例如，若要佈建保留方案為 7 天的實例，請執行下列指令：

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



