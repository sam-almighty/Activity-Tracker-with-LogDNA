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

# Zur Webbenutzerschnittstelle navigieren
{: #launch}

Nachdem Sie eine Instanz des {{site.data.keyword.at_full_notm}}-Service in der {{site.data.keyword.cloud_notm}} bereitgestellt haben, können Sie Ereignisse über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle anzeigen, überwachen und verwalten.
{:shortdesc}


## Schritt 1. IAM-Richtlinien für einen Benutzer zum Anzeigen von Daten zuweisen  
{: #step1}

**Hinweis:** Sie müssen ein Administrator des {{site.data.keyword.at_full_notm}}-Service sein, ein Administrator einer {{site.data.keyword.at_full_notm}}-Instanz sein oder über IAM-Berechtigungen für das Konto verfügen, um anderen Benutzern Richtlinien zuweisen zu können. 

In der folgenden Tabelle ist die mindestens erforderliche Richtlinie aufgeführt, die einem Benutzer zugewiesen sein muss, damit er die Webbenutzerschnittstelle starten und Daten über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle anzeigen kann: 

| Rolle                      | Erteilte Berechtigung            |
|---------------------------|---------------------|
| Plattformrolle: `Anzeigeberechtigter`     | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| Servicerolle: `Leseberechtigter`      | Ermöglicht dem Benutzer, Ereignisse über die Webbenutzerschnittstelle anzuzeigen. | 
{: caption="Tabelle 1. IAM-Richtlinien" caption-side="top"} 

Weitere Informationen finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events). 


## Schritt 2. Webbenutzerschnittstelle über die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle starten
{: #launch_step2}

Sie starten die Webbenutzerschnittstelle im Kontext einer {{site.data.keyword.at_full_notm}}-Instanz über die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle.  

Führen Sie die folgenden Schritte aus, um die Webbenutzerschnittstelle zu starten: 

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird das {{site.data.keyword.cloud_notm}}-Dashboard geöffnet. 

2. Wählen Sie im Navigationsmenü **Beobachtbarkeit** aus.  

3. Wählen Sie **Activity Tracker** aus.  

    Die Liste von Instanzen, die in der {{site.data.keyword.cloud_notm}} verfügbar sind, wird angezeigt. 

4. Wählen Sie eine Instanz aus. Klicken Sie dann auf **LogDNA anzeigen**. 

Die Webbenutzerschnittstelle wird geöffnet. 


## URL der Webbenutzerschnittstelle aus der {{site.data.keyword.cloud_notm}} abrufen
{: #launch_get}

Führen Sie die folgenden Schritte in einem Terminal aus, um die URL der Webbenutzerschnittstelle abzurufen: 

1. Geben Sie die Ressourcengruppe an, in der die {{site.data.keyword.at_full_notm}}-Instanz bereitgestellt wird. 

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. Geben Sie den {{site.data.keyword.at_full_notm}}-Instanznamen an. 

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. Legen Sie den Endpunkt fest. 

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. Legen Sie das IAM-Token fest.

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **Hinweis:** Wenn Sie an einem MacOS-Terminal arbeiten, lautet der Befehl wie folgt: `export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. Legen Sie die Ressourcengruppen-ID fest. 

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. Legen Sie die URL der Webbenutzerschnittstelle in einer Variablen fest. 

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. Rufen Sie die URL der Webbenutzerschnittstelle ab. 

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

