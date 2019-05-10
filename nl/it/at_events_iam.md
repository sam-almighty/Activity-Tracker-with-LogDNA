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


# Eventi IAM
{: #at_events_iam}

In qualità di responsabile della sicurezza, revisore o gestore, puoi utilizzare il servizio {{site.data.keyword.at_full_notm}} per tracciare come gli utenti e le applicazioni interagiscono con il servizio {{site.data.keyword.iamlong}} (IAM) in {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Il servizio {{site.data.keyword.at_full_notm}} registra le attività avviate dall'utente che modificano lo stato di un servizio in {{site.data.keyword.cloud_notm}}. Per iniziare a monitorare le azioni del tuo utente, vedi [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started).  

Un iniziatore può essere un utente, un servizio o un'applicazione.
{: tip}

## Gestione dei gruppi di accesso 
{: #at_events_iam_access}

La seguente tabella elenca le azioni che generano un evento: 

| Azione |Descrizione     |
|----------|---------|
| `iam-groups.group.create`   | Un evento viene generato quando un iniziatore crea un gruppo di accesso. | 
| `iam-groups.group.read`     | Un evento viene generato quando un iniziatore ricerca le informazioni correlate ai gruppi di accesso. |
| `iam-groups.group.update`   | Un evento viene generato quando un iniziatore aggiorna un nome o una descrizione del gruppo. |
| `iam-groups.group.delete`   | Un evento viene generato quando un iniziatore elimina un gruppo di accesso. |
| `iam-groups.member.add`     | Un evento viene generato quando un iniziatore aggiunge un membro a un gruppo di accesso. |
| `iam-groups.member.delete`  | Un evento viene generato quando un iniziatore rimuove un membro da un gruppo di accesso. |
| `iam-groups.member.read`    | Un evento viene generato quando un iniziatore controlla l'appartenenza di un membro. |
| `iam-groups.rule.read`      | Un evento viene generato quando un iniziatore visualizza una regola di un gruppo di accesso. |
| `iam-groups.rule.create`    | Un evento viene generato quando un iniziatore aggiunge una regola a un gruppo di accesso. |
| `iam-groups.rule.update`    | Un evento viene generato quando un iniziatore modifica il nome della regola. |
| `iam-groups.rule.delete`    | Un evento viene generato quando un iniziatore elimina una regola da un gruppo di accesso. |
{: caption="Tabella 1. Gestisci le azioni dei gruppi di accesso" caption-side="top"} 




## Visualizzazione degli eventi
{: #at_events_iam_ui}

Gli eventi sono disponibili nella regione **US-South**. 

Per visualizzare questi eventi, devi [ eseguire il provisioning di un'istanza](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servizio {{site.data.keyword.at_full_notm}} nella regione **US-South**. Successivamente, devi [aprire l'IU {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


