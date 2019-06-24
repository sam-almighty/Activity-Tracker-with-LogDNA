---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# Evénements IAM
{: #at_events_iam}

En tant que responsable de la sécurité, auditeur ou responsable, vous pouvez utiliser le service {{site.data.keyword.at_full_notm}} pour suivre comment les utilisateurs et les applications interagissent avec le service {{site.data.keyword.iamlong}} (IAM) dans {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

IAM vous permet d'authentifier de manière sécurisée les utilisateurs pour les deux services de plateforme et de contrôler de manière cohérente l'accès aux ressources dans {{site.data.keyword.cloud_notm}}. [En savoir plus](/docs/iam?topic=iam-iamoverview). 


Le service {{site.data.keyword.at_full_notm}} enregistre les activités initiées par l'utilisateur qui changent l'état d'un service dans {{site.data.keyword.cloud_notm}}. Pour commencer à surveiller les actions de vos utilisateurs, veuillez vous reporter à [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). L'initiateur peut être un utilisateur, un service ou une application.


## Evénements des groupes d'accès
{: #at_events_iam_access}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                      | Description |
|-----------------------------|---------|
| `iam-groups.group.create`   | Un événement est généré lorsqu'un initiateur crée un groupe d'accès. | 
| `iam-groups.group.read`     | Un événement est généré lorsqu'un initiateur examine les informations qui sont associées à des groupes d'accès. |
| `iam-groups.group.update`   | Un événement est généré lorsqu'un initiateur met à jour un nom de groupe ou une description. |
| `iam-groups.group.delete`   | Un événement est généré lorsqu'un initiateur supprime un groupe d'accès. |
| `iam-groups.member.add`     | Un événement est généré lorsqu'un initiateur ajoute un membre à un groupe d'accès. |
| `iam-groups.member.delete`  | Un événement est généré lorsqu'un initiateur supprime un membre d'un groupe d'accès. |
| `iam-groups.member.read`    | Un événement est généré lorsqu'un initiateur vérifie l'appartenance d'un membre. |
| `iam-groups.rule.read`      | Un événement est généré lorsqu'un initiateur affiche une règle dans un groupe d'accès. |
| `iam-groups.rule.create`    | Un événement est généré lorsqu'un initiateur ajoute une règle à un groupe d'accès. |
| `iam-groups.rule.update`    | Un événement est généré lorsqu'un initiateur modifie le nom de la règle. |
| `iam-groups.rule.delete`    | Un événement est généré lorsqu'un initiateur supprime une règle d'un groupe d'accès. |
{: caption="Tableau 1. Gestion des actions des groupes d'accès" caption-side="top"} 



## Evénements de règle
{: #at_events_iam_policies}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                 | Description |
|------------------------|---------|
| `iam-am.policy.create` | Un événement est généré lorsqu'un initiateur ajoute une règle à un utilisateur ou un groupe d'accès. |
| `iam-am.policy.delete` | Un événement est généré lorsqu'un initiateur modifie les droits d'accès à une règle d'un utilisateur ou d'un groupe d'accès.|
| `iam-am.policy.update` | Un événement est généré lorsqu'un initiateur supprime une règle qui est affectée à un utilisateur ou un groupe d'accès. |
{: caption="Tableau 5. Gestion des actions de règle" caption-side="top"} 



## Evénements d'ID de service
{: #at_events_iam_serviceids}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action | Description |
|----------|---------|
| `iam-identity.account-serviceid.create` | Un événement est généré lorsqu'un initiateur crée un ID de service.  | 
| `iam-identity.account-serviceid.update` | Un événement est généré lorsqu'un initiateur renomme un ID de service ou modifie sa description. | 
| `iam-identity.account-serviceid.delete` | Un événement est généré lorsqu'un initiateur supprime un ID de service. | 
{: caption="Tableau 2. Utilisation des actions d'ID de service" caption-side="top"} 


## Evénements de clé d'API
{: #at_events_iam_apikeys}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action | Description |
|----------|---------|
| `iam-identity.user-apikey.create`      | Un événement est généré lorsqu'un initiateur crée une clé d'API. | 
| `iam-identity.user-apikey.update`      | Un événement est généré lorsqu'un initiateur renomme une clé d'API ou modifie sa description. |  
| `iam-identity.user-apikey.delete`      | Un événement est généré lorsqu'un initiateur supprime une clé d'API. |  
| `iam-identity.serviceid-apikey.create` | Un événement est généré lorsqu'un initiateur crée une clé d'API pour un ID de service. |  
| `iam-identity.serviceid-apikey.delete` | Un événement est généré lorsqu'un initiateur supprime une clé d'API pour un ID de service. |  
{: caption="Tableau 3. Utilisation des actions des clés d'API" caption-side="top"} 


## Evénements de connexion
{: #at_events_iam_login}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action                                   | Description |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | Un événement est généré lorsqu'un initiateur se connecte à {{site.data.keyword.cloud_notm}} à l'aide d'une clé d'API. |  
| `iam-identity.serviceid-apikey.login`    | Un événement est généré lorsqu'un initiateur se connecte à {{site.data.keyword.cloud_notm}} à l'aide d'une clé d'API qui est associée à un ID de service. |  
| `iam-identity.user-identitycookie.login` | Il s'agit d'un événement qui est généré lorsqu'un initiateur demande un cookie d'identité pour effectuer une action. |
| `iam-identity.user-refreshtoken.login`   | Il s'agit d'un événement qui est généré lorsque l'initiateur se connecte à IBM Cloud, ou lorsqu'un initiateur qui s'est déjà connecté à IBM Cloud demande un nouveau jeton d'actualisation pour exécuter une action. |
{: caption="Tableau 4. Actions de connexion utilisateur" caption-side="top"} 


## Affichage d'événements
{: #at_events_iam_ui}

Les événements sont disponibles dans la région **Francfort (eu-de)**. Pour afficher ces événements, vous devez [mettre à disposition une instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) du service {{site.data.keyword.at_full_notm}} dans la région **Francfort (eu-de)**. Ensuite, vous devez [ouvrir l'interface utilisateur {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


## Analyse des événements
{: #at_events_iam_analyze}


### Supprimer un groupe d'accès
{: #an_del_ag}

Lorsque vous supprimez un groupe d'accès, la zone `action` de l'événement déclenché est définie sur `iam-groups.group.delete`.

Lorsqu'un groupe d'accès est supprimé, prenez note des informations suivantes : 
* D'autres actions sont déclenchées automatiquement pour nettoyer les autres ressources associées au groupe. Certaines actions déclenchées signalent des événements liés à la suppression de membres dans un groupe d'accès, à la suppression de règles et à la suppression de règles dynamiques.  
* L'initiateur de ces actions est un ID service {{site.data.keyword.IBM_notm}}. 


Si aucun membre, stratégie ou règle n'est affecté au groupe d'accès supprimé, les événements générés pour l'une de ces ressource signalent un résultat `failure` avec un code résultat `404`. L'exemple suivant montre les événements générés si un groupe d'accès auquel aucun membre, stratégie ou règle n'a été affecté est supprimé : 

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

