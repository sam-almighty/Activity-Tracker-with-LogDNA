---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #view_events}

Après avoir mis à disposition une instance du service {{site.data.keyword.at_full_notm}} dans {{site.data.keyword.cloud_notm}}, vous pouvez visualiser les événements via l'interface utilisateur web {{site.data.keyword.at_full_notm}}. Vous visualisez les événements dans l'heure locale.
{:shortdesc}


## Afficher les événements
{: #view_events_step1}

Pour visualiser les événements, procédez comme suit : 

1. Vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements.  

    Le tableau suivant répertorie les rôles minimaux qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher, rechercher et filtrer des événements : 

    <table>
      <caption>Tableau 1. Rôles IAM</caption>
      <tr>
        <th>Rôle</th>
        <th>Droits accordés</th>
      </tr>
      <tr>
        <td>Rôle de plateforme : `Afficheur `</td>
        <td>Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord *Observabilité*. </td>
      </tr>
      <tr>
        <td>Rôle de service : `Lecteur`</td>
        <td>Permet à l'utilisateur de lancer l'interface utilisateur Web, puis d'afficher, de rechercher et de filtrer les événements dans l'interface utilisateur Web. </td>
      </tr>
    </table>

    Pour plus d'informations sur la configuration des stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

2. [Accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

3. Cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png).

4. Sélectionnez **Tout** pour afficher tous les événements ou une vue.  

Vous pouvez afficher les événements via la vue que vous avez sélectionnée. 



## Afficher un sous-ensemble des événements en appliquant une requête de recherche
{: #view_events_step2}

Vous pouvez sélectionner les événements affichés par l'intermédiaire d'une vue en appliquant une requête de recherche. Vous pouvez sauvegarder cette vue pour la réutiliser ultérieurement. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2). 

 


## Afficher un sous-ensemble des événements en appliquant une période
{: #view_events_step3}

Vous pouvez sélectionner les événements affichés par l'intermédiaire d'une vue en appliquant une période. 

Vous pouvez appliquer un horodatage en spécifiant une heure absolue, une heure relative ou un intervalle.

Pour accéder à une heure spécifique, procédez comme suit : 
1. [Accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png).
3. Sélectionnez **Tout** ou bien une vue.
4. Entrez une requête temporelle. Choisissez l'une des options suivantes : 

    * Entrez une heure absolue pour accéder à un certain moment dans vos événements, tel que `May 20 7:00pm`.
    
    * Entrez une heure relative, telle que `2 days ago`, `today at 12am` ou `an hour ago`.

    * Entrez un intervalle, tel que le suivant : `yesterday 10am to yesterday 11am`, `last fri 4:30pm to 11/12 1 AM`, `last wed 4:30pm to 23/05 1 AM` ou `May 20 10am to May 22 10am`. Assurez-vous d'inclure `to` pour séparer l'horodatage initial de l'horodatage de fin.

5. Cliquez sur **ENTREE**.

    Le message d'erreur suivant risque de s'afficher : `Your request is taking longer than expected, try refreshing your browser in a bit as we try to catch up. Réessayez.` Vous risquez de recevoir cette erreur s'il n'existe pas d'événements disponibles à afficher pour la période que vous avez spécifiée. Modifiez la requête temporelle, puis réessayez. 



## Afficher un événement en contexte
{: #view_events_step4}

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
{: #view_events_step5}


Effectuez les étapes suivantes pour copier un événement dans le presse-papiers : 

1. Dans l'interface Web, cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png "Icône Configuration").
2. Sélectionnez **Tout** ou une vue personnalisée.
3. Identifiez la ligne que vous souhaitez explorer.
4. Développez la ligne d'événement. 

    Des informations relatives aux identificateurs, aux étiquettes et aux libellés de la ligne s'affichent.

5. Cliquez sur **Copier dans le presse-papiers** pour copier l'événement dans le presse-papiers.

Lorsque vous avez terminé d'explorer l'événement, cliquez sur **Fermer** pour fermer la ligne.




