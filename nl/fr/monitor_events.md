---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, monitor events

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


# Surveillance de l'activité dans votre compte
{: #monitor_events}

Vous pouvez surveiller l'activité dans votre compte à l'aide de l'interface utilisateur Web {{site.data.keyword.at_full_notm}}. Vous pouvez également exporter des ensembles d'événements pour les analyser dans un autre contexte.
{:shortdesc}

Il existe une instance du service {{site.data.keyword.at_full_notm}} par emplacement. Par conséquent, pour surveiller l'activité dans votre compte, vous devrez peut-être afficher et analyser les événements par l'intermédiaire de différentes instances {{site.data.keyword.at_full_notm}}.  

Dans {{site.data.keyword.cloud_notm}}, vous pouvez cliquer sur l'icône **Menu** ![Icône Menu](../icons/icon_hamburger.svg) > **Observabilité** > **Activity Tracker** pour afficher le tableau de bord dans lequel toutes les instances mises à disposition dans le compte sont répertoriées.
{: tip}

Pour afficher les événements, vous devez [lancer l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) dans l'emplacement où les événements sont disponibles. Vous pourrez ensuite utiliser des vues pour surveiller ces événements. Vous visualisez les événements dans l'heure locale.


Vous pouvez sélectionner les événements affichés par l'intermédiaire d'une vue en appliquant un horodatage et/ou une requête de recherche. 

* Vous pouvez appliquer une requête de recherche et la sauvegarder comme vue personnalisée.  
* Vous pouvez appliquer un horodatage pour accéder à une heure spécifique dans votre journal des événements.  

Lorsque vous appliquez une requête de recherche, vous pouvez sauvegarder cette vue pour la réutiliser ultérieurement. Toutefois, les horodatages ne sont pas sauvegardés. 

Notez que les instances peuvent avoir des plans de service différents et donc des périodes de conservation de données différentes, qui déterminent le nombre de jours pendant lesquels les données peuvent être recherchées via l'interface utilisateur Web. Vous ne pouvez surveiller les événements que pendant votre période de conservation. Des [plans de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan) différents possèdent des périodes de conservation différentes. 


## Surveillance des événements globaux et des événements basés sur un emplacement
{: #mon_def_event_type}

Les événements peuvent être classés comme globaux ou basés sur un emplacement. Le type d'événement détermine l'endroit où vous devez surveiller les événements. 

Le thème commun pour les événements globaux est un emplacement synchronisé unique dans lequel les administrateurs de compte peuvent surveiller certains types d'activité sur le cloud. Pendant ce temps, les événements basés sur un emplacement restent à l'emplacement où le service cloud souscrit est hébergé.
{: note}

### Evénements globaux
{: #mon_def_global}

Les **événements globaux** signalent l'activité sur votre compte qui est liée aux données et ressources généralement synchronisées entre toutes les régions.
{: note}

Les services avec lesquels les utilisateurs interagissent sont intégrés au coeur de l'expérience {{site.data.keyword.cloud_notm}} globale. 

Le domaine global est défini à **Francfort**. Les événements globaux sont capturés et mis à disposition via l'instance {{site.data.keyword.at_full_notm}} configurée à Francfort.

Par exemple, lorsqu'un administrateur de compte invite des utilisateurs à rejoindre le compte, ils peuvent le faire à partir de tout emplacement du cloud. Ils peuvent inviter un utilisateur situé à Francfort et lui octroyer des droits d'utilisation d'un service mis à disposition à Dallas. Où l'événement doit-il aller ? La réponse est un domaine global qui ignore l'origine ou l'emplacement et où les informations sont synchronisées entre toutes les régions. 
    
Autre exemple : les événements du contrôleur de ressources sont également considérées comme des événements globaux dans IBM Cloud. Ces événements signalent la mise à disposition et la suppression d'instances de service sur le cloud. Une instance de service est créée dans un emplacement spécifique, mais les actions du contrôleur de ressources sont signalées comme des événements globaux pour offrir une vue unique de toutes les instances de service mises à disposition dans le compte. 


### Evénements basés sur l'emplacement
{: #mon_def_location}

Les **événements basés sur l'emplacement** signalent l'activité sur votre compte qui est générée par les services {{site.data.keyword.cloud_notm}} services hébergés dans un emplacement de centre de données {{site.data.keyword.IBM_notm}}, tel que Dallas ou Francfort.
{: note}


Lorsque les clients et les applications interagissent avec les services cloud hébergés dans un emplacement, les événements basés sur un emplacement sont capturés et mis à disposition via l'instance {{site.data.keyword.at_full_notm}} configurée dans cet emplacement. Vous pouvez afficher ces événements en y [lançant l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch). 
    
Les événements basés sur un emplacement conservent la localité des données avec les services exécutés dans cet emplacement cloud. 

Par exemple, si vous mettez à disposition le service {{site.data.keyword.cloudcerts_short}} à l'emplacement Francfort, les événements de cette instance seront envoyés à l'instance {{site.data.keyword.at_full_notm}} mise à disposition à Francfort. Si vous mettez à disposition le service {{site.data.keyword.cloudcerts_short}} à l'emplacement Dallas, les événements de cette instance seront envoyés à l'instance {{site.data.keyword.at_full_notm}} mise à disposition à Dallas. Dans les deux cas, les événements sont conservés en local dans la région et l'emplacement du service cloud souscrit. 




## Surveillance des événements par l'intermédiaire de la vue par défaut
{: #mon_def_view}

La vue par défaut s'intitule **Tout**.  

Dès que vous ouvrez l'interface utilisateur Web dans un emplacement, il s'agit de la vue qui s'affiche. 

Tous les événements de votre instance s'affichent dans cette vue. 

Pour savoir comment afficher les événements par l'intermédiaire de cette vue, voir [Affichage d'événements](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1). 

## Surveillance des événements par l'intermédiaire de vues personnalisées
{: #mon_cus_view}

Vous pouvez surveiller un ensemble d'événements dans votre compte. Pour analyser un sous-ensemble d'événements, vous pouvez créer des vues personnalisées.  

Pour créer une vue personnalisée, vous devez appliquer une requête de recherche qui définit les événements à afficher par l'intermédiaire de la vue. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2). 

Vous pouvez [joindre des alertes](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts) à une vue personnalisée.  

Vous pouvez [exporter des données](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export) à partir d'une vue personnalisée.  

Vous pouvez [renommer une vue, lui ajouter une description ou modifier cette description](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5). 

Vous pouvez [appliquer un modèle de ligne](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4) à une vue pour personnaliser le mode d'affichage des données.  

Vous pouvez organiser les vues en les regroupant en **catégories*. 


## Surveillance des événements en appliquant une période
{: #mon_time_view}

Vous pouvez visualiser les événements au cours d'une période spécifique.

Vous pouvez sélectionner les événements affichés par l'intermédiaire d'une vue en [appliquant une période](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3). 

Vous pouvez appliquer un horodatage en spécifiant une heure absolue, une heure relative ou un intervalle.

* Une heure absolue spécifie un moment précis dans votre journal des événements, tel que `May 20 7:00pm`. 
    
* Une heure relative spécifie une période non précise, telle que `2 days ago`.

* Un intervalle spécifie un intervalle de temps, tel que le suivant : `yesterday 10am to yesterday 11am`.



## Configuration d'alertes
{: #mon_alerts}

Dans certains scénarios, vous pouvez souhaiter être averti si des événements spécifiques sont générés dans votre compte. Par exemple, si le nombre d'actions qui échouent est supérieur à un seuil que vous spécifiez.  

Via l'interface utilisateur Web {{site.data.keyword.at_full_notm}}, vous pouvez appliquer des requêtes de recherche pour définir les événements affichés via une vue personnalisée. Ensuite, vous pouvez associer une alerte à cette vue pour être averti d'une condition. Une icône en forme de cloche s'affiche avec la vue pour indiquer qu'une alerte est associée à cette vue.

* Vous pouvez [joindre une alerte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4) par vue. 
* Vous pouvez configurer des conditions basées sur le nombre de lignes d'événement qui correspondent à la requête de recherche dans la vue et/ou sur une fréquence. 
* Vous pouvez définir plusieurs canaux de notification pour une alerte. Pour plus d'informations sur les canaux pris en charge, voir [Canaux de notification d'alerte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels). 
* Vous pouvez [définir un **préréglage**](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3). Un préréglage est un modèle d'alerte que vous pouvez associer à un nombre illimité de vues. Vous pouvez utiliser des préréglages pour définir des modèles que les utilisateurs peuvent réutiliser lorsqu'ils joignent une alerte à une vue.  
* Vous pouvez désactiver le son d'une alerte. 
* Vous pouvez [dissocier une alerte](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view) d'une vue.  


### Types d'alerte
{: #mon_alerts_types}

Vous pouvez configurer les types d'alerte suivants : 

* **Alerte de présence** : vous pouvez utiliser ce type d'alerte pour générer un avertissement si le nombre d'événements affichés dans une vue est supérieur au nombre attendu.  
* **Alerte d'absence** : vous pouvez utiliser ce type d'alerte pour générer un avertissement si le nombre d'événements affichés dans une vue est inférieur au nombre attendu ou nul.  

Par exemple, l'une de vos vues peut afficher les événements qui signalent la suppression d'instances de service dans votre compte. Vous ne vous attendez pas à ce que des instances de service soient supprimées. Vous pouvez configurer une *alerte de présence** qui déclenche une alerte si un ou plusieurs événements sont affichés dans la vue. 

L'alerte d'absence est activée une fois qu'un événement est affiché dans la vue.
{: note}


### Conditions d'alerte
{: #mon_alerts_conditions}

Vous pouvez configurer l'une des conditions suivantes pour une alerte :

* **Fréquence** : vous définissez cette condition pour spécifier la fréquence à laquelle une alerte doit être déclenchée. Les valeurs admises sont : 30 secondes, 1 minute, 5 minutes, 15 minutes, 30 minutes, 1 heure, 6 heures, 12 heures et 24 heures.
* **Compteur de lignes d'événement** : vous définissez cette condition pour spécifier le nombre de lignes d'événement qui satisfont les critères de filtrage et de recherche de la vue. Lorsque le nombre de lignes d'événement est atteint, une alerte est déclenchée.

Vous pouvez décider si les deux conditions doivent être remplies ou une seule uniquement. Si les deux conditions sont définies, une alerte est déclenchée lorsque l'un des seuils est atteint. 

Si vous définissez le *compteur de lignes d'événement* comme la seule condition qui déclenche une alerte, notez que la fréquence définie lorsque vous configurez la condition détermine le délai de réinitialisation de la condition d'alerte une fois que l'alerte a été déclenchée.
{: note}

Par exemple, vous pouvez configurer une alerte déclenchée après 30 secondes ou lors de la collecte de 100 lignes d'événement correspondant aux critères de filtrage et de recherche de la vue.



## Exportation d'événements
{: #mon_export}

Il se peut que vous deviez accéder à un ensemble d'événements externes à l'interface utilisateur pour étudier un problème de manière plus approfondie.  

Vous pouvez exporter des données au format JSONL à partir d'une instance {{site.data.keyword.at_full_notm}} dans un fichier local. 

Vous pouvez exporter des événements par l'intermédiaire d'une vue de l'interface utilisateur Web, ou de programmes, à l'aide d'une API REST. 

Lorsque vous exportez des événements, tenez compte des informations suivantes :
* Vous exportez un ensemble d'entrées d'événement. 
* Pour définir l'ensemble de données à exporter, vous pouvez appliquer des filtres et des critères de recherche. Vous pouvez également indiquer une plage horaire. 
* Vous pouvez exporter un maximum de 20 000 lignes.

### A l'aide de l'API REST
{: #mon_export_api}

Vous pouvez exporter des événements à l'aide d'un programme, via l'API REST LogDNA. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api). 

Lorsque vous exportez des événements à l'aide d'un programme, prenez note des informations suivantes : 

* Vous pouvez choisir d'envoyer un courrier électronique ou de les diffuser en continu sur votre terminal. 
* Vous devez utiliser une clé permettant de transmettre les données d'identification à utiliser lors d'une exportation via un appel d'API REST.  

    Vous devez avoir disposer du rôle **responsable** sur l'instance ou le service {{site.data.keyword.at_full_notm}} pour afficher et générer des clés de service dans l'interface utilisateur Web. 


### A l'aide d'une vue de l'interface utilisateur Web
{: #mon_export_ui}

Vous pouvez exporter des événements par l'intermédiaire d'une vue de l'interface utilisateur Web.  

Dans l'interface utilisateur Web, vous pouvez sélectionner une vue qui affiche les données à exporter. Pour cette vue, vous devez sélectionner la tâche **Export Lines**. Vous devez spécifier un intervalle et indiquer si l'exportation doit porter sur les lignes les plus récentes ou les plus anciennes. Vous pouvez ensuite demander l'exportation.  

Une fois que vous avez soumis une demande, vous recevez un courrier électronique qui est envoyé à votre adresse électronique, avec un lien vers un fichier compressé contenant les données.  
* Pour obtenir les données, vous devez cliquer sur le lien et télécharger le fichier compressé. 
* Le fichier compressé contenant les données que vous souhaitez exporter est disponible 48 heures au maximum. 

[En savoir plus sur l'exportation d'événements via l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui). 








