---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# Creazione delle viste personalizzate
{: #views}

Tramite l'IU web {{site.data.keyword.at_full_notm}}, puoi applicare dei criteri di ricerca e di filtro per definire gli eventi che vengono visualizzati tramite una vista personalizzata.
{:shortdesc}


## Prerequisiti
{: #views_prereqs}

Prima di cominciare, controlla che il tuo ID utente abbia le autorizzazioni per avviare l'IU web e visualizzare gli eventi. La seguente tabella elenca i ruoli minimi che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare, ricercare e filtrare gli eventi:

| Ruolo                      | Autorizzazione concessa            |
|---------------------------|-------------------------------|  
| Ruolo piattaforma: `Viewer`     | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Osservabilità. |
| Ruolo servizio: `Reader`      | Consente all'utente di avviare l'IU web e visualizzare gli eventi nell'IU web.  |
{: caption="Tabella 1. Ruoli IAM" caption-side="top"} 

Per ulteriori informazioni su come configurare le politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Passo 1. Vai all'IU web e seleziona una vista
{: #views_step1}

Completa la seguente procedura:

1. [Vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Fai clic sull'icona **Views** ![icona Configuration](images/views.png).
3. Seleziona **Everything** oppure una vista. 


## Passo 2. Seleziona l'insieme di eventi da visualizzare tramite una vista applicando una query di ricerca
{: #views_step2}

Per cercare eventi specifici, puoi applicare una query di ricerca. 

* Puoi eseguire delle semplici ricerche (ricerca di stringa di un singolo termine), una ricerca composta (più termini e operatori di ricerca), ricerche di campo se la riga di log può essere analizzata e altre ancora. Per ulteriori informazioni, vedi il documento relativo alla [modalità di ricerca dei log nei documenti LogDNA ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://docs.logdna.com/docs/search){:new_window}.
* Gli operatori AND e OR sono sensibili a maiuscole/minuscole e devono essere scritti in maiuscolo.

Puoi cercare gli eventi solo per il numero di giorni specificato tramite il piano di servizio dell'istanza.
{: important}


Completa la seguente procedura:
1. Immetti una query di ricerca. 
2. Fai clic su **Enter**. 

Quando applichi una query, tieni presente che il nome della vista viene modificato con **Unsaved View**.


### Query per eventi generati da un servizio
{: #views_step1_1}

Per filtrare gli eventi per un servizio specifico, devi immettere la seguente query:

```
_supertenant:SERVICENAME
```
{: codeblock}

Dove `SERVICENAME` è il nome del servizio in {{site.data.keyword.cloud_notm}}.

La seguente tabella elenca i servizi principali:

| Eventi generati da               | Valore                         | Query di esempio                     |
|--------------------------------------------|-------------------------------|----------------------------------|
| [Servizio di gestione accesso IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [Servizio di identità IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [Servizio di gruppi di accesso IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)   | `iam-groups`  | `_supertenant:iam-groups`     |
| [Servizio controller delle risorse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="Tabella 2. Query in base al nome servizio" caption-side="top"}

### Query per insiemi di eventi generati da un servizio
{: #views_step1_2}

Quando un servizio genera diversi tipi di eventi, puoi immettere la seguente query:

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

Dove 

* `SERVICENAME` è il nome del servizio in {{site.data.keyword.cloud_notm}}
* `TYPEOFACTION` è una query composta in cui puoi utilizzare gli operatori AND e OR e puoi anche utilizzare `-` per escludere i dati. Tieni presente che gli operatori `AND` e `OR` sono sensibili a maiuscole/minuscole e devono essere scritti in maiuscolo.


La seguente tabella mostra esempi su come eseguire una query per un gruppo di eventi generati da un servizio:

| Eventi generati da               | Tipo di eventi     | Query di esempio                     |
|--------------------------------------------|--------------------|---------------------------------|
| `IAM Identity service`                     | [Eventi di accesso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `IAM Identity service`                     | [Eventi della chiave API](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `IAM Identity service`                     | [Eventi dell'ID servizio dell'account](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `Resource controller`                      | [Provisioning e gestione delle istanze del servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `Resource controller`                      | [Gestione degli utenti nell'account](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="Tabella 3. Esempi di query più complesse" caption-side="top"}


### Query per eventi che hanno un'azione specifica
{: #views_step1_3}

Ogni evento ha un campo di **azione** che informa sull'azione che ha attivato l'evento. Puoi immettere la seguente query per cercare tutti gli eventi che hanno la stessa azione:

```
action ACTIONVALUE
```
{: codeblock}

Dove `ACTIONVALUE` è il valore del campo di azione o parte del valore.

La seguente tabella mostra esempi di query per azioni diverse:

| Azione                 | Query di esempio                     |
|------------------------|----------------------------------|
| Esegui il provisioning di un servizio    | `action instance.create`         |
| Rimuovi un'istanza     | `action instance.delete`         |
| Aggiungi un utente             | `action user-management.user.create` |
{: caption="Tabella 4. Esempi di query in base al tipo di azione" caption-side="top"}



### Query per eventi la cui azione ha esito negativo
{: #views_step1_4}

Quando un'azione richiesta ha esito negativo, il campo **outcome** viene impostato su **failure**. Puoi immettere la seguente query per cercare questi tipi di eventi:

```
outcome failure
```
{: codeblock}


### Query in base alla criticità dell'evento
{: #views_step1_5}

Ogni evento ha un campo di **severità** che definisce il livello di minaccia che un'azione può avere sul cloud. 

I valori validi sono *normal*, *warning* e *critical*. 
* **Normal** è impostato per le azioni di routine nel cloud. Ad esempio, avvio di un'istanza o aggiornamento di un token. 
* **Warning** è impostato per le azioni in cui una risorsa cloud viene aggiornata o i relativi metadati vengono modificati. Ad esempio, l'aggiornamento della versione di un nodo di lavoro, la ridenominazione di un certificato o di un'istanza del servizio. 
* **Critical** è impostato per le azioni che influiscono sulla sicurezza nel cloud. Ad esempio, la modifica delle credenziali di un utente, l'eliminazione dei dati, l'accesso non autorizzato all'utilizzo di una risorsa cloud.

Puoi immettere la seguente query per cercare questi tipi di eventi:

```
severity VALUE
```
{: codeblock}

Dove `VALUE` può essere impostato su *normal*, *warning* o *critical*

Ad esempio, per eseguire una query per gli eventi critici, puoi immettere la seguente query:

```
severity critical
```
{: codeblock}



## Passo 3. Crea una vista personalizzata
{: #views_step3}

Dopo aver applicato la query di ricerca alla vista **Everything** o a una vista personalizzata esistente, completa la seguente procedura per salvare il risultato come vista personalizzata:

1. Nell'IU web, fai clic su **Unsaved View**.
2. Seleziona **Save as new view / alert**. Si apre la pagina *Create new view*.
3. Immetti un nome per la vista nel campo *Name*.
4. Facoltativamente, aggiungi una categoria. Immetti un nome e fai quindi clic su **Add this as new view category**.
5. Facoltativamente, collega un avviso. Viene visualizzata una nuova sezione per consentirti di configurare l'avviso.
6. Fai clic su **Save View**


## Passo 4. Personalizza il modo in cui le righe evento vengono visualizzate tramite una vista
{: #views_step4}

Esistono diverse opzioni per personalizzare la modalità di visualizzazione dei dati in una vista:
* Puoi modificare le proprietà di una vista, puoi ridenominare una vista, aggiungere o modificare la sua descrizione e applicare un formato di riga specifico.
* Puoi modificare il `log format` nella sezione *USER PREFERENCES*.
* Puoi applicare un template di riga dalla sezione *Tools*. Tieni presente che questo sovrascrive qualsiasi altra configurazione di riga. Se selezioni **Persist these settings**, tutte le viste nell'IU mostreranno i dati per il formato di riga specificato in questa sezione.
* Puoi applicare il colore a termini o stringhe impostando **Highlight Terms** nella sezione **Tools**.



### Modifica il formato di riga attraverso la pagina delle proprietà della vista
{: #views_step4_1}

Completa la seguente procedura per modificare il formato di una riga di evento un una singola vista:

1. Nella tua vista, seleziona **Edit View Properties**. Si apre la pagina *Edit View Properties*.

2. Immetti un formato di riga personalizzato nella sezione **Custom %LINE Template**. Il valore predefinito è impostato su `{{line}}`.

    Per ulteriori informazioni sulle linee guida del template di riga, vedi [Linee guida](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).

3. Fai clic su **Save properties*.



### Modifica il formato di riga attraverso la sezione delle preferenze utente
{: #views_step4_2}

Nella sezione **USER PREFERENCES**, puoi modificare l'ordine dei campi di dati visualizzati per ogni riga.

Per modificare il formato di una riga di evento, completa la seguente procedura:

1. Nell'IU web, fai clic sull'icona **Configuration** ![Icona Configuration](images/admin.png "Icona Admin").
2. Seleziona **USER PREFERENCES**. Viene visualizzata una nuova finestra.
3. Seleziona **Log Format**.
4. Modifica la sezione *Line Format* in modo che corrisponda ai tuoi requisiti. Trascina le caselle.


### Modifica il formato di riga attraverso il template di riga nella sezione degli strumenti
{: #views_step4_3}

Per modificare il formato di una riga di evento, completa la seguente procedura:

1. Nella vista, fai clic sull'icona **Tools** ![Icona Tools](images/tool.png "Icona Tools").
2. Nel campo **Line Template**, immetti il tuo formato di riga personalizzato. Per ulteriori informazioni sulle linee guida del template di riga, vedi [Linee guida](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).
3. Facoltativamente, fai clic su **Persist these settings** per applicare il formato di riga a tutte le viste.



### Evidenzia i termini
{: #view_events_step4_4}

Completa la seguente procedura per evidenziare i termini in una vista:

1. Nella vista, fai clic sull'icona **Tools** ![Icona Tools](images/tool.png "Icona Tools").
2. Nel campo **Line Template**, immetti una parola o una stringa nella sezione **Highlight Terms**.
3. Facoltativamente, fai clic su **Persist these settings** per applicare questa impostazione a tutte le viste.



## Modifica il nome e la descrizione di una vista personalizzata
{: #views_step5}

Puoi ridenominare una vista e puoi aggiungere o modificare la descrizione di una vista.


Completa la seguente procedura:

1. Nella tua vista, seleziona **Edit View Properties**. Si apre la pagina *Edit View Properties*.

    Puoi ridenominare la vista, aggiungere o modificare la descrizione della vista e applicare un formato di riga personalizzato.

2. Immetti un nuovo nome nella sezione **Rename View** per ridenominare la vista.

3. Immetti o modifica la descrizione nella sezione **Description**.

4. Fai clic su **Save properties**.



## Linee guida per la definizione dei template di riga
{: #views_line}

Considera le seguenti linee guida che devi applicare quando definisci un template di riga:
* Utilizza variabili di stile mustache `{{field.name}}` o di stile bash `${field.name}` per costruire il tuo template. 
* Utilizza `{{line}}` o `$@` per fare riferimento alla riga originale. 
* Tutti gli altri caratteri o stringhe vengono interpretati come valore letterale di testo. 


Ad esempio, puoi definire un template di riga come `{{initiator.id}} -- {{action}} -- {{message}}` per visualizzare questi campi per ogni evento in una vista.


