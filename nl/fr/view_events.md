---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# Affichage d'événements
{: #view_events.md}

Après avoir mis à disposition une instance du service {{site.data.keyword.at_full_notm}} dans {{site.data.keyword.cloud_notm}}, vous pouvez visualiser les événements via l'interface utilisateur web {{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Conditions préalables
{: #view_events_prereqs}

Avant de commencer, vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements.  

**Remarque :** vous devez être administrateur du service {{site.data.keyword.at_full_notm}}, administrateur de l'instance {{site.data.keyword.at_full_notm}} ou disposer de droits IAM sur le compte pour gérer des règles.

Le tableau suivant répertorie les règles minimales qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher les événements :

|Rôle | Droits accordés            |
|---------------------------|-------------------------------|  
|  Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur de lancer l'interface utilisateur Web et d'afficher les événements dans l'interface utilisateur Web. |
{: caption="Tableau 1. Règles IAM" caption-side="top"} 

Pour plus d'informations sur la configuration de ces stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Afficher des événements via l'interface utilisateur Web
{: #view_events_step1}

Pour lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}}, procédez comme suit :

1. [Connectez-vous à votre compte {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://cloud.ibm.com/login){:new_window}.

	Une fois connecté avec votre ID utilisateur et votre mot de passe, le *tableau de bord* {{site.data.keyword.cloud_notm}} s'ouvre.

2. Cliquez sur l'icône Menu ![Icône Menu](../../icons/icon_hamburger.svg) et sélectionnez **Observabilité**.  

3. Sélectionnez **Activity Tracker**. 

    La liste des instances {{site.data.keyword.at_full_notm}} s'affiche.

    **Remarque :** il existe 1 instance par région.

4. Sélectionnez l'instance dans la région où vous souhaitez afficher les événements. Ensuite, cliquez sur **Afficher LogDNA**.

L'interface utilisateur Web {{site.data.keyword.at_full_notm}} s'ouvre et affiche la vue **Tout**. Grâce à cette vue, vous pouvez voir les événements de votre compte relatifs à la région que vous avez sélectionnée. 

**Remarque :** si vous disposez d'un forfait `Lite` et que vous ne pouvez pas voir les événements que vous recherchez, vous devrez peut-être passer à un forfait payant pour activer les fonctionnalités de recherche d'événements plus anciens. Le nombre de jours pendant lesquels les événements sont disponibles pour la recherche dépend du forfait que vous avez choisi. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).


## Personnaliser l'affichage par défaut
{: #view_events_step2}

Dans la section **Préférences utilisateur**, vous pouvez modifier l'ordre des zones de données qui s'affichent pour chaque ligne.

Effectuez les étapes suivantes pour modifier le format d'une ligne d'événement : 

1. Dans l'interface Web, cliquez sur l'icône **Configuration** ![Icône Configuration](images/admin.png "Icône Admin"). 
2. Sélectionnez **Préférences utilisateur**. Une nouvelle fenêtre s'ouvre.
3. Sélectionnez **Format de journal**.
4. Modifiez la section *Format de ligne* de manière à répondre à vos exigences. Faites glisser les zones.




## Afficher un événement en contexte
{: #view_events_step3}

A tout moment, vous pouvez visualiser chaque ligne d'événement dans son contexte. 

Effectuez les étapes suivantes : 

1. Dans l'interface Web, cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png "Icône Configuration").
2. Sélectionnez **Tout** ou une vue personnalisée.
3. Identifiez la ligne que vous souhaitez explorer.
4. Développez la ligne d'événement. 

    Des informations relatives aux identificateurs, aux étiquettes et aux libellés de la ligne s'affichent.

5. Cliquez sur **Afficher en contexte** pour voir la ligne d'événement dans le contexte des autres entrées depuis l'hôte, l'appli ou les deux.

Lorsque vous avez terminé d'explorer l'événement, cliquez sur **Fermer** pour fermer la ligne.




## Copier un événement dans le presse-papiers
{: #view_events_step4}


Effectuez les étapes suivantes pour copier un événement dans le presse-papiers :  

1. Dans l'interface Web, cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png "Icône Configuration").
2. Sélectionnez **Tout** ou une vue personnalisée.
3. Identifiez la ligne que vous souhaitez explorer.
4. Développez la ligne d'événement. 

    Des informations relatives aux identificateurs, aux étiquettes et aux libellés de la ligne s'affichent.

5. Cliquez sur **Copier dans le presse-papiers** pour copier l'événement dans le presse-papiers.

Lorsque vous avez terminé d'explorer l'événement, cliquez sur **Fermer** pour fermer la ligne.




