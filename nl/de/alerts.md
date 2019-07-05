---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #alerts}

In der {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle können Sie Suchkriterien anwenden, um die Ereignisse zu definieren, die in einer angepassten Ansicht angezeigt werden. Anschließend können Sie einen Alert an diese Ansicht anhängen, um benachrichtigt zu werden, falls es zu dieser Bedingung kommt. Sie können einen oder mehrere Alerts an eine Ansicht anhängen. Sie können mehrere Benachrichtigungskanäle für einen Alert definieren. Sie können Alerts stumm schalten. Sie können Alerts aus einer Ansicht lösen.
{:shortdesc}


## Voraussetzungen
{: #alerts_prereqs}

* [Weitere Informationen zu Alerts](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts).

* **Sie müssen über einen bezahlten Serviceplan** für den {{site.data.keyword.at_full_notm}}-Service verfügen. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).

* Prüfen Sie, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt. In der folgenden Tabelle sind die mindestens erforderlichen Rollen aufgeführt, die ein Benutzer aufweisen muss, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten und um Ereignisse anzuzeigen, zu suchen und zu filtern.

| Rolle                      | Erteilte Berechtigung            |
|---------------------------|-------------------------------|  
| Plattformrolle: `Anzeigeberechtigter`     | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| Servicerolle: `Leseberechtigter`      | Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen.  |
{: caption="Tabelle 1. IAM-Rollen" caption-side="top"} 

Weitere Informationen zum Konfigurieren von Richtlinien für einen Benutzer finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

 


## Schritt 1. Webbenutzerschnittstelle öffnen
{: #alerts_step1}

[Zur Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)


## Schritt 2. Ansicht erstellen
{: #alerts_step2}

[Ansicht erstellen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)



## Schritt 3. [Optional] Voreinstellung (Alertvorlage) konfigurieren
{: #alerts_step3}

Um eine Alertkonfiguration mit verschiedenen Ansichten wiederzuverwenden, konfigurieren Sie eine **Alertvoreinstellung**.
{: note}

Führen Sie die folgenden Schritte aus, um eine Voreinstellung zu konfigurieren:

1. Wählen Sie in der Webbenutzerschnittstelle das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png "Administratorsymbol") aus.
2. Wählen Sie **Alerts** aus.
3. Wählen Sie **Voreinstellungsalert hinzufügen** aus.
4. Wählen Sie einen Benachrichtigungskanal aus. Die Liste der unterstützten Kanäle finden Sie unter [Alertbenachrichtigungskanäle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
5. Wählen Sie den Typ des Alerts aus. Wählen Sie den Alerttyp für das **Vorhandensein** von Ereignissen aus, um eine Benachrichtigung zu erhalten, wenn die Anzahl der in einer Ansicht angezeigten Ereignisse die erwartete Anzahl überschreitet. Wählen Sie den Alerttyp für das **Nichtvorhandensein** von Ereignissen aus, um eine Benachrichtigung zu erhalten, wenn die Anzahl der in einer Ansicht angezeigten Ereignisse die erwartete Anzahl unterschreitet oder null ist.  
5. Wählen Sie einen Benachrichtigungskanal aus. Die Liste der unterstützten Kanäle finden Sie unter [Alertbenachrichtigungskanäle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
6. Definieren Sie Schwellenwertbedingungen. 

    1. Wählen Sie eine Frequenz aus. Beispiel: 12 Stunden.

    2. Geben Sie die Anzahl von Ereigniszeilen ein, nach der Sie den Alert auslösen möchten.

    3. Wählen Sie aus, ob beide Bedingungen geprüft werden oder nur eine.

7. Fügen Sie die Details für den ausgewählten Benachrichtigungskanal hinzu.

    Fügen Sie beispielsweise für den E-Mail-Benachrichtigungskanal einen oder mehrere Empfänger und optional eine Zeitzone hinzu.

8. Klicken Sie auf **Alert speichern**.



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
5. Wählen Sie den Typ des Alerts aus. Wählen Sie den Alerttyp für das **Vorhandensein** von Ereignissen aus, um eine Benachrichtigung zu erhalten, wenn die Anzahl der in einer Ansicht angezeigten Ereignisse die erwartete Anzahl überschreitet. Wählen Sie den Alerttyp für das **Nichtvorhandensein** von Ereignissen aus, um eine Benachrichtigung zu erhalten, wenn die Anzahl der in einer Ansicht angezeigten Ereignisse die erwartete Anzahl unterschreitet oder null ist.  
6. Definieren Sie Schwellenwertbedingungen.

    1. Wählen Sie eine Frequenz aus. Beispiel: 12 Stunden.

    2. Geben Sie die Anzahl von Ereigniszeilen ein, nach der Sie den Alert auslösen möchten.

    3. Wählen Sie aus, ob beide Bedingungen geprüft werden oder nur eine.

7. Fügen Sie die Details für den ausgewählten Benachrichtigungskanal hinzu.

    Fügen Sie beispielsweise für den E-Mail-Benachrichtigungskanal einen oder mehrere Empfänger und optional eine Zeitzone hinzu.

8. Klicken Sie auf **Alert speichern**.



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












