---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# Evénements d'instance de service  
{: #at_events_rc}

En tant que responsable de la sécurité, auditeur ou responsable, vous pouvez utiliser le service {{site.data.keyword.at_full_notm}} pour suivre comment les utilisateurs et les applications interagissent avec les services {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

Le service {{site.data.keyword.at_full_notm}} enregistre les activités initiées par l'utilisateur qui changent l'état d'un service dans {{site.data.keyword.cloud_notm}}. Pour commencer à surveiller les actions de vos utilisateurs, veuillez vous reporter à [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 


## Evénements liés à la mise à disposition et à la gestion des instances de service
{: #rc_provision}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                         | Description |
|--------------------------------|---------|
| `service_name.instance.create` | Un événement est généré lorsque vous mettez à disposition une instance de service. |
| `service_name.instance.update` | Un événement est généré lorsque vous renommez une instance de service ou lorsque vous modifiez le plan de service. |
| `service_name.instance.delete` | Un événement est généré lorsqu'une instance de service est supprimée. |
{: caption="Tableau 1. Actions qui génèrent des événements" caption-side="top"} 


##  Evénements de gestion des alias associés à une instance de service
{: #rc_alias}

Un alias est une connexion entre votre service géré par IAM dans un groupe de ressources et une application dans une organisation ou un espace.

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                         | Description |
|--------------------------------|---------|
| `service_name.alias.create` | Un événement est généré lorsqu'un alias d'une instance est créé. |
| `service_name.alias.update` | Un événement est généré lorsqu'un alias d'une instance est mis à jour. |
| `service_name.alias.delete` | Un événement est généré lorsqu'un alias d'une instance est supprimé. |
{: caption="Tableau 2. Actions qui génèrent des événements" caption-side="top"} 


##  Evénements de gestion des données d'identification associés à une instance de service
{: #rc_keys}

Les données d'identification du service fournissent les informations nécessaires pour connecter une application à une instance de service.  

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                         | Description |
|--------------------------------|---------|
| `service_name.key.create` | Un événement est généré lorsqu'une clé d'API est créée pour une instance de service via la section *Données d'identification pour le service* de l'interface utilisateur de l'instance de service. |
| `service_name.key.delete` | Un événement est généré lorsqu'une clé d'API qui est associée à une instance de service est supprimée de la section *Données d'identification pour le service* de l'interface utilisateur de l'instance de service. |
{: caption="Tableau 3. Actions qui génèrent des événements" caption-side="top"} 



##  Evénements de liaison d'une instance de service à une application et de suppression d'une telle liaison
{: #rc_bind}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                         | Description |
|--------------------------------|---------|
| `service_name.binding.create` | Un événement est généré lorsque vous liez une instance de service à une application. |
| `service_name.binding.delete` | Un événement est généré lorsque vous annulez la liaison d'une instance de service à une application. |
{: caption="Tableau 4. Actions qui génèrent des événements" caption-side="top"} 



## Où rechercher les événements ?
{: #rc_ui}

Les événements sont disponibles dans la région **Francfort (eu-de)**.  

Pour afficher ces événements, vous devez [mettre à disposition une instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) du service {{site.data.keyword.at_full_notm}} dans la région **Francfort (eu-de)**. Ensuite, vous devez [ouvrir l'interface utilisateur {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 



## Analyse des événements
{: #rc_analyze}

**Action : service_name.instance.delete**

Lorsqu'une instance de service est supprimée, prenez note des informations suivantes : 
* D'autres actions sont déclenchées automatiquement pour nettoyer les droits IAM. Ces actions suppriment les règles configurées pour que les utilisateurs et les ID service du compte puissent utiliser l'instance de service.  
* L'initiateur de ces actions est un ID service {{site.data.keyword.IBM_notm}}. 


Si aucune stratégie IAM n'est configurée pour les utilisateurs et ID service de l'instance de service supprimée, les événements automatiquement générés pour l'une de ces ressource signalent un résultat `failure` avec un code résultat `404`. L'exemple suivant montre les événements générés si une instance de service pour laquelle aucune stratégie n'a été configurée dans le compte est supprimée. 

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



