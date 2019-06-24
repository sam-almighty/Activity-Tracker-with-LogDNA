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


# Servizi cloud
{: #cloud_services}

Utilizza il servizio {{site.data.keyword.at_full}} per monitorare le attività avviate dall'utente che modificano lo stato di uno dei seguenti servizi in {{site.data.keyword.cloud_notm}}.
{:shortdesc}


## Servizi integrati principali della piattaforma
{: #platform_core_integrated}


I servizi principali della piattaforma generano degli eventi che puoi visualizzare tramite l'IU web {{site.data.keyword.at_full_notm}} di **Francoforte (eu-de)**. Per visualizzare questi eventi, devi [eseguire il provisioning di un'istanza](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servizio {{site.data.keyword.at_full_notm}} nella regione **Francoforte (eu-de)**.
{: note}

La seguente tabella elenca le azioni della piattaforma principali che inviano eventi a {{site.data.keyword.at_full_notm}}:

| Azione                           | Descrizione | Eventi {{site.data.keyword.at_full_notm}} |
|----------------------------------|-------------|-------------------------------------------|
| [Gestione di un account](/docs/account?topic=account-accounts#accounts) | Puoi registrarti per un account {{site.data.keyword.IBM_notm}} utilizzando un ID IBM esistente, creando un nuovo ID IBM oppure utilizzando un ID federato. | [Eventi generati quando gestisci un account](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [Gestione di utenti](/docs/iam?topic=iam-iamuserinv#iamusermanage) | Puoi visualizzare e gestire gli utenti nell'account o nelle organizzazioni di cui sei proprietario o che gestisci.  | [Eventi generati quando gestisci gli utenti](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [Gestione di organizzazioni](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | Come proprietario di un account, puoi aggiungere e gestire le organizzazioni nell'account. | [Eventi generati quando gestisci le organizzazioni](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [Provisioning e gestione dei servizi del catalogo abilitati a {{site.data.keyword.iamshort}} (IAM)](/docs/overview?topic=overview-ui#catalogcreate) | Puoi eseguire il provisioning, ridenominare, modificare il piano e rimuovere un'istanza del servizio. | [Eventi generati quando interagisci con i servizi del catalogo](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [Utilizzo degli alias del servizio](/docs/resources?topic=resources-connect_app#what_is_alias) | Un alias è una connessione tra il tuo servizio gestito da IAM all'interno di un gruppo di risorse e un'applicazione all'interno di un'organizzazione o di uno spazio. | [Eventi per la gestione degli alias associati a un'istanza del servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [Utilizzo delle credenziali del servizio](/docs/resources?topic=resources-service_credentials#service_credentials) | Una credenziale del servizio fornisce le informazioni necessarie per connettere un'applicazione a un'istanza del servizio. | [Eventi per la gestione delle credenziali del servizio associate a un'istanza del servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [Associazione mediante bind di un'istanza del servizio a un'applicazione](/docs/resources?topic=resources-s2s_binding#s2s_binding) | Puoi generare un'istanza o un alias Cloud Foundry (CF) di un'istanza del servizio con lo stesso nome in uno spazio.  | [Eventi per l'associazione e l'annullamento dell'associazione mediante bind di un'istanza del servizio a un'applicazione](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [Gestione delle tag](/docs/resources?topic=resources-tag) | Una tag è un'etichetta che assegni a una risorsa per un facile filtraggio delle risorse nel tuo elenco di risorse. | [Eventi per la gestione delle tag](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="Elenco delle azioni della piattaforma principali" caption-side="top"} 






## Servizi di sicurezza integrati della piattaforma
{: #platform_integrated_security}

I servizi di sicurezza integrati generano degli eventi che puoi visualizzare tramite l'IU web {{site.data.keyword.at_full_notm}} di **Francoforte (eu-de)**. Per visualizzare questi eventi, devi [eseguire il provisioning di un'istanza](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servizio {{site.data.keyword.at_full_notm}} nella regione **Francoforte (eu-de)**.
{: note}

La seguente tabella elenca le azioni della piattaforma di sicurezza principali che inviano eventi a {{site.data.keyword.at_full_notm}}:

| Azioni                                                     | Descrizione | Eventi {{site.data.keyword.at_full_notm}} |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [Gestione dei gruppi di accesso](/docs/iam?topic=iam-groups#groups) | Puoi definire i gruppi di accesso per organizzare una serie di utenti e ID servizio in una sola entità che ti rende facile assegnare le autorizzazioni. | [Eventi generati quando gestisci i gruppi di accesso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [Gestione delle politiche](/docs/iam?topic=iam-userroles#userroles) | Puoi utilizzare IAM per gestire gli utenti e i ruoli nei servizi di infrastruttura e piattaforma {{site.data.keyword.cloud_notm}}. | [Eventi generati quando gestisci le politiche IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [Accedi a {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)| Puoi accedere a {{site.data.keyword.cloud_notm}} utilizzando una password, una chiave API, un codice di autorizzazione o un passcode. Come utente federato, puoi accedere dall'interfaccia della riga di comando (CLI) utilizzando un passcode monouso o una chiave API. | [Eventi generati quando un utente o un'applicazione accede a {{site.data.keyword.cloud_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) |
| [Gestione delle chiavi API della piattaforma](/docs/iam?topic=iam-manapikey#platform-api-keys) | Puoi definire le chiavi API in {{site.data.keyword.IBM_notm}} Cloud che sono associate a un utente o a un ID servizio. | [Eventi generati quando gestisci le chiavi API della piattaforma](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [Gestione degli ID servizio](/docs/iam?topic=iam-serviceids#serviceids) | Puoi definire gli ID servizio a livello dell'account in {{site.data.keyword.IBM_notm}} Cloud. | [Eventi generati quando gestisci gli ID del servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="Elenco dei servizi della piattaforma di sicurezza principali" caption-side="top"} 



## Servizi di integrazione della piattaforma
{: #integration}

La seguente tabella elenca i servizi di integrazione che inviano eventi a {{site.data.keyword.cloudaccesstrailshort}}:

| Servizio     | Descrizione | Eventi {{site.data.keyword.cloudaccesstrailshort}} |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| {{site.data.keyword.messagehub}} è un bus di messaggi ad alta velocità creato con Apache Kafka. È ottimizzato per l'inserimento di eventi in {{site.data.keyword.IBM_notm}} e la distribuzione del flusso di eventi tra i tuoi servizi e le tue applicazioni. | [Eventi generati da {{site.data.keyword.messagehub}} ](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="Elenco dei servizi cloud di integrazione che inviano eventi a {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 



## Servizi di rete della piattaforma
{: #network}

La seguente tabella elenca i servizi di rete che inviano eventi a {{site.data.keyword.at_full_notm}}:

| Servizio     | Descrizione | Eventi {{site.data.keyword.at_full_notm}} |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| IBM Cloud Internet Services (CIS) fornisce un servizio Internet veloce, ad alte prestazioni, affidabile e sicuro. | [Eventi generati da IBM Cloud Internet Services](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="Elenco dei servizi di rete" caption-side="top"} 



## Servizi di sicurezza della piattaforma
{: #security}

La seguente tabella elenca i servizi cloud di sicurezza che inviano eventi a {{site.data.keyword.cloudaccesstrailshort}}:


| Servizio     | Descrizione | Eventi {{site.data.keyword.at_full_notm}}          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | Puoi utilizzare {{site.data.keyword.cloudcerts_short}} per gestire i certificati SSL per le tue applicazioni e i tuoi servizi basati su {{site.data.keyword.cloud_notm}}.  | [Eventi generati dal servizio {{site.data.keyword.cloudcerts_short}}](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="Elenco dei servizi cloud di sicurezza che inviano eventi a {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 


