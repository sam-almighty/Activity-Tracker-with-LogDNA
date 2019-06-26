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

# Eventi dell'istanza del servizio  
{: #at_events_rc}

In qualità di responsabile della sicurezza, revisore o gestore, puoi utilizzare il servizio {{site.data.keyword.at_full_notm}} per tenere traccia di come gli utenti e le applicazioni interagiscono con i servizi {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Il servizio {{site.data.keyword.at_full_notm}} registra le attività avviate dall'utente che modificano lo stato di un servizio in {{site.data.keyword.cloud_notm}}. Per iniziare a monitorare le azioni del tuo utente, vedi [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 


## Eventi per il provisioning e la gestione delle istanze del servizio
{: #rc_provision}

La seguente tabella elenca le azioni che generano un evento:

| Azione                         | Descrizione |
|--------------------------------|---------|
| `service_name.instance.create` | Un evento viene generato quando esegui il provisioning di un'istanza del servizio.|
| `service_name.instance.update` | Un evento viene generato quando ridenomini un'istanza del servizio o modifichi il piano di servizio.|
| `service_name.instance.delete` | Un evento viene generato quando un'istanza del servizio viene eliminata. |
{: caption="Tabella 1. Azioni che generano eventi" caption-side="top"} 


##  Eventi per la gestione degli alias associati a un'istanza del servizio
{: #rc_alias}

Un alias è una connessione tra il tuo servizio gestito da IAM all'interno di un gruppo di risorse e un'applicazione all'interno di un'organizzazione o di uno spazio.

La seguente tabella elenca le azioni che generano un evento:

| Azione                         | Descrizione |
|--------------------------------|---------|
| `service_name.alias.create` | Un evento viene generato quando viene creato un alias per un'istanza. |
| `service_name.alias.update` | Un evento viene generato quando viene aggiornato un alias per un'istanza. |
| `service_name.alias.delete` | Un evento viene generato quando viene eliminato un alias per un'istanza. |
{: caption="Tabella 2. Azioni che generano eventi" caption-side="top"} 


##  Eventi per la gestione delle credenziali del servizio associate a un'istanza del servizio
{: #rc_keys}

Una credenziale del servizio fornisce le informazioni necessarie per connettere un'applicazione a un'istanza del servizio. 

La seguente tabella elenca le azioni che generano un evento:

| Azione                         | Descrizione |
|--------------------------------|---------|
| `service_name.key.create` | Un evento viene generato quando si crea una chiave API per un'istanza del servizio tramite la sezione *Service credentials* dell'IU dell'istanza del servizio. |
| `service_name.key.delete` | Un evento viene generato quando una chiave API associata a un'istanza del servizio viene eliminata dalla sezione *Service credentials* dell'IU dell'istanza del servizio. |
{: caption="Tabella 3. Azioni che generano eventi" caption-side="top"} 



##  Eventi per l'associazione e l'annullamento dell'associazione mediante bind di un'istanza del servizio a un'applicazione
{: #rc_bind}

La seguente tabella elenca le azioni che generano un evento:

| Azione                         | Descrizione |
|--------------------------------|---------|
| `service_name.binding.create` | Un evento viene generato quando associ mediante bind un'istanza del servizio a un'applicazione. |
| `service_name.binding.delete` | Un evento viene generato quando annulli l'associazione mediante bind di un'istanza del servizio a un'applicazione.|
{: caption="Tabella 4. Azioni che generano eventi" caption-side="top"} 



## Dove cercare gli eventi
{: #rc_ui}

Gli eventi sono disponibili nella regione **Francoforte (eu-de)**. 

Per visualizzare questi eventi, devi [eseguire il provisioning di un'istanza](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servizio {{site.data.keyword.at_full_notm}} nella regione **Francoforte (eu-de)**. Successivamente, devi [aprire l'IU {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 



## Analisi degli eventi
{: #rc_analyze}

**Azione: service_name.instance.delete**

Quando un'istanza del servizio viene eliminata, tieni conto delle seguenti informazioni:
* Vengono attivate automaticamente altre azioni per ripulire le autorizzazioni IAM. Queste azioni rimuovono le politiche che vengono configurate affinché gli utenti e gli ID servizio nell'account lavorino con l'istanza del servizio. 
* L'iniziatore di queste azioni è un ID servizio {{site.data.keyword.IBM_notm}}.


Quando l'istanza del servizio che viene eliminata non ha politiche IAM configurate per gli utenti e gli ID servizio, gli eventi generati automaticamente per una di queste risorse segnalano un risultato di `failure` con un codice risultato `404`. Il seguente esempio mostra gli eventi che vengono generati quando un'istanza del servizio che non ha politiche configurate nell'account viene eliminata:

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



