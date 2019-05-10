---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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

# Instanz bereitstellen
{: #provision}

Bevor Sie Ereignisdaten mit {{site.data.keyword.at_full_notm}} überwachen und verwalten können, müssen Sie eine Instanz des Service in {{site.data.keyword.cloud_notm}} bereitstellen.
{:shortdesc}

Um eine {{site.data.keyword.at_full_notm}}-Instanz in einer Public Cloud-Region bereitzustellen, müssen Sie den Serviceplan auswählen, der der Instanz zugeordnet ist, die Region, in der Ihre Protokolle gesammelt werden, sowie den Plan, der die Aufbewahrungszeit für Ihre Protokolle bestimmt. Sie können zwischen Aufbewahrungszeiträumen von 7, 14, oder 30 Tagen auswählen. 

Alternativ bietet {{site.data.keyword.at_full_notm}} einen Plan `Lite` an, den Sie zum Anzeigen Ihrer Ereignisse auf ihrem Weg durch das System verwenden können. Sie können Ereignisse mithilfe von Ereignis-Tailing anzeigen. Sie können außerdem Filter zur Vorbereitung von Upgrades auf einen Plan mit längeren Aufbewahrungszeiträumen konzipieren. Dieser Plan hat einen Aufbewahrungsdauer von 0 Tagen. 

Um eine Serviceinstanz bereitzustellen, muss Ihre Benutzer-ID über Berechtigungen für die Bereitstellung eines Service in einer Ressourcengruppe verfügen. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups).
{: tip}


## Instanz über das Dashboard 'Beobachtbarkeit' bereitstellen
{: #provision_ui}

Führen Sie die folgenden Schritte aus, um eine Instanz über das Dashboard 'Beobachtbarkeit' in der {{site.data.keyword.cloud_notm}} bereitzustellen: 

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle geöffnet. 

2. Navigieren Sie zum Menüsymbol ![Menüsymbol](../../icons/icon_hamburger.svg). Wählen Sie dann **Beobachtbarkeit** aus, um auf das Dashboard *Beobachtbarkeit* zuzugreifen. 

3. Wählen Sie **Activity Tracker** aus und klicken Sie dann auf **Instanz erstellen**.  

4. Geben Sie einen Namen für die Serviceinstanz ein. 

5. Wählen Sie die Region aus, in der Sie die Instanz bereitstellen möchten. 

6. Wählen Sie eine Ressourcengruppe aus.  

    Standardmäßig wird die Ressourcengruppe **Standard** festgelegt. 

    **Hinweis:** Wenn Sie keine Ressourcengruppe auswählen können, prüfen Sie, dass Sie über Bearbeitungsberechtigungen für die Ressourcengruppe verfügen, in der Sie die Instanz bereitstellen möchten. 

7. Wählen Sie den Serviceplan `Lite` aus.  

    Der Plan 'Lite' ist standardmäßig festgelegt. 

8. Klicken Sie auf **Erstellen**. 

Nachdem Sie eine Instanz bereitgestellt haben, wird das *Activity Tracker*-Dashboard geöffnet.  

Öffnen Sie anschließend die Webbenutzerschnittstelle, um Ereignisse in Ihrem Konto zu verwalten. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events.md#view_events.md). 



## Instanz über den Katalog bereitstellen
{: #provision_catalog}

Führen Sie die folgenden Schritte aus, um eine Instanz von {{site.data.keyword.at_full_notm}} über den {{site.data.keyword.cloud_notm}}-Katalog bereitzustellen: 

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle geöffnet. 

2. Klicken Sie auf **Katalog**. Die Liste von Services, die in der {{site.data.keyword.cloud_notm}} verfügbar sind, wird geöffnet. 

3. Um die angezeigte Liste von Services zu filtern, wählen Sie die Kategorie **Entwicklertools** aus. 

4. Klicken Sie auf die **{{site.data.keyword.at_full_notm}}**-Kachel.  

5. Geben Sie einen Namen für die Serviceinstanz ein. 

6. Wählen Sie eine Ressourcengruppe aus.  

    Standardmäßig ist die Ressourcengruppe **Standard** festgelegt. 

    **Hinweis:** Wenn Sie keine Ressourcengruppe auswählen können, prüfen Sie, dass Sie über Bearbeitungsberechtigungen für die Ressourcengruppe verfügen, in der Sie die Instanz bereitstellen möchten. 

7. Wählen Sie den Serviceplan `Lite` aus.  

    Der Plan 'Lite' ist standardmäßig festgelegt. 

8. Klicken Sie auf **Erstellen**. 

Nachdem Sie eine Instanz bereitgestellt haben, wird das *Activity Tracker*-Dashboard geöffnet.  

Öffnen Sie anschließend die Webbenutzerschnittstelle, um Ereignisse in Ihrem Konto zu verwalten. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch). 


## Instanz über die Befehlszeilenschnittstelle bereitstellen
{: #provision_cli}

Führen Sie die folgenden Schritte aus, um eine Instanz von {{site.data.keyword.at_full_notm}} über die Befehlszeile bereitzustellen: 

1. [Voraussetzung] Installation der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle. [Weitere Informationen](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli). 

   Wenn die Befehlszeilenschnittstelle installiert ist, fahren Sie mit dem nächsten Schritt fort. 

2. Melden Sie sich bei der Region in der {{site.data.keyword.cloud_notm}} an, in der Sie die Instanz bereitstellen möchten. Führen Sie den folgenden Befehl aus: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login). 

3. Geben Sie die Ressourcengruppe an, in der Sie die Instanz bereitstellen möchten. Führen Sie den folgenden Befehl aus: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target). 

    Standardmäßig ist die Ressourcengruppe `Standard` festgelegt. 

4. Erstellen Sie die Instanz. Führen Sie den Befehl [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create) aus: 

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    Dabei gilt: 

    * NAME ist der Name der Instanz. 

    * Der Wert *logdnaat* ist der Name des {{site.data.keyword.at_full_notm}}-Service in der {{site.data.keyword.cloud_notm}}. 

    * SERVICE_PLAN_NAME ist der Typ von Plan. Gültige Werte sind *lite*, *7-days*, *14-days*, *30-days*. 
    
    * LOCATION ist die Region, in der die LogDNA-Instanz erstellt wird. Ein gültiger Wert ist beispielsweise *us-south* (USA (Süden)). 

    
Um beispielsweise eine Instanz mit dem 7-Tage-Aufbewahrungsplan bereitzustellen, führen Sie den folgenden Befehl aus: 

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



