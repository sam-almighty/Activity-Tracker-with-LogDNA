---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# 導覽至 Web 使用者介面
{: #launch}

在 {{site.data.keyword.cloud_notm}} 中佈建 {{site.data.keyword.at_full_notm}} 服務的實例之後，您可以透過 {{site.data.keyword.at_full_notm}} Web 使用者介面檢視、監視及管理事件。
{:shortdesc}


## 步驟 1. 將 IAM 原則授與使用者以檢視資料 
{: #step1}

**附註：**您必須是 {{site.data.keyword.at_full_notm}} 服務的管理者、{{site.data.keyword.at_full_notm}} 實例的管理者，或具有要授與其他使用者原則的帳戶 IAM 許可權。

下表列出使用者必須具有的最低原則，才能啟動 Web 使用者介面，並透過 {{site.data.keyword.at_full_notm}} Web 使用者介面檢視資料：

| 角色                      | 授與的許可權            |
|---------------------------|---------------------|
| 平台角色：`檢視者`     | 容許使用者在「觀察」儀表板中檢視服務實例的清單。|
| 服務角色：`讀者`      | 容許使用者透過 Web 使用者介面檢視事件。| 
{: caption="表 1. IAM 原則" caption-side="top"} 

如需相關資訊，請參閱[將使用者許可權授與使用者或服務 ID](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)。


## 步驟 2. 透過 {{site.data.keyword.cloud_notm}} 使用者介面啟動 Web 使用者介面
{: #launch_step2}

您可以從 {{site.data.keyword.cloud_notm}} 使用者介面，在 {{site.data.keyword.at_full_notm}} 實例的環境定義內啟動 Web 使用者介面。 

請完成下列步驟來啟動 Web 使用者介面：

1. [登入 {{site.data.keyword.cloud_notm}} 帳戶 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}。

	在使用您的使用者 ID 和密碼登入之後，{{site.data.keyword.cloud_notm}} 儀表板即會開啟。

2. 按一下**功能表**圖示 ![「功能表」圖示](../icons/icon_hamburger.svg) > **觀察**。 

3. 選取 **Activity Tracker**。 

    即會顯示 {{site.data.keyword.at_full_notm}} 實例的清單。

    每個地區都會有 1 個實例。
    {: important}

4. 在您要檢視事件的地區中選取實例。然後，按一下**檢視 LogDNA**。

{{site.data.keyword.at_full_notm}} Web 使用者介面即會開啟，並顯示**所有項目**視圖。透過此視圖，您可以針對已選取的地區查看帳戶中的事件。



## 從 {{site.data.keyword.cloud_notm}} 取得 Web 使用者介面 URL
{: #launch_get}

若要取得 Web 使用者介面 URL，請從終端機完成下列步驟：

1. 設定在其中佈建 {{site.data.keyword.at_full_notm}} 實例的資源群組。

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. 設定 {{site.data.keyword.at_full_notm}} 實例名稱。

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. 設定端點。

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. 設定 IAM 記號。

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **附註：**如果您是在 MacOS 終端機中工作，則指令如下：`export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. 設定資源群組 ID。

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. 在變數中設定 Web 使用者介面 URL。

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. 取得 Web 使用者介面 URL。

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

