---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# Configuration d'alertes
{: #alerts.md}

Via l'interface utilisateur Web {{site.data.keyword.at_full_notm}}, vous pouvez appliquer des critères de recherche et de filtrage pour définir les événements affichés via une vue personnalisée. Ensuite, vous pouvez associer une alerte à une vue pour être averti. Vous pouvez associer une ou plusieurs alertes à une vue. Vous pouvez définir plusieurs canaux de notification pour une alerte. Vous pouvez désactiver le son d'une alerte. Vous pouvez dissocier des alertes d'une vue.
{:shortdesc}


Vous pouvez configurer l'une des conditions suivantes pour une alerte :

* *Time frequency* : fréquence à laquelle déclencher une alerte. Les valeurs admises sont : 30 secondes, 1 minute, 5 minutes, 15 minutes, 30 minutes, 1 heure, 6 heures, 12 heures et 24 heures.
* *event lines counter* : spécifiez le nombre de lignes d'événement correspondant aux critères de filtrage et de recherche de la vue. Lorsque le nombre de lignes d'événement est atteint, une alerte est déclenchée. 

Vous pouvez décider si les deux conditions doivent être remplies ou une seule uniquement. Si les deux conditions sont définies, une alerte est déclenchée lorsque l'un des seuils est atteint. 

Par exemple, vous pouvez configurer une alerte déclenchée après 30 secondes ou lors de la collecte de 100 lignes d'événement correspondant aux critères de filtrage et de recherche de la vue. 

Vous pouvez configurer plusieurs canaux de notification. Les canaux admis sont `email`, `Slack`, `PagerDuty`, `Webhook`, `OpsGenie`, `Datadog`, `AppOptics` et `VictorOps`

Vous pouvez également définir un **préréglage**. Un préréglage est un modèle d'alerte que vous pouvez associer à un nombre illimité de vues. 

Une icône en forme de cloche s'affiche avec la vue pour indiquer qu'une alerte est associée à cette vue.


## Conditions préalables
{: #views_prereqs}

Avant de commencer, vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements.  

**Remarque :** vous devez être administrateur du service {{site.data.keyword.at_full_notm}}, administrateur de l'instance {{site.data.keyword.at_full_notm}} ou disposer de droits IAM sur le compte pour gérer des règles.

Le tableau suivant répertorie les règles minimales qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher, rechercher et filtrer des événements : 

|Rôle | Droits accordés            |
|---------------------------|-------------------------------|  
|  Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur de lancer l'interface utilisateur Web et d'afficher les événements dans l'interface utilisateur Web. |
{: caption="Tableau 1. Règles IAM" caption-side="top"} 

Pour plus d'informations sur la configuration de ces stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

**Vous devez disposer d'un forfait de service payant pour le service **{{site.data.keyword.at_full_notm}}. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 


## Etape 1. Accès à l'interface utilisateur Web 
{: #alerts_step1}

[Accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Etape 2. Création d'une vue 
{: #alerts_step2}

[Créez une vue](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md).



## Etape 3. [Facultatif] Configuration d'un préréglage (modèle d'alerte) 
{: #alerts_step3}

Pour réutiliser une configuration d'alerte avec différentes vues, configurez un **préréglage d'alerte**.
{: note}

Pour configurer un préréglage, procédez comme suit :

1. Dans l'interface Web, sélectionnez l'icône **Configuration** ![Icône Configuration](images/admin.png "Icône Admin"). 
2. Sélectionnez **Alerts**.
3. Sélectionnez **Add a preset alert**.
4. Sélectionnez un canal de notification. 
5. Définissez des conditions de seuil.

    1. Sélectionnez une fréquence. Par exemple, 12 heures.

    2. Entrez le nombre de lignes d'événement après lesquelles vous souhaitez que l'alerte se déclenche. 

    3. Indiquez si vous voulez que les deux conditions soient remplies ou une seule uniquement.

6. Ajoutez des détails concernant le canal de notification que vous avez sélectionné.

    Par exemple, pour le canal de notification par courrier électronique, ajoutez un ou plusieurs destinataires et éventuellement un fuseau horaire.

7. Cliquez sur **Save alert**.



## Etape 4. Configuration d'une alerte 
{: #alerts_step4}

Choisissez l’une des options suivantes pour associer une alerte à une vue : 

### Option 1. Configurer une alerte en utilisant un préréglage 
{: #alerts_step4_preset}

Pour associer un préréglage à une vue, procédez comme suit :

1. Dans l'interface Web, cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png).
2. Cliquez sur le nom de la vue à laquelle vous souhaitez associer une alerte. Puis sélectionnez **Attach an alert**.
3. Sélectionnez un préréglage pour réutiliser une définition d'alerte. 
4. Cliquez sur **Save alert**. 




### Option 2. Configurer une alerte spécifique à une vue 
{: #alerts_step4_view}

Pour associer une alerte à une vue, procédez comme suit :

1. Dans l'interface Web, cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png).
2. Cliquez sur le nom de la vue. Puis sélectionnez **Attach an alert**.
3. Sélectionnez **view-specific alert**.
4. Sélectionnez un canal de notification. 
5. Définissez des conditions de seuil.

    1. Sélectionnez une fréquence. Par exemple, 12 heures.

    2. Entrez le nombre de lignes d'événement après lesquelles vous souhaitez que l'alerte se déclenche. 

    3. Indiquez si vous voulez que les deux conditions soient remplies ou une seule uniquement.

6. Ajoutez des détails concernant le canal de notification que vous avez sélectionné.

    Par exemple, pour le canal de notification par courrier électronique, ajoutez un ou plusieurs destinataires et éventuellement un fuseau horaire.

7. Cliquez sur **Save alert**.



## Suppression d'un préréglage (modèle d'alerte)
{: #alerts_delete_preset}

Pour supprimer un préréglage, procédez comme suit :

1. Dans l'interface Web, sélectionnez l'icône **Configuration** ![Icône Configuration](images/admin.png "Icône Admin"). 
2. Sélectionnez **Alerts**.
3. Survolez avec la souris le bouton *Editer* du préréglage que vous voulez supprimer. L'option *Supprimer* s'affiche.
4. Sélectionner **Supprimer**.
5. Confirmez la suppression du préréglage. Cliquez sur **Supprimer**.

## Dissociation d'une vue d'une alerte spécifique à une vue
{: #alerts_delete_view}

Pour dissocier un préréglage, procédez comme suit :

1. Dans l'interface Web, sélectionnez l'icône **Configuration** ![Icône Configuration](images/admin.png "Icône Admin"). 
2. Sélectionnez **Alerts**.
3. Survolez avec la souris le bouton *Editer* de l'alerte que vous voulez supprimer. L'option *Supprimer* s'affiche.
4. Sélectionner **Detach**.
5. Confirmez la suppression de l'alerte. Cliquez sur **Detach**.












