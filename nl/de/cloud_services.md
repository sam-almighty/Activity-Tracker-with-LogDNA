---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, services

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


# Cloud-Services
{: #cloud_services}

Verwenden Sie den {{site.data.keyword.at_full}}-Service, um benutzerinitiierte Aktivitäten zu überwachen, die den Status der folgenden Services in der {{site.data.keyword.cloud_notm}} ändern.
{:shortdesc}


## Zentrale integrierte Services für die Plattform
{: #platform_core_integrated}


Zentrale Plattformservices generieren Ereignisse, die Sie über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle in **Frankfurt (eu-de)** anzeigen können. Um diese Ereignisse anzuzeigen, müssen Sie [eine Instanz](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) des {{site.data.keyword.at_full_notm}}-Service in der Region **Frankfurt (eu-de)** bereitstellen.
{: note}

Die folgende Tabelle enthält eine Auflistung von zentralen Aktionen der Plattform, die Ereignisse an {{site.data.keyword.at_full_notm}} senden:

| Aktion                           | Beschreibung | {{site.data.keyword.at_full_notm}}-Ereignisse |
|----------------------------------|-------------|-------------------------------------------|
| [Verwalten eines Kontos](/docs/account?topic=account-accounts#accounts) | Sie können sich für ein {{site.data.keyword.IBM_notm}} Konto anmelden, indem Sie eine vorhandene IBMid verwenden, eine neue IBMid erstellen oder eine föderierte ID benutzen. | [Bei der Verwaltung eines Kontos generierte Ereignisse](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [Verwalten von Benutzern](/docs/iam?topic=iam-iamuserinv#iamusermanage) | Sie können Benutzer übergreifend über die Konten oder Organisationen, deren Eigner Sie sind oder die Sie verwalten, anzeigen und verwalten.  | [Bei der Verwaltung von Benutzern generierte Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [Verwalten von Organisationen](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | Als Kontoeigner können Sie Organisationen zum Account hinzufügen und verwalten. | [Bei der Verwaltung von Organisationen generierte Ereignisse](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [Bereitstellung und Verwaltung von Katalogservices, die für {{site.data.keyword.iamshort}} (IAM) aktiviert sind ](/docs/overview?topic=overview-ui#catalogcreate) | Sie können eine Serviceinstanz bereitstellen, eine Serviceinstanz umbenennen, den Plan für eine Serviceinstanz ändern und eine Serviceinstanz entfernen. | [Bei der Interaktion mit den Katalogservices generierte Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [Arbeiten mit Servicealiasnamen](/docs/resources?topic=resources-connect_app#what_is_alias) | Ein Aliasname ist eine Verbindung zwischen Ihrem durch IAM verwalteten Service innerhalb einer Ressourcengruppe und einer Anwendung innerhalb einer Organisation oder eines Bereichs. | [Ereignisse zum Verwalten von Aliasnamen, die einer Serviceinstanz zugeordnet sind](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [Arbeiten mit Serviceberechtigungsnachweisen](/docs/resources?topic=resources-service_credentials#service_credentials) | Durch einen Serviceberechtigungsnachweis werden die erforderlichen Informationen bereitgestellt, um eine Anwendung mit einer Serviceinstanz zu verbinden. | [Ereignisse zum Verwalten von Serviceberechtigungsnachweisen, die einer Serviceinstanz zugeordnet sind](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [Binden einer Serviceinstanz an eine App](/docs/resources?topic=resources-s2s_binding#s2s_binding) | Sie können eine Cloud Foundry-Instanz (CF) oder einen Aliasnamen einer Serviceinstanz mit demselben Namen in einem Bereich erstellen. | [Ereignisse für das Binden und das Aufheben einer Bindung einer Serviceinstanz an eine App](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [Verwalten von Tags](/docs/resources?topic=resources-tag) | Ein Tag ist eine Bezeichnung, die einer Ressource zugewiesen wird und die das Filtern von Ressourcen in der Ressourcenliste vereinfacht. | [Ereignisse für die Verwaltung von Tags](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="Liste der zentralen Aktionen für die Plattform" caption-side="top"} 






## Integrierte Sicherheitsservices für die Plattform
{: #platform_integrated_security}

Integrierte Sicherheitsservices generieren Ereignisse, die Sie über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle in **Frankfurt (eu-de)** anzeigen können. Um diese Ereignisse anzuzeigen, müssen Sie [eine Instanz](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) des {{site.data.keyword.at_full_notm}}-Service in der Region **Frankfurt (eu-de)** bereitstellen.
{: note}

Die folgende Tabelle enthält eine Auflistung von zentralen Aktionen der Sicherheitsplattform, die Ereignisse an {{site.data.keyword.at_full_notm}} senden:

| Aktionen                                                     | Beschreibung | {{site.data.keyword.at_full_notm}}-Ereignisse |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [Zugriffsgruppen verwalten](/docs/iam?topic=iam-groups#groups) | Sie können Zugriffsgruppen verwalten, um eine Gruppe von Benutzern und Service-IDs in einer einzigen Entität zu organisieren, die das Zuweisen von Berechtigungen vereinfacht. | [Ereignisse, die beim Verwalten von Zugriffsgruppen generiert werden](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [Richtlinien verwalten](/docs/iam?topic=iam-userroles#userroles) | Mit IAM können Sie Benutzer und Rollen für alle Plattform- und Infrastrukturservices von {{site.data.keyword.cloud_notm}} verwalten. | [Bei der Verwaltung von IAM-Richtlinien generierte Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [Anmelden bei {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)| Zum Anmelden bei {{site.data.keyword.cloud_notm}} können Sie ein Kennwort, einen API-Schlüssel, einen Berechtigungscode oder einen Kenncode verwenden. Als föderierter Benutzer können Sie sich über die Befehlszeilenschnittstelle (CLI) mit einem einmaligen Kenncode oder einem API-Schlüssel anmelden. | [Bei der Anmeldung eines Benutzers oder einer App bei {{site.data.keyword.cloud_notm}} generierte Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) |
| [Verwalten von Plattform-API-Schlüsseln](/docs/iam?topic=iam-manapikey#platform-api-keys) | In {{site.data.keyword.IBM_notm}} können Sie Plattform-API-Schlüssel definieren, die einem Benutzer oder einer Service-ID zugeordnet sind. | [Bei der Verwaltung von Plattform-API-Schlüsseln generierte Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [Verwalten von Service-IDs](/docs/iam?topic=iam-serviceids#serviceids) | Sie können Service-IDs auf Kontoebene in {{site.data.keyword.IBM_notm}} Cloud definieren. | [Bei der Verwaltung von Service-IDs generierte Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="Liste von zentralen Sicherheitsplattformservices" caption-side="top"} 



## Plattformintegrationsservices
{: #integration}

Die folgende Tabelle enthält eine Auflistung von Integrationsservices, die Ereignisse an {{site.data.keyword.cloudaccesstrailshort}} senden:

| Service     | Beschreibung | {{site.data.keyword.cloudaccesstrailshort}}-Ereignisse |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| {{site.data.keyword.messagehub}} ist ein Nachrichtenbus mit hohem Durchsatz, der mit Apache Kafka erstellt wurde. Er ist für die Aufnahme von Ereignissen in {{site.data.keyword.IBM_notm}} und die Verteilung des Ereignisstroms zwischen Ihren Services und Anwendungen optimiert. | [Von {{site.data.keyword.messagehub}} generierte Ereignisse](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="Liste der Integrations-Cloud-Services, die Ereignisse an {{site.data.keyword.cloudaccesstrailshort}} senden" caption-side="top"} 



## Plattformnetzservices
{: #network}

Die folgende Tabelle enthält eine Auflistung von Netzservices, die Ereignisse an {{site.data.keyword.at_full_notm}} senden:

| Service     | Beschreibung | {{site.data.keyword.at_full_notm}}-Ereignisse |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| IBM Cloud Internet Services (CIS) bietet einen schnellen, hochleistungsfähigen, zuverlässigen und sicheren Internet-Service. | [Von IBM Cloud Internet Services generierte Ereignisse](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="Liste der Netzservices" caption-side="top"} 



## Plattformsicherheitsservices
{: #security}

Die folgende Tabelle enthält eine Auflistung von Cloud-Services für Sicherheit, die Ereignisse an {{site.data.keyword.cloudaccesstrailshort}} senden:


| Service     | Beschreibung | {{site.data.keyword.at_full_notm}}-Ereignisse          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | Mit {{site.data.keyword.cloudcerts_short}} können Sie die SSL-Zertifikate für Ihre {{site.data.keyword.cloud_notm}}-basierten Apps und Services verwalten.  | [Vom {{site.data.keyword.cloudcerts_short}}-Service generierte Ereignisse](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="Liste der Cloud-Services für Sicherheit, die Ereignisse an {{site.data.keyword.cloudaccesstrailshort}} senden" caption-side="top"} 


