---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# Visualizzazione degli eventi
{: #view_events.md}

Dopo aver eseguito il provisioning a un'istanza del servizio {{site.data.keyword.at_full_notm}} in {{site.data.keyword.cloud_notm}}, puoi visualizzare gli eventi tramite l'IU web {{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Prerequisiti
{: #view_events_prereqs}

Prima di cominciare, controlla che il tuo ID utente abbia le autorizzazioni per avviare l'IU web e gli eventi della vista. 

**Nota:** devi essere un amministratore del servizio {{site.data.keyword.at_full_notm}}, un amministratore dell'istanza {{site.data.keyword.at_full_notm}} o disporre delle autorizzazioni IAM dell'account per gestire le politiche.

La seguente tabella elenca le politiche minime che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare gli eventi:

| Ruolo                      | Autorizzazione concessa            |
|---------------------------|-------------------------------|  
| Ruolo piattaforma: `Viewer`     | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Observability. |
| Ruolo servizio: `Reader`      | Consente all'utente di avviare l'IU web e visualizzare gli eventi nell'IU web.  |
{: caption="Tabella 1. Politiche IAM" caption-side="top"} 

Per ulteriori informazioni su come configurare queste politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o a un ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Visualizza gli eventi tramite l'IU web 
{: #view_events_step1}

Per avviare l'IU web {{site.data.keyword.at_full_notm}}, completa la seguente procedura:

1. [Accedi al tuo account {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/login){:new_window}.

	Dopo che hai effettuato l'accesso con i tuoi ID utente e password, viene aperto il *dashboard* {{site.data.keyword.cloud_notm}}. 

2. Vai all'icona di menu ![icona di menu](../../icons/icon_hamburger.svg) e seleziona **Osservabilità**. 

3. Seleziona **Programma di traccia dell'attività**. 

    Viene visualizzato l'elenco delle istanze di {{site.data.keyword.at_full_notm}}.

    **Nota:** è presente 1 istanza per regione.

4. Seleziona l'istanza nella regione in cui vuoi visualizzare gli eventi. Fai quindi clic su **Visualizza LogDNA**.

Si apre l'IU web {{site.data.keyword.at_full_notm}} che mostra la vista **Everything**. Tramite questa vista, puoi visualizzare gli eventi nel tuo account per la regione che hai selezionato. 

**Nota:** se disponi di un piano `Lite` e non puoi visualizzare gli eventi che stai cercando, potresti dover eseguire l'upgrade a un piano a pagamento per abilitare le funzionalità di ricerca sugli eventi precedenti. Il numero di giorni in cui gli eventi sono disponibili per la ricerca dipende dal piano che scegli. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).


## Personalizza la tua vista predefinita 
{: #view_events_step2}

Nella sezione **USER PREFERENCES**, puoi modificare l'ordine dei campi di dati visualizzati per ogni riga. 

Per modificare il formato di una riga di evento, completa la seguente procedura: 

1. Nell'IU web, fai clic sull'icona **Configuration** ![Icona Configuration](images/admin.png "Icona Admin").
2. Seleziona **USER PREFERENCES**. Viene visualizzata una nuova finestra.
3. Seleziona **Log Format**.
4. Modifica la sezione *Line Format* in modo che corrisponda ai tuoi requisiti. Trascina le caselle. 




## Visualizza un evento nel contesto 
{: #view_events_step3}

In qualsiasi momento, puoi visualizzare ogni riga di evento nel contesto.

Completa la seguente procedura: 

1. Nell'IU web, fai clic sull'icona **Views** ![Icona Configuration](images/views.png "Icona Configuration").
2. Seleziona **Everything** oppure una vista personalizzata. 
3. Identifica una riga che vuoi esplorare.
4. Espandi la riga di evento. 

    Vengono visualizzate le informazioni su etichette, tag e identificativi riga.

5. Fai clic su **View in Context** per visualizzare la riga di evento nel contesto delle altre righe voci da tale host, applicazione o entrambi.

Quando hai terminato di esplorare l'evento, fai clic su **Close** per chiudere la riga.




## Copia un evento negli appunti
{: #view_events_step4}


Completa la seguente procedura per copiare un evento negli appunti:  

1. Nell'IU web, fai clic sull'icona **Views** ![Icona Configuration](images/views.png "Icona Configuration").
2. Seleziona **Everything** oppure una vista personalizzata. 
3. Identifica una riga che vuoi esplorare.
4. Espandi la riga di evento. 

    Vengono visualizzate le informazioni su etichette, tag e identificativi riga.

5. Fai clic su **Copy to clipboard** per copiare l'evento negli appunti.

Quando hai terminato di esplorare l'evento, fai clic su **Close** per chiudere la riga.




