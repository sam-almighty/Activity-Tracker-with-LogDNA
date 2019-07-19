---

copyright:
  years: 2019
lastupdated: "2019-05-21"

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

Mit IAM können Sie Benutzer für beide Plattformservices sicher authentifizieren und den Zugriff auf Ressourcen konsistent in {{site.data.keyword.cloud_notm}} steuern. [Weitere Informationen](/docs/iam?topic=iam-iamoverview).


Der {{site.data.keyword.at_full_notm}}-Service zeichnet benutzerinitiierte Aktivitäten auf, die den Status eines Service in {{site.data.keyword.cloud_notm}} ändern. Informationen zur Überwachung der Aktionen Ihrer Benutzer finden Sie unter [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Ein Initiator kann ein Benutzer, ein Service oder eine Anwendung sein.


## Ereignisse für Zugriffsgruppen
{: #at_events_iam_access}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                      | Beschreibung |
|-----------------------------|---------|
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



## Richtlinienereignisse
{: #at_events_iam_policies}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                 | Beschreibung |
|------------------------|---------|
| `iam-am.policy.create` | Ein Ereignis wird generiert, wenn ein Initiator eine Richtlinie zu einer Benutzer- oder Zugriffsgruppe hinzufügt. |
| `iam-am.policy.delete` | Ein Ereignis wird generiert, wenn ein Initiator Berechtigungen für eine Richtlinie einer Benutzer- oder Zugriffsgruppe modifiziert. |
| `iam-am.policy.update` | Ein Ereignis wird generiert, wenn ein Initiator eine Richtlinie löscht, die einer Benutzer- oder Zugriffsgruppe zugewiesen ist. |
{: caption="Tabelle 5. Richtlinienaktionen verwalten" caption-side="top"} 



## Ereignisse für Service-IDs
{: #at_events_iam_serviceids}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion | Beschreibung |
|----------|---------|
| `iam-identity.account-serviceid.create` | Ein Ereignis wird generiert, wenn ein Initiator eine Service-ID erstellt.  | 
| `iam-identity.account-serviceid.update` | Ein Ereignis wird generiert, wenn ein Initiator eine Service-ID umbenennt oder dessen Beschreibung ändert. | 
| `iam-identity.account-serviceid.delete` | Ein Ereignis wird generiert, wenn ein Initiator eine Service-ID löscht.  | 
{: caption="Tabelle 2. Mit Aktionen für Service-IDs arbeiten" caption-side="top"} 


## Ereignisse für API-Schlüssel
{: #at_events_iam_apikeys}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion | Beschreibung |
|----------|---------|
| `iam-identity.user-apikey.create`      | Ein Ereignis wird generiert, wenn ein Initiator einen API-Schlüssel erstellt. | 
| `iam-identity.user-apikey.update`      | Ein Ereignis wird generiert, wenn ein Initiator einen API-Schlüssel umbenennt oder dessen Beschreibung ändert. |  
| `iam-identity.user-apikey.delete`      | Ein Ereignis wird generiert, wenn ein Initiator einen API-Schlüssel löscht. |  
| `iam-identity.serviceid-apikey.create` | Ein Ereignis wird generiert, wenn ein Initiator einen API-Schlüssel für eine Service-ID erstellt. |  
| `iam-identity.serviceid-apikey.delete` | Ein Ereignis wird generiert, wenn ein Initiator einen API-Schlüssel für eine Service-ID löscht. |  
{: caption="Tabelle 3. Mit Aktionen für API-Schlüssel arbeiten" caption-side="top"} 


## Anmeldeereignisse
{: #at_events_iam_login}

In der folgenden Tabelle sind die Aktionen aufgeführt, die ein Ereignis generieren:

| Aktion                                   | Beschreibung |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | Ein Ereignis wird generiert, wenn sich ein Benutzer bei {{site.data.keyword.cloud_notm}} mithilfe eines API-Schlüssels anmeldet. |  
| `iam-identity.serviceid-apikey.login`    | Ein Ereignis wird generiert, wenn sich ein Initiator bei {{site.data.keyword.cloud_notm}} mithilfe eines API-Schlüssels anmeldet, der einer Service-ID zugeordnet ist. |  
| `iam-identity.user-identitycookie.login` | Dies ist ein Ereignis, das generiert wird, wenn ein Initiator ein Identitätscookie anfordert, um eine Aktion auszuführen. |
| `iam-identity.user-refreshtoken.login`   | Dies ist ein Ereignis, das generiert wird, wenn sich der Initiator bei der IBM Cloud anmeldet, oder wenn ein Initiator, der sich bereits bei der IBM Cloud angemeldet hat, ein neues Aktualisierungstoken anfordert, um eine Aktion auszuführen. |
{: caption="Tabelle 4. Benutzeranmeldeaktionen" caption-side="top"} 


## Ereignisse anzeigen
{: #at_events_iam_ui}

Ereignisse sind in der Region **Frankfurt (eu-de)** verfügbar. Um diese Ereignisse anzuzeigen, müssen Sie [eine Instanz](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) des {{site.data.keyword.at_full_notm}}-Service in der Region **Frankfurt (eu-de)** bereitstellen. Anschließend müssen Sie [die {{site.data.keyword.at_full_notm}}-Benutzerschnittstelle öffnen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


## Ereignisse analysieren
{: #at_events_iam_analyze}


### Zugriffsgruppe löschen
{: #an_del_ag}

Beim Löschen einer Zugriffsgruppe weist das ausgelöste Ereignis das auf `iam-groups.group.delete` gesetzte Feld `action` auf.

Beachten Sie beim Löschen einer Zugriffsgruppe die folgenden Informationen:
* Weitere Aktionen werden automatisch ausgelöst, um andere Ressourcen zu bereinigen, die der Gruppe zugeordnet sind. Einige Aktionen, die ausgelöst werden, melden Ereignisse, die sich auf das Löschen von Mitgliedern in einer Zugriffsgruppe, das Löschen von Richtlinien sowie das Löschen dynamischer Regeln beziehen. 
* Der Initiator dieser Aktionen ist eine {{site.data.keyword.IBM_notm}}-Service-ID.


Wenn der gelöschten Zugriffsgruppe keine Mitglieder, Richtlinien und Regeln zugewiesen sind, melden die Ereignisse, die für eine dieser Ressourcen generiert werden, das Ergebnis `failure` mit einem Ergebniscode von `404`. Das folgende Beispiel zeigt die Ereignisse, die generiert werden, wenn eine Zugriffsgruppe, der keine Mitglieder, Richtlinien oder dynamischen Regeln zugeordnet sind, gelöscht wird:

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

