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


# Eventi IAM
{: #at_events_iam}

In qualità di responsabile della sicurezza, revisore o gestore, puoi utilizzare il servizio {{site.data.keyword.at_full_notm}} per tracciare come gli utenti e le applicazioni interagiscono con il servizio {{site.data.keyword.iamlong}} (IAM) in {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

IAM ti consente di autenticare in modo sicuro gli utenti per i servizi della piattaforma e di controllare l'accesso alle risorse in modo coerente su {{site.data.keyword.cloud_notm}}. [Ulteriori informazioni](/docs/iam?topic=iam-iamoverview).


Il servizio {{site.data.keyword.at_full_notm}} registra le attività avviate dall'utente che modificano lo stato di un servizio in {{site.data.keyword.cloud_notm}}. Per iniziare a monitorare le azioni del tuo utente, vedi [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Un iniziatore può essere un utente, un servizio o un'applicazione.


## Eventi dei gruppi di accesso
{: #at_events_iam_access}

La seguente tabella elenca le azioni che generano un evento:

| Azione                      | Descrizione |
|-----------------------------|---------|
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



## Eventi della politica
{: #at_events_iam_policies}

La seguente tabella elenca le azioni che generano un evento:

| Azione                 | Descrizione |
|------------------------|---------|
| `iam-am.policy.create` | Un evento viene generato quando un iniziatore aggiunge una politica a un utente o a un gruppo di accesso. |
| `iam-am.policy.delete` | Un evento viene generato quando un iniziatore modifica le autorizzazioni di una politica di un utente o di un gruppo di accesso.|
| `iam-am.policy.update` | Un evento viene generato quando un iniziatore elimina una politica assegnata a un utente o a un gruppo di accesso. |
{: caption="Tabella 5. Gestione delle azioni della politica" caption-side="top"} 



## Eventi dell'ID servizio
{: #at_events_iam_serviceids}

La seguente tabella elenca le azioni che generano un evento:

| Azione | Descrizione |
|----------|---------|
| `iam-identity.account-serviceid.create` | Un evento viene generato quando un iniziatore crea un ID servizio.  | 
| `iam-identity.account-serviceid.update` | Un evento viene generato quando un iniziatore ridenomina un ID servizio o ne modifica la descrizione. | 
| `iam-identity.account-serviceid.delete` | Un evento viene generato quando un iniziatore elimina un ID servizio. | 
{: caption="Tabella 2. Utilizzo delle azioni degli ID servizio" caption-side="top"} 


## Eventi della chiave API
{: #at_events_iam_apikeys}

La seguente tabella elenca le azioni che generano un evento:

| Azione | Descrizione |
|----------|---------|
| `iam-identity.user-apikey.create`      | Un evento viene generato quando un iniziatore crea una chiave API. | 
| `iam-identity.user-apikey.update`      | Un evento viene generato quando un iniziatore ridenomina una chiave API o ne modifica la descrizione. |  
| `iam-identity.user-apikey.delete`      | Un evento viene generato quando un iniziatore elimina una chiave API. |  
| `iam-identity.serviceid-apikey.create` | Un evento viene generato quando un iniziatore crea una chiave API di un ID servizio. |  
| `iam-identity.serviceid-apikey.delete` | Un evento viene generato quando un iniziatore elimina una chiave API di un ID servizio. |  
{: caption="Tabella 3. Utilizzo delle azioni delle chiavi API" caption-side="top"} 


## Eventi di accesso
{: #at_events_iam_login}

La seguente tabella elenca le azioni che generano un evento:

| Azione                                   | Descrizione |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | Un evento viene generato quando un utente accede a {{site.data.keyword.cloud_notm}} utilizzando una chiave API. |  
| `iam-identity.serviceid-apikey.login`    | Un evento viene generato quando un iniziatore accede a {{site.data.keyword.cloud_notm}} utilizzando una chiave API associata a un ID servizio. |  
| `iam-identity.user-identitycookie.login` | Questo è un evento generato quando un iniziatore richiede un cookie di identità per eseguire un'azione. |
| `iam-identity.user-refreshtoken.login`   | Questo è un evento generato quando l'iniziatore accede a IBM Cloud o quando un iniziatore che ha già eseguito l'accesso a IBM Cloud richiede un nuovo token di aggiornamento per eseguire un'azione. |
{: caption="Tabella 4. Azioni di accesso dell'utente" caption-side="top"} 


## Visualizzazione degli eventi
{: #at_events_iam_ui}

Gli eventi sono disponibili nella regione **Francoforte (eu-de)**. Per visualizzare questi eventi, devi [eseguire il provisioning di un'istanza](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servizio {{site.data.keyword.at_full_notm}} nella regione **Francoforte (eu-de)**. Successivamente, devi [aprire l'IU {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


## Analisi degli eventi
{: #at_events_iam_analyze}


### Elimina un gruppo di accesso
{: #an_del_ag}

Quando elimini un gruppo di accesso, l'evento che viene attivato ha un campo `action` impostato su `iam-groups.group.delete`.

Quando un gruppo di accesso viene eliminato, tieni conto delle seguenti informazioni:
* Vengono attivate automaticamente ulteriori azioni per ripulire altre risorse associate al gruppo. Alcune azioni che vengono attivate segnalano eventi correlati all'eliminazione di membri in un gruppo di accesso, all'eliminazione di politiche e all'eliminazione di regole dinamiche. 
* L'iniziatore di queste azioni è un ID servizio {{site.data.keyword.IBM_notm}}.


Quando il gruppo di accesso che viene eliminato non ha membri, politiche e regole assegnate, gli eventi generati per una di queste risorse segnalano un risultato di `failure` con un codice risultato `404`. Il seguente esempio mostra gli eventi che vengono generati quando un gruppo di accesso che non ha membri, politiche o regole dinamiche assegnate viene eliminato:

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

