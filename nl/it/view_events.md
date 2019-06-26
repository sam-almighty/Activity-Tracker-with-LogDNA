---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #view_events}

Dopo aver eseguito il provisioning a un'istanza del servizio {{site.data.keyword.at_full_notm}} in {{site.data.keyword.cloud_notm}}, puoi visualizzare gli eventi tramite l'IU web {{site.data.keyword.at_full_notm}}. Gli eventi vengono visualizzati nella tua ora locale.
{:shortdesc}


## Visualizza gli eventi
{: #view_events_step1}

Completa la seguente procedura per visualizzare gli eventi:

1. Verifica che il tuo ID utente disponga delle autorizzazioni per avviare l'IU web e visualizzare gli eventi.  

    La seguente tabella elenca i ruoli minimi che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare, ricercare e filtrare gli eventi:

    <table>
      <caption>Tabella 1. Ruoli IAM</caption>
      <tr>
        <th>Ruolo</th>
        <th>Autorizzazione concessa</th>
      </tr>
      <tr>
        <td>Ruolo piattaforma: `Viewer`</td>
        <td>Consente all'utente di visualizzare l'elenco di istanze del servizio nel dashboard *Osservabilità*.</td>
      </tr>
      <tr>
        <td>Ruolo servizio: `Reader`</td>
        <td>Consente all'utente di avviare l'IU web e di visualizzare, cercare e filtrare gli eventi nell'IU web.</td>
      </tr>
    </table>

    Per ulteriori informazioni su come configurare le politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

2. [Vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

3. Fai clic sull'icona **Views** ![icona Configuration](images/views.png).

4. Seleziona **Everything** per visualizzare tutti gli eventi o una vista. 

Puoi visualizzare gli eventi tramite la vista che hai selezionato.



## Visualizza un sottoinsieme di eventi applicando una query di ricerca
{: #view_events_step2}

Puoi selezionare gli eventi visualizzati tramite una vista applicando una query di ricerca. Puoi salvare tale vista per riutilizzarla in seguito. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2).

 


## Visualizza un sottoinsieme di eventi applicando un periodo di tempo
{: #view_events_step3}

Puoi selezionare gli eventi visualizzati tramite una vista applicando un periodo di tempo.

Puoi applicare una data/ora specificando un tempo assoluto, un tempo relativo o un intervallo di tempo.

Completa la seguente procedura per passare a un tempo specifico:
1. [Vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Fai clic sull'icona **Views** ![icona Configuration](images/views.png).
3. Seleziona **Everything** oppure una vista.
4. Immetti una query di tempo. Scegli una delle seguenti opzioni:

    * Immetti un tempo assoluto per passare a un punto nel tempo nei tuoi eventi, ad esempio `May 20 7:00pm`.
    
    * Immetti un tempo relativo come `2 days ago`, `today at 12am` o `an hour ago`.

    * Immetti un intervallo di tempo come `yesterday 10am to yesterday 11am`, `last fri 4:30pm to 11/12 1 AM`, `last wed 4:30pm to 23/05 1 AM` o `May 20 10am to May 22 10am`. Assicurati di includere `to` per separare la data/ora iniziale dalla data/ora finale.

5. Fai clic su **ENTER**.

    Potresti ricevere il messaggio di errore: `Your request is taking longer than expected, try refreshing your browser in a bit as we try to catch up. Retry.` Potresti ricevere questo errore quando per il periodo di tempo che hai specificato non ci sono eventi disponibili da mostrare. Modifica la query di tempo e riprova.



## Visualizza un evento nel contesto
{: #view_events_step4}

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
{: #view_events_step5}


Completa la seguente procedura per copiare un evento negli appunti: 

1. Nell'IU web, fai clic sull'icona **Views** ![Icona Configuration](images/views.png "Icona Configuration").
2. Seleziona **Everything** oppure una vista personalizzata.
3. Identifica una riga che vuoi esplorare.
4. Espandi la riga di evento. 

    Vengono visualizzate le informazioni su etichette, tag e identificativi riga.

5. Fai clic su **Copy to clipboard** per copiare l'evento negli appunti.

Quando hai terminato di esplorare l'evento, fai clic su **Close** per chiudere la riga.




