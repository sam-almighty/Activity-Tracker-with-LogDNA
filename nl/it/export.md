---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# Esportazione degli eventi
{: #export}

Puoi esportare i dati in formato JSONL da un'istanza {{site.data.keyword.at_full_notm}} in un file locale. Puoi esportare i log in modo programmatico con l'API REST LogDNA oppure tramite l'IU web.
{:shortdesc}


## Prerequisiti
{: #export_prereqs}

* [Ulteriori informazioni sull'esportazione di eventi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_export).

* **Devi avere un piano di servizio a pagamento** per il servizio {{site.data.keyword.at_full_notm}}. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 

* Verifica che il tuo ID utente disponga delle autorizzazioni per avviare l'IU web e visualizzare gli eventi. La seguente tabella elenca i ruoli minimi che un utente deve avere per poter avviare l'IU web {{site.data.keyword.at_full_notm}} e visualizzare, ricercare e filtrare gli eventi:

| Ruolo                      | Autorizzazione concessa            |
|---------------------------|-------------------------------|  
| Ruolo piattaforma: `Viewer`     | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Osservabilità. |
| Ruolo servizio: `Reader`      | Consente all'utente di avviare l'IU web e visualizzare gli eventi nell'IU web.  |
{: caption="Tabella 1. Ruoli IAM" caption-side="top"} 

Per ulteriori informazioni su come configurare le politiche per un utente, vedi [Concessione delle autorizzazioni utente a un utente o ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Passo 1. Vai all'IU web
{: #export_step1}

[Vai all'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Passo 2. Crea una vista
{: #export_step2}

[Crea una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).


## Passo 3. Esporta i dati
{: #export_step3}

Scegli una delle seguenti opzioni per esportare gli eventi:

### Opzione 1. Esportazione degli eventi dall'IU web
{: #export_ui}

Completa la seguente procedura per esportare i dati:

1. Fai clic sull'icona **Views** ![icona Configuration](images/views.png).
2. Seleziona **Everything** oppure una vista.
3. Applica un intervallo di tempo, i filtri e i criteri di ricerca fino a quando non vedi le voci che desideri esportare.
4. Fai clic su **Unsaved View** se stai iniziando dalla vista **Everything**. Fai clic sul nome della tua vista, se hai selezionato una vista nel passo precedente.
5. Seleziona **Export lines**. Viene visualizzata una nuova finestra.
6. Controlla l'intervallo di tempo. Se hai bisogno di modificarlo, fai clic sull'intervallo di tempo predefinito nel campo *Change the Time Range for export*.
7. Seleziona **Prefer newer lines** o **Prefer older lines** nel caso in cui la richiesta di esportazione superi il limite di righe.
8. Controlla la tua email. Ricevi un'email da **LogDNA** con un link per scaricare le righe esportate.


### Opzione 2. Esportazione degli eventi in modo programmatico utilizzando l'API
{: #export_api}

Completa la seguente procedura per esportare gli eventi in modo programmatico:

1. Genera una chiave di servizio. 

    **Nota:** per completare questo passo, devi disporre del ruolo **gestore** per il servizio o l'istanza {{site.data.keyword.at_full_notm}}.

    1. [Avvia l'IU web {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2).

    2. Seleziona l'icona **Configuration** ![Icona Configuration](images/admin.png). Seleziona quindi **Organization**. 

    3. Seleziona **API keys**.

        Puoi visualizzare le chiavi di servizio create. 

    4. Fai clic su **Generate Service Key**. Una nuova chiave viene aggiunta all'elenco. Copia questa chiave.

2. Esporta gli eventi. Immetti il seguente comando cURL:

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    Dove 

    * ENDPOINT rappresenta il punto di ingresso del servizio. Ogni regione ha un URL differente. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints).
    * QUERY_PARAMETERS sono i parametri che definiscono i criteri di filtro applicati alla richiesta di esportazione.
    * SERVICE_KEY è la chiave che hai creato nel passo precedente.

La seguente tabella elenca i parametri di query che puoi impostare:

| Parametro di query | Tipo       | Stato     | Descrizione |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | Obbligatorio   | Ora di inizio. Imposta come data/ora UNIX in secondi o millisecondi. |
| `to`        | `int32`      | Obbligatorio   | Ora di fine. Imposta come data/ora UNIX in secondi o millisecondi.    |
| `size`      | `string`     | Facoltativo   | Numero di righe di log da includere nell'esportazione.  | 
| `hosts`     | `string`     | Facoltativo   | Elenco separato da virgole di host. |
| `apps`      | `string`     | Facoltativo   | Elenco separato da virgole di applicazioni. |
| `levels`    | `string`     | Facoltativo   | Elenco separato da virgole di livelli di log. |
| `query`     | `string`     | Facoltativo   | Query di ricerca. Per ulteriori informazioni, vedi [Cerca nei log](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6). |
| `prefer`    | `string`     | Facoltativo   | Definisce le righe di log che desideri esportare. I valori validi sono `head`, prime righe del log, e `tail`, ultime righe del log. Se non viene specificato, per impostazione predefinita viene utilizzato tail.  |
| `email`     | `string`     | Facoltativo   | Specifica l'email con il link scaricabile della tua esportazione. Per impostazione predefinita, le righe di log sono inviate in flusso.|
| `emailSubject` | `string`     | Facoltativo   | Utilizzalo per impostare l'oggetto della email. </br>Utilizza `%20` per rappresentare uno spazio. Un valore di esempio può essere `Export%20logs`. |
{: caption="Parametri di query" caption-side="top"} 

Ad esempio, per inviare in streaming gli eventi nel terminale, puoi eseguire questo comando:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

Per inviare una email con il link per scaricare gli eventi specificati nell'esportazione, puoi eseguire questo comando:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


Per inviare un'email con un oggetto personalizzato, puoi eseguire questo comando:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

