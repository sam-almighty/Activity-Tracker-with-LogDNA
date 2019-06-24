---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #alerts}

Via l'interface utilisateur Web {{site.data.keyword.at_full_notm}}, vous pouvez appliquer des requêtes de recherche pour définir les événements affichés via une vue personnalisée. Ensuite, vous pouvez associer une alerte à cette vue pour être averti d'une condition. Vous pouvez associer une ou plusieurs alertes à une vue. Vous pouvez définir plusieurs canaux de notification pour une alerte. Vous pouvez désactiver le son d'une alerte. Vous pouvez dissocier des alertes d'une vue.
{:shortdesc}


## Conditions préalables
{: #alerts_prereqs}

* [En savoir plus sur les alertes](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts).

* **Vous devez disposer d'un forfait de service payant pour le service **{{site.data.keyword.at_full_notm}}. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).

* Vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements. Le tableau suivant répertorie les rôles minimaux qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher, rechercher et filtrer des événements : 

| Rôle                      | Droits accordés            |
|---------------------------|-------------------------------|  
| Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur de lancer l'interface utilisateur Web et d'afficher les événements dans l'interface utilisateur Web.  |
{: caption="Tableau 1. Rôles IAM" caption-side="top"} 

Pour plus d'informations sur la configuration des stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

 


## Etape 1. Accès à l'interface utilisateur Web
{: #alerts_step1}

[Accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Etape 2. Création d'une vue
{: #alerts_step2}

[Créez une vue](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).



## Etape 3. [Facultatif] Configuration d'un préréglage (modèle d'alerte)
{: #alerts_step3}

Pour réutiliser une configuration d'alerte avec différentes vues, configurez un **préréglage d'alerte**.
{: note}

Pour configurer un préréglage, procédez comme suit :

1. Dans l'interface Web, sélectionnez l'icône **Configuration** ![Icône Configuration](images/admin.png "Icône Admin").
2. Sélectionnez **Alerts**.
3. Sélectionnez **Add a preset alert**.
4. Sélectionnez un canal de notification. Pour la liste des canaux pris en charge, voir [Canaux de notification d'alerte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels). 
5. Sélectionnez le type d'alerte. Sélectionnez le type **Alerte de présence** pour générer un avertissement si le nombre d'événements affichés dans une vue est supérieur au nombre attendu. Sélectionnez le type **Alerte d'absence** pour générer un avertissement si le nombre d'événements affichés dans une vue est inférieur au nombre attendu ou nul.  
5. Sélectionnez un canal de notification. Pour la liste des canaux pris en charge, voir [Canaux de notification d'alerte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels). 
6. Définissez des conditions de seuil.

    1. Sélectionnez une fréquence. Par exemple, 12 heures.

    2. Entrez le nombre de lignes d'événement après lesquelles vous souhaitez que l'alerte se déclenche.

    3. Indiquez si vous voulez que les deux conditions soient remplies ou une seule uniquement.

7. Ajoutez des détails concernant le canal de notification que vous avez sélectionné.

    Par exemple, pour le canal de notification par courrier électronique, ajoutez un ou plusieurs destinataires et éventuellement un fuseau horaire.

8. Cliquez sur **Save alert**.



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
5. Sélectionnez le type d'alerte. Sélectionnez le type **Alerte de présence** pour générer un avertissement si le nombre d'événements affichés dans une vue est supérieur au nombre attendu. Sélectionnez le type **Alerte d'absence** pour générer un avertissement si le nombre d'événements affichés dans une vue est inférieur au nombre attendu ou nul.  
6. Définissez des conditions de seuil.

    1. Sélectionnez une fréquence. Par exemple, 12 heures.

    2. Entrez le nombre de lignes d'événement après lesquelles vous souhaitez que l'alerte se déclenche.

    3. Indiquez si vous voulez que les deux conditions soient remplies ou une seule uniquement.

7. Ajoutez des détails concernant le canal de notification que vous avez sélectionné.

    Par exemple, pour le canal de notification par courrier électronique, ajoutez un ou plusieurs destinataires et éventuellement un fuseau horaire.

8. Cliquez sur **Save alert**.



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












