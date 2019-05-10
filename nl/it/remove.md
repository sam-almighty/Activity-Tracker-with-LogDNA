---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# Rimozione di un'istanza 
{: #remove}

Puoi rimuovere un'istanza del servizio {{site.data.keyword.at_full_notm}} dall'IU {{site.data.keyword.cloud_notm}} o dalla riga di comando. {:shortdesc}



## Rimozione di un'istanza mediante l'IU {{site.data.keyword.cloud_notm}} 
{: #remove_ui}

Per rimuovere un'istanza di {{site.data.keyword.at_full_notm}} utilizzando l'IU {{site.data.keyword.cloud_notm}}, completa la seguente procedura: 

1. [Accedi al tuo account {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/login){:new_window}.

	Dopo aver eseguito l'accesso con i tuoi ID e password utente, viene aperta la IU {{site.data.keyword.cloud_notm}}.

2. Vai all'icona di menu ![icona di menu ](../../icons/icon_hamburger.svg) &gt; **Osservabilità** per accedere al dashboard *Osservabilità*. 

3. Seleziona **Programma di traccia dell'attività**. Viene visualizzato l'elenco delle istanze.

4. Seleziona l'istanza che desideri eliminare. 

5. Dal menu *Azione*, seleziona **Rimuovi**. 

Successivamente, rimuovi le autorizzazioni concesse agli utenti per utilizzare l'istanza che hai eliminato. 

## Rimozione di un'istanza mediante la CLI 
{: #remove_cli}

Per rimuovere un'istanza di {{site.data.keyword.at_full_notm}} mediante la riga di comando, completa la seguente procedura: 

1. [Prerequisito] Installazione della CLI {{site.data.keyword.cloud_notm}}.

   Per ulteriori informazioni, vedi [Installazione della CLI {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Se la CLI è installata, continua con il passo successivo.

2. Accedi alla regione in {{site.data.keyword.cloud_notm}} dove desideri eseguire il provisioning dell'istanza. Esegui il seguente comando: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Imposta il gruppo di risorse in cui è stato eseguito il provisioning dell'istanza. Esegui il seguente comando: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    Per impostazione predefinita, è impostato il gruppo di risorse *default*.

4. Rimuovi l'istanza. Esegui il comando [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete): 

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    Dove NAME è il nome dell'istanza. 

    Per elencare tutte le istanze disponibili nel gruppo di risorse in cui hai eseguito l'accesso, immetti il seguente comando: 

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
Ad esempio, per rimuovere un'istanza, immetti il seguente comando: 

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

Successivamente, rimuovi le autorizzazioni concesse agli utenti per utilizzare l'istanza che hai eliminato. 


