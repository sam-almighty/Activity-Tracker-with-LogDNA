---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# Serviceinstanzereignisse  
{: #at_events_rc}

Als Sicherheitsbeauftragter, Prüfer oder Manager können Sie den {{site.data.keyword.at_full_notm}}-Service verwenden, um nachzuverfolgen, wie viele Benutzer und Anwendungen mit den {{site.data.keyword.cloud_notm}}-Services interagieren.
{:shortdesc}

Der {{site.data.keyword.at_full_notm}}-Service zeichnet benutzerinitiierte Aktivitäten auf, die den Status eines Service in {{site.data.keyword.cloud_notm}} ändern. Informationen zur Überwachung der Aktionen Ihrer Benutzer finden Sie unter [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 


## Ereignisse für die Bereitstellung und Verwaltung von Serviceinstanzen
{: #rc_provision}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                         | Beschreibung |
|--------------------------------|---------|
| `service_name.instance.create` | Ein Ereignis wird generiert, wenn Sie eine Serviceinstanz bereitstellen. |
| `service_name.instance.update` | Ein Ereignis wird generiert, wenn Sie eine Serviceinstanz umbenennen oder wenn Sie den Serviceplan ändern. |
| `service_name.instance.delete` | Ein Ereignis wird generiert, wenn eine Serviceinstanz gelöscht wird. |
{: caption="Tabelle 1. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 


##  Ereignisse zum Verwalten von Aliasnamen, die einer Serviceinstanz zugeordnet sind
{: #rc_alias}

Ein Aliasname ist eine Verbindung zwischen Ihrem durch IAM verwalteten Service innerhalb einer Ressourcengruppe und einer Anwendung innerhalb einer Organisation oder eines Bereichs.

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                         | Beschreibung |
|--------------------------------|---------|
| `service_name.alias.create` | Ein Ereignis wird generiert, wenn ein Aliasname für eine Instanz erstellt wird. |
| `service_name.alias.update` | Ein Ereignis wird generiert, wenn ein Aliasname für eine Instanz aktualisiert wird. |
| `service_name.alias.delete` | Ein Ereignis wird generiert, wenn ein Aliasname für eine Instanz gelöscht wird. |
{: caption="Tabelle 2. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 


##  Ereignisse zum Verwalten von Serviceberechtigungsnachweisen, die einer Serviceinstanz zugeordnet sind
{: #rc_keys}

Durch einen Serviceberechtigungsnachweis werden die erforderlichen Informationen bereitgestellt, um eine Anwendung mit einer Serviceinstanz zu verbinden. 

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                         | Beschreibung |
|--------------------------------|---------|
| `service_name.key.create` | Ein Ereignis wird generiert, wenn ein API-Schlüssel für eine Serviceinstanz über den Abschnitt *Serviceberechtigungsnachweise* der Benutzerschnittstelle der Serviceinstanz erstellt wird. |
| `service_name.key.delete` | Ein Ereignis wird generiert, wenn ein API-Schlüssel, der einer Serviceinstanz zugeordnet ist, aus dem Abschnitt *Serviceberechtigungsnachweise* der Benutzerschnittstelle der Serviceinstanz gelöscht wird. |
{: caption="Tabelle 3. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 



##  Ereignisse für das Binden und das Aufheben einer Bindung einer Serviceinstanz an eine App
{: #rc_bind}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                         | Beschreibung |
|--------------------------------|---------|
| `service_name.binding.create` | Ein Ereignis wird generiert, wenn Sie eine Serviceinstanz an eine Anwendung binden. |
| `service_name.binding.delete` | Ein Ereignis wird generiert, wenn Sie die Bindung einer Serviceinstanz an eine Anwendung aufheben. |
{: caption="Tabelle 4. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 



## Wo wird nach Ereignissen gesucht?
{: #rc_ui}

Ereignisse sind in der Region **Frankfurt (eu-de)** verfügbar.  

Um diese Ereignisse anzuzeigen, müssen Sie [eine Instanz](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) des {{site.data.keyword.at_full_notm}}-Service in der Region **Frankfurt (eu-de)** bereitstellen. Anschließend müssen Sie [die {{site.data.keyword.at_full_notm}}-Benutzerschnittstelle öffnen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 



## Ereignisse analysieren
{: #rc_analyze}

**Aktion: service_name.instance.delete**

Beachten Sie beim Löschen einer Serviceinstanz die folgenden Informationen:
* Weitere Aktionen werden automatisch ausgelöst, um IAM-Berechtigungen zu bereinigen. Durch diese Aktionen werden Richtlinien entfernt, die für Benutzer und Service-IDs in dem Konto konfiguriert sind, um mit der Serviceinstanz zu arbeiten. 
* Der Initiator dieser Aktionen ist eine {{site.data.keyword.IBM_notm}}-Service-ID.


Wenn die gelöschte Serviceinstanz keine für Benutzer und Service-IDs konfigurierten IAM-Richtlinien aufweist, melden die Ereignisse, die für eine dieser Ressourcen automatisch generiert werden, das Ergebnis `failure` mit einem Ergebniscode von `404`. Das folgende Beispiel zeigt die Ereignisse, die generiert werden, wenn eine Serviceinstanz, für die keine Richtlinien im Konto konfiguriert sind, gelöscht wird:

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



