---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# Suppression d'une instance
{: #remove}

Vous pouvez retirer une instance du service {{site.data.keyword.at_full_notm}} à partir de l'interface utilisateur {{site.data.keyword.cloud_notm}} ou via la ligne de commande.
{:shortdesc}



## Suppression d'une instance à l'aide de l'interface utilisateur {{site.data.keyword.cloud_notm}}
{: #remove_ui}

Pour supprimer une instance {{site.data.keyword.at_full_notm}} en utilisant l'interface utilisateur {{site.data.keyword.cloud_notm}}, procédez comme suit :

1. [Connectez-vous à votre compte {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://cloud.ibm.com/login){:new_window}.

	Une fois que vous êtes connecté avec votre ID utilisateur et votre mot de passe, l'interface utilisateur {{site.data.keyword.cloud_notm}} s'ouvre. 

2. Cliquez sur l'icône Menu ![Icône Menu](../../icons/icon_hamburger.svg) &gt; **Observabilité** pour accéder au tableau de bord *Observabilité*.

3. Sélectionnez **Activity Tracker**. La liste des instances s'affiche.

4. Sélectionnez l'instance que vous souhaitez supprimer.

5. Dans le menu *Action*, sélectionnez **Retirer**. 

Ensuite, retirez aux utilisateurs les droits accordés de travailler avec l'instance que vous avez supprimée. 

## Suppression d'une instance à l'aide de l'interface de ligne de commande
{: #remove_cli}

Pour supprimer une instance {{site.data.keyword.at_full_notm}} via la ligne de commande, procédez comme suit :

1. [Prérequis] Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.

   Pour plus d'informations, voir [Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)

   Si l'interface de ligne de commande est installée, passez à l'étape suivante.

2. Connectez-vous à la région {{site.data.keyword.cloud_notm}} où vous voulez mettre l'instance à disposition. Exécutez la commande suivante : [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Définissez le groupe de ressources où l'instance est mise à disposition. Exécutez la commande suivante : [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    Le groupe de ressources *default* est sélectionné par défaut.

4. Supprimez l'instance. Exécutez la commande [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) :

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    Où NAME est le nom de l'instance

    Pour répertorier toutes les instances disponibles dans le groupe de ressources auquel vous vous êtes connecté, exécutez la commande suivante : 

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
Par exemple, pour supprimer une instance, exécutez la commande suivante :

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

Ensuite, retirez aux utilisateurs les droits accordés de travailler avec l'instance que vous avez supprimée. 


