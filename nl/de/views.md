---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# Angepasste Ansichten erstellen
{: #views.md}

In der {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle können Sie Such- und Filterkriterien anwenden, um die Ereignisse zu definieren, die in einer angepassten Ansicht angezeigt werden. {:shortdesc}


## Voraussetzungen
{: #views_prereqs}

Prüfen Sie zunächst, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt. [Wechseln Sie dann zur Webbenutzerschnittstelle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch). 

**Hinweis:** Sie müssen ein Administrator des {{site.data.keyword.at_full_notm}}-Service sein, ein Administrator der {{site.data.keyword.at_full_notm}}-Instanz sein oder über IAM-Berechtigungen für das Konto verfügen, um Richtlinien verwalten zu können. 

In der folgenden Tabelle sind die mindestens erforderlichen Richtlinien aufgeführt, über die ein Benutzer verfügen muss, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten und um Ereignisse anzuzeigen, zu suchen und zu filtern. 

| Rolle                      | Erteilte Berechtigung            |
|---------------------------|-------------------------------|  
| Plattformrolle: `Anzeigeberechtigter`     | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| Servicerolle: `Leseberechtigter`      | Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen.                             |
{: caption="Tabelle 1. IAM-Richtlinien" caption-side="top"} 

Weitere Informationen zum Konfigurieren dieser Richtlinien für einen Benutzer finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events). 



## Schritt 1. Ereignisse filtern
{: #views_step1}

Sie können Ereignisse nach Quelle, Anwendung oder Protokollebene filtern.  

* Eine Quelle kann ein Host, ein Computer, eine virtuelle Maschine oder eine Heroku-App sein. 
* Eine Anwendung stellt eine Protokolldatei, ein Programm oder einen Container dar. 
* Beispiele von Protokollebenen sind: INFO, DEBUG, ERROR

Führen Sie die folgenden Schritte aus, um Protokolle zu filtern: 

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png "Konfigurationssymbol"). 
2. Wählen Sie **Alles** oder eine Ansicht aus. 
3. Erweitern Sie **Alle Tags**, um die Liste der verfügbaren Tags anzuzeigen. Wählen Sie dann die gewünschten Tags aus. 
4. Erweitern Sie **Alle Quellen**, um die Liste der verfügbaren Quellen anzuzeigen. Wählen Sie dann die gewünschten Quellen aus. 
5. Erweitern Sie **Alle Apps**, um die Liste der verfügbaren Apps anzuzeigen. Wählen Sie dann die gewünschten Apps aus. 
6. Erweitern Sie **Alle Ebenen**, um die Liste der verfügbaren Ebenen anzuzeigen. Wählen Sie dann die gewünschten Ebenen aus. 

Beachten Sie beim Anwenden von Filtern, dass sich der Name der Ansicht in **Nicht gespeicherte Ansicht** ändert. 

**Hinweis:** In jedem Abschnitt können Sie mehrere Optionen in einer Gruppe gruppieren. Gruppieren Sie Tags, Quellen, Apps und Ebenen, um diese Gruppierungen wiederzuverwenden, wenn Sie Daten in anderen angepassten Ansichten filtern. 

Wählen Sie verschiedene Werte aus, um eine Gruppe zu erstellen. Klicken Sie dann auf **Als Gruppe speichern**. Geben Sie einen Namen für die Gruppe ein und speichern Sie sie. 


## Schritt 2. Ereignisse suchen
{: #views_step2}

Wenn Sie nach Ereignissen suchen, wendet die Suche alle Filter und Zeitabfragen an, die in dieser Ansicht konfiguriert sind. 

Sie können einfache Suchen (einzelner Begriff), Verbundsuchen (mehrere Suchbegriffe und Operatoren), Feldsuchen, falls die Protokollzeile geparst werden kann, und mehr ausführen. Weitere Informationen finden Sie in der LogDNA-Dokumentation unter [How to Search Logs ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://docs.logdna.com/docs/search){:new_window}. 

**Hinweis:** Bei AND- und OR-Operatoren muss die Groß-/Kleinschreibung beachtet und sie müssen großgeschrieben werden. 

Beachten Sie beim Anwenden von Suchkriterien, dass sich der Name der Ansicht in **Nicht gespeicherte Ansicht** ändert. 



## Schritt 3. Angepasste Ansicht erstellen
{: #views_step3}

Nachdem Sie einen Zeitrahmen, Filter und Suchkriterien auf die Ansicht **Alles** oder auf eine vorhandene angepasste Ansicht angewendet haben, führen Sie die folgenden Schritte aus, um die Ausgabe als angepasste Ansicht zu speichern: 

1. Klicken Sie in der Webbenutzerschnittstelle auf **Nicht gespeicherte Ansicht**. 
2. Wählen Sie **Als neue Ansicht speichern/Als neuen Alerts speichern** aus. Die Seite *Neue Ansicht erstellen* wird geöffnet. 
3. Geben Sie einen Namen für die Ansicht im Feld *Name* ein. 
4. Fügen Sie optional eine Kategorie hinzu. Geben Sie einen Namen ein und klicken Sie dann auf **Als neue Ansichtskategorie hinzufügen**. 
5. Hängen Sie optional einen Alert an. Ein neuer Abschnitt wird angezeigt, in dem Sie den Alert konfigurieren können. 
6. Klicken Sie auf **Ansicht speichern**. 




