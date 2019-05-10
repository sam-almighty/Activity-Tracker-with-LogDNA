---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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
{: #views.md}

Tramite l'IU web {{site.data.keyword.at_full_notm}}, puoi applicare dei criteri di ricerca e di filtro per definire gli eventi che vengono visualizzati tramite una vista personalizzata.
{:shortdesc}


## Prerequisiti
{: #views_prereqs}

Prima di cominciare, controlla che il tuo ID utente abbia le autorizzazioni per avviare l'IU web e gli eventi della vista. Successivamente, [vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

**Nota:** devi essere un amministratore del servizio {{site.data.keyword.at_full_notm}}, un amministratore dell'istanza {{site.data.keyword.at_full_notm}} o disporre delle autorizzazioni IAM dell'account per gestire le politiche.

La seguente tabella elenca le politiche minime che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare, ricercare e filtrare gli eventi:

| Ruolo                      | Autorizzazione concessa            |
|---------------------------|-------------------------------|  
| Ruolo piattaforma: `Viewer`     | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Observability. |
| Ruolo servizio: `Reader`      | Consente all'utente di avviare l'IU web e visualizzare gli eventi nell'IU web.  |
{: caption="Tabella 1. Politiche IAM" caption-side="top"} 

Per ulteriori informazioni su come configurare queste politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o a un ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Passo 1. Filtra gli eventi 
{: #views_step1}

Puoi filtrare gli eventi per origine, applicazione e livello di log.  

* Un'origine può essere un host, un computer, una macchina virtuale o un'applicazione Heroku. 
* Un'applicazione rappresenta un file di log, un programma o un contenitore. 
* Esempi di livelli di log sono: INFO, DEBUG, ERROR 

Per filtrare i log, completa la seguente procedura: 

1. Nell'IU web, fai clic sull'icona **Views** ![Icona Configuration](images/views.png "Icona Configuration").
2. Seleziona **Everything** oppure una vista.
3. Espandi **All Tags** per visualizzare l'elenco delle tag disponibili. Scegli quindi quelle che desideri. 
4. Espandi **All Sources** per visualizzare l'elenco delle origini disponibili. Scegli quindi quelle che desideri. 
5. Espandi **All Apps** per visualizzare l'elenco delle applicazioni disponibili. Scegli quindi quelle che desideri. 
6. Espandi **All Levels** per visualizzare l'elenco dei livelli disponibili. Scegli quindi quelle che desideri. 

Come applichi i filtri, tieni presente che il nome della vista viene modificato con **Unsaved View**.

**Nota:** in ciascuna sezione, puoi raggruppare più opzioni in un gruppo. Raggruppa le tag, le origini, le applicazioni e i livelli per riutilizzare questi raggruppamenti quando filtri i dati in altre viste personalizzate. 

Per creare un gruppo, seleziona più valori. Fai quindi clic su **Save as group**. Immetti un nome per il gruppo e salvalo. 


## Passo 2. Cerca gli eventi 
{: #views_step2}

Quando ricerchi gli eventi, la ricerca applica tutti i filtri e le query di tempo configurati in tale vista. 

Puoi eseguire delle semplici ricerche (ricerca di stringa di un singolo termine), una ricerca composta (più termini e operatori di ricerca), ricerche di campo se la riga di log può essere analizzata e altre ancora. Per ulteriori informazioni, vedi il documento relativo alla [modalità di ricerca dei log nei documenti LogDNA ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://docs.logdna.com/docs/search){:new_window}. 

**Nota:** gli operatori AND e OR sono sensibili a maiuscole/minuscole e devono essere scritti in maiuscolo. 

Come applichi i criteri di ricerca, tieni presente che il nome della vista viene modificato con **Unsaved View**.



## Passo 3. Crea una vista personalizzata 
{: #views_step3}

Dopo aver applicato un intervallo di tempo, i filtri e i criteri di ricerca per la vista **Everything** o per una vista personalizzata esistente, completa la seguente procedura per salvare il risultato come una vista personalizzata:

1. Nell'IU web, fai clic su **Unsaved View**.
2. Seleziona **Save as new view / alert**. Si apre la pagina *Create new view*.
3. Immetti un nome per la vista nel campo *Name*. 
4. Facoltativamente, aggiungi una categoria. Immetti un nome e fai quindi clic su **Add this as new view category**. 
5. Facoltativamente, collega un avviso. Viene visualizzata una nuova sezione per consentirti di configurare l'avviso. 
6. Fai clic su **Save View**




