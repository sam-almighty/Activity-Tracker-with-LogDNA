---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# Exportation d'événements
{: #export}

Vous pouvez exporter des données au format JSONL à partir d'une instance {{site.data.keyword.at_full_notm}} dans un fichier local. Vous pouvez exporter les journaux à l'aide de programmes, via l'API REST LogDNA ou l'interface utilisateur Web.
{:shortdesc}


## Conditions préalables
{: #export_prereqs}

* [En savoir plus sur l'exportation d'événements](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_export).

* **Vous devez disposer d'un forfait de service payant pour le service **{{site.data.keyword.at_full_notm}}. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 

* Vérifiez que votre ID utilisateur dispose des droits nécessaires pour lancer l'interface utilisateur Web et afficher les événements. Le tableau suivant répertorie les rôles minimaux qu'un utilisateur doit posséder pour pouvoir lancer l'interface utilisateur Web {{site.data.keyword.at_full_notm}} et afficher, rechercher et filtrer des événements : 

| Rôle                      | Droits accordés            |
|---------------------------|-------------------------------|  
| Rôle de plateforme : `Afficheur `     | Autorise l'utilisateur à afficher la liste des instances de service dans le tableau de bord Observabilité. |
| Rôle de service : `Lecteur`      | Permet à l'utilisateur de lancer l'interface utilisateur Web et d'afficher les événements dans l'interface utilisateur Web.  |
{: caption="Tableau 1. Rôles IAM" caption-side="top"} 

Pour plus d'informations sur la configuration des stratégies pour un utilisateur, voir [Octroi de droits utilisateur à un utilisateur ou à un ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Etape 1. Accès à l'interface utilisateur Web
{: #export_step1}

[Accédez à l'interface utilisateur Web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Etape 2. Création d'une vue
{: #export_step2}

[Créez une vue](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).


## Etape 3. Exportation de données
{: #export_step3}

Choisissez l'une des options suivantes pour exporter des événements :

### Option 1. Exportation d'événements à partir de l'interface utilisateur Web
{: #export_ui}

Pour exporter des données, procédez comme suit :

1. Cliquez sur l'icône **Vues** ![Icône Configuration](images/views.png).
2. Sélectionnez **Tout** ou bien une vue.
3. Appliquez une période, des filtres et des critères de recherche jusqu'à ce que les entrées que vous souhaitez exporter soient affichées.
4. Cliquez sur **Unsaved View** si vous commencez par la vue **Tout**. Cliquez sur le nom de la vue si vous avez sélectionné une vue à l'étape précédente.
5. Sélectionnez **Export lines**. Une nouvelle fenêtre s'ouvre.
6. Vérifiez la plage horaire. Si vous devez la modifier, cliquez sur la plage horaire prédéfinie dans la zone *Change the Time Range for export*.
7. Sélectionnez **Prefer newer lines** ou **Prefer older lines** pour le cas où l'exportation dépasse la limite de lignes.
8. Consultez votre courrier électronique. Vous recevez de **LogDNA** un courrier électronique qui contient un lien pour télécharger les lignes exportées.


### Option 2. Exportation d'événements par programmation à l'aide de l'API
{: #export_api}

Pour exporter des événements par programmation, procédez comme suit :

1. Générez une clé de service. 

    **Remarque :** vous devez avoir le rôle **responsable** sur l'instance {{site.data.keyword.at_full_notm}} ou le service pour effectuer cette étape.

    1. [Lancez l'interface utilisateur Web {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2).

    2. Cliquez sur l'icône **Configuration** ![Icône Configuration](images/admin.png). Puis sélectionnez **Organisation**. 

    3. Sélectionnez **Clés d'API**.

        Les clés de service créées s'affichent. 

    4. Cliquez sur **Générer une clé de service**. Une nouvelle clé est ajoutée à la liste. Copiez cette clé.

2. Exportez des événements. Exécutez la commande cURL suivante :

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    Où 

    * ENDPOINT représente le point d'entrée vers le service. Chaque région a une adresse URL différente. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints).
    * QUERY_PARAMETERS sont les paramètres qui définissent les critères de filtrage appliqués à la demande d'exportation.
    * SERVICE_KEY est la clé de service créée à l'étape précédente.

Le tableau suivant répertorie les paramètres de requête que vous pouvez définir :

| Paramètre de requête | Type       | Etat     | Description |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | Requis   | Heure de début. Défini en tant qu'horodatage UNIX en secondes ou millisecondes. |
| `to`        | `int32`      | Requis   | Heure de fin. Défini en tant qu'horodatage UNIX en secondes ou millisecondes.    |
| `size`      | `string`     | Facultatif   | Nombre de lignes de journal à inclure dans l'exportation.  | 
| `hosts`     | `string`     | Facultatif   | Liste d'hôtes séparés par des virgules. |
| `apps`      | `string`     | Facultatif   | Liste d'applications séparées par des virgules. |
| `levels`    | `string`     | Facultatif   | Liste de niveaux de journalisation séparés par des virgules. |
| `query`     | `string`     | Facultatif   | Requête de recherche. Pour plus d'informations, voir [Recherche dans les journaux](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6). |
| `prefer`    | `string`     | Facultatif   | Définit les lignes de journal à exporter. Les valeurs admises sont `head`, premières lignes de journal et `tail`, dernières lignes de journal. La valeur par défaut est tail.  |
| `email`     | `string`     | Facultatif   | Indique le courrier électronique avec le lien de téléchargement de l'exportation. Par défaut, les lignes de journal sont diffusées.|
| `emailSubject` | `string`     | Facultatif   | Permet de définir la ligne Objet du courrier électronique. </br>Utilisez `%20` pour représenter un espace. Par exemple, `Exporter%20journaux`. |
{: caption="Paramètres de requête" caption-side="top"} 

Par exemple, pour diffuser des événements dans le terminal, vous pouvez exécuter la commande suivante :

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

Pour envoyer un courrier électronique avec le lien permettant de télécharger les événements spécifiés lors de l'exportation, vous pouvez exécuter la commande suivante :

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


Pour envoyer un courrier électronique dont l'objet est personnalisé, vous pouvez exécuter la commande suivante :

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

