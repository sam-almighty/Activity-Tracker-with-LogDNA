---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# Evénements de gestion des comptes  
{: #at_events_acc_mgt}

En tant que responsable de la sécurité, auditeur ou responsable, vous pouvez utiliser le service {{site.data.keyword.at_full_notm}} pour suivre comment les utilisateurs et les applications interagissent avec le compte {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

Le service {{site.data.keyword.at_full_notm}} enregistre les activités initiées par l'utilisateur qui changent l'état d'un service dans {{site.data.keyword.cloud_notm}}. Pour commencer, voir [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started).  



## Evénements de gestion des comptes
{: #at_events_acc_mgt_account}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                               | Description |
|--------------------------------------|-------------|
| `billing.account.create`             | Un événement est généré lorsque vous mettez à disposition un compte une fois que l'ID compte a été affecté au compte. |
| `billing.account.update`             |Un événement est généré lorsque vous mettez à jour les informations sur le compte.|
| `billing.account.active`             | Un événement est généré lorsque vous vérifiez le compte, c'est-à-dire quand le compte devient actif. |
| `billing.account.subscription.create` | Un événement est généré lorsque vous créez un <a href="/docs/account?topic=account-accounts#subscription-account">compte d'abonnement</a>. |
{: caption="Tableau 1. Actions qui génèrent des événements" caption-side="top"} 




## Evénements liés à la gestion des utilisateurs
{: #at_events_acc_mgt_users}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                               | Description |
|--------------------------------------|-------------|
| `user-management.user.create`        | Un événement est généré lorsque vous envoyez une invitation à un utilisateur pour qu'il rejoigne un compte. |
| `user-management.user.active`        | Un événement est généré lorsque vous activez l'utilisateur dans le compte. Lorsque l'utilisateur vérifie l'adresse e-mail, l'événement est généré. |
| `user-management.user.delete`        | Un événement est généré lorsque vous supprimez un utilisateur du compte. |
{: caption="Tableau 2. Actions qui génèrent des événements" caption-side="top"} 




## Evénements liés à la gestion des organisations
{: #at_events_acc_mgt_org}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                               | Description |
|--------------------------------------|-------------|
| `billing.account.org.create`         | Un événement est généré lorsque vous ajoutez une organisation au compte. |
{: caption="Tableau 3. Actions qui génèrent des événements" caption-side="top"} 


## Evénements de gestion des balises
{: #at_events_acc_mgt_resources}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                               | Description |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | Un événement est généré lorsque vous ajoutez une balise à une ressource. |
| `ghost-tags.tag.detach-tag`          | Un événement est généré lorsque vous supprimez une balise d'une ressource. |
{: caption="Tableau 4. Actions qui génèrent des événements" caption-side="top"} 


## Où rechercher les événements ?
{: #at_events_acc_mgt_ui}

Les événements sont disponibles dans la région **Francfort (eu-de)**.  

Pour afficher ces événements, vous devez [mettre à disposition une instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) du service {{site.data.keyword.at_full_notm}} dans la région **Francfort (eu-de)**. Ensuite, vous devez [ouvrir l'interface utilisateur {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 












