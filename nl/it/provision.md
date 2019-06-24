---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# Provisioning di un'istanza
{: #provision}

Prima di poter monitorare e gestire i dati di evento con {{site.data.keyword.at_full_notm}}, devi eseguire il provisioning di un'istanza del servizio in {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Per eseguire il provisioning di un'istanza {{site.data.keyword.at_full_notm}} in una regione cloud pubblica, tieni conto delle seguenti informazioni:
* Devi selezionare il piano di servizio associato all'istanza, la regione in cui vengono raccolti i log e il piano che determina il periodo di conservazione per i tuoi log. Puoi scegliere da periodi di conservazione di 7, 14 o 30 giorni. In alternativa, {{site.data.keyword.at_full_notm}} offre un piano `Lite` che puoi utilizzare per visualizzare i tuoi eventi quando transitano per il sistema. Puoi visualizzare gli eventi utilizzando l'accodamento di eventi. Puoi anche progettare dei filtri per la preparazione all'upgrade a un piano con un periodo di conservazione più lungo. Questo piano ha un periodo di conservazione di 0 giorni.
* Il tuo ID utente deve disporre delle autorizzazioni per eseguire il provisioning di un servizio in un gruppo di risorse. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups).


Puoi eseguire il provisioning di solo 1 istanza del servizio per ogni regione {{site.data.keyword.cloud_notm}}.
{: important}

## Provisioning di un'istanza mediante il dashboard Osservabilità
{: #provision_ui}

Per eseguire il provisioning di un'istanza dal dashboard Osservabilità in {{site.data.keyword.cloud_notm}}, completa la seguente procedura:

1. [Accedi al tuo account {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/login){:new_window}.

	Dopo aver eseguito l'accesso con i tuoi ID e password utente, viene aperta la IU {{site.data.keyword.cloud_notm}}.

2. Vai all'icona di menu ![icona di menu](../../icons/icon_hamburger.svg). Seleziona quindi **Osservabilità** per accedere al dashboard *Osservabilità*.

3. Seleziona **Programma di traccia dell'attività**, quindi fai clic su **Crea istanza**. 

4. Immetti un nome per l'istanza del servizio.

5. Seleziona l'[ubicazione](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions) in cui intendi eseguire il provisioning dell'istanza. 

6. Seleziona un gruppo di risorse. 

    Per impostazione predefinita, è impostato il gruppo di risorse **Predefinito**.

    **Nota:** se non sei in grado di selezionare un gruppo di risorse, controlla di disporre delle autorizzazioni di modifica sul gruppo di risorse dove desideri eseguire il provisioning dell'istanza.

7. Seleziona il piano di servizio `Lite`. 

    Per impostazione predefinita, è impostato il piano Lite.

8. Fai clic su **Crea**.

Dopo che hai eseguito il provisioning di un'istanza, viene aperto il dashboard *Programma di traccia dell'attività*. 

Successivamente, vai all'IU web per visualizzare gli eventi nel tuo account. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events).



## Provisioning di un'istanza mediante il catalogo
{: #provision_catalog}

Per eseguire il provisioning di un'istanza di {{site.data.keyword.at_full_notm}} mediante il catalogo {{site.data.keyword.cloud_notm}}, completa la seguente procedura:

1. [Accedi al tuo account {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/login){:new_window}.

	Dopo aver eseguito l'accesso con i tuoi ID e password utente, viene aperta la IU {{site.data.keyword.cloud_notm}}.

2. Fai clic su **Catalogo**. Viene aperto l'elenco dei servizi disponibili in {{site.data.keyword.cloud_notm}}.

3. Per filtrare l'elenco dei servizi che viene visualizzato, seleziona la categoria **Strumenti per gli sviluppatori**.

4. Fai clic sul tile **{{site.data.keyword.at_full_notm}}**. 

5. Immetti un nome per l'istanza del servizio.

6. Seleziona l'ubicazione in cui intendi eseguire il provisioning dell'istanza. 

    Per ottenere l'elenco aggiornato delle ubicazioni disponibili per il servizio {{site.data.keyword.at_full_notm}}, vedi [Ubicazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions).

7. Seleziona un gruppo di risorse. 

    Per impostazione predefinita, è impostato il gruppo di risorse **Predefinito**.

    **Nota:** se non sei in grado di selezionare un gruppo di risorse, controlla di disporre delle autorizzazioni di modifica sul gruppo di risorse dove desideri eseguire il provisioning dell'istanza.

8. Seleziona il piano di servizio `Lite`. 

    Per impostazione predefinita, è impostato il piano Lite.

9. Fai clic su **Crea**.

Dopo che hai eseguito il provisioning di un'istanza, viene aperto il dashboard *Programma di traccia dell'attività*. 

Successivamente, passa all'IU web per gestire gli eventi nel tuo account. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Provisioning di un'istanza mediante la CLI
{: #provision_cli}

Per eseguire il provisioning di un'istanza di {{site.data.keyword.at_full_notm}} mediante la riga di comando, completa la seguente procedura:

1. [Prerequisito] Installazione della CLI {{site.data.keyword.cloud_notm}}. [Ulteriori informazioni](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Se la CLI è installata, continua con il passo successivo.

2. Accedi all'ubicazione in {{site.data.keyword.cloud_notm}} in cui vuoi eseguire il provisioning dell'istanza. Esegui il seguente comando: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

    Per ottenere l'elenco aggiornato delle ubicazioni disponibili per il servizio {{site.data.keyword.at_full_notm}}, vedi [Ubicazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions).

3. Configura il gruppo di risorse in cui vuoi eseguire il provisioning dell'istanza. Esegui il seguente comando: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    Per impostazione predefinita, è impostato il gruppo di risorse `default`.

4. Crea l'istanza. Esegui il comando [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create):

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    Dove

    * NAME è il nome dell'istanza.

    * Il valore *logdnaat* è il nome del servizio {{site.data.keyword.at_full_notm}} in {{site.data.keyword.cloud_notm}}

    * SERVICE_PLAN_NAME è il tipo di piano. I valori validi sono *lite*, *7-days*, *14-days*, *30-days*
    
    * LOCATION è la regione in cui viene creata l'istanza LogDNA. Per ottenere l'elenco aggiornato delle ubicazioni disponibili per il servizio {{site.data.keyword.at_full_notm}}, vedi [Ubicazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions).

    
Ad esempio, per eseguire il provisioning di un'istanza con il piano di conservazione di 7 giorni, esegui questo comando:

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



