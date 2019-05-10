---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# 移除實例
{: #remove}

您可以從 {{site.data.keyword.cloud_notm}} 使用者介面或透過指令行移除 {{site.data.keyword.at_full_notm}} 服務的實例。
{:shortdesc}



## 透過 {{site.data.keyword.cloud_notm}} 使用者介面移除實例
{: #remove_ui}

若要使用 {{site.data.keyword.cloud_notm}} 使用者介面移除 {{site.data.keyword.at_full_notm}} 的實例，請完成下列步驟：

1. [登入 {{site.data.keyword.cloud_notm}} 帳戶 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}。

	在使用您的使用者 ID 和密碼登入之後，{{site.data.keyword.cloud_notm}} 使用者介面即會開啟。

2. 移至功能表圖示 ![「功能表」圖示](../../icons/icon_hamburger.svg) &gt; **觀察**，以存取*觀察* 儀表板。

3. 選取 **Activity Tracker**。即會顯示實例清單。

4. 選取您要刪除的實例。

5. 從*動作* 功能表中，選取**移除**。

接著，移除已授與使用者使用所刪除實例的許可權。

## 透過 CLI 移除實例
{: #remove_cli}

若要透過指令行移除 {{site.data.keyword.at_full_notm}} 的實例，請完成下列步驟：

1. [必要條件] 安裝 {{site.data.keyword.cloud_notm}} CLI。

   如需相關資訊，請參閱[安裝 {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

   如果已安裝 CLI，請繼續進行下一步。

2. 登入 {{site.data.keyword.cloud_notm}} 中您要佈建實例的地區。請執行下列指令：[`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. 設定在其中佈建實例的資源群組。請執行下列指令：[`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    依預設，會設定 *Default* 資源群組。

4. 移除實例。執行 [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) 指令：

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    其中 NAME 是實例的名稱

    若要列出您登入之資源群組中的所有可用實例，請執行下列指令：

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
例如，若要移除實例，請執行下列指令：

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

接著，移除已授與使用者使用所刪除實例的許可權。


