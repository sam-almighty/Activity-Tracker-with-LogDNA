---

copyright:
  years: 2019
lastupdated: "2019-05-22"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# Octroi de droits d'administration à un utilisateur ou à un ID de service
{: #iam_manage_events}

{{site.data.keyword.iamlong}} (IAM) vous permet d'authentifier de manière sécurisée les utilisateurs et de contrôler de manière cohérente l'accès à toutes les ressources de cloud dans {{site.data.keyword.cloud_notm}}. Effectuez les étapes suivantes pour accorder à un utilisateur ou à un ID de service des droits d’administration sur le service {{site.data.keyword.at_full_notm}} :
{:shortdesc}

Par exemple, en tant qu'administrateur du service, vous pouvez mettre à disposition et supprimer des instances du service, octroyer aux autres utilisateurs des droits d'utilisation du service, archiver les journaux sur une instance {{site.data.keyword.cos_full_notm}} (COS), etc. [En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

## Conditions préalables
{: #iam_manage_events_prereq}

Votre ID utilisateur a besoin de **droits de plateforme d'administrateur** pour gérer le service {{site.data.keyword.at_full_notm}}. Contactez l'administrateur du compte. le propriétaire du compte peut octroyer l'accès au compte à un autre utilisateur afin que ce dernier gère les accès utilisateur et les ressources du compte. [En savoir plus](/docs/iam?topic=iam-userroles).



## Etape 1. Création d'un groupe d'accès
{: #ime_step1}

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez un nom et une description facultative pour votre groupe, puis cliquez sur **Créer**.

Vous pouvez supprimer un groupe en sélectionnant l'option **Retirer le groupe**. Lorsque vous retirez un groupe du compte, vous retirez tous les utilisateurs et ID de service du groupe et tous les accès affectés à ce dernier.
{: note}

Pour créer un groupe d'accès en utilisant l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## Etape 2. Ajout de droits pour gérer des événements
{: #ime_step2}

Après avoir configuré votre groupe, vous pouvez attribuer une règle d'accès commun au groupe. 

Toute règle que vous définissez pour un groupe d'accès s'applique à l'ensemble des entités, utilisateurs et ID de service du groupe. 
{: note}

Vous pouvez attribuer la règle à l'aide de l'interface utilisateur ou via la ligne de commande.

Pour créer une règle de groupe d'accès en utilisant l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Lorsque vous définissez la règle, vous devez sélectionner un rôle de plateforme et un rôle de service : 
* Les rôles de gestion de plateforme couvrent une gamme d'actions, notamment la possibilité de créer et de supprimer des instances, de gérer des alias, des liaisons, des données d'identification et de gérer les accès. Les rôles de plateforme sont les suivants : administrateur, éditeur, opérateur, afficheur. Les rôles de gestion de plateforme s'appliquent également aux services de gestion de compte qui permettent aux utilisateurs d'inviter des utilisateurs, de gérer les ID de service, les règles d'accès, les entrées de catalogue et d'effectuer le suivi de la facturation et de l'utilisation compte tenu du rôle qui leur est affecté dans un compte de gestion de service.
* Les rôles d'accès au service définissent la capacité d'un utilisateur ou d'un service à effectuer des actions sur une instance de service. Les rôles d'accès au service sont les suivants : responsable, auteur et lecteur.

Pour gérer le service {{site.data.keyword.at_full_notm}}, un utilisateur doit disposer des rôles suivants : 
* Rôle de plateforme : **Administrateur**. 
* Rôle de service : **Responsable**.
[En savoir plus](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

Effectuez les étapes suivantes pour affecter une règle à un groupe d'accès via l'interface utilisateur :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès. 
3. Cliquez sur **Règles d'accès**.
4. Cliquez sur **Affecter un accès**.
5. Choisissez d'affecter l'accès par ressources dans un groupe de ressources ou par ressources individuelles disponibles dans le compte. Par exemple, vous pouvez choisir l’une des options suivantes pour attribuer à un utilisateur un rôle d’administrateur afin de gérer {{site.data.keyword.at_full_notm}} : 

### Option 1. Octroi de droits sur le service
{: #admin_account_opt1}

Pour affecter à un utilisateur le rôle d'administrateur sur le service {{site.data.keyword.at_full_notm}} dans le compte, procédez comme suit : 

1. Sélectionnez **Affecter l'accès aux ressources**.
2. Sélectionnez **IBM Cloud Activity Tracker with LogDNA**.
3. Sélectionnez **Toutes les régions en cours**.
4. Sélectionnez **Toutes les instances de service en cours**
5. Sélectionnez le rôle de plateforme **Administrateur**.
6. Sélectionnez le rôle de service **Responsable**.
7. Cliquez sur **Affecter**.

### Option 2. Octroi de droits dans le contexte d'un groupe de ressources. 
{: #admin_account_opt2}

Pour affecter à un utilisateur le rôle d'administrateur sur le service {{site.data.keyword.at_full_notm}} dans le contexte d'un groupe de ressources, procédez comme suit : 

1. Sélectionnez **Affecter l'accès au sein d'un groupe de ressources**.
2. Sélectionnez un groupe de ressources.
3. Si aucun rôle n'a encore été accordé à l'utilisateur pour le groupe de ressources concerné, sélectionnez un rôle pour la zone **Affecter l'accès à un groupe de ressources**. 

    Selon le rôle que vous sélectionnez, l'utilisateur peut afficher le groupe de ressources sur son tableau de bord, modifier le nom du groupe de ressources, ou gérer l'accès des utilisateurs au groupe. 
    
    Vous pouvez sélectionner **Aucun accès** si vous voulez que l'utilisateur puisse uniquement accéder au service {{site.data.keyword.at_full_notm}} dans le groupe de ressources.

4. Sélectionnez **IBM Cloud Activity Tracker with LogDNA**.
5. Sélectionnez le rôle de plateforme **Administrateur**.
6. Sélectionnez le rôle de service **Responsable**.
7. Cliquez sur **Affecter**.

### Option 3. Octroi de droits dans un emplacement
{: #admin_account_opt3}

Vous ne pouvez mettre à disposition qu'une instance du service {{site.data.keyword.at_full_notm}} par emplacement. Par conséquent, lorsque vous octroyez des droits à l'aide de cette option, vous contrôlez l'accès par emplacement.
{: note}

Pour affecter à un utilisateur le rôle d'administrateur sur une instance du service {{site.data.keyword.at_full_notm}}, procédez comme suit : 

1. Sélectionnez **Affecter l'accès aux ressources**.
2. Sélectionnez **IBM Cloud Activity Tracker with LogDNA**.
3. Sélectionnez l'instance.
4. Sélectionnez le rôle de plateforme **Administrateur**.
5. Sélectionnez le rôle de service **Responsable**.
6. Cliquez sur **Affecter**.



## Etape 3. Ajout d'un utilisateur ou d'un ID de service au groupe d'accès
{: #ime_step3}

Continuez à configurer votre groupe en ajoutant des utilisateurs ou des ID de service.

### Ajouter un utilisateur au groupe d'accès
{: #ime_step3_user}

Pour ajouter un utilisateur, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès. 
3. Cliquez sur **Ajouter des utilisateurs** sur l'onglet **Utilisateurs**.
4. Sélectionnez dans la liste les utilisateurs que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.


### Ajouter un ID de service au groupe d'accès
{: #ime_step3_svcid}

Pour ajouter un ID de service, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès. 
3. Cliquez sur l'onglet **ID de service**, puis sur **Ajouter un ID de service**.
4. Sélectionnez dans la liste les ID que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.




