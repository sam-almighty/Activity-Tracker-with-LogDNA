---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# Configurazione degli avvisi
{: #alerts.md}

Tramite l'IU web {{site.data.keyword.at_full_notm}}, puoi applicare dei criteri di ricerca e di filtro per definire gli eventi che vengono visualizzati tramite una vista personalizzata. Successivamente, puoi collegare un avviso a una vista per ricevere una notifica. Puoi collegare uno o più avvisi a una vista. Puoi definire più canali di notifica per un avviso. Puoi disattivare la notifica degli avvisi. Puoi scollegare gli avvisi da una vista.
{:shortdesc}


Puoi configurare le seguenti condizioni per un avviso: 

* *Frequenza temporale*: specifica la frequenza con cui attivare un avviso. I valori validi sono: 30 secondi, 1 minuto, 5 minuti, 15 minuti, 30 minuti, 1 ora, 6 ore, 12 ore, 24 ore 
* *Contatore righe evento*: specifica il numero di righe evento che corrispondono ai criteri di filtro e ricerca della vista. Quando il numero di righe evento viene raggiunto, viene attivato un avviso.

Puoi decidere se vengono controllate entrambe le condizioni oppure solo una. Se sono impostate entrambe le condizioni, viene attivato un avviso quando viene raggiunta una qualsiasi delle soglie.  

Ad esempio, puoi configurare un avviso che viene attivato dopo 30 secondi o quando vengono raccolte 100 righe evento che corrispondono ai criteri di filtro e ricerca della vista. 

Puoi configurare più canali di notifica. I canali validi sono: `email`, `Slack`, `PagerDuty`, `Webhook`, `OpsGenie`, `Datadog`, `AppOptics`, `VictorOps` 

Puoi anche definire una **preimpostazione**. Una preimpostazione è un template di avviso che puoi collegare a qualsiasi numero di viste.  

Con la vista viene visualizzata un'icona a forma di campana per indicare che a questa vista è collegato un avviso. 


## Prerequisiti
{: #views_prereqs}

Prima di cominciare, controlla che il tuo ID utente abbia le autorizzazioni per avviare l'IU web e gli eventi della vista.  

**Nota:** devi essere un amministratore del servizio {{site.data.keyword.at_full_notm}}, un amministratore dell'istanza {{site.data.keyword.at_full_notm}} o disporre delle autorizzazioni IAM dell'account per gestire le politiche.

La seguente tabella elenca le politiche minime che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare, ricercare e filtrare gli eventi:

| Ruolo                      | Autorizzazione concessa            |
|---------------------------|-------------------------------|  
| Ruolo piattaforma: `Viewer`     | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Observability. |
| Ruolo servizio: `Reader`      | Consente all'utente di avviare l'IU web e visualizzare gli eventi nell'IU web.  |
{: caption="Tabella 1. Politiche IAM" caption-side="top"} 

Per ulteriori informazioni su come configurare queste politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o a un ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

**Devi avere un piano di servizio a pagamento** per il servizio {{site.data.keyword.at_full_notm}}. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 


## Passo 1. Vai all'IU web 
{: #alerts_step1}

[Vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Passo 2. Crea una vista
{: #alerts_step2}

[Crea una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md).



## Passo 3. [Facoltativo] Configura una preimpostazione (template di avviso)
{: #alerts_step3}

Per riutilizzare una configurazione di avviso con altre viste, configura una **preimpostazione di avviso**.
{: note}

Per configurare una preimpostazione, completa la seguente procedura: 

1. Nell'IU web, seleziona l'icona **Configuration** ![Icona Configuration](images/admin.png "Icona Admin").
2. Seleziona **Alerts**.
3. Seleziona **Add a preset alert**.
4. Scegli un canale di notifica.  
5. Definisci le condizioni di soglia. 

    1. Seleziona una frequenza temporale. Ad esempio, 12 ore. 

    2. Immetti il numero di righe evento dopo le quali vuoi venga attivato l'avviso.

    3. Seleziona se desideri che entrambe le condizioni vengano controllate o solo una. 

6. Aggiungi i dettagli per il canale di notifica che hai scelto. 

    Ad esempio, per il canale di notifica email, aggiungi uno o più destinatari e, facoltativamente, un fuso orario. 

7. Fai clic su **Save alert**.



## Passo 4. Configura un avviso
{: #alerts_step4}

Scegli una delle seguenti opzioni per collegare un avviso a una vista:

### Opzione 1. Configura un avviso utilizzando una preimpostazione
{: #alerts_step4_preset}

Per collegare una preimpostazione a una vista, completa la seguente procedura: 

1. Nell'IU web, fai clic sull'icona **Views** ![Icona Configuration](images/views.png).
2. Fai clic sul nome della vista a cui vuoi collegare un avviso. Quindi, seleziona **Attach an alert**.
3. Scegli una preimpostazione per riutilizzare una definizione di avviso.  
4. Fai clic su **Save alert**. 




### Opzione 2. Configura un avviso specifico per la vista
{: #alerts_step4_view}

Completa la seguente procedura per collegare un avviso a una vista:

1. Nell'IU web, fai clic sull'icona **Views** ![Icona Configuration](images/views.png).
2. Fai clic sul nome della vista. Quindi, seleziona **Attach an alert**.
3. Scegli **view-specific alert**.
4. Scegli un canale di notifica.  
5. Definisci le condizioni di soglia. 

    1. Seleziona una frequenza temporale. Ad esempio, 12 ore. 

    2. Immetti il numero di righe evento dopo le quali vuoi venga attivato l'avviso.

    3. Seleziona se desideri che entrambe le condizioni vengano controllate o solo una. 

6. Aggiungi i dettagli per il canale di notifica che hai scelto. 

    Ad esempio, per il canale di notifica email, aggiungi uno o più destinatari e, facoltativamente, un fuso orario. 

7. Fai clic su **Save alert**.



## Elimina una preimpostazione (template di avviso) 
{: #alerts_delete_preset}

Per eliminare una preimpostazione, completa la seguente procedura: 

1. Nell'IU web, seleziona l'icona **Configuration** ![Icona Configuration](images/admin.png "Icona Admin").
2. Seleziona **Alerts**.
3. Passa il puntatore del mouse sul pulsante *edit* della preimpostazione che desideri eliminare. Viene visualizzata l'opzione *delete*. 
4. Seleziona **Delete**.
5. Conferma che desideri eliminare la preimpostazione. Fai clic su **Delete**.

## Scollega un avviso specifico per la vista da una vista 
{: #alerts_delete_view}

Per scollegare una preimpostazione, completa la seguente procedura: 

1. Nell'IU web, seleziona l'icona **Configuration** ![Icona Configuration](images/admin.png "Icona Admin").
2. Seleziona **Alerts**.
3. Passa il puntatore del mouse sul pulsante *edit* dell'avviso che desideri eliminare. Viene visualizzata l'opzione *delete*. 
4. Seleziona **Detach**.
5. Conferma che desideri eliminare l'avviso. Fai clic su **Detach**.












