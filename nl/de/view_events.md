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


# Ereignisse anzeigen
{: #view_events}

Nachdem Sie eine Instanz des {{site.data.keyword.at_full_notm}}-Service in der {{site.data.keyword.cloud_notm}} bereitgestellt haben, können Sie Ereignisse über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle anzeigen. Sie können Ereignisse in Ihrer Ortszeit anzeigen.
{:shortdesc}


## Ereignisse anzeigen
{: #view_events_step1}

Führen Sie die folgenden Schritte aus, um Ereignisse anzuzeigen:

1. Prüfen Sie, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt. 

    In der folgenden Tabelle sind die mindestens erforderlichen Rollen aufgeführt, die ein Benutzer aufweisen muss, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten und um Ereignisse anzuzeigen, zu suchen und zu filtern.

    <table>
      <caption>Tabelle 1. IAM-Rollen</caption>
      <tr>
        <th>Rolle</th>
        <th>Erteilte Berechtigung</th>
      </tr>
      <tr>
        <td>Plattformrolle: `Anzeigeberechtigter`</td>
        <td>Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard *Beobachtbarkeit* anzuzeigen.</td>
      </tr>
      <tr>
        <td>Servicerolle: `Leseberechtigter`</td>
        <td>Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen, zu durchsuchen und zu filtern.</td>
      </tr>
    </table>

    Weitere Informationen zum Konfigurieren von Richtlinien für einen Benutzer finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

2. [Zur Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)

3. Klicken Sie auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png).

4. Wählen Sie **Alles** aus, um alle Ereignisse anzuzeigen, oder wählen Sie eine Ansicht aus. 

Sie können Ereignisse über die von Ihnen ausgewählte Ansicht anzeigen.



## Teilmenge der Ereignisse durch Anwendungen einer Suchabfrage anzeigen
{: #view_events_step2}

Sie können die Ereignisse auswählen, die in einer Ansicht angezeigt werden, indem Sie eine Suchabfrage anwenden. Sie können diese Ansicht für eine spätere Wiederverwendung speichern. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2).

 


## Teilmenge der Ereignisse durch Anwendungen eines Zeitrahmens anzeigen
{: #view_events_step3}

Sie können die Ereignisse auswählen, die in einer Ansicht angezeigt werden, indem Sie einen Zeitrahmen anwenden.

Sie können eine Zeitmarke anwenden, indem Sie eine absolute Zeit, eine relative Zeit oder einen Zeitbereich angeben.

Führen Sie die folgenden Schritte aus, um zu einer bestimmten Zeit zu wechseln:
1. [Zur Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)
2. Klicken Sie auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png).
3. Wählen Sie **Alles** oder eine Ansicht aus.
4. Geben Sie eine Zeitabfrage ein. Sie haben die Auswahl zwischen den folgenden Optionen:

    * Geben Sie eine absolute Zeit ein, um zu einem Zeitpunkt in Ihren Ereignissen zu wechseln, z. B. `May 20 7:00pm`.
    
    * Geben Sie eine relative Zeit ein, beispielsweise `2 days ago`, `today at 12am` oder `an hour ago`. 

    * Geben Sie einen Zeitraum ein, beispielsweise `yesterday 10am to yesterday 11am`, `last fri 4:30pm to 11/12 1 AM`, `last wed 4:30pm to 23/05 1 AM` oder `May 20 10am to May 22 10am`. Stellen Sie sicher, dass die Angabe `to` enthalten ist, um die Anfangszeitmarke von der Endzeitmarke zu trennen. 

5. Drücken Sie die Eingabetaste.

    Möglicherweise wird die folgende Fehlernachricht angezeigt: `Die Anforderung nimmt mehr Zeit in Anspruch als erwartet. Warten Sie einige Minuten, während die Anforderung weiter verarbeitet wird, und aktualisieren Sie dann den Browser. Wiederholen Sie den Vorgang. ` Dieser Fehler wird möglicherweise ausgegeben, wenn für den von Ihnen angegebenen Zeitrahmen keine anzuzeigenden Ereignisse verfügbar sind. Ändern Sie die Zeitabfrage und wiederholen Sie den Vorgang.



## Ereignis im Kontext anzeigen
{: #view_events_step4}

Sie können die Ereigniszeilen jederzeit im Kontext anzeigen.

Führen Sie die folgenden Schritte aus: 

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png "Konfigurationssymbol").
2. Wählen Sie **Alles** oder eine angepasste Ansicht aus.
3. Geben Sie eine Zeile an, die Sie untersuchen möchten.
4. Erweitern Sie die Ereigniszeile. 

    Informationen zu Zeilenkennungen, Tags und Bezeichnungen werden angezeigt.

5. Klicken Sie auf **In Kontext anzeigen**, um die Ereigniszeile im Kontext anderer Einträge von diesem Host, dieser App oder beiden anzuzeigen.

Wenn Sie das Ereignis abschließend untersucht haben, klicken Sie auf **Schließen**, um die Zeile zu schließen.



## Ereignis in Zwischenablage kopieren
{: #view_events_step5}


Führen Sie die folgenden Schritte aus, um ein Ereignis in die Zwischenablage zu kopieren: 

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png "Konfigurationssymbol").
2. Wählen Sie **Alles** oder eine angepasste Ansicht aus.
3. Geben Sie eine Zeile an, die Sie untersuchen möchten.
4. Erweitern Sie die Ereigniszeile. 

    Informationen zu Zeilenkennungen, Tags und Bezeichnungen werden angezeigt.

5. Klicken Sie auf **In Zwischenablage kopieren**, um das Ereignis in die Zwischenablage zu kopieren.

Wenn Sie das Ereignis abschließend untersucht haben, klicken Sie auf **Schließen**, um die Zeile zu schließen.




