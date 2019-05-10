---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# Ereignisse exportieren
{: #export}

Sie können Daten im JSONL-Format aus einer {{site.data.keyword.at_full_notm}}-Instanz in eine lokale Datei exportieren. Sie können Protokolle programmgesteuert oder aus der IBM Log Analysis-Webbenutzerschnittstelle exportieren.
{:shortdesc}

Berücksichtigen Sie die folgenden Informationen, wenn Sie Protokolldaten exportieren: 
* Sie exportieren einen Satz von Ereigniseinträgen. Um den Datensatz, den Sie exportieren möchten, zu definieren, können Sie Filter und Suchen anwenden. Sie können auch den Zeitraum angeben.  
* Wenn Sie Ereignisse aus der Webbenutzerschnittstelle exportieren, erhalten Sie eine E-Mail an Ihre E-Mail-Adresse mit einem Link zu einer komprimierten Datei, die die Daten enthält. Um diese Daten abzurufen, müssen Sie auf den Link klicken und die komprimierte Datei herunterladen. 
* Wenn Sie Ereignisse programmgesteuert exportieren, können Sie auswählen, ob eine E-Mail gesendet werden soll oder ob Ereignisse in Ihr Terminal gestreamt werden sollen. 
* Die komprimierte Datei mit den Daten, die Sie exportieren möchten, ist maximal 48 Stunden verfügbar.  
* Sie können maximal 10.000 Zeilen exportieren. 



## Voraussetzungen
{: #export_prereqs}

Prüfen Sie zunächst, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt. [Wechseln Sie dann zur Webbenutzerschnittstelle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch). 

**Hinweis:** Sie müssen ein Administrator des {{site.data.keyword.at_full_notm}}-Service sein, ein Administrator der {{site.data.keyword.at_full_notm}}-Instanz sein oder über IAM-Berechtigungen für das Konto verfügen, um Richtlinien verwalten zu können. 

In der folgenden Tabelle sind die mindestens erforderlichen Richtlinien aufgeführt, über die ein Benutzer verfügen muss, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten und um Ereignisse anzuzeigen, zu suchen und zu filtern. 

| Rolle                      | Erteilte Berechtigung                  |
|---------------------------|-------------------------------|  
| Plattformrolle: `Anzeigeberechtigter`     | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| Servicerolle: `Leseberechtigter`      | Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen.                             |
{: caption="Tabelle 1. IAM-Richtlinien" caption-side="top"} 

Weitere Informationen zum Konfigurieren dieser Richtlinien für einen Benutzer finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events). 

**Sie müssen über einen bezahlten Serviceplan** für den {{site.data.keyword.at_full_notm}}-Service verfügen. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).  



