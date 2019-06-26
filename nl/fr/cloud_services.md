---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, services

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


# Services Cloud
{: #cloud_services}

Utilisez le service {{site.data.keyword.at_full}} pour surveiller les activités initiées par l'utilisateur qui modifient l'état de l'un des services suivants dans {{site.data.keyword.cloud_notm}}.
{:shortdesc}


## Services de plateforme de base intégrés
{: #platform_core_integrated}


Les services de la plateforme de base génèrent des événements que vous pouvez visualiser via l'interface utilisateur Web **Francfort (eu-de)** {{site.data.keyword.at_full_notm}}. Pour afficher ces événements, vous devez [mettre à disposition une instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) du service {{site.data.keyword.at_full_notm}} dans la région **Francfort (eu-de)**.
{: note}

Le tableau suivant répertorie les actions de la plateforme de base qui envoient des événements à {{site.data.keyword.at_full_notm}} :

| Action                           | Description | Evénements {{site.data.keyword.at_full_notm}} |
|----------------------------------|-------------|-------------------------------------------|
| [Gestion d'un compte](/docs/account?topic=account-accounts#accounts) | Vous pouvez vous inscrire à un compte {{site.data.keyword.IBM_notm}} en utilisant un IBMid existant, en créant un nouvel IBMid ou en utilisant un ID fédéré. | [Evénements générés lorsque vous gérez un compte](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [Gestion des utilisateurs](/docs/iam?topic=iam-iamuserinv#iamusermanage) | Vous pouvez afficher et gérer des utilisateurs au niveau du compte ou des organisations que vous possédez ou gérez.  | [Evénements générés lorsque vous gérez des utilisateurs ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [Gestion des organisations](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | En tant que propriétaire de compte, vous pouvez ajouter et gérer des organisations sur le compte. | [Evénements générés lorsque vous gérez des organisations ](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [Mise à disposition et gestion des services de catalogue activés par {{site.data.keyword.iamshort}} (IAM)](/docs/overview?topic=overview-ui#catalogcreate) | Vous pouvez mettre à disposition une instance de service, la renommer, modifier son plan et la supprimer. | [Evénements générés lors de vos interactions avec les services de catalogue ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [Utilisation des alias de service](/docs/resources?topic=resources-connect_app#what_is_alias) | Un alias est une connexion entre votre service géré par IAM dans un groupe de ressources et une application dans une organisation ou un espace. | [Evénements de gestion des alias associés à une instance de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [Utilisation de données d'identification de service](/docs/resources?topic=resources-service_credentials#service_credentials) |Les données d'identification du service fournissent les informations nécessaires pour connecter une application à une instance de service. | [Evénements de gestion des données d'identification associés à une instance de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [Liaison entre une instance de service et une application](/docs/resources?topic=resources-s2s_binding#s2s_binding) | Vous pouvez générer une instance CF (Cloud Foundry), ou un alias, d'une instance de service de même nom dans un espace. | [Evénements de liaison d'une instance de service à une application et de suppression d'une telle liaison](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [Gestion des balises](/docs/resources?topic=resources-tag) | Une balise est un libellé affecté à une ressource pour un filtrage simple des ressources de votre liste de ressources. | [Evénements de gestion des balises](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="Liste des actions de plateforme de base" caption-side="top"} 






## Services de sécurité intégrés de plateforme
{: #platform_integrated_security}

Les services de sécurité intégrés génèrent des événements que vous pouvez visualiser via l'interface utilisateur Web **Francfort (eu-de)** {{site.data.keyword.at_full_notm}}. Pour afficher ces événements, vous devez [mettre à disposition une instance](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) du service {{site.data.keyword.at_full_notm}} dans la région **Francfort (eu-de)**.
{: note}

Le tableau suivant répertorie les actions de la plateforme de sécurité de base qui envoient des événements à {{site.data.keyword.at_full_notm}} :

| Actions                                                     | Description | Evénements {{site.data.keyword.at_full_notm}} |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [Gestion des groupes d'accès](/docs/iam?topic=iam-groups#groups) | Vous pouvez définir des groupes d'accès afin d'organiser un ensemble d'utilisateurs et d'ID de service dans une seule entité, et de faciliter l'affectation de droits d'accès. | [Evénements générés lorsque vous gérez des groupes d'accès](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [Gestion des règles](/docs/iam?topic=iam-userroles#userroles) | Vous pouvez utiliser IAM pour gérer des utilisateurs et des rôles dans les services de plateforme et d'infrastructure {{site.data.keyword.cloud_notm}}. | [Evénements générés lorsque vous gérez des règles IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [Connexion à {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)| Vous pouvez vous connecter à {{site.data.keyword.cloud_notm}} en utilisant un mot de passe, une clé d'API, un code d'autorisation ou un code d'accès. En tant qu'utilisateur fédéré, vous pouvez vous connecter à partir de l'interface de ligne de commande en utilisant un code d'accès à usage unique ou une clé d'API. | [Evénements générés lorsqu'un utilisateur ou une application se connecte à {{site.data.keyword.cloud_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) |
| [Gestion des clés d'API de plateforme](/docs/iam?topic=iam-manapikey#platform-api-keys) | Vous pouvez définir des clés d'API de plateforme qui sont associées à un ID utilisateur ou de service dans {{site.data.keyword.IBM_notm}} Cloud. | [Evénements générés lorsque vous gérez des clés d'API de plateforme](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [Gestion des ID de service](/docs/iam?topic=iam-serviceids#serviceids) | Vous pouvez définir des ID de service au niveau du compte dans {{site.data.keyword.IBM_notm}} Cloud. | [Evénements générés lorsque vous gérez des ID de service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="Liste des services de plateforme de sécurité de base" caption-side="top"} 



## Services d'intégration de plateforme
{: #integration}

Le tableau suivant répertorie les services d'intégration qui envoient des événements à {{site.data.keyword.cloudaccesstrailshort}} :

| Service     | Description | Evénements {{site.data.keyword.cloudaccesstrailshort}} |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| {{site.data.keyword.messagehub}} est un bus de messages à haute capacité qui est généré avec Apache Kafka. Il est optimisé pour l'ingestion d'événements dans {{site.data.keyword.IBM_notm}} et la distribution de flux d'événements dans des services et des applications. | [Evénements générés par {{site.data.keyword.messagehub}} ](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="Liste des services Cloud d'intégration qui envoient des événements à {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 



## Services de réseau de plateforme
{: #network}

Le tableau suivant répertorie les services de réseau qui envoient des événements à {{site.data.keyword.at_full_notm}} :

| Service     | Description | Evénements {{site.data.keyword.at_full_notm}} |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| IBM Cloud Internet Services (CIS) fournit un service Internet rapide, très performant, fiable et sécurisé. | [Evénements générés par IBM Cloud Internet Services](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="Liste des services de réseau" caption-side="top"} 



## Services de sécurité de plateforme
{: #security}

Le tableau suivant répertorie les services Cloud de sécurité qui envoient des événements à {{site.data.keyword.cloudaccesstrailshort}} :


| Service     | Description | Evénements {{site.data.keyword.at_full_notm}}          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | Vous pouvez utiliser {{site.data.keyword.cloudcerts_short}} pour gérer les certificats SSL pour vos applications et services {{site.data.keyword.cloud_notm}}.  | [Evénements générés par le service {{site.data.keyword.cloudcerts_short}}](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="Liste des services Cloud de sécurité qui envoient des événements à {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 


