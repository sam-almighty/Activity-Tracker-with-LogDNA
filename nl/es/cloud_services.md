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


# Servicios en la nube
{: #cloud_services}

Utilice el servicio {{site.data.keyword.at_full}} para supervisar actividades iniciadas por el usuario que cambien el estado de cualquiera de los servicios siguientes en {{site.data.keyword.cloud_notm}}.
{:shortdesc}


## Servicios básicos integrados de la plataforma
{: #platform_core_integrated}


Los servicios básicos de la plataforma generan sucesos que puede ver a través de la interfaz de usuario web de {{site.data.keyword.at_full_notm}} en **Frankfurt (eu-de)**. Para ver estos sucesos, debe [suministrar una instancia](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servicio {{site.data.keyword.at_full_notm}} en la región **Frankfurt (eu-de)**.
{: note}

La tabla siguiente contiene las acciones básicas de la plataforma que envían sucesos a {{site.data.keyword.at_full_notm}}:

| Acción                           | Descripción | Sucesos de {{site.data.keyword.at_full_notm}} |
|----------------------------------|-------------|-------------------------------------------|
| [Gestión de una cuenta](/docs/account?topic=account-accounts#accounts) | Puede registrarse para una cuenta de {{site.data.keyword.IBM_notm}} utilizando un IBMid existente, creando un nuevo IBMid o utilizando un ID federado. | [Sucesos generados al gestionar una cuenta](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [Gestión de usuarios](/docs/iam?topic=iam-iamuserinv#iamusermanage) | Puede ver y gestionar usuarios de la cuenta o de las organizaciones que posee o gestiona.  | [Sucesos generados al gestionar usuarios ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [Gestión de organizaciones](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | Como propietario de la cuenta, puede añadir y gestionar organizaciones de la cuenta. | [Sucesos generados al gestionar organizaciones ](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [Suministro y gestión de servicios habilitados para {{site.data.keyword.iamshort}} (IAM) del catálogo](/docs/overview?topic=overview-ui#catalogcreate) | Puede suministrar una instancia de servicio, cambiar el nombre de una instancia de servicio, cambiar el plan de una instancia de servicio y eliminar una instancia de servicio. | [Sucesos generados al interactuar con servicios de catálogo ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [Cómo trabajar con alias de servicio](/docs/resources?topic=resources-connect_app#what_is_alias) | Un alias es una conexión entre su servicio gestionado por IAM dentro de un grupo de recursos y una aplicación dentro de una organización o un espacio. | [Sucesos para gestionar los alias que están asociados a una instancia de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [Cómo trabajar con credenciales de servicio](/docs/resources?topic=resources-service_credentials#service_credentials) | Una credencial de servicio proporciona la información necesaria para conectar una aplicación a una instancia de servicio. | [Sucesos para gestionar las credenciales de servicio alias que están asociadas a una instancia de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [Enlazar una instancia de servicio a una app](/docs/resources?topic=resources-s2s_binding#s2s_binding) | Puede generar una instancia de Cloud Foundry (CF), o un alias, de una instancia de servicio con el mismo nombre en un espacio.  | [Sucesos para enlazar y desenlazar una instancia de servicio con una app](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [Gestión de etiquetas](/docs/resources?topic=resources-tag) | El usuario asigna una etiqueta a un recurso para filtrar fácilmente los recursos en la lista de recursos. | [Sucesos para gestionar etiquetas](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="Lista de acciones básicas de la plataforma" caption-side="top"} 






## Servicios de seguridad integrados en la plataforma
{: #platform_integrated_security}

Los servicios de seguridad integrados generan sucesos que puede ver a través de la interfaz de usuario web de {{site.data.keyword.at_full_notm}} en **Frankfurt (eu-de)**. Para ver estos sucesos, debe [suministrar una instancia](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servicio {{site.data.keyword.at_full_notm}} en la región **Frankfurt (eu-de)**.
{: note}

La tabla siguiente contiene las acciones básicas de la plataforma de seguridad que envían sucesos a {{site.data.keyword.at_full_notm}}:

| Acciones                                                     | Descripción | Sucesos de {{site.data.keyword.at_full_notm}} |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [Gestión de grupos de acceso](/docs/iam?topic=iam-groups#groups) | Puede definir grupos de acceso para organizar un conjunto de usuarios y de ID de servicio en una sola entidad, lo que le facilita la asignación de permisos. | [Sucesos generados al gestionar grupos de acceso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [Gestión de políticas](/docs/iam?topic=iam-userroles#userroles) | Puede utilizar IAM para gestionar usuarios y roles en la plataforma {{site.data.keyword.cloud_notm}} y servicios de infraestructura. | [Sucesos generados al gestionar políticas de IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [Inicie una sesión en {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)| Puede iniciar la sesión en {{site.data.keyword.cloud_notm}} utilizando una contraseña, una clave de API, un código de autorización o un código de acceso. Como usuario federado, puede iniciar la sesión desde la interfaz de línea de mandatos (CLI) utilizando un código de acceso de una sola vez o una clave de API. | [Sucesos generados cuando un usuario o app inicia una sesión en {{site.data.keyword.cloud_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) |
| [Gestión de claves de API de la plataforma](/docs/iam?topic=iam-manapikey#platform-api-keys) | Puede definir claves de API de la plataforma en el {{site.data.keyword.IBM_notm}} Cloud que están asociadas con un usuario o un ID de servicio. | [Sucesos generados al gestionar claves de API de la plataforma](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [Gestión de los ID de servicio](/docs/iam?topic=iam-serviceids#serviceids) | Puede definir los ID de servicio a nivel de cuenta en {{site.data.keyword.IBM_notm}} Cloud. | [Sucesos generados al gestionar ID de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="Lista de servicios básicos de seguridad de la plataforma" caption-side="top"} 



## Servicios de integración de la plataforma
{: #integration}

La tabla siguiente contiene los servicios de integración que envían sucesos a {{site.data.keyword.cloudaccesstrailshort}}:

| Servicio     | Descripción | Sucesos de {{site.data.keyword.cloudaccesstrailshort}} |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| {{site.data.keyword.messagehub}} es un bus de mensajes de alto rendimiento creado con Apache Kafka. Está optimizado para la ingesta de sucesos en {{site.data.keyword.IBM_notm}} y la distribución de secuencias de sucesos entre los servicios y las aplicaciones. | [Sucesos generados por {{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="Lista de los servicios de nube de integración que envían sucesos a {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 



## Servicios de red de la plataforma
{: #network}

La tabla siguiente contiene los servicios de red que envían sucesos a {{site.data.keyword.at_full_notm}}:

| Servicio     | Descripción | Sucesos de {{site.data.keyword.at_full_notm}} |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| IBM Cloud Internet Services (CIS) proporciona un servicio de internet rápido, de alto rendimiento, fiable y seguro. | [Sucesos generados por IBM Cloud Internet Services](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="Lista de servicios de red" caption-side="top"} 



## Servicios de seguridad de la plataforma
{: #security}

La tabla siguiente contiene los servicios de nube de seguridad que envían sucesos a {{site.data.keyword.cloudaccesstrailshort}}:


| Servicio     | Descripción | Sucesos de {{site.data.keyword.at_full_notm}}          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | Puede utilizar {{site.data.keyword.cloudcerts_short}} para gestionar los certificados SSL para las apps y servicios basados en {{site.data.keyword.cloud_notm}}.  | [Sucesos generados por el servicio {{site.data.keyword.cloudcerts_short}}](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="Lista de los servicios de nube de seguridad que envían sucesos a {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 


