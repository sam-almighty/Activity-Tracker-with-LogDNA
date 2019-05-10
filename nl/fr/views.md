---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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
{: #views.md}

Via l'interface utilisateur Web {{site.data.keyword.at_full_notm}}, vous pouvez appliquer des critères de recherche et de filtrage pour définir les événements affichés via une vue personnalisée. {:shortdesc}


## Conditions préalables
{: #views_prereqs}

Avant de commencer, vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements. Puis, [accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

**Remarque :** vous devez être administrateur du service {{site.data.keyword.at_full_notm}}, administrateur de l'instance {{site.data.keyword.at_full_notm}} ou disposer de droits IAM sur le compte pour gérer des règles.

Le tableau suivant répertorie les règles minimales qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher, rechercher et filtrer des événements : 

|Rôle | Droits accordés            |
|---------------------------|-------------------------------|  
|  Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur de lancer l'interface utilisateur Web et d'afficher les événements dans l'interface utilisateur Web. |
{: caption="Tableau 1. Règles IAM" caption-side="top"} 

Pour plus d'informations sur la configuration de ces stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Etape 1. Filtrage d'événements 
{: #views_step1}

Vous pouvez filtrer les événements par source, application et niveau de journalisation.  

* Une source peut être un hôte, un ordinateur, une machine virtuelle ou une application Heroku.
* Une application représente un fichier journal, un programme ou un conteneur.
* Exemples de niveau de journalisation : INFO, DEBUG, ERROR

Pour filtrer des journaux, procédez comme suit :

1. Dans l'interface Web, cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png "Icône Configuration").
2. Sélectionnez **Tout** ou bien une vue.
3. Développez **All Tags** pour afficher la liste des balises disponibles. Puis sélectionnez celles qui vous intéressent.
4. Développez **All Sources** pour afficher la liste des sources disponibles. Puis sélectionnez celles qui vous intéressent.
5. Développez **All Apps** pour afficher la liste des applis disponibles. Puis sélectionnez celles qui vous intéressent.
6. Développez **All Levels** pour afficher la liste des niveaux disponibles. Puis sélectionnez ceux qui vous intéressent.

Lorsque vous appliquez des filtres, notez que le nom de la vue devient **Unsaved View**.

**Remarque :** dans chaque section, vous pouvez regrouper plusieurs options dans un groupe. Groupez les balises, les sources, les applications et les niveaux pour réutiliser ces groupes lorsque vous filtrez les données dans d'autres vues personnalisées. 

Pour créer un groupe, sélectionnez plusieurs valeurs. Puis cliquez sur **Sauvegarder en tant que groupe**. Entrez un nom pour le groupe, puis sauvegardez-le.


## Etape 2. Recherche d'événements 
{: #views_step2}

Lorsque vous recherchez des événements, la recherche applique les filtres et les requêtes temporelles configurés dans cette vue. 

Vous pouvez effectuer des recherches simples (recherche de chaîne d'un seul terme), des recherches composées (plusieurs opérateurs et termes de recherche), des recherches de zone si la ligne de journal peut être analysée, et d'autres types de recherche. Pour plus d'informations, voir [comment effectuer des recherches dans les journaux dans la documentation LogDNA![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.logdna.com/docs/search){:new_window}.

**Remarque :** les opérateurs AND et OR sont sensibles à la casse et doivent être indiqués en majuscules.

Lorsque vous appliquez des critères de recherche, notez que le nom de la vue devient **Unsaved View**.



## Etape 3. Création d'une vue personnalisée 
{: #views_step3}

Après avoir appliqué une période, des filtres et des critères de recherche à la vue **Tout** ou à une vue personnalisée existante, procédez comme suit pour enregistrer le résultat en tant que vue personnalisée :

1. Dans l'interface Web, cliquez sur **Unsaved View**.
2. Sélectionnez **Save as new view / alert**. La page *Créer une nouvelle vue* s'ouvre.
3. Dans la zone *Name*, entrez un nom pour la vue.
4. Vous pouvez éventuellement ajouter une catégorie. Entrez un nom, puis cliquez sur **Add this as new view category**.
5. Vous pouvez éventuellement associer une alerte. Une nouvelle section permettant de configurer l'alerte s'affiche.
6. Cliquez sur **Sauvegarder la vue**




