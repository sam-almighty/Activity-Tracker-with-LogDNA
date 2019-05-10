---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, archive logs, COS, cloud object storage

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

 
# 將事件保存至 IBM Cloud Object Storage
{: #archiving}

您可以將事件從 {{site.data.keyword.at_full_notm}} 實例保存至 {{site.data.keyword.cos_full_notm}} (COS) 實例中的儲存區。
{:shortdesc}

若要配置保存，您必須對 {{site.data.keyword.at_full_notm}} 服務具有平台角色為**檢視者**，且服務角色為**管理員**的 IAM 原則。

您可以將事件從 {{site.data.keyword.at_full_notm}} 實例保存至 {{site.data.keyword.cos_full_notm}} (COS) 實例中的儲存區。每一個 {{site.data.keyword.at_full_notm}} 實例都有它自己的保存配置。 

事件會以壓縮格式 **(.json.gz)** 自動保存，一天一次。每一行都會保留其 meta 資料。

事件會在您儲存配置之後的 24-48 小時內進行保存。 

{{site.data.keyword.cos_full_notm}} 實例是在資源群組的環境定義內佈建。{{site.data.keyword.at_full_notm}} 實例也是在資源群組的環境定義內佈建。這兩個實例可以在相同的資源群組之下或在不同的資源群組中分組。 

{{site.data.keyword.at_full_notm}} 會使用服務 ID 與 {{site.data.keyword.cos_full_notm}} 服務通訊。

* 您為 {{site.data.keyword.cos_full_notm}} 實例建立的服務 ID 是由 {{site.data.keyword.at_full_notm}} 用來鑑別及存取 {{site.data.keyword.cos_full_notm}} 實例。 
* 您可以將特定存取原則指派給限制 {{site.data.keyword.cos_full_notm}} 實例之許可權的服務 ID。將服務 ID 限制為僅對您計劃保存事件的儲存區具有寫入許可權。

下圖顯示在保存事件時整合之不同元件的高階視圖：

![保存事件的高階視圖](images/archive.png "保存事件的高階視圖")


請完成下列步驟，將 {{site.data.keyword.at_full_notm}} 實例保存至 {{site.data.keyword.cos_full_notm}} 實例中的儲存區：


## 步驟 1. 將 IAM 原則授與使用者，以使用 {{site.data.keyword.cos_full_notm}}
{: #archiving_step1}

**附註：**這個步驟必須由帳戶擁有者或 {{site.data.keyword.cloud_notm}} 上 {{site.data.keyword.cos_full_notm}} 服務的管理者來完成。

身為 {{site.data.keyword.cos_full_notm}} 服務的管理者，您必須能夠佈建服務的實例、授與其他使用者使用這些實例的許可權，以及建立服務 ID。 

有不同方式，您可以用來授與使用者許可權，使其變成 {{site.data.keyword.cos_full_notm}} 服務的編輯者：

* 作為帳戶中服務的管理者，使用者必須具有平台角色*管理者*對 {{site.data.keyword.cos_full_notm}} 服務的 IAM 原則。您必須將此使用者存取權指派給帳戶中的個別資源。 

* 對於資源群組之環境定義內的服務，作為該服務的管理者，使用者在該資源群組的環境定義內，必須具有平台角色*管理者*對 {{site.data.keyword.cos_full_notm}} 服務的 IAM 原則。 


下表列出使用者可以具有的角色，以完成針對 {{site.data.keyword.cos_full_notm}} 服務列出的動作：

| 服務                    | 平台角色    | 動作                                                                                        | 
|----------------------------|-------------------|-----------------------------------------------------------------------------------------------|       
| `Cloud Object Storage`     | 管理者     | 容許使用者將原則指派給帳戶中的使用者，以使用 {{site.data.keyword.cos_full_notm}} 服務。|
| `Cloud Object Storage`     | 管理者     </br>編輯者 | 容許使用者佈建 {{site.data.keyword.cos_full_notm}} 服務的實例。|
| `Cloud Object Storage`     | 管理者     </br>編輯者 </br>操作員 | 容許使用者建立服務 ID。| 
{: caption="表格 1. 角色與動作" caption-side="top"} 


請完成下列步驟，將資源群組環境定義內 {{site.data.keyword.cos_full_notm}} 服務的管理者角色指派給使用者： 

1. [登入 {{site.data.keyword.cloud_notm}} 帳戶 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}。

	在使用您的使用者 ID 和密碼登入之後，{{site.data.keyword.cloud_notm}} 使用者介面即會開啟。
    
2. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
3. 從您要指派存取權之使用者的列中，選取**動作**功能表，然後按一下**指派存取權**。
4. 選取**指派資源群組內的存取權**。
5. 選取資源群組。
6. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.at_full_notm}} 服務的存取權，可以選取**不存取**。

