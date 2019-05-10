---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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
{: #view_events.md}

Nachdem Sie eine Instanz des {{site.data.keyword.at_full_notm}}-Service in der {{site.data.keyword.cloud_notm}} bereitgestellt haben, können Sie Ereignisse über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle anzeigen.
{:shortdesc}


## Voraussetzungen
{: #view_events_prereqs}

Prüfen Sie zunächst, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt.  

**Hinweis:** Sie müssen ein Administrator des {{site.data.keyword.at_full_notm}}-Service sein, ein Administrator der {{site.data.keyword.at_full_notm}}-Instanz sein oder über IAM-Berechtigungen für das Konto verfügen, um Richtlinien verwalten zu können. 

In der folgenden Tabelle sind die mindestens erforderlichen Richtlinien aufgeführt, über die ein Benutzer verfügen muss, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten und um Ereignisse anzuzeigen. 

| Rolle                      | Erteilte Berechtigung            |
|---------------------------|-------------------------------|  
| Plattformrolle: `Anzeigeberechtigter`     | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| Servicerolle: `Leseberechtigter`      | Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen.                             |
{: caption="Tabelle 1. IAM-Richtlinien" caption-side="top"} 

Weitere Informationen zum Konfigurieren dieser Richtlinien für einen Benutzer finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events). 


## Ereignisse über die Webbenutzerschnittstelle anzeigen
{: #view_events_step1}

Führen Sie die folgenden Schritte aus, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten: 

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird das {{site.data.keyword.cloud_notm}}*-Dashboard* geöffnet. 

2. Navigieren Sie zum Menüsymbol ![Menüsymbol](../../icons/icon_hamburger.svg) und wählen Sie **Beobachtbarkeit** aus.  

3. Wählen Sie **Activity Tracker** aus.  

    Die Liste von {{site.data.keyword.at_full_notm}}-Instanzen wird angezeigt. 

    **Hinweis:** Es gibt eine Instanz pro Region. 

4. Wählen Sie die Instanz in der Region aus, in der Sie Ereignisse anzeigen möchten. Klicken Sie dann auf **LogDNA anzeigen**. 

Die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle wird mit der Ansicht **Alles** geöffnet. In dieser Ansicht können Sie die Ereignisse in Ihrem Konto für ausgewählte Region sehen. 

**Hinweis:** Wenn Sie einen Plan `Lite` haben und die gesuchten Ereignisse nicht finden können, müssen Sie unter Umständen auf einen bezahlten Plan upgraden, um auch nach älteren Ereignissen suchen zu können. Die Anzahl der Tage, in denen nach Ereignissen gesucht werden kann, hängt von dem ausgewählten Plan ab. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 


## Standardansicht anpassen
{: #view_events_step2}

Im Abschnitt **BENUTZERVORGABEN** können Sie die Reihenfolge der Datenfelder ändern, die in einer Zeile angezeigt werden. 

Führen Sie die folgenden Schritte aus, um das Format einer Ereigniszeile zu ändern: 

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png "Administratorsymbol"). 
2. Wählen Sie **BENUTZERVORGABEN** aus. Ein neues Fenster wird geöffnet. 
3. Wählen Sie **Protokollformat** aus. 
4. Ändern Sie den Abschnitt *Zeilenformat* Ihren Anforderungen entsprechend. Ziehen Sie die Felder. 




## Ereignis im Kontext anzeigen
{: #view_events_step3}

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
{: #view_events_step4}


Führen Sie die folgenden Schritte aus, um ein Ereignis in die Zwischenablage zu kopieren:  

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png "Konfigurationssymbol"). 
2. Wählen Sie **Alles** oder eine angepasste Ansicht aus. 
3. Geben Sie eine Zeile an, die Sie untersuchen möchten. 
4. Erweitern Sie die Ereigniszeile.  

    Informationen zu Zeilenkennungen, Tags und Bezeichnungen werden angezeigt. 

5. Klicken Sie auf **In Zwischenablage kopieren**, um das Ereignis in die Zwischenablage zu kopieren. 

Wenn Sie das Ereignis abschließend untersucht haben, klicken Sie auf **Schließen**, um die Zeile zu schließen. 




