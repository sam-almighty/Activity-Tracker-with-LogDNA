---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# Mise à disposition d'une instance
{: #provision}

Pour surveiller et gérer les données d'événement avec {{site.data.keyword.at_full_notm}}, vous devez mettre à disposition une instance du service dans {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Pour mettre à disposition une instance {{site.data.keyword.at_full_notm}} dans une région de cloud public, prenez en compte les informations suivantes : 
* Vous devez sélectionner le forfait de service associé à l'instance, la région dans laquelle vos journaux sont collectés et le forfait qui détermine la durée de conservation de vos journaux. Vous avez le choix entre 7, 14 ou 30 jours de conservation. {{site.data.keyword.at_full_notm}} propose un forfait `Lite` qui vous permet d'afficher vos événements lorsqu'ils passent par le système. Vous pouvez afficher les événements à l'aide de la fonction de mise à la queue (tailing) des événements. Vous pouvez également concevoir des filtres afin de préparer une mise à niveau vers un forfait avec une durée de conservation plus longue. Ce forfait a une durée de conservation de 0 jour.
* Votre ID utilisateur doit disposer de droits pour mettre à disposition un service dans un groupe de ressources. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups). 


Vous ne pouvez mettre à disposition qu'une instance du service par région {{site.data.keyword.cloud_notm}}.
{: important}

## Mise à disposition d'une instance via le tableau de bord Observabilité
{: #provision_ui}

Pour mettre à disposition une instance à partir du tableau de bord Observabilité dans {{site.data.keyword.cloud_notm}}, procédez comme suit :

1. [Connectez-vous à votre compte {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://cloud.ibm.com/login){:new_window}.

	Une fois que vous êtes connecté avec votre ID utilisateur et votre mot de passe, l'interface utilisateur {{site.data.keyword.cloud_notm}} s'ouvre.

2. Cliquez sur l'icône Menu ![Icône Menu](../../icons/icon_hamburger.svg). Ensuite, sélectionnez **Observabilité** pour accéder au tableau de bord *Observabilité*.

3. Sélectionnez **Activity Tracker**, puis cliquez sur **Créer une instance**. 

4. Saisissez un nom pour l'instance de service.

5. Sélectionnez l'[emplacement](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions) dans lequel vous prévoyez de mettre à disposition l'instance.  

6. Sélectionnez un groupe de ressources. 

    Le groupe de ressources **par défaut** est défini automatiquement.

    **Remarque :** si vous n'arrivez pas à sélectionner un groupe de ressources, vérifiez que vous disposez du droit d'édition sur le groupe de ressources où vous voulez mettre l'instance à disposition.

7. Sélectionnez le forfait de service `Lite`. 

    Le forfait Lite est sélectionné par défaut.

8. Cliquez sur **Créer**.

Une fois que vous avez mis une instance à disposition, le tableau de bord *Activity Tracker* apparaît. 

Accédez ensuite à l'interface Web pour afficher les événements de votre compte. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events). 



## Mise à disposition d'une instance via le catalogue
{: #provision_catalog}

Pour mettre à disposition une instance {{site.data.keyword.at_full_notm}} via le catalogue {{site.data.keyword.cloud_notm}}, procédez comme suit :

1. [Connectez-vous à votre compte {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://cloud.ibm.com/login){:new_window}.

	Une fois que vous êtes connecté avec votre ID utilisateur et votre mot de passe, l'interface utilisateur {{site.data.keyword.cloud_notm}} s'ouvre.

2. Cliquez sur **Catalogue**. La liste des services disponibles dans {{site.data.keyword.cloud_notm}} s'affiche.

3. Pour filtrer la liste de services qui s'affiche, sélectionnez la catégorie **Developer Tools**.

4. Cliquez sur la vignette **{{site.data.keyword.at_full_notm}}**. 

5. Saisissez un nom pour l'instance de service.

6. Sélectionnez l'emplacement dans lequel vous prévoyez de mettre à disposition l'instance.  

    Pour obtenir la liste la plus récente des emplacements disponibles pour le service {{site.data.keyword.at_full_notm}}, voir [Emplacements](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions). 

7. Sélectionnez un groupe de ressources. 

    Le groupe de ressources **par défaut** est défini automatiquement.

    **Remarque :** si vous n'arrivez pas à sélectionner un groupe de ressources, vérifiez que vous disposez du droit d'édition sur le groupe de ressources où vous voulez mettre l'instance à disposition.

8. Sélectionnez le forfait de service `Lite`. 

    Le forfait Lite est sélectionné par défaut.

9. Cliquez sur **Créer**.

Une fois que vous avez mis une instance à disposition, le tableau de bord *Activity Tracker* apparaît. 

Accédez ensuite à l'interface Web pour gérer les événements de votre compte. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Mise à disposition d'une instance via l'interface de ligne de commande
{: #provision_cli}

Pour mettre à disposition une instance {{site.data.keyword.at_full_notm}} via la ligne de commande, procédez comme suit :

1. [Prérequis] Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}. [En savoir plus](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Si l'interface de ligne de commande est installée, passez à l'étape suivante.

2. Connectez-vous à l'emplacement {{site.data.keyword.cloud_notm}} où vous voulez mettre l'instance à disposition. Exécutez la commande suivante : [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

    Pour obtenir la liste la plus récente des emplacements disponibles pour le service {{site.data.keyword.at_full_notm}}, voir [Emplacements](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions). 

3. Définissez le groupe de ressources dans lequel vous voulez mettre l'instance à disposition. Exécutez la commande suivante : [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    Le groupe de ressources `default` est sélectionné par défaut.

4. Créez l'instance. Exécutez la commande [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create) :

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    Où

    * NAME est le nom de l'instance

    * La valeur *logdnaat* est le nom du service {{site.data.keyword.at_full_notm}} dans {{site.data.keyword.cloud_notm}}

    * SERVICE_PLAN_NAME est le type de forfait. Les valeurs admises sont *Lite*, *7-days*, *14-days* et *30-days*
    
    * LOCATION est la région où l'instance LogDNA est créée. Pour obtenir la liste la plus récente des emplacements disponibles pour le service {{site.data.keyword.at_full_notm}}, voir [Emplacements](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions). 

    
Par exemple, pour mettre une instance à disposition avec un forfait de conservation de 7 jours, exécutez la commande suivante :

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



