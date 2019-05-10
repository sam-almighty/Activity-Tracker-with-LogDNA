---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# Passaggio alla IU web 
{: #launch}

Dopo aver eseguito il provisioning a un'istanza del servizio {{site.data.keyword.at_full_notm}} in {{site.data.keyword.cloud_notm}}, puoi visualizzare, monitorare e gestire gli eventi tramite l'IU web {{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Passo 1. Concessione di politiche IAM a un utente per visualizzare i dati  
{: #step1}

**Nota:** devi essere un amministratore del servizio {{site.data.keyword.at_full_notm}}, un amministratore di un'istanza {{site.data.keyword.at_full_notm}} o disporre delle autorizzazioni IAM dell'account per concedere le politiche ad altri utenti.

La seguente tabella elenca le politiche minime che un utente deve avere per poter avviare l'IU web e visualizzare i dati tramite l'IU web {{site.data.keyword.at_full_notm}}:

| Ruolo                      | Autorizzazione concessa       |
|---------------------------|---------------------|
| Ruolo piattaforma: `Viewer`   | Consente all'utente di visualizzare l'elenco delle istanze del servizio nel dashboard Observability. |
| Ruolo servizio: `Reader`    |Consente all'utente di visualizzare gli eventi tramite l'IU web. | 
{: caption="Tabella 1. Politiche IAM" caption-side="top"} 

Per ulteriori informazioni, vedi [Concessione delle autorizzazioni utente a un utente o a un ID servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Passo 2. Avvio dell'IU web mediante l'IU {{site.data.keyword.cloud_notm}} 
{: #launch_step2}

Avvia l'IU web all'interno del contesto di un'istanza {{site.data.keyword.at_full_notm}}, dall'IU {{site.data.keyword.cloud_notm}}.  

Completa la seguente procedura per avviare l'IU web:

1. [Accedi al tuo account {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/login){:new_window}.

	Dopo che hai eseguito l'accesso con il tuo ID utente e la tua password, viene aperto il dashboard {{site.data.keyword.cloud_notm}}.

2. Nel menu di navigazione, seleziona **Osservabilità**. 

3. Seleziona **Programma di traccia dell'attività**. 

    Viene visualizzato l'elenco delle istanze disponibili in {{site.data.keyword.cloud_notm}}.

4. Seleziona un'istanza. Fai quindi clic su **Visualizza LogDNA**.

Viene aperta l'IU web


## Ottenimento dell'URL dell'IU web da {{site.data.keyword.cloud_notm}} 
{: #launch_get}

Per ottenere l'URL dell'IU web, completa la seguente procedura da un terminale: 

1. Imposta il gruppo di risorse in cui viene eseguito il provisioning dell'istanza {{site.data.keyword.at_full_notm}}.

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. Imposta il nome dell'istanza {{site.data.keyword.at_full_notm}}.

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. Imposta l'endpoint.

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. Imposta il token IAM.

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **Nota:** se stai utilizzando un terminale MacOS, il comando è il seguente: `export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. Imposta l'ID del gruppo di risorse.

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. Imposta l'URL dell'IU web in una variabile.

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. Ottieni l'URL dell'IU web. 

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

