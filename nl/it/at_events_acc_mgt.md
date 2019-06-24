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

# Eventi di gestione dell'account  
{: #at_events_acc_mgt}

In qualità di responsabile della sicurezza, revisore o gestore, puoi utilizzare il servizio {{site.data.keyword.at_full_notm}} per tenere traccia di come gli utenti e le applicazioni interagiscono con l'account {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Il servizio {{site.data.keyword.at_full_notm}} registra le attività avviate dall'utente che modificano lo stato di un servizio in {{site.data.keyword.cloud_notm}}. Per iniziare, vedi [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 



## Eventi per la gestione degli account
{: #at_events_acc_mgt_account}

La seguente tabella elenca le azioni che generano un evento:

| Azione                               | Descrizione |
|--------------------------------------|-------------|
| `billing.account.create`             | Un evento viene generato quando esegui il provisioning di un account dopo che l'ID account è stato assegnato all'account. |
| `billing.account.update`             | Un evento viene generato quando aggiorni le informazioni sull'account.  |
| `billing.account.active`             | Un evento viene generato quando verifichi l'account, ovvero, un evento viene generato quando l'account diventa attivo. |
| `billing.account.subscription.create` | Un evento viene generato quando crei un <a href="/docs/account?topic=account-accounts#subscription-account">Account di sottoscrizione</a>. |
{: caption="Tabella 1. Azioni che generano eventi" caption-side="top"} 




## Eventi per la gestione degli utenti
{: #at_events_acc_mgt_users}

La seguente tabella elenca le azioni che generano un evento:

| Azione                               | Descrizione |
|--------------------------------------|-------------|
| `user-management.user.create`        | Un evento viene generato quando invii un invito a un utente per unirsi a un account. |
| `user-management.user.active`        | Un evento viene generato quando attivi l'utente nell'account. Quando l'utente verifica l'indirizzo email, l'evento viene generato. |
| `user-management.user.delete`        | Un evento viene generato quando rimuovi un utente dall'account. |
{: caption="Tabella 2. Azioni che generano eventi" caption-side="top"} 




## Eventi per la gestione delle organizzazioni
{: #at_events_acc_mgt_org}

La seguente tabella elenca le azioni che generano un evento:

| Azione                               | Descrizione |
|--------------------------------------|-------------|
| `billing.account.org.create`         | Un evento viene generato quando aggiungi un'organizzazione all'account. |
{: caption="Tabella 3. Azioni che generano eventi" caption-side="top"} 


## Eventi per la gestione delle tag
{: #at_events_acc_mgt_resources}

La seguente tabella elenca le azioni che generano un evento:

| Azione                               | Descrizione |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | Un evento viene generato quando aggiungi una tag a una risorsa. |
| `ghost-tags.tag.detach-tag`          | Un evento viene generato quando rimuovi una tag da una risorsa. |
{: caption="Tabella 4. Azioni che generano eventi" caption-side="top"} 


## Dove cercare gli eventi
{: #at_events_acc_mgt_ui}

Gli eventi sono disponibili nella regione **Francoforte (eu-de)**. 

Per visualizzare questi eventi, devi [eseguire il provisioning di un'istanza](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servizio {{site.data.keyword.at_full_notm}} nella regione **Francoforte (eu-de)**. Successivamente, devi [aprire l'IU {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 












