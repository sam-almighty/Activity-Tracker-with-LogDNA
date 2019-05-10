---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access

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

 
# Gestion des accès utilisateur à l'aide d'IAM
{: #iam}

{{site.data.keyword.iamlong}} (IAM) vous permet d'authentifier de manière sécurisée les utilisateurs et de contrôler de manière cohérente l'accès à toutes les ressources de cloud dans {{site.data.keyword.cloud_notm}}.
{:shortdesc}

**Une règle d'accès avec un rôle utilisateur IAM doit être affectée à chaque utilisateur disposant d'un accès au service {{site.data.keyword.at_full_notm}}.** La règle détermine les actions que l'utilisateur peut exécuter dans le contexte du service ou de l'instance que vous sélectionnez. Les actions autorisées sont personnalisées et définies en tant qu'opérations exécutables sur le service. Les actions sont ensuite mappées à des rôles utilisateur IAM.

Les *règles* permettent d'accorder l'accès à différents niveaux. Certaines des options sont les suivantes :  

* Accès à tous les services activés par IAM dans votre compte
* Accès à toutes les instances du service dans une région unique dans votre compte
* Accès à une instance de service individuelle de votre compte
* Accès à toutes les instances du service dans le cadre d'un groupe de ressources
* Accès à toutes les instances du service dans une région unique dans le cadre d'un groupe de ressources
* Accès à tous les services activés par IAM dans le cadre d'un groupe de ressources

Les *rôles* définissent les actions qu'un utilisateur ou un ID de service peut exécuter. Il existe différents types de rôles dans {{site.data.keyword.cloud_notm}} : 

* Les *rôles de gestion de plateforme* permettent aux utilisateurs d'effectuer des tâches sur des ressources de service au niveau de la plateforme, par exemple d'affecter un accès utilisateur pour le service, de créer ou supprimer des ID de service, de créer des instances, d'affecter des règles pour votre service à d'autres utilisateurs et de lier des instances à des applications.
* Les *rôles d'accès à un service* permettent d'affecter divers niveaux de droits aux utilisateurs pour appeler l'API du service.

**Pour organiser un ensemble d'utilisateurs et d'ID de service en une même entité afin de faciliter la gestion des droits IAM, utilisez des *groupes d'accès*.** Vous pouvez affecter une seule règle au groupe au lieu d'affecter individuellement le même accès plusieurs fois pour chaque utilisateur ou ID de service.
{: tip}

En savoir plus grâce aux tutoriels suivants :
* [Octroi de droits d'administration à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_manage_events#iam_manage_events)
* [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)

## Gestion des accès à l'aide de groupes d'accès
{: #groups}

Pour gérer les accès ou affecter un nouvel accès à des utilisateurs à l'aide de groupes d'accès, vous devez être le propriétaire du compte, l'administrateur ou l'éditeur sur tous les services avec l'offre Identity and Access activée dans le compte, ou être l'administrateur ou l'éditeur affecté pour le service Groupes d'accès IAM.  

Sélectionnez l'une des actions suivantes pour gérer les groupes d'accès dans {{site.data.keyword.cloud_notm}} :

* [Création d'un groupe d'accès](/docs/iam?topic=iam-groups#create_ag).
* [Affectation d'accès à un groupe](/docs/iam?topic=iam-groups#access_ag).


## Gestion des accès par affectation de règles directement aux utilisateurs
{: #users}

Pour gérer les accès ou affecter un nouvel accès à des utilisateurs à l'aide de règles IAM, vous devez être le propriétaire du compte, l'administrateur de tous les services du compte, ou un administrateur du service ou de l'instance de service spécifique. 

Sélectionnez l'une des actions suivantes pour gérer les règles IAM dans {{site.data.keyword.cloud_notm}} :

* Pour modifier les droits d'un utilisateur, voir [Edition d'un accès existant](/docs/iam?topic=iam-iammanidaccser#edit_existing).
* Pour accorder des droits à un utilisateur, voir [Affectation d'un nouvel accès](/docs/iam?topic=iam-iammanidaccser#assign_new_access). 
* Pour révoquer des droits d'accès, voir [Retrait de l'accès](/docs/iam?topic=iam-iammanidaccser#removing_access).
* Pour consulter les droits d'un utilisateur, voir [Révision des accès affectés](/docs/iam?topic=iam-iammanidaccser#review_your_access).



## Rôles de plateforme {{site.data.keyword.cloud_notm}}
{: #platform}

Utilisez le tableau suivant pour identifier le rôle de plateforme que vous pouvez accorder à un utilisateur dans {{site.data.keyword.cloud_notm}} afin d'exécuter l'une des actions de plateforme suivantes : 

| Actions de plateforme                                                        | Rôles de plateforme {{site.data.keyword.cloud_notm}}    | 
|-------------------------------------------------------------------------|------------------------------------------------------|
| `Accorder à d'autres membres du compte un accès leur permettant d'utiliser le service`           |Administrateur                    | 
| `Mettre à disposition une instance de service`                                          |Editeur | 
| `Supprimer une instance de service`                                             |Administrateur                    </br>Editeur | 
| `Créer un ID de service`                                                   |Administrateur                    </br>Editeur |
| `Afficher les détails d'une instance de service`                                    |Administrateur                    </br>Editeur </br>Opérateur</br>Visualiseur  | 
| `Afficher les instances de service dans le tableau de bord Observabilité d'Activity Tracker`   |Administrateur                    </br>Editeur </br>Opérateur</br>Visualiseur  | 
{: caption="Tableau 1. Actions et rôles utilisateur IAM" caption-side="top"}



## Rôles de service {{site.data.keyword.cloud_notm}}
{: #service}

Utilisez le tableau suivant pour identifier le rôle de service que vous pouvez accorder à un utilisateur pour exécuter les actions de service suivantes :

| Actions                                                                 | Rôles de service {{site.data.keyword.cloud_notm}}     | 
|-------------------------------------------------------------------------|------------------------------------------------------|
| `Archiver les événements`                                                        | Responsable                                             |
| `Configurer des alertes`                                                      | Responsable                                             </br>Lecteur                                  | 
| `Filtrer et rechercher des données`                                                | Responsable                                             </br>Lecteur                                  |
| `Créer des vues`                                                          | Responsable                                             </br>Lecteur                                  |
| `Exporter des événements`                                                         | Responsable                                             </br>Lecteur                                  |
| `Configurer des préférences utilisateur dans l'interface utilisateur Web LogDNA`                       | Responsable                                             </br>Lecteur                                  |
| `Afficher des événements via l'interface utilisateur Web LogDNA`                                 | Responsable                                             </br>Lecteur                                  | 
{: caption="Tableau 2. Actions et rôles utilisateur IAM" caption-side="top"}


**Remarque :** le rôle de service **responsable** est automatiquement associé au rôle d'administrateur LogDNA.






