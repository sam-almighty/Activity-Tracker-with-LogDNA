---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access

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

 
# Benutzerzugriff mit IAM verwalten
{: #iam}

Mit {{site.data.keyword.iamlong}} (IAM) können Sie Benutzer sicher authentifizieren und den Zugriff auf alle Cloudressourcen konsistent in der {{site.data.keyword.cloud_notm}} steuern. {:shortdesc}

**Jedem Benutzer, der auf den {{site.data.keyword.at_full_notm}}-Service in Ihrem Konto zugreift, muss eine Zugriffsrichtlinie mit einer definierten IAM-Benutzerrolle zugewiesen werden.** Die Richtlinie bestimmt, welche Aktionen der Benutzer im Kontext des ausgewählten Service oder der ausgewählten Instanz ausführen kann. Die zulässigen Aktionen werden angepasst und definiert als Operationen, die für den Service ausgeführt werden dürfen. Die Aktionen werden dann IAM-Benutzerrollen zugeordnet. 

*Richtlinien* machen es möglich, dass Zugriff auf verschiedenen Ebenen erteilt werden kann. Unter anderem sind die folgenden Optionen verfügbar:  

* Zugriff auf alle IAM-aktivierten Services in Ihrem Konto. 
* Zugriff auf alle Instanzen des Service in einer einzelnen Region in Ihrem Konto. 
* Zugriff auf eine einzelne Serviceinstanz in Ihrem Konto. 
* Zugriff auf alle Instanzen des Service im Kontext einer Ressourcengruppe. 
* Zugriff auf alle Instanzen des Service in einer einzelnen Region im Kontext einer Ressourcengruppe. 
* Zugriff auf alle IAM-aktivierten Services im Kontext einer Ressourcengruppe. 

*Rollen* definieren die Aktionen, die ein Benutzer oder eine Service-ID ausführen kann. Es gibt verschiedene Typen von Rollen in der {{site.data.keyword.cloud_notm}}: 

* *Plattformmanagementrollen* ermöglichen Benutzern, Tasks in Serviceressourcen auf Plattformebene auszuführen, z. B. das Zuweisen von Benutzerzugriff für den Service, das Erstellen oder Löschen von Service-IDs, das Erstellen von Instanzen, das Zuweisen von Richtlinien für Ihren Service an andere Benutzer und das Binden von Instanzen an Anwendungen. 
* *Servicezugriffsrollen* ermöglichen Benutzern, unterschiedliche Berechtigungsebenen für den Aufruf der Service-API zugewiesen zu bekommen. 

**Um eine Gruppe von Benutzern und Service-IDs in einer einzelnen Entität zu organisieren, die Ihnen das Verwalten von IAM-Berechtigungen vereinfacht, verwenden Sie *Zugriffsgruppen*.** Sie können der Gruppe eine einzelne Richtlinie zuweisen statt denselben Zugriff pro Benutzer oder Service-ID mehrfach zuzuweisen.
{: tip}

Weitere Informationen erhalten Sie in den folgenden Lernprogrammen: 
* [Einem Benutzer oder einer Service-ID Verwaltungsberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_manage_events#iam_manage_events)
* [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)

## Zugriff mithilfe von Zugriffsgruppen verwalten
{: #groups}

Um für Benutzer mithilfe von Zugriffsgruppen den Zugriff verwalten oder neuen Zugriff zuweisen zu können, müssen Sie der Kontoeigner, Administrator oder Editor für alle Identity and Access Management-aktivierten Services in dem Konto bzw. der zugewiesene Administrator oder Editor für den IAM-Zugriffsgruppenservice sein.  

Wählen Sie eine der folgenden Aktionen aus, um Zugriffsgruppen in der {{site.data.keyword.cloud_notm}} zu verwalten: 

* [Zugriffsgruppe erstellen](/docs/iam?topic=iam-groups#create_ag)
* [Zugriff für eine Gruppe zuweisen](/docs/iam?topic=iam-groups#access_ag)


## Zugriff durch direktes Zuweisen von Richtlinien an Benutzer verwalten
{: #users}

Um für Benutzer mithilfe von IAM-Richtlinien den Zugriff verwalten oder neuen Zugriff zuweisen zu können, müssen Sie der Kontoeigner oder Administrator für alle Services in dem Konto sein bzw. ein Administrator für den bestimmten Service oder die bestimmte Serviceinstanz.  

Wählen Sie eine der folgenden Aktionen aus, um IAM-Richtlinien in der {{site.data.keyword.cloud_notm}} zu verwalten: 

* Informationen zum Ändern der Berechtigungen eines Benutzers finden Sie unter [Vorhandenen Zugriff bearbeiten](/docs/iam?topic=iam-iammanidaccser#edit_existing). 
* Informationen zum Erteilen von Berechtigungen für einen Benutzer finden Sie unter [Neuen Zugriff zuweisen](/docs/iam?topic=iam-iammanidaccser#assign_new_access). 
* Informationen zum Widerrufen von Berechtigungen finden Sie unter [Zugriff entfernen](/docs/iam?topic=iam-iammanidaccser#removing_access). 
* Informationen zum Überprüfen der Berechtigungen eines Benutzers finden Sie unter [Zugewiesenen Zugriff überprüfen](/docs/iam?topic=iam-iammanidaccser#review_your_access). 



## {{site.data.keyword.cloud_notm}}-Plattformrollen
{: #platform}

In der folgenden Tabelle können Sie sehen, welche Plattformrolle Sie einem Benutzer in der {{site.data.keyword.cloud_notm}} zuweisen können, damit er die folgenden Plattformaktionen ausführen kann: 

| Plattformaktionen                                                        | {{site.data.keyword.cloud_notm}}-Plattformrollen    | 
|-------------------------------------------------------------------------|------------------------------------------------------|
| `Anderen Mitgliedern Zugriff für die Arbeit mit dem Service erteilen`           | Administrator                                        | 
| `Serviceinstanz bereitstellen`                                          | Editor                            | 
| `Serviceinstanz löschen`                                             | Administrator </br>Editor                            | 
| `Service-ID erstellen`                                                   | Administrator </br>Editor                            |
| `Details einer Serviceinstanz anzeigen`                                    | Administrator </br>Editor </br>Operator </br>Anzeigeberechtigter  | 
| `Serviceinstanzen im Activity Tracker-Dashboard 'Beobachtbarkeit' anzeigen`   | Administrator </br>Editor </br>Operator </br>Anzeigeberechtigter  | 
{: caption="Tabelle 1. IAM-Benutzerrollen und Aktionen" caption-side="top"}



## {{site.data.keyword.cloud_notm}}-Servicerollen
{: #service}

In der folgenden Tabelle können Sie sehen, welche Servicerollen Sie einem Benutzer zuweisen können, damit er die folgenden Serviceaktionen ausführen kann: 

| Aktionen                                                                 | {{site.data.keyword.cloud_notm}}-Servicerollen     | 
|-------------------------------------------------------------------------|------------------------------------------------------|
| `Ereignisse archivieren`                                                        | Manager                                              |
| `Alerts konfigurieren`                                                      | Manager </br>Leseberechtigter                            | 
| `Daten filtern und suchen`                                                | Manager </br>Leseberechtigter                                  |
| `Ansichten erstellen`                                                          | Manager </br>Leseberechtigter                                  |
| `Ereignisse exportieren`                                                         | Manager </br>Leseberechtigter                                  |
| `Benutzervorgaben in der LogDNA-Webbenutzerschnittstelle konfigurieren`                       | Manager </br>Leseberechtigter                                  |
| `Ereignisse in der LogDNA-Webbenutzerschnittstelle anzeigen`                                 | Manager </br>Leseberechtigter                                  | 
{: caption="Tabelle 2. IAM-Benutzerrollen und Aktionen" caption-side="top"}


**Hinweis:** Die Servicerolle **Manager** ist der LogDNA-Administratorrolle direkt zugeordnet. 






