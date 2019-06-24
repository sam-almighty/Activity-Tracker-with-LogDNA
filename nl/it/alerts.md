---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #alerts}

Attraverso l'IU web {{site.data.keyword.at_full_notm}}, puoi applicare query di ricerca per definire gli eventi che vengono visualizzati tramite una vista personalizzata. Quindi, puoi collegare un avviso a tale vista per ricevere una notifica quando si verifica una condizione. Puoi collegare uno o più avvisi a una vista. Puoi definire più canali di notifica per un avviso. Puoi disattivare la notifica degli avvisi. Puoi scollegare gli avvisi da una vista.
{:shortdesc}


## Prerequisiti
{: #alerts_prereqs}

* [Ulteriori informazioni sugli avvisi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts).

* **Devi avere un piano di servizio a pagamento** per il servizio {{site.data.keyword.at_full_notm}}. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).

* Verifica che il tuo ID utente disponga delle autorizzazioni per avviare l'IU web e visualizzare gli eventi. La seguente tabella elenca i ruoli minimi che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare, ricercare e filtrare gli eventi:

| Ruolo                      | Autorizzazione concessa            |
|---------------------------|-------------------------------|  
| Ruolo piattaforma: `Viewer`     | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Osservabilità. |
| Ruolo servizio: `Reader`      | Consente all'utente di avviare l'IU web e visualizzare gli eventi nell'IU web.  |
{: caption="Tabella 1. Ruoli IAM" caption-side="top"} 

Per ulteriori informazioni su come configurare le politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

 


## Passo 1. Vai all'IU web
{: #alerts_step1}

[Vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Passo 2. Crea una vista
{: #alerts_step2}

[Crea una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).



## Passo 3. [Facoltativo] Configura una preimpostazione (template di avviso)
{: #alerts_step3}

Per riutilizzare una configurazione di avviso con altre viste, configura una **preimpostazione di avviso**.
{: note}

Per configurare una preimpostazione, completa la seguente procedura:

1. Nell'IU web, seleziona l'icona **Configuration** ![Icona Configuration](images/admin.png "Icona Admin").
2. Seleziona **Alerts**.
3. Seleziona **Add a preset alert**.
4. Scegli un canale di notifica. Per l'elenco dei canali supportati, vedi [Canali di notifica degli avvisi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
5. Seleziona il tipo di avviso. Scegli il tipo di avviso di presenza (**Presence alert**) per ricevere una notifica quando il numero di eventi visualizzati in una vista è superiore a quello previsto. Scegli il tipo di avviso di assenza (**Absence alert**) per ricevere una notifica quando il numero di eventi visualizzati in una vista è inferiore a quello previsto o non ci sono eventi visualizzati. 
5. Scegli un canale di notifica. Per l'elenco dei canali supportati, vedi [Canali di notifica degli avvisi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
6. Definisci le condizioni di soglia.

    1. Seleziona una frequenza temporale. Ad esempio, 12 ore.

    2. Immetti il numero di righe evento dopo le quali vuoi venga attivato l'avviso.

    3. Seleziona se desideri che entrambe le condizioni vengano controllate o solo una.

7. Aggiungi i dettagli per il canale di notifica che hai scelto.

    Ad esempio, per il canale di notifica email, aggiungi uno o più destinatari e, facoltativamente, un fuso orario.

8. Fai clic su **Save alert**.



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
5. Seleziona il tipo di avviso. Scegli il tipo di avviso di presenza (**Presence alert**) per ricevere una notifica quando il numero di eventi visualizzati in una vista è superiore a quello previsto. Scegli il tipo di avviso di assenza (**Absence alert**) per ricevere una notifica quando il numero di eventi visualizzati in una vista è inferiore a quello previsto o non ci sono eventi visualizzati. 
6. Definisci le condizioni di soglia.

    1. Seleziona una frequenza temporale. Ad esempio, 12 ore.

    2. Immetti il numero di righe evento dopo le quali vuoi venga attivato l'avviso.

    3. Seleziona se desideri che entrambe le condizioni vengano controllate o solo una.

7. Aggiungi i dettagli per il canale di notifica che hai scelto.

    Ad esempio, per il canale di notifica email, aggiungi uno o più destinatari e, facoltativamente, un fuso orario.

8. Fai clic su **Save alert**.



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












