---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, event fields

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



# Ereignisfelder
{: #event}

{{site.data.keyword.at_full_notm}}-Ereignisse basieren auf dem CADF-Standard (Cloud Auditing Data Federation).
{:shortdesc}

## Initiatorfelder
{: #initiator}

In der folgenden Liste sind allgemeine Felder aufgeführt, die für ein {{site.data.keyword.at_full_notm}}-Ereignis verfügbar sind: 

| Feldname | Beschreibung | Wert |
|------------|-------------|-------|
| `initiator.id` | ID des Initiators der Aktion. </br></br>Gültige Typen von Initiatoren sind `IBMID`, `serviceID` und `Cloud Foundry (CF) user ID`. | Beispiel für eine IBMid ist `IBMid-000000XXX2`. </br>Beispiel für eine Service-ID ist `iam-ServiceId-12345678-0165-4c89-847d-9660b1632e14`. </br>Beispiel für eine CF-Benutzer-ID ist `7666666b-23ae-4a34-8569-cu75tgdr4da3`. |
| `initiator.name` | Benutzername des Benutzers, der die Aktion initialisiert hat. | Beispielsweise eine E-Mail-Adresse. |
| `initiator.typeURI` | Typ der Quelle des Ereignisses. |Gültige Werte sind *service/security/account/user*, *service/security/clientid* und *service/security/account/serviceid*. |
| `initiator.credential.type` | Typ des Initiator-ID-Berechtigungsnachweises. | Gültige Werte sind *user*, *token* und *apikey*. |
{: caption="Tabelle 1. Allgemeine Initiatorfelder" caption-side="top"} 

  

## Zielfelder
{: #target}

In der folgenden Liste sind allgemeine Zielfelder aufgeführt, die für ein {{site.data.keyword.at_full_notm}}-Ereignis verfügbar sind: 

| Feldname | Beschreibung | Wert |
|------------|-------------|-------|
| `target.id` | Cloudressourcenname (CRN) der Ressource, für die die Aktion ausgeführt wird. </br>Weitere Informationen finden Sie unter [CRN-Format](/docs/overview?topic=overview-format-crn#format). |Beispiel: `crn:v1:bluemix:public:cloud-object-storage:global:a/12345678e6232019c6567c9123456789:fr56et47-befb-440a-a223c-12345678dae1:bucket:bucket1` |
| `target.name` | Lesbarer Name der Cloudressource, für die die Aktion ausgeführt wird. |  |
| `target.typeURI` | Typ der Cloudressource, für die die Aktion ausgeführt wird. </br>Das Format dieses Felds ist **serviceName/objectType**, wobei `servicename` der Name des Service ist. |Beispiel: `iam-am/policy` oder `cloud-object-storage/bucket/acl` |
{: caption="Tabelle 2. Allgemeine Zielfelder" caption-side="top"} 


 
## Aktionsfelder
{: #action}

In der folgenden Liste sind allgemeine Aktionsfelder aufgeführt, die für ein {{site.data.keyword.at_full_notm}}-Ereignis verfügbar sind: 

| Feldname | Beschreibung | Wert |
|------------|-------------|-------|
| `action` | Aktion, die das Ereignis auslöst. </br>Das Format dieses Felds ist **serviceName.objectType.action**, wobei `servicename` der Name des Service ist. </br>Weitere Informationen zu Aktionswerten für Ereignisse, die von einem Service generiert werden, finden Sie unter <a href="/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#cloud_services">Cloud-Services</a> | Beispiel: `iam-identity.serviceid-apikey.login` |
| `eventTime` | Gibt die Zeitmarke an, zu der das Ereignis erstellt wurde. </br>Das Datum wird in Coordinated Universal Time (UTC) angegeben. </br>Das Format ist kompatibel mit ISO 8601. | Beispiel: `2017-10-19T19:07:50.32+0000` |
{: caption="Tabelle 3. Allgemeine Aktionsfelder" caption-side="top"} 



## Ergebnisfelder
{: #outcomes}

In der folgenden Liste sind allgemeine Ergebnisfelder aufgeführt, die für ein {{site.data.keyword.at_full_notm}}-Ereignis verfügbar sind: 

| Feldname | Beschreibung | Wert |
|------------|-------------|-------|
| `outcome` | Ergebnis der Aktion. |Gültige Werte sind *success*, *failure* und *pending*. |
| `reason.reasonCode` | Numerisches Feld, das den HTTP-Antwortcode einschließt. |Beispiel: *200* für ein erfolgreiches Ergebnis. |
| `severity` | Definiert die Bedrohung, die eine Aktion für eine Cloud bedeuten könnte. |Gültige Werte sind *normal*, *warning* und *critical*. </br></br>**normal** ist für Routineaktionen in der Cloud festgelegt. Dazu zählt beispielsweise das Starten einer Instanz oder das Aktualisieren eines Tokens. </br></br>**warning** ist für Aktionen festgelegt, bei denen eine Cloudressource aktualisiert wird oder ihre Metadaten geändert werden. Dazu zählt beispielsweise das Aktualisieren der Version eines Workerknotens, das Umbenennen von Zertifikaten oder das Umbenennen einer Serviceinstanz. </br></br>**critical** ist für Aktionen festgelegt, die die Sicherheit in der Cloud betreffen. Dazu zählt beispielsweise das Ändern der Berechtigungsnachweise eines Benutzers, das Löschen von Daten oder der unbefugte Zugriff für die Arbeit mit einer Cloudressource. |
{: caption="Tabelle 4. Allgemeine Ergebnisfelder" caption-side="top"} 


