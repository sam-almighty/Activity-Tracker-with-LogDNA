---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# Alerts konfigurieren
{: #alerts.md}

In der {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle können Sie Such- und Filterkriterien anwenden, um die Ereignisse zu definieren, die in einer angepassten Ansicht angezeigt werden. Anschließend können Sie einen Alert an eine Ansicht anhängen, um benachrichtigt zu werden. Sie können einen oder mehrere Alerts an eine Ansicht anhängen. Sie können mehrere Benachrichtigungskanäle für einen Alert definieren. Sie können Alerts stumm schalten. Sie können Alerts aus einer Ansicht lösen.
{:shortdesc}


Sie können alle folgenden Bedingungen für einen Alert konfigurieren: 

* *Frequenz*: Geben Sie an, wie oft ein Alert ausgelöst werden soll. Gültige Werte sind: 30 Sekunden, 1 Minute, 5 Minuten, 15 Minuten, 30 Minuten, 1 Stunde, 6 Stunden, 12 Stunden, 24 Stunden
* *Ereigniszeilenzähler*: Geben Sie die Anzahl von Ereigniszeilen an, die mit den Filter- und Suchkriterien der Ansicht übereinstimmen. Wenn die angegebene Anzahl von Ereigniszeilen erreicht wird, wird ein Alert ausgelöst. 

Sie können entscheiden, ob beide Bedingungen geprüft werden sollen oder nur eine. Falls beide Bedingungen festgelegt sind, wird ein Alert ausgelöst, wenn einer der Schwellenwerte erreicht wird.  

Sie können beispielsweise einen Alert konfigurieren, der nach 30 Sekunden ausgelöst wird oder wenn 100 Ereigniszeilen erreicht wurden, die mit den Filter- und Suchkriterien der Ansicht übereinstimmen. 

Sie können mehrere Benachrichtigungskanäle konfigurieren. Gültige Kanäle sind: `email`, `Slack`, `PagerDuty`, `Webhook`, `OpsGenie`, `Datadog`, `AppOptics`, `VictorOps`. 

Sie können auch eine **Voreinstellung** definieren. Eine Voreinstellung ist eine Alertvorlage, die Sie an eine Reihe von Ansichten anhängen können.  

Ein Klingelsymbol wird mit der Ansicht angezeigt, um darauf hinzuweisen, dass dieser Ansicht ein Alert angehängt ist. 


## Voraussetzungen
{: #views_prereqs}

Prüfen Sie zunächst, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt.  

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
{: #alerts_step1}

[Zur Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)


## Schritt 2. Ansicht erstellen
{: #alerts_step2}

[Ansicht erstellen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md)



## Schritt 3. [Optional] Voreinstellung (Alertvorlage) konfigurieren
{: #alerts_step3}

Um eine Alertkonfiguration mit verschiedenen Ansichten wiederzuverwenden, konfigurieren Sie eine **Alertvoreinstellung**.
{: note}

Führen Sie die folgenden Schritte aus, um eine Voreinstellung zu konfigurieren: 

1. Wählen Sie in der Webbenutzerschnittstelle das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png "Administratorsymbol") aus. 
2. Wählen Sie **Alerts** aus. 
3. Wählen Sie **Voreinstellungsalert hinzufügen** aus. 
4. Wählen Sie einen Benachrichtigungskanal aus.  
5. Definieren Sie Schwellenwertbedingungen. 

    1. Wählen Sie eine Frequenz aus. Beispiel: 12 Stunden. 

    2. Geben Sie die Anzahl von Ereigniszeilen ein, nach der Sie den Alert auslösen möchten. 

    3. Wählen Sie aus, ob beide Bedingungen geprüft werden oder nur eine. 

6. Fügen Sie die Details für den ausgewählten Benachrichtigungskanal hinzu. 

    Fügen Sie beispielsweise für den E-Mail-Benachrichtigungskanal einen oder mehrere Empfänger und optional eine Zeitzone hinzu. 

7. Klicken Sie auf **Alert speichern**. 



## Schritt 4. Alert konfigurieren
{: #alerts_step4}

Wählen Sie eine der folgenden Optionen aus, um einen Alert an eine Ansicht anzuhängen: 

### Option 1. Konfigurieren eines Alerts mithilfe einer Voreinstellung
{: #alerts_step4_preset}

Führen Sie die folgenden Schritte aus, um eine Voreinstellung an eine Ansicht anzuhängen: 

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png). 
2. Klicken Sie auf den Namen der Ansicht, an die Sie einen Alert anhängen möchten. Wählen Sie dann **Alert anhängen** aus. 
3. Wählen Sie eine Voreinstellung aus, um eine Alertdefinition wiederzuverwenden.  
4. Klicken Sie auf **Alert speichern**.  




### Option 2. Konfigurieren eines ansichtsspezifischen Alerts
{: #alerts_step4_view}

Führen Sie die folgenden Schritte aus, um einen Alert an eine Ansicht anzuhängen: 

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png). 
2. Klicken Sie auf den Ansichtsnamen. Wählen Sie dann **Alert anhängen** aus. 
3. Wählen Sie **Ansichtsspezifischer Alert** aus. 
4. Wählen Sie einen Benachrichtigungskanal aus.  
5. Definieren Sie Schwellenwertbedingungen. 

    1. Wählen Sie eine Frequenz aus. Beispiel: 12 Stunden. 

    2. Geben Sie die Anzahl von Ereigniszeilen ein, nach der Sie den Alert auslösen möchten. 

    3. Wählen Sie aus, ob beide Bedingungen geprüft werden oder nur eine. 

6. Fügen Sie die Details für den ausgewählten Benachrichtigungskanal hinzu. 

    Fügen Sie beispielsweise für den E-Mail-Benachrichtigungskanal einen oder mehrere Empfänger und optional eine Zeitzone hinzu. 

7. Klicken Sie auf **Alert speichern**. 



## Voreinstellung löschen (Alertvorlage)
{: #alerts_delete_preset}

Führen Sie die folgenden Schritte aus, um eine Voreinstellung zu löschen: 

1. Wählen Sie in der Webbenutzerschnittstelle das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png "Administratorsymbol") aus. 
2. Wählen Sie **Alerts** aus. 
3. Bewegen Sie den Mauszeiger über die Schaltfläche *Bearbeiten* der Voreinstellung, die Sie löschen möchten. Die Option *Löschen* wird angezeigt. 
4. Wählen Sie **Löschen** aus. 
5. Bestätigen Sie, dass Sie die Voreinstellung löschen möchten. Klicken Sie auf **Löschen**. 

## Ansichtsspezifischen Alert von einer Ansicht abhängen
{: #alerts_delete_view}

Führen Sie die folgenden Schritte aus, um eine Voreinstellung abzuhängen: 

1. Wählen Sie in der Webbenutzerschnittstelle das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png "Administratorsymbol") aus. 
2. Wählen Sie **Alerts** aus. 
3. Bewegen Sie den Mauszeiger über die Schaltfläche *Bearbeiten* des Alerts, den Sie löschen möchten. Die Option *Löschen* wird angezeigt. 
4. Wählen Sie **Zuordnung aufheben** aus. 
5. Bestätigen Sie, dass Sie den Alert löschen möchten. Klicken Sie auf **Zuordnung aufheben**. 