7. 選取 **Cloud Object Storage**。
8. 選取平台角色**管理者**。
9. 按一下**指派**。



## 步驟 2. 佈建 {{site.data.keyword.cos_full_notm}} 的實例
{: #archiving_step2}

**附註：**這個步驟必須由編輯者或 {{site.data.keyword.cloud_notm}} 上 {{site.data.keyword.cos_full_notm}} 服務的管理者來完成。請完成下列步驟來佈建 {{site.data.keyword.cos_full_notm}} 實例：

1. 從功能表列中，按一下**型錄**。即會開啟 {{site.data.keyword.cloud_notm}} 中可用的服務清單。

2. 若要過濾顯示的服務清單，請選取**儲存空間**種類。

3. 按一下 **Object Storage** 磚。

4. 輸入服務實例的名稱。

5. 選取資源群組。 

    依預設，會設定 **Default** 資源群組。

6. 選取服務方案。 

    依預設，會設定**精簡**方案。

7. 按一下**建立**。



## 步驟 3. 建立儲存區
{: #archiving_step3}

儲存區是一種在 {{site.data.keyword.cos_full_notm}} 實例中組織您資料的方法。 

若要管理儲存區，必須授與您的使用者在 {{site.data.keyword.cos_full_notm}} 實例上使用儲存區的許可權。下表概述不同動作，以及使用者可以具有的角色，以使用儲存區：

| 服務                    | 角色                   | 動作                             | 
|----------------------------|-------------------------|------------------------------------|       
| `Cloud Object Storage`     | 平台角色：檢視者   | 容許使用者檢視所有儲存區，並透過 {site.data.keyword.Bluemix_notm}} 使用者介面列出其中的物件。|
| `Cloud Object Storage`     | 服務角色：管理員   | 容許使用者將物件公開。                                                       |
| `Cloud Object Storage`     | 服務角色：管理員   </br>撰寫者 | 容許使用者建立及破壞儲存區及物件。                         | 
| `Cloud Object Storage`     | 服務角色：讀者   | 容許使用者列出及下載物件。                                                 |
{: caption="表 1. 要使用儲存區的角色和動作" caption-side="top"} 

**附註：**若要建立儲存區，您的使用者必須對 {{site.data.keyword.cos_full_notm}} 實例具有管理者或撰寫者許可權。

請完成下列步驟來建立儲存區：

1. 從「導覽」功能表中，選取**資源清單**。

2. 選取您計劃要在其中建立儲存區的 {{site.data.keyword.cos_full_notm}} 實例。

3. 選取**儲存區**。然後，按一下**建立儲存區**。

4. 對*唯一儲存區名稱*欄位輸入儲存區名稱。

    **附註：**全球所有地區的所有儲存區都共用單一名稱空間。 

    您可以使用您的 {{site.data.keyword.at_full_notm}} 實例名稱作為儲存區名稱的一部分。例如，對於名稱為 *logdna-1* 的實例，您可以使用 *accountN-logdna-1* 作為儲存區名稱。

    您需要此名稱，才能透過 {{site.data.keyword.at_full_notm}} Web 使用者介面配置保存。

5. 選擇備援類型及您想要實際儲存資料的位置。

    備援是指資料分散的地理區域範圍及規模。 
    
    跨區域備援會將資料分散到數個都會區。
    
    區域性備援會將資料分散到單一都會區。 
    
    「單一資料中心」只會在單一網站內的各個裝置之間分散存放資料。

    如需相關資訊，請參閱[選取地區及端點](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints)。

6. 選擇*儲存空間類別* 的類型。

    您可以建立不同儲存空間類別的儲存區。根據您擷取資料的需求，選擇儲存區的儲存空間類別類別。如需相關資訊，請參閱[使用儲存空間類別](/docs/services/cloud-object-storage?topic=cloud-object-storage-use-storage-classes#use-storage-classes)。

    **附註：**一旦建立了儲存區，就無法變更儲存區的儲存空間類別。如果需要重新分類物件，則需要將資料移至另一個具有所需儲存空間類別的儲存區。

7. 選擇性地新增「Key Protect 金鑰」，以加密靜態資料。

    依預設，所有物件都使用隨機產生的金鑰和 all-or-nothing-transform 來加密。雖然這個預設加密模型提供靜態安全，但是有些工作負載需要擁有已使用的加密金鑰。如需相關資訊，請參閱[管理加密](/docs/services/cloud-object-storage?topic=cloud-object-storage-manage-encryption#manage-encryption)。



## 步驟 4. 建立 {{site.data.keyword.cos_full_notm}} 實例的服務 ID
{: #archiving_step4}

服務 ID 可識別服務，與使用者 ID 識別使用者的方式類似。服務 ID 不會關聯於特定使用者。如果建立服務 ID 的使用者離開您的組織，並且已從帳戶中刪除，則服務 ID 仍會保留。

您必須為 {{site.data.keyword.cos_full_notm}} 實例建立服務 ID。此服務 ID 由 {{site.data.keyword.at_full_notm}} 實例使用，以對您的 {{site.data.keyword.cos_full_notm}} 實例進行鑑別。 

您必須將特定的存取原則指派給限制使用特定服務之許可權的服務 ID，甚至結合用於存取不同服務的許可權。例如，若要將存取限制為單一儲存區，請確保服務 ID 沒有使用主控台或 CLI 的任何實例層次原則。


請完成下列步驟，為 {{site.data.keyword.cos_full_notm}} 實例建立具有寫入許可權的服務 ID。

1. 從「儀表板」中，選取您計劃要在其中建立儲存區的 {{site.data.keyword.cos_full_notm}} 實例。

2. 選取**服務認證**。然後，選取**新建認證**。

3. 請輸入容易辨識的名稱。例如，您可以將服務 ID 命名為 `activity-tracker-cos-serviceID`。 

4. 選取**撰寫者**角色。

5. 按一下**新增**。

    即會建立新的服務 ID，並將其新增至清單。 

    **附註：**在 {{site.data.keyword.cloud_notm}} 中建立且透過 IAM 使用者介面列出的服務 ID 具有通用名稱。IAM 使用者介面中的服務 ID 名稱，會對映至您透過 COS 服務 ID 使用者介面在此步驟中建立的 **iam_apikey_name** 欄位值。
    
6. [選用] 若要鎖定服務 ID 以防止刪除，請從功能表列中，按一下**管理** &gt; **存取權 (IAM)**。搜尋服務 ID。然後，選取動作**鎖定**。


對於您剛建立的服務 ID，按一下**檢視認證**。您可以查看與服務 ID 相關的資訊。 

* 複製 API 金鑰。這是針對欄位 **apikey** 設定的值。
* 複製資源實例 ID。這是針對欄位 **resource_instance_id** 設定的值。
* 複製 **iam_apikey_name** 欄位的值。


## 步驟 5. 將服務 ID 限制為僅具有儲存區的寫入許可權
{: #archiving_step5}

如果您想要將服務 ID 限制為僅具有儲存區的寫入許可權，請完成下列步驟：

1. 從 COS 使用者介面中，選取儲存區。

2. 從儲存區功能表中，選取**原則**。即會開啟*儲存區存取原則* 頁面。

3. 選取**服務 ID**。

4. 在**選取服務 ID** 欄位中，尋找具有下列名稱的服務 ID：**auto-generated-serviceId-<ID>，這是 iam_apikey_name value 的一部分。

5. 選取服務 ID。然後，在**存取原則**中，選取**撰寫者**。

6. 按一下**建立存取原則**。



## 步驟 6. 選取端點
{: #archiving_step6}

端點會定義要在其中尋找儲存區的位置。有不同的端點，視地區及備援類型而定。如需相關資訊，請參閱[選取地區及端點](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints)。

請完成下列步驟來取得儲存區的端點：

1. 登入 {{site.data.keyword.cloud_notm}} 帳戶。

    按一下 [{{site.data.keyword.cloud_notm}} 儀表板 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/login){:new_window}，以啟動 {{site.data.keyword.cloud_notm}} 儀表板。

	在使用您的使用者 ID 和密碼登入之後，「{{site.data.keyword.cloud_notm}} 儀表板」即會開啟。

2. 從「儀表板」中，選取您計劃要在其中建立儲存區的 {{site.data.keyword.cos_full_notm}} 實例。

3. 選取**儲存區**。然後，選取您已建立要在其中保存事件的儲存區。

4. 選取**配置**。

5. 複製其中一個專用端點。 



## 步驟 7. 將 IAM 原則授與使用者來保存事件
{: #archiving_step7}

下表列出使用者必須具有的原則，以配置將事件從 {{site.data.keyword.at_full_notm}} Web 使用者介面保存至 {{site.data.keyword.cos_full_notm}} 實例中的儲存區：

| 服務                    | 角色                      | 授與的許可權            | 
|--------------------------------------|---------------------------|-------------------------------------|  
| `{{site.data.keyword.at_full_notm}}` | 平台角色：檢視者   | 容許使用者在「觀察記載」儀表板中檢視服務實例的清單。|
| `{{site.data.keyword.at_full_notm}}` | 服務角色：管理員   | 容許使用者啟動 Web 使用者介面，以及在 Web 使用者介面中檢視事件。|
{: caption="表 2. IAM 原則" caption-side="top"} 

[進一步瞭解](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam)。

請完成下列步驟，將保存事件的許可權指派給使用者： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權之使用者的列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派資源群組內的存取權**。
4. 選取資源群組。
5. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.at_full_notm}} 服務的存取權，可以選取**不存取**。

6. 選取 **IBM Log Analysis with LogDNA**.
7. 選取平台角色**檢視者**。
8. 選取服務角色**管理員**。
9. 按一下**指派**。



## 步驟 8. 配置 {{site.data.keyword.at_full_notm}} 實例的保存
{: #archiving_step8}


請完成下列步驟，配置將您的 {{site.data.keyword.at_full_notm}} 實例保存至 COS 儲存區：

1. 啟動 {{site.data.keyword.at_full_notm}} Web 使用者介面。[進一步瞭解](/docs/services/Log-Analysis-with-LogDNA/view_logs.html#view_logs_step2)。

2. 選取**配置**圖示。然後，選取**保存**。 

3. 選取 **IBM Cloud Object Storage**。

4. 設定您要在其中保存事件的儲存區、端點、API 金鑰及實例 ID。

    <table>
      <caption>表 3. COS 欄位</caption>
      <tr>
         <th>欄位</th>
         <th>值</th>
      </tr>
      <tr>
         <td>儲存區</td>
         <td>設為 COS 儲存區名稱。</td>
      </tr>
      <tr>
         <td>端點</td>
         <td>設為 COS 儲存區專用端點。</td>
      </tr>
      <tr>
         <td>API 金鑰</td>
         <td>設為與 COS 服務 ID 相關聯的 API 金鑰。</td>
      </tr>
      <tr>
         <td>實例 ID</td>
         <td>設為 COS 實例 ID。</td>
      </tr>
    </table>

5. 按一下**儲存**。


在儲存配置之後，即會保存事件，一天一次。



