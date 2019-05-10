---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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

Le service {{site.data.keyword.at_full_notm}} enregistre les activités initiées par l'utilisateur qui changent l'état d'un service dans {{site.data.keyword.cloud_notm}}. Pour commencer à surveiller les actions de vos utilisateurs, veuillez vous reporter à [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 

L'initiateur peut être un utilisateur, un service ou une application.
{: tip}

## Evénements de gestion des groupes d'accès
{: #at_events_iam_access}

Le tableau ci-dessous répertorie les actions qui génèrent un événement :

| Action | Description |
|----------|---------|
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




## Affichage d'événements
{: #at_events_iam_ui}

Les événements sont disponibles dans la région **Sud des Etats-Unis**. 

Pour afficher ces événements, vous devez [mettre à disposition une instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) du service {{site.data.keyword.at_full_notm}} dans la région **Sud des Etats-Unis**. Ensuite, vous devez [ouvrir l'interface utilisateur {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


