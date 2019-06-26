---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# Création de vues personnalisées
{: #views}

Via l'interface utilisateur Web {{site.data.keyword.at_full_notm}}, vous pouvez appliquer des critères de recherche et de filtrage pour définir les événements affichés via une vue personnalisée.
{:shortdesc}


## Conditions préalables
{: #views_prereqs}

Avant de commencer, vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements. Le tableau suivant répertorie les rôles minimaux qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher, rechercher et filtrer des événements : 

| Rôle                      | Droits accordés            |
|---------------------------|-------------------------------|  
| Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur de lancer l'interface utilisateur Web et d'afficher les événements dans l'interface utilisateur Web.  |
{: caption="Tableau 1. Rôles IAM" caption-side="top"} 

Pour plus d'informations sur la configuration des stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Etape 1. Accès à l'interface utilisateur Web et sélection d'une vue
{: #views_step1}

Effectuez les étapes suivantes :

1. [Accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png).
3. Sélectionnez **Tout** ou bien une vue. 


## Etape 2. Sélection de l'ensemble d'événements à afficher par l'intermédiaire d'une vue en appliquant une requête de recherche
{: #views_step2}

Pour rechercher des événements spécifiques, vous pouvez appliquer une requête de recherche.  

* Vous pouvez effectuer des recherches simples (recherche de chaîne d'un seul terme), des recherches composées (plusieurs opérateurs et termes de recherche), des recherches de zone si la ligne de journal peut être analysée, et d'autres types de recherche. Pour plus d'informations, voir [comment effectuer des recherches dans les journaux dans la documentation LogDNA![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.logdna.com/docs/search){:new_window}.
* Les opérateurs AND et OR sont sensibles à la casse et doivent être indiqués en majuscules.

Vous ne pouvez rechercher des événements que pour le nombre de jours spécifié via le forfait de service de l'instance.
{: important}


Effectuez les étapes suivantes :
1. Entrez une requête de recherche.  
2. Cliquez sur **Entrée**.  

Lorsque vous appliquez une requête, notez que le nom de la vue devient **Unsaved View**.


### Rechercher les événements générés par un service
{: #views_step1_1}

Pour supprimer les événements d'un service spécifique, vous devez entrer la requête suivante : 

```
_supertenant:SERVICENAME
```
{: codeblock}

Où `SERVICENAME` représente le nom du service dans {{site.data.keyword.cloud_notm}}. 

Le tableau suivant répertorie les services de base : 

| Evénements générés par                     | Valeur                         | Exemple de requête              |
|--------------------------------------------|-------------------------------|----------------------------------|
| [Service IAM Access Management](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [Service IAM Identity](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [Service IAM Access Groups](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)   | `iam-groups`  | `_supertenant:iam-groups`     |
| [Service Resource Controller](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="Tableau 2. Requête par nom de service" caption-side="top"}

### Rechercher les ensembles d'événements générés par un service
{: #views_step1_2}

Si un service génère différents types d'événement, vous pouvez entrer la requête suivante : 

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

Où 

* `SERVICENAME` représente le nom du service dans {{site.data.keyword.cloud_notm}}
* `TYPEOFACTION` est une requête composée dans laquelle vous pouvez utiliser des opérateurs AND et OR, ainsi que `-`, pour exclure des données. Notez que les opérateurs `AND` et `OR` sont sensibles à la casse et doivent être indiqués en majuscules. 


Le tableau suivant montre des exemples de recherche d'un groupe d'événements généré par un service : 

| Evénements générés par                     | Types d'événement  | Exemple de requête              |
|--------------------------------------------|--------------------|---------------------------------|
| `Service IAM Identity`   | [Evénements de connexion](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `Service IAM Identity`   | [Evénements de clé d'API](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `Service IAM Identity`   | [Evénements ID service de compte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `Resource Controller`                      | [Mise à disposition et gestion des instances de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `Resource Controller`                      | [Gestion des utilisateurs dans le compte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="Tableau 3. Exemples de requête plus complexe" caption-side="top"}


### Rechercher les événements ayant une action spécifique
{: #views_step1_3}

Chaque événement comporte une zone **action** qui informe de l'action ayant déclenché l'événement. Vous pouvez entrer la requête suivante pour rechercher tous les événements possédant la même action. 

```
action ACTIONVALUE
```
{: codeblock}

Où `ACTIONVALUE` correspond à la valeur de la zone d'action ou à une partie de cette valeur. 

Le tableau suivant illustre des exemples de requêtes pour différentes actions : 

| Action                 | Exemple de requête              |
|------------------------|----------------------------------|
| Mettre à disposition un service  | `action instance.create`         |
| Supprimer une instance           | `action instance.delete`         |
| Ajouter un utilisateur           | `action user-management.user.create` |
{: caption="Tableau 4. Exemples de requête par type d'action" caption-side="top"}



### Rechercher les événements dont l'action échoue
{: #views_step1_4}

Si une action demandée échoue, la zone **résultat** est définie sur **échec**. Vous pouvez entrer la requête suivante pour rechercher ces types d'événement : 

```
outcome failure
```
{: codeblock}


### Rechercher par criticité des événements
{: #views_step1_5}

Chaque événement contient une zone **gravité** qui définit le niveau de menace d'une action sur le cloud.  

Les valeurs valides sont *normal*, *avertissement* et *critique*.  
* **Normal** est défini pour les actions de routine dans le cloud. Par exemple, le démarrage d'une instance ou l'actualisation d'un jeton. 
* **Avertissement** est défini pour les actions où une ressource de cloud est mise à jour ou dont les métadonnées sont modifiées. Par exemple, la mise à jour de la version d'un noeud worker, le changement de nom d'un certificat ou d'une instance de service. 
* **Critique** est défini pour les actions qui affectent la sécurité du cloud. Par exemple, la modification des données d'identification d'un utilisateur, la suppression de données, l'accès non autorisé pour travailler avec une ressource de cloud.

Vous pouvez entrer la requête suivante pour rechercher ces types d'événement : 

```
severity VALUE
```
{: codeblock}

Où `VALUE` peut être défini sur *normal*, *avertissement* ou *critique*

Par exemple, pour rechercher les événements critiques, vous pouvez exécuter la requête suivante : 

```
severity critical
```
{: codeblock}



## Etape 3. Création d'une vue personnalisée
{: #views_step3}

Une fois que vous avez appliqué la requête de recherche à la vue **Tout** ou à une vue personnalisée existante, procédez comme suit pour enregistrer le résultat en tant que vue personnalisée : 

1. Dans l'interface Web, cliquez sur **Vue non sauvegardée**.
2. Sélectionnez l'option de sauvegarde en tant de nouvelle vue ou alerte. La page *Créer une nouvelle vue* s'ouvre.
3. Dans la zone *Nom*, entrez un nom pour la vue.
4. Vous pouvez éventuellement ajouter une catégorie. Entrez un nom, puis cliquez sur l'option permettant de l'ajouter comme nouvelle catégorie de vue.
5. Vous pouvez éventuellement associer une alerte. Une nouvelle section permettant de configurer l'alerte s'affiche.
6. Cliquez sur **Sauvegarder la vue**


## Etape 4. Personnalisation du mode d'affichage des lignes d'événement par l'intermédiaire d'une vue
{: #views_step4}

Pour personnaliser la manière d'afficher les données dans une vue, vous disposez de trois options : 
* Vous pouvez modifier les propriétés d'une vue. Vous pouvez renommer une vue, ajouter ou modifier sa description et appliquer un format de ligne spécifique. 
* Vous pouvez modifier le `format de journal` dans la section *Préférences utilisateur*. 
* Vous pouvez appliquer un modèle de ligne dans la section *Outils*. Notez qu'il remplace toute autre configuration de ligne. Si vous sélectionnez **Conserver ces paramètres**, toutes les vues de l'interface utilisateur affichent les données conformément au format de ligne spécifié dans cette section. 
* Vous pouvez appliquer une couleur aux termes ou aux chaînes en définissant **Mettre en évidence les termes** dans la section **Outils**. 



### Modifier le format de ligne par l'intermédiaire de la page des propriétés de vue
{: #views_step4_1}

Effectuez les étapes suivantes pour modifier le format d'une ligne d'événement dans une même vue :

1. Dans votre vue, sélectionnez **Editer les propriétés de la vue**. La page *Editer les propriétés de la vue* s'ouvre. 

2. Entrez un format de ligne personnalisé dans la section **Modèle %LINE personnalisé**. La valeur par défaut est définie sur `{{line}}`.

    Pour plus d'informations sur les instructions des modèles de ligne, voir [Instructions](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line). 

3. Cliquez sur **Sauvegarder les propriétés**.



### Modifier le format de ligne par l'intermédiaire de la section des préférences utilisateur
{: #views_step4_2}

Dans la section **Préférences utilisateur**, vous pouvez modifier l'ordre des zones de données qui s'affichent pour chaque ligne.

Effectuez les étapes suivantes pour modifier le format d'une ligne d'événement :

1. Dans l'interface Web, cliquez sur l'icône **Configuration** ![Icône Configuration](images/admin.png "Icône Admin").
2. Sélectionnez **Préférences utilisateur**. Une nouvelle fenêtre s'ouvre.
3. Sélectionnez **Format de journal**.
4. Modifiez la section *Format de ligne* de manière à répondre à vos exigences. Faites glisser les zones.


### Modifier le format de ligne par l'intermédiaire du modèle de ligne dans la section des outils
{: #views_step4_3}

Effectuez les étapes suivantes pour modifier le format d'une ligne d'événement :

1. Dans la vue, cliquez sur l'icône **Outils** ![Icône Outils](images/tool.png "Icône Outils"). 
2. Dans la zone **Modèle de ligne**, entrez votre format de ligne personnalisé. Pour plus d'informations sur les instructions des modèles de ligne, voir [Instructions](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line). 
3. Cliquez éventuellement sur **Conserver ces paramètres** pour appliquer le format de ligne à toutes les vues. 



### Mettre en évidence des termes
{: #view_events_step4_4}

Pour mettre en évidence des termes dans une vue, procédez comme suit : 

1. Dans la vue, cliquez sur l'icône **Outils** ![Icône Outils](images/tool.png "Icône Outils"). 
2. Dans la zone **Line Template**, entrez un mot ou une chaîne dans la section **Highlight Terms**. 
3. Cliquez éventuellement sur **Persist these settings** pour appliquer ces paramètres à toutes les vues. 



## Modifier le nom et la description d'une vue personnalisée
{: #views_step5}

Vous pouvez renommer une vue. Vous pouvez ajouter ou modifier la description d'une vue. 


Effectuez les étapes suivantes :

1. Dans votre vue, sélectionnez **Editer les propriétés de la vue**. La page *Editer les propriétés de la vue* s'ouvre. 

    Vous pouvez renommer la vue, ajouter ou modifier la description de la vue et appliquer un format de ligne personnalisé. 

2. Entrez un nouveau nom dans la section **Renommer la vue** pour renommer la vue. 

3. Entrez ou modifiez la description dans la section **Description**. 

4. Cliquez sur **Sauvegarder les propriétés**. 



## Instructions de définition des modèles de ligne
{: #views_line}

Etudiez les instructions suivantes que vous devez appliquer lorsque vous définissez un modèle de ligne : 
* Utilisez des variables entre accolades (`{{field.name}}`) ou de style bash (`${field.name}`) pour construire votre modèle.  
* Utilisez `{{line}}` ou `$@` pour faire référence à la ligne d'origine.  
* Tous les autres caractères ou chaînes sont interprétés comme du texte littéral.  


Par exemple, vous pouvez définir le modèle de ligne `{{initiator.id}} -- {{action}} -- {{message}}` pour afficher ces zones pour chaque événement d'une vue. 


