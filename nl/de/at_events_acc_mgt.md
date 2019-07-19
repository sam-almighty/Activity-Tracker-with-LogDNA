---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# Ereignisse für die Kontoverwaltung  
{: #at_events_acc_mgt}

Als Sicherheitsbeauftragter, Prüfer oder Manager können Sie den {{site.data.keyword.at_full_notm}}-Service verwenden, um nachzuverfolgen, wie viele Benutzer und Anwendungen mit dem {{site.data.keyword.cloud_notm}}-Konto interagieren.
{:shortdesc}

Der {{site.data.keyword.at_full_notm}}-Service zeichnet benutzerinitiierte Aktivitäten auf, die den Status eines Service in {{site.data.keyword.cloud_notm}} ändern. Informationen zum Einstieg finden Sie unter [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started).  



## Ereignisse für die Verwaltung von Konten
{: #at_events_acc_mgt_account}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                               | Beschreibung |
|--------------------------------------|-------------|
| `billing.account.create`             | Ein Ereignis wird generiert, wenn Sie ein Konto bereitstellen, nachdem die Konto-ID dem Konto zugeordnet wurde. |
| `billing.account.update`             | Ein Ereignis wird generiert, wenn Sie Informationen zu dem Konto aktualisieren.  |
| `billing.account.active`             | Ein Ereignis wird generiert, wenn Sie das Konto überprüfen, d. h. ein Ereignis wird generiert, wenn das Konto aktiv wird. |
| `billing.account.subscription.create` | Ein Ereignis wird generiert, wenn Sie ein <a href="/docs/account?topic=account-accounts#subscription-account">Abonnementkonto</a> erstellen. |
{: caption="Tabelle 1. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 




## Ereignisse für die Verwaltung von Benutzern
{: #at_events_acc_mgt_users}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                               | Beschreibung |
|--------------------------------------|-------------|
| `user-management.user.create`        | Ein Ereignis wird generiert, wenn Sie eine Einladung an einen Benutzer zur Teilnahme an einem Konto senden. |
| `user-management.user.active`        | Ein Ereignis wird generiert, wenn Sie den Benutzer in dem Konto aktivieren. Wenn der Benutzer die E-Mail-Adresse überprüft, wird das Ereignis generiert. |
| `user-management.user.delete`        | Ein Ereignis wird generiert, wenn Sie einen Benutzer aus dem Konto entfernen. |
{: caption="Tabelle 2. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 




## Ereignisse für die Verwaltung von Organisationen
{: #at_events_acc_mgt_org}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                               | Beschreibung |
|--------------------------------------|-------------|
| `billing.account.org.create`         | Ein Ereignis wird generiert, wenn Sie dem Konto eine Organisation hinzufügen. |
{: caption="Tabelle 3. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 


## Ereignisse für die Verwaltung von Tags
{: #at_events_acc_mgt_resources}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                               | Beschreibung |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | Ein Ereignis wird generiert, wenn Sie einer Ressource einen Tag hinzufügen. |
| `ghost-tags.tag.detach-tag`          | Ein Ereignis wird generiert, wenn Sie einen Tag aus einer Ressource entfernen. |
{: caption="Tabelle 4. Aktionen, durch die Ereignisse generiert werden" caption-side="top"} 


## Wo wird nach Ereignissen gesucht?
{: #at_events_acc_mgt_ui}

Ereignisse sind in der Region **Frankfurt (eu-de)** verfügbar.  

Um diese Ereignisse anzuzeigen, müssen Sie [eine Instanz](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) des {{site.data.keyword.at_full_notm}}-Service in der Region **Frankfurt (eu-de)** bereitstellen. Anschließend müssen Sie [die {{site.data.keyword.at_full_notm}}-Benutzerschnittstelle öffnen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 