## Schritt 1. Webbenutzerschnittstelle öffnen
{: #export_step1}

[Zur Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)


## Schritt 2. Ansicht erstellen
{: #export_step2}

[Ansicht erstellen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md)


## Schritt 3. Daten exportieren
{: #export_step3}

Wählen Sie eine der folgenden Optionen aus, um Ereignisse zu exportieren. 

### Option 1. Exportieren von Ereignissen aus der Webbenutzerschnittstelle
{: #export_ui}

Führen Sie die folgenden Schritte aus, um Daten zu exportieren: 

1. Klicken Sie auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png). 
2. Wählen Sie **Alles** oder eine Ansicht aus. 
3. Wenden Sie einen Zeitrahmen, Filter und Suchkriterien an, bis Ihnen die Einträge angezeigt werden, die Sie exportieren möchten. 
4. Klicken Sie auf **Nicht gespeicherte Ansicht**, wenn Sie in der Ansicht **Alles** beginnen. Klicken Sie auf Ihren Ansichtsnamen, wenn Sie im vorherigen Schritt eine Ansicht ausgewählt haben. 
5. Wählen Sie **Zeilen exportieren** aus. Ein neues Fenster wird geöffnet. 
6. Wählen Sie den Zeitraum aus. Wenn Sie ihn ändern müssen, klicken Sie auf den vordefinierten Zeitraum im Feld *Zu exportierenden Zeitraum ändern*. 
7. Wählen Sie **Neue Zeilen bevorzugen** oder **Ältere Zeilen bevorzugen** aus, für den Fall, dass die Exportanforderung das Zeilenlimit überschreitet. 
8. Prüfen Sie Ihre E-Mail. Sie erhalten eine E-Mail von **LogDNA** mit einem Link zum Download Ihrer exportierten Zeilen. 


### Option 2. Programmgesteuertes Exportieren von Ereignissen mithilfe der API
{: #export_api}

Führen Sie die folgenden Schritte aus, um Ereignisse programmgesteuert zu exportieren: 

1. Generieren Sie einen Serviceschlüssel.  

    **Hinweis:** Sie müssen die Rolle **Manager** für die {{site.data.keyword.at_full_notm}}-Instanz oder den Service innehaben, um diesen Schritt abzuschließen. 

    1. Starten Sie die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle. Weitere Informationen finden Sie unter [Zur {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 

    2. Wählen Sie das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png) aus. Wählen Sie dann **Organisation** aus.  

    3. Wählen Sie **API-Schlüssel** aus. 

        Sie können die erstellten Serviceschlüssel anzeigen.  

    4. Klicken Sie auf **Serviceschlüssel generieren**. 

        Ein neuer Schlüssel wird zur Liste hinzugefügt. Kopieren Sie diesen Schlüssel. 

2. Exportieren Sie Ereignisse. Führen Sie den folgenden cURL-Befehl aus: 

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    Dabei gilt:  

    * ENDPOINT stellt den Eingangspunkt des Service dar. Jede Region hat eine andere URL. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints). 
    * QUERY_PARAMETERS sind Parameter, die die Filterkriterien definieren, die auf die Exportanforderung angewendet werden. 
    * SERVICE_KEY ist der Serviceschlüssel, den Sie im vorherigen Schritt erstellt haben. 

In der folgenden Tabelle sind die Abfrageparameter aufgeführt, die Sie festlegen können: 

| Abfrageparameter | Typ       | Status     | Beschreibung |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | Erforderlich   | Startzeit. Festlegen als UNIX-Zeitmarke in Sekunden oder Millisekunden. |
| `to`        | `int32`      | Erforderlich   | Endzeit. Festlegen als UNIX-Zeitmarke in Sekunden oder Millisekunden. |
| `size`      | `string`     | Optional   | Anzahl von Protokollzeilen, die in den Bericht aufgenommen werden sollen.  | 
| `hosts`     | `string`     | Optional   | Durch Kommas getrennte Liste von Hosts. |
| `apps`      | `string`     | Optional   | Durch Kommas getrennte Liste von Anwendungen. |
| `levels`    | `string`     | Optional   | Durch Kommas getrennte Liste von Protokollebenen. |
| `query`     | `string`     | Optional   | Suchabfrage. Weitere Informationen finden Sie unter [Suchprotokolle](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6). |
| `prefer`    | `string`     | Optional   | Definiert die Protokollzeilen, die Sie exportieren möchten. Gültige Werte sind `head` für die ersten Protokollzeilen und `tail` für die letzten Protokollzeilen. Der Standardwert ist 'tail'.  |
| `email`     | `string`     | Optional   | Gibt die E-Mail mit dem für den Download verfügbaren Link Ihres Exports an. Standardmäßig werden die Protokollzeilen gestreamt. |
| `emailSubject` | `string`     | Optional   | Zum Festlegen des Betreffs der E-Mail. </br>Geben Sie `%20` für Leerzeichen an. Ein Beispielwert ist `Export%20logs`. |
{: caption="Abfrageparameter" caption-side="top"} 

Führen Sie beispielsweise den folgenden Befehl aus, um Ereignisse in das Terminal zu streamen: 

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

Sie können den folgenden Befehl ausführen, um eine E-Mail mit dem Link zum Download der Ereignisse zu senden, die im Export angegeben sind: 

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


Sie können den folgenden Befehl ausführen, um eine E-Mail mit einem angepassten Betreff zu senden: 

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

