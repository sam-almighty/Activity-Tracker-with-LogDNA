---

copyright:
  years: 2019
lastupdated: "2019-05-22"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# Concessione delle autorizzazioni di amministrazione a un utente o ID servizio
{: #iam_manage_events}

IAM ({{site.data.keyword.iamlong}}) ti consente di autenticare in modo sicuro gli utenti e di controllare l'accesso a tutte le risorse cloud in modo congruente in {{site.data.keyword.cloud_notm}}. Completa la seguente procedura per concedere le autorizzazioni di amministrazione a un utente o un ID servizio per utilizzare il servizio {{site.data.keyword.at_full_notm}}:
{:shortdesc}

Ad esempio, come amministratore del servizio, puoi eseguire il provisioning e rimuovere le istanze del servizio, concedere le autorizzazioni ad altri utenti per utilizzare il servizio, archiviare i log su un'istanza {{site.data.keyword.cos_full_notm}} (COS) e altro ancora. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

## Prerequisiti
{: #iam_manage_events_prereq}

Il tuo ID utente ha bisogno delle **autorizzazioni della piattaforma di amministratore** per gestire il servizio {{site.data.keyword.at_full_notm}}. Contatta l'amministratore dell'account. Il proprietario dell'account può concedere a un altro utente l'accesso all'account ai fini della gestione dell'accesso utente e della gestione delle risorse dell'account. [Ulteriori informazioni](/docs/iam?topic=iam-userroles).


## Passo 1. Crea un gruppo di accesso
{: #ime_step1}

Completa la seguente procedura per creare un gruppo di accesso:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Fai clic su **Crea**.
3. Immetti un nome e una descrizione facoltativi per il gruppo e fai clic su **Crea**.

Puoi eliminare un gruppo selezionando l'opzione **Rimuovi gruppo**. Quando rimuovi un gruppo dall'account, rimuovi tutti gli utenti e gli ID servizio dal gruppo e tutto l'accesso assegnato al gruppo.
{: note}

Per creare un gruppo di accesso utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## Passo 2. Aggiungi le autorizzazioni per gestire gli eventi
{: #ime_step2}

Dopo aver configurato il tuo gruppo, puoi assegnare una politica di accesso comune al gruppo. 

Tutte le politiche che configuri per un gruppo di accesso si applicano a tutti gli ID servizio, gli utenti e le entità all'interno del gruppo. 
{: note}

Puoi assegnare la politica utilizzando l'IU o tramite la riga di comando.

Per creare una politica del gruppo di accesso utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Quando definisci la politica, devi selezionare un ruolo della piattaforma e un ruolo del servizio:
* I ruoli di gestione della piattaforma coprono una gamma di azioni, inclusa la capacità di creare ed eliminare le istanze, gestire gli alias, i bind e le credenziali e gestire l'accesso. I ruoli della piattaforma sono amministratore, editor, operatore, visualizzatore. I ruoli di gestione della piattaforma si applicano anche ai servizi di gestione dell'account che consentono agli utenti di invitare utenti, gestire ID di servizio, politiche di accesso, voci di catalogo e tenere traccia della fatturazione e dell'utilizzo in base al proprio ruolo assegnato in un servizio di gestione dell'account.
* I ruoli di accesso al servizio definiscono la capacità di un utente o un servizio di eseguire azioni su un'istanza del servizio. I ruoli di accesso al servizio sono gestore, scrittore e lettore.

Per gestire il servizio {{site.data.keyword.at_full_notm}}, un utente ha bisogno dei seguenti ruoli:
* Ruolo della piattaforma: **Amministratore**. 
* Ruolo del servizio: **Gestore**.
[Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

Completa la seguente procedura per assegnare una politica a un gruppo di accesso tramite l'IU:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso. 
3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Assegna accesso**.
5. Scegli di assegnare l'accesso in base alle risorse all'interno di un gruppo di risorse o in base alle singole risorse disponibili nell'account. Ad esempio, puoi scegliere una delle seguenti opzioni per concedere a un utente un ruolo di amministratore per gestire {{site.data.keyword.at_full_notm}}:

### Opzione 1. Concedi le autorizzazioni sul servizio
{: #admin_account_opt1}

Completa la seguente procedura per assegnare a un utente il ruolo di amministratore per il servizio {{site.data.keyword.at_full_notm}} nell'account: 

1. Seleziona **Assegna l'accesso alle risorse**.
2. Seleziona **IBM Cloud Activity Tracker with LogDNA**.
3. Seleziona **Tutte le regioni correnti**.
4. Seleziona **Tutte le istanze del servizio correnti**.
5. Seleziona il ruolo della piattaforma **Amministratore**.
6. Seleziona il ruolo del servizio **Gestore**.
7. Fai clic su **Assegna**.

### Opzione 2. Concedi le autorizzazioni all'interno del contesto di un gruppo di risorse
{: #admin_account_opt2}

Completa la seguente procedura per assegnare a un utente il ruolo di amministratore per il servizio {{site.data.keyword.at_full_notm}} nel contesto di un gruppo di risorse: 

1. Seleziona **Assegna l'accesso in un gruppo di risorse**.
2. Seleziona un gruppo di risorse.
3. Se all'utente non è stato già concesso un ruolo per il gruppo di risorse selezionato, scegli un ruolo per il campo **Assegna accesso a un gruppo di risorse**. 

    A seconda del ruolo che selezioni, l'utente può visualizzare il gruppo di risorse nel suo dashboard, modificarne il nome o gestire l'accesso degli utenti ad esso. 
    
    Puoi selezionare **Nessun accesso** se desideri che l'utente abbia accesso solo al servizio {{site.data.keyword.at_full_notm}} nel gruppo di risorse.

4. Seleziona **IBM Cloud Activity Tracker with LogDNA**.
5. Seleziona il ruolo della piattaforma **Amministratore**.
6. Seleziona il ruolo del servizio **Gestore**.
7. Fai clic su **Assegna**.

### Opzione 3. Concedi le autorizzazioni in un'ubicazione
{: #admin_account_opt3}

Puoi eseguire il provisioning di solo 1 istanza del servizio {{site.data.keyword.at_full_notm}} per ogni ubicazione. Pertanto, quando concedi le autorizzazioni utilizzando questa opzione, controlli l'accesso per ubicazione.
{: note}

Completa la seguente procedura per assegnare a un utente il ruolo di amministratore su un'istanza del servizio {{site.data.keyword.at_full_notm}}: 

1. Seleziona **Assegna l'accesso alle risorse**.
2. Seleziona **IBM Cloud Activity Tracker with LogDNA**.
3. Seleziona l'istanza.
4. Seleziona il ruolo della piattaforma **Amministratore**.
5. Seleziona il ruolo del servizio **Gestore**.
6. Fai clic su **Assegna**.



## Passo 3. Aggiungi un utente o un ID servizio al gruppo di accesso
{: #ime_step3}

Continua con la configurazione del tuo gruppo aggiungendo utenti o ID servizio.

### Aggiungi un utente al gruppo di accesso
{: #ime_step3_user}

Per aggiungere un utente, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso. 
3. Fai clic su **Aggiungi utenti** nella scheda **Utenti**.
4. Seleziona gli utenti che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.


### Aggiungi un ID servizio al gruppo di accesso
{: #ime_step3_svcid}

Per aggiungere un ID servizio, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso. 
3. Fai clic sulla scheda **ID servizio** e su **Aggiungi ID servizio**.
4. Seleziona gli ID che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.




