---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# Accès à l'interface utilisateur Web
{: #launch}

Après avoir mis à disposition une instance du service {{site.data.keyword.at_full_notm}} dans {{site.data.keyword.cloud_notm}}, vous pouvez visualiser, surveiller et gérer les événements via l'interface utilisateur web {{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Etape 1. Octroi de règles IAM à un utilisateur pour afficher des données  
{: #step1}

**Remarque :** vous devez être administrateur du service {{site.data.keyword.at_full_notm}}, administrateur d'une instance {{site.data.keyword.at_full_notm}} ou disposer de droits IAM sur le compte pour accorder des règles à d'autres utilisateurs.

Le tableau suivant répertorie la règle minimale qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web et afficher les données via l'interface utilisateur Web {{site.data.keyword.at_full_notm}} : 

|Rôle | Droits accordés       |
|---------------------------|---------------------|
|  Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur d'afficher les événements dans l'interface utilisateur Web. | 
{: caption="Tableau 1. Règles IAM" caption-side="top"} 

Pour plus d'informations, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Etape 2. Lancement de l'interface utilisateur Web via l'interface utilisateur {{site.data.keyword.cloud_notm}} 
{: #launch_step2}

Le démarrage de l'interface utilisateur Web dans le contexte d'une instance {{site.data.keyword.at_full_notm}} s'effectue depuis l'interface utilisateur {{site.data.keyword.cloud_notm}}. 

Pour lancer l'interface utilisateur Web, procédez comme suit :

1. [Connectez-vous à votre compte {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://cloud.ibm.com/login){:new_window}.

	Une fois connecté avec votre ID utilisateur et votre mot de passe, le tableau de bord {{site.data.keyword.cloud_notm}} s'ouvre.

2. Dans le menu de navigation, sélectionnez **Observabilité**.  

3. Sélectionnez **Activity Tracker**. 

    La liste des instances disponibles sur {{site.data.keyword.cloud_notm}} s'affiche. 

4. Sélectionnez une instance. Ensuite, cliquez sur **Afficher LogDNA**.

L'interface utilisateur Web s'ouvre.


## Obtention de l'adresse URL de l'interface utilisateur Web depuis {{site.data.keyword.cloud_notm}}
{: #launch_get}

Pour obtenir l'adresse URL de l'interface utilisateur Web, procédez comme suit à partir d'un terminal :

1. Définissez le groupe de ressources dans lequel l'instance {{site.data.keyword.at_full_notm}} est à disposition.

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. Définissez le nom de l'instance {{site.data.keyword.at_full_notm}}.

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. Définissez le noeud final.

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. Définissez le jeton IAM.

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **Remarque :** Si vous travaillez sur un terminal MacOS, la commande est la suivante : `export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. Définissez l'ID du groupe de ressources.

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. Définissez l'adresse URL de l'interface utilisateur Web dans une variable.

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. Obtenez l'adresse URL de l'interface utilisateur Web.

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

