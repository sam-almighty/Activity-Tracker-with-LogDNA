---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# IAM-Ereignisse
{: #at_events_iam}

Als Sicherheitsbeauftragter, Prüfer oder Manager können Sie den {{site.data.keyword.at_full_notm}}-Service verwenden, um nachzuverfolgen, wie viele Benutzer und Anwendungen mit dem {{site.data.keyword.iamlong}}-Service (IAM) in {{site.data.keyword.cloud_notm}} interagieren.
{:shortdesc}

Der {{site.data.keyword.at_full_notm}}-Service zeichnet benutzerinitiierte Aktivitäten auf, die den Status eines Service in {{site.data.keyword.cloud_notm}} ändern. Informationen zur Überwachung der Aktionen Ihrer Benutzer finden Sie unter [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started).  

Ein Initiator kann ein Benutzer, ein Service oder eine Anwendung sein.
{: tip}

## Zugriffsgruppenereignisse verwalten
{: #at_events_iam_access}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren: 

| Aktion   | Beschreibung |
|----------|---------|
| `iam-groups.group.create`   | Ein Ereignis wird generiert, wenn ein Initiator eine Zugriffsgruppe erstellt. | 
| `iam-groups.group.read`     | Ein Ereignis wird generiert, wenn ein Initiator Informationen zu Zugriffsgruppen aufruft. |
| `iam-groups.group.update`   | Ein Ereignis wird generiert, wenn ein Initiator einen Gruppennamen oder eine Beschreibung aktualisiert. |
| `iam-groups.group.delete`   | Ein Ereignis wird generiert, wenn ein Initiator eine Zugriffsgruppe löscht. |
| `iam-groups.member.add`     | Ein Ereignis wird generiert, wenn ein Initiator ein Mitglied zu einer Zugriffsgruppe hinzufügt. |
| `iam-groups.member.delete`  | Ein Ereignis wird generiert, wenn ein Initiator ein Mitglied aus einer Zugriffsgruppe entfernt. |
| `iam-groups.member.read`    | Ein Ereignis wird generiert, wenn ein Initiator die Mitgliedschaft eines Mitglieds prüft. |
| `iam-groups.rule.read`      | Ein Ereignis wird generiert, wenn ein Initiator eine Regel in einer Zugriffsgruppe anzeigt. |
| `iam-groups.rule.create`    | Ein Ereignis wird generiert, wenn ein Initiator eine Regel zu einer Zugriffsgruppe hinzufügt. |
| `iam-groups.rule.update`    | Ein Ereignis wird generiert, wenn ein Initiator den Regelnamen ändert. |
| `iam-groups.rule.delete`    | Ein Ereignis wird generiert, wenn ein Initiator eine Regel aus einer Zugriffsgruppe löscht. |
{: caption="Tabelle 1. Zugriffsgruppenaktionen verwalten" caption-side="top"} 




## Ereignisse anzeigen
{: #at_events_iam_ui}

Ereignisse sind in der Region **US-South** (USA (Süden)) verfügbar.  

Um diese Ereignisse anzuzeigen, müssen Sie [eine Instanz](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) des {{site.data.keyword.at_full_notm}}-Service in der Region **US-South** (USA (Süden)) bereitstellen. Anschließend müssen Sie [die {{site.data.keyword.at_full_notm}}-Benutzerschnittstelle öffnen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2).  


